---
title: "Actualización de datos en un entorno aislado"
description: "Este tema explica cómo realizar una actualización de datos de Dynamics AX 2012 a Dynamics 365 for Finance and Operations en un entorno aislado."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 7140bf740f37a5eb970a5103750a7095d12a33cc
ms.contentlocale: es-es
ms.lasthandoff: 06/15/2017

---

# Actualización de datos en un entorno aislado
<a id="data-upgrade-in-a-sandbox-environment" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

El resultado de esta tarea es una base de datos actualizada que puede usar en un entorno aislado. Un entorno aislado es un entorno donde los usuarios empresariales y los miembros del equipo funcional pueden validar la funcionalidad de la aplicación. Esta funcionalidad incluye personalizaciones y los datos que se han trasladado desde Microsoft Dynamics AX 2012.

Se recomienda que ejecute el proceso de actualización de datos en un entorno de desarrollo antes de ejecutarlo en un entorno aislado compartido, pues este método ayudará a reducir el tiempo total requerido para una actualización de datos correcta. Si desea más información, consulte [Actualización de datos en un entorno de desarrollo](prepare-data-upgrade.md).

## Visión general del proceso de actualización de datos en un entorno aislado
<a id="overview-of-the-sandbox-data-upgrade-process" class="xliff"></a>

Antes de empezar actualizar datos en un entorno aislado, ya habrá actualizado datos en un entorno de desarrollo, como se explica en [Actualización de datos en un entorno de desarrollo](prepare-data-upgrade.md). Los dos procesos son muy similares. La principal diferencia es que un entorno aislado usa la base de datos de Microsoft SQL Azure para el almacenamiento de datos, mientras que un entorno de desarrollo usa Microsoft SQL Server. Esta diferencia técnica en el nivel de la base de datos requiere que modifique el procedimiento de actualización de datos ligeramente en un entorno aislado, porque una copia de seguridad de la instancia de la base de datos de AX 2012 no se puede restablecer a la base de datos SQL.

![Proceso de actualización de datos en un entorno aislado](./media/data-upgrade-sandbox.png)

He aquí el proceso de actualización a grandes rasgos.

1. Cree una copia de la base de datos de AX 2012. Se recomienda que utilice una copia, ya que debe eliminar algunos objetos de la copia que se va a exportar.
2. Exporte la base de datos copiada a un archivo bacpac mediante una herramienta gratuita de SQL Server llamada SQLPackage.exe. Esta herramienta proporciona un tipo especial de copia de seguridad de la base de datos que se pueda importar en la base de datos SQL.
3. Cargue el archivo bacpac al almacenamiento de Azure.
4. Descargue el archivo bacpac al equipo de Application Object Server (AOS) en el entorno aislado y, a continuación, impórtelo con SQLPackage.exe. A continuación ejecute un script en la base de datos importada para restablecer a los usuarios de la base de datos SQL.
5. Ejecute el paquete MajorVersionDataUpgrade.zip para llevar a cabo la actualización de datos en la base de datos importada.

## Creación de una copia de la base de datos de AX 2012
<a id="create-a-copy-of-the-ax-2012-database" class="xliff"></a>

Debe crear una copia de la base de datos de AX 2012 que va a actualizar, ya que debe eliminar algunos objetos de la base de datos. Estos objetos incluyen todos los usuarios de autenticación de Microsoft Windows. Estos cambios dejan la base de datos modificada inutilizable en AX 2012. Durante este paso, creará una copia de la base de datos y eliminará estos objetos.

Este paso debe hacerlo el administrador de la base de datos (DBA) o una persona con conocimientos y experiencia similares.

Para crear una copia de la base de datos, haga una copia de seguridad de la base de datos original y restablézcala con un nombre nuevo. Asegúrese de que haya suficiente espacio disponible para ambas bases de datos. Puede crear la copia en otro servidor. La versión de la instancia de SQL Server que ejecute la base de datos no es importante.

He aquí un ejemplo del código que crea una copia de la base de datos. Debe modificar este ejemplo para reflejar los nombres específicos de la base de datos.

    BACKUP DATABASE [AxDB] TO  DISK = N'D:\Backups\axdb_copyForUpgrade.bak' WITH NOFORMAT, NOINIT,  
    NAME = N'AxDB_copyForUpgrade-Full Database Backup', SKIP, NOREWIND, NOUNLOAD, COMPRESSION,  STATS = 10
    GO

    RESTORE DATABASE [AxDB_copyForUpgrade] FROM  DISK = N'D:\Backups\axdb_copyForUpgrade.bak'   WITH  FILE = 1,  
    MOVE N'AXDBBuild_Data' TO N'F:\MSSQL_DATA\AxDB_copyForUpgrade.mdf',  
    MOVE N'AXDBBuild_Log' TO N'G:\MSSQL_LOGS\AxDB_CopyForUpgrade.ldf',  
    NOUNLOAD,  STATS = 5

Una vez creada la copia, ejecute el siguiente script de Transact-SQL (T-SQL) contra ella.
TAREAS 

### Exportación de la base de datos copiada a un archivo bacpac
<a id="export-the-copied-database-to-a-bacpac-file" class="xliff"></a>

Exporte la base de datos copiada a un archivo bacpac mediante la herramienta SQLPackage.exe. Este paso debe hacerlo el DBA o un miembro del equipo que tenga un conocimiento equivalente.

Es muy importante que instale la última versión de SQL Server Management Studio antes de comenzar este paso. Aunque SQLPackage esté presente en versiones anteriores de Management Studio, no funcionará correctamente en este paso a menos que primero instale la última versión.

