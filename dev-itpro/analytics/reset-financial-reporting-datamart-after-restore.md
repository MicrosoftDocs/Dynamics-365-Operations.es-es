---
title: "Restablecer el data mart de informes financieros después de restablecer una base de datos"
description: "Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d227452e48914170404f0ee5163a05e6b875e69f
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Restablecer el data mart de informes financieros después de restablecer una base de datos

[!include[banner](../includes/banner.md)]


Este tema describe cómo restablecer el data mart de informes financieros después de restaurar una base de datos de Microsoft Dynamics 365 for Operations. 

Existen varias situaciones donde puede necesitar restablecer la base de datos de Dynamics 365 for Operations desde una copia de seguridad o copiar la base de datos desde otro entorno. Si esto ocurre, también necesitará seguir los pasos adecuados para garantizar que el data mart de informes financieros use correctamente la base de datos de Dynamics 365 for Operations restaurada. Si tiene preguntas sobre cómo restablecer el data mart de informes financieros por motivos que no sean restablecer una base de datos de Dynamics 365 for Operations, consulte [cómo restablecer el data mart de Management Reporter](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) para obtener más información. Tenga en cuenta que los pasos de este proceso se admiten para la versión de mayo de 2016 de Dynamics 365 (compilación de la aplicación 7.0.1265.23014 y compilación de informe financiero 7.0.10000.4) y versiones posteriores. Si tiene una versión anterior de Dynamics 365 for Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.

## <a name="export-report-definitions"></a>Exportar las definiciones de informe
En primer lugar, exporte los diseños de informe que se encuentran en el Diseñador de informes, mediante los pasos siguientes:

1.  En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.
2.  Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**. **Nota:** Para Dynamics 365 for Operations, se admite solo un grupo de bloque de creación, **Valor predeterminado**.
3.  Seleccione las definiciones del informe que quiere exportar:
    -   Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla CTRL para seleccionar varios elementos en una pestaña. Cuando selecciona informes para exportar, se seleccionan las filas, columnas, organigramas y conjuntos de dimensión asociados.

4.  Haga clic en **Exportar**.
5.  Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.
6.  Haga clic en **Guardar**.

El archivo se puede copiar o cargar en una ubicación segura, lo que permite importarlo a otro entorno en otra hora. La información sobre el uso de una cuenta de almacenamiento de Microsoft Azure puede ser encontrada en la sección sobre [datos de la transferencia con el programa de línea de comandos de AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). 
> [!NOTE]
> Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Dynamics 365 for Operations. Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente. 
> [!WARNING]
> Tenga en cuenta el comportamiento de la unidad D en Azure Virtual Machines. No retenga sus grupos exportados del bloque de creación aquí permanentemente. Para obtener más información acerca de unidades temporales, vea la sección sobre [entendiendo la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Detener servicios
Use Escritorio remoto para conectarse con todos los equipos del entorno y detener los servicios siguientes de Windows mediante services.msc:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Servicio de administración por lotes de Microsoft Dynamics 365 for Operations (solo en equipos AOS que no son privados)
-   Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)

Estos servicios tendrán conexiones abiertas con la base de datos de Dynamics 365 for Operations.

## <a name="reset"></a>Restablecer
#### <a name="locate-the-latest-dataupgradezip-package"></a>Localice el último paquete de DataUpgrade.zip

Localice el último paquete de DataUpgrade.zip mediante las instrucciones que se encuentran en la sección de [descarga de la secuencia de comandos de DataUpgrade.zip](..\migration-upgrade\upgrade-data-to-latest-update.md). Las instrucciones explican cómo encontrar la versión correcta del paquete de actualización de datos para su entorno.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Ejecute las secuencias de comandos en la base de datos de Dynamics 365 for Operations

Ejecute las secuencias de comandos siguientes en la base de datos de Dynamics 365 for Operations (no en la base de datos del informe financiero).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Estas secuencias de comandos garantizan que la configuración de usuarios, roles y seguimiento de cambios sea correcta.

#### <a name="execute-powershell-command-to-reset-database"></a>Ejecute el comando PowerShell para restablecer la base de datos

Ejecute el siguiente comando, directamente en el equipo AOS, para restablecer la integración entre Dynamics 365 for Operations y el informe financiero:

1.  Abra Windows PowerShell como administrador.
2.  Ejecute F:
3.  Ejecute: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Ejecute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1
5.  Ejecute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;mi motivo para restablecer&gt;”
    -   Se le solicitará que introduzca “Y” para confirmar.

Explicación de parámetros:

-   Los valores válidos para el motivo son: SERVICING, BADDATA, OTHER.
-   El parámetro ReasonDetail es de texto libre.
-   El motivo y reasonDetail se registrarán en telemetría/seguimiento del entorno.

## <a name="start-services"></a>Iniciar los servicios
Use services.msc para reiniciar los servicios que ha detenido anteriormente:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Servicio de administración por lotes de Microsoft Dynamics 365 for Operations (solo en equipos AOS que no son privados)
-   Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)

## <a name="import-report-definitions"></a>Importar las definiciones de informe
Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación:

1.  En el Diseñador de informes, vaya a **Empresa** &gt; **Grupos de bloque de creación**.
2.  Seleccione el grupo de bloque de creación para exportar y haga clic en **Exportar**. 
    > [!NOTE]
    > Para Dynamics 365 for Operations, se admite solo un grupo de bloqueos de creación, **Valor predeterminado**.
3.  Seleccione el bloque de creación **Predeterminado** y haga clic en **Importar**.
4.  Seleccione el archivo que contiene las definiciones de informe exportadas y haga clic **Abrir**.
5.  En el cuadro de diálogo Importar, seleccione las definiciones del informe que desea importar:
    -   Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.

6.  Haga clic en **Importar**.




