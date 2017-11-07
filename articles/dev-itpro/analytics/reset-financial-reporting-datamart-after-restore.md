---
title: "Restablecer el data mart de informes financieros después de restablecer una base de datos"
description: "Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Restablecer el data mart de informes financieros después de restablecer una base de datos

[!include[banner](../includes/banner.md)]


Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Finance and Operations.

Si se restablece la base de datos de Finance and Operations desde una copia de seguridad o copia de la base de datos de otro entorno, debe seguir los pasos de este tema para garantizar que el informe financiero data mart usa correctamente la base de datos restaurada de Finance and Operations. 
> [!Note] 
> Los pasos de este proceso se admiten para la versión de mayo de 2016 de Dynamics 365 for Operation (compilación de la aplicación 7.0.1265.23014 y compilación de informe financiero 7.0.10000.4) y versiones posteriores. Si tiene una versión anterior de Finance and Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.

## <a name="export-report-definitions"></a>Exportar las definiciones de informe
En primer lugar, exporte los diseños de informe que se encuentran en el Diseñador de informes, mediante los pasos siguientes:

1.  En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.
2.  Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**. 

    > [!Note] 
    > Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.
    
3.  Seleccione las definiciones del informe que quiere exportar:
    -   Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla Ctrl para seleccionar varios artículos en una pestaña. Al seleccionar los informes para exportar, las filas, columnas, árboles y conjuntos de dimensiones asociados se seleccionan también.

4.  Haga clic en **Exportar**.
5.  Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.
6.  Haga clic en **Guardar**.

El archivo se puede copiar o cargar en una ubicación segura, lo que permite importarlo a otro entorno en otra hora. La información sobre el uso de una cuenta de almacenamiento de Microsoft Azure puede ser encontrada en la sección sobre [datos de la transferencia con el programa de línea de comandos de AzCopy](/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Finance and Operations. Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente. 
> [!WARNING]
> Tenga en cuenta el comportamiento de la unidad D en Azure Virtual Machines. No retenga sus grupos exportados del bloque de creación aquí permanentemente. Para obtener más información acerca de unidades temporales, vea la sección sobre [entendiendo la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Detener servicios
Use Escritorio remoto para conectarse con todos los equipos del entorno y detener los servicios siguientes de Windows mediante services.msc:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)
-   Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)

Estos servicios tendrán conexiones abiertas con la base de datos de Finance and Operations.

## <a name="reset"></a>Restablecer
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Localice y descargue el último paquete de MinorVersionDataUpgrade.zip

Localice el último paquete de MinorVersionDataUpgrade.zip mediante las instrucciones que se encuentran en la sección de [Descarga del paquete desplegable de la última actualización de datos](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Las instrucciones explican cómo encontrar y descargar la versión correcta del paquete de actualización de datos. No se requiere una actualización para descargar el paquete de MinorVersionDataUpgrade.zip. Sólo necesita completar los pasos de la sección “Descarga del paquete desplegable de la última actualización de datos” sin realizar ningún otro paso del artículo para recuperar una copia del paquete de MinorVersionDataUpgrade.zip.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Ejecute las secuencias de comandos en la base de datos de Finance and Operations

Ejecute las secuencias de comandos siguientes en la base de datos de Finance and Operations (no en la base de datos del informe financiero).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Estas secuencias de comandos garantizan que la configuración de usuarios, roles y seguimiento de cambios sea correcta.

### <a name="execute-powershell-command-to-reset-database"></a>Ejecute el comando PowerShell para restablecer la base de datos

En el equipo de Microsoft Dynamics AX Application Object Server (AOS), ejecute los siguientes comandos en PowerShell como administrador para restablecer la integración entre Finance and Operations y el informe financiero:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> Una vez ejecutados los comandos, se le solicitará que introduzca “Y” para confirmar.

Explicación de parámetros:

-   Los valores válidos para el motivo son: SERVICING, BADDATA, OTHER.
-   El parámetro ReasonDetail es de texto libre.
-   El motivo y reasonDetail se registrarán en telemetría/seguimiento del entorno.

## <a name="start-services"></a>Iniciar los servicios
Use services.msc para reiniciar los servicios que ha detenido anteriormente:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)
-   Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)

## <a name="import-report-definitions"></a>Importar las definiciones de informe
Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación:

1.  En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.
2.  Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**. 

    > [!NOTE]
    > Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.
    
3.  Seleccione el bloque de creación **Predeterminado** y haga clic en **Importar**.
4.  Seleccione el archivo que contiene las definiciones de informe exportadas y haga clic **Abrir**.
5.  En el cuadro de diálogo Importar, seleccione las definiciones del informe que desea importar:
    -   Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.

6.  Haga clic en **Importar**.