Este paso es importante, porque la exportación tendrá que repetirse durante el tiempo de inactividad antes del lanzamiento. He aquí algunos consejos:

- El proceso de bacpac es muy exigente con la E/S y la CPU. Por lo tanto, ejecute la exportación en un equipo de mucha potencia.
- SQLPackage se debe ejecutar localmente en el equipo que aloja la base de datos. No ejecute SQLPackage en un portátil local que conecte al equipo de la base de datos, pues este proceso también es muy exigente con la red.

A continuación, abra una ventana del **símbolo del sistema** como administrador y ejecute los comandos siguientes.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:export /ssn:localhost /sdn:<database to export> /tf:D:\Exportedbacpac\my.bacpac /p:CommandTimeout=1200 /p:VerifyFullTextDocumentTypesSupported=false

A continuación se ofrece una explicación de los parámetros:

- **ssn** (nombre del servidor de origen): el nombre del SQL Server desde el que se exporta. Para nuestro proceso, este parámetro se debe establecer siempre en **localhost**.
- **sdn** (nombre de la base de datos de origen): nombre de la base de datos que se va a exportar.
- **tf** (archivo de destino): la ruta y el nombre del archivo al que se va a exportar. La carpeta debe existir, pero se creará el archivo por el proceso.
- **/p: CommandTimeout**: el valor de tiempo de espera por consulta. Este parámetro habilita la exportación de tablas grandes sin topar con un error por tiempo de espera.

### Cargar el archivo bacpac al almacenamiento de Azure.
<a id="upload-the-bacpac-file-to-azure-storage" class="xliff"></a>

Cargue el archivo bacpac al almacenamiento de Azure. Consulte TAREAS de UsingStorageExplorer.docx

### Importación del archivo bacpac a la base de datos SQL
<a id="import-the-bacpac-file-into-sql-database" class="xliff"></a>

Durante este paso, se importarán el archivo bacpac exportado a la instancia de la base de datos SQL que el entorno aislado utiliza. Primero debe instalar la última versión de Management Studio en el equipo de AOS aislado. A continuación importar el archivo mediante la herramienta SQLPackage.exe.

Realizará estas tareas directamente en el equipo de AOS en el entorno aislado, porque hay las reglas de firewall que restringen el acceso a la instancia de la base de datos SQL. Sin embargo, mediante el equipo de AOS, puede obtener acceso.

Con respecto al paso de la exportación, debe tener la última versión de Management Studio antes del inicio de la importación. Este paso no funcionará si tiene una versión anterior.

Por motivos de rendimiento, se recomienda colocar el archivo de bacpac en la unidad D del equipo de AOS. En las máquinas virtuales de Azure (VM), la unidad D es un disco físico que suele tener un mayor rendimiento que otros discos disponibles.

Abra una ventana del **símbolo del sistema** como administrador y ejecute los comandos siguientes.

    cd C:\Program Files (x86)\Microsoft SQL Server\130\DAC\bin\

    SqlPackage.exe /a:import /sf:D:\Exportedbacpac\my.bacpac /tsn:<azure sql database server name>.database.windows.net /tu:sqladmin /tp:<password from LCS> /tdn:<New database name> /p:CommandTimeout=1200 /p:DatabaseEdition=Premium /p:DatabaseServiceObjective=P1

A continuación se ofrece una explicación de los parámetros:

- **tsn** (nombre de servidor de destino): el nombre del servidor de SQL Azure al que se va a importar. El nombre puede encontrarse en LCS. Añádale el sufijo **.database.windows.net**.
- **tdn** (nombre de la base de datos de destino): nombre de la base de datos desde la que se va a importar. La base de datos no debe existir. El proceso de importación la creará.
- **sf** (archivo de origen): la ruta y el nombre del archivo desde el que se va a importar.
- **tp** (contraseña de destino): la contraseña de SQL de la instancia de la base de datos SQL de destino.
- **tu** (usuario de destino): el nombre de usuario de SQL de la instancia de la base de datos SQL de destino. Recomendamos que use **sqladmin**. Puede recuperar la contraseña de este usuario de su proyecto de LCS.
- **/p: CommandTimeout**: el valor de tiempo de espera por consulta. Este parámetro habilita la exportación de tablas grandes sin topar con un error por tiempo de espera.
- **/p:DatabaseServiceObjective**: el nivel de servicio de la base de datos que se crea. Puede comprobar el valor de la base de datos existente mediante Management Studio. Haga clic con el botón derecho en la base de datos y seleccione **Propiedades**.

Tras ejecutar los comandos, recibirá la advertencia siguiente. Puede omitirla sin miedo.

![Error de espacio aislado](./media/sandbox-2.png)
 
### Ejecute el paquete MajorVersionDataUpgrade.zip
<a id="run-the-majorversiondataupgradezip-package" class="xliff"></a>

Ejecute el paquete desplegable de actualización de datos como se describe en [Actualizar datos en entornos de desarrollo, demostración o aislados](upgrade-data-to-latest-update.md).

### Actualización de una copia de la base de datos en un entorno de desarrollo
<a id="upgrade-a-copy-of-the-database-in-a-development-environment" class="xliff"></a>

Resulta útil actualizar la misma base de datos en un entorno de desarrollo. Si tiene una copia de la base de datos disponible para los entornos de desarrollo, será mucho más fácil investigar los errores que se encuentren en el entorno aislado actualizado.

