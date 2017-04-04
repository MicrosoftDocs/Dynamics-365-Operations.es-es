---
title: "Restablecer el informe financiero data mart restablecer después de una base de datos"
description: "Este tema describe cómo restablecer el informe financiero data mart después de restaurar un Microsoft Dynamics 365 de la base de datos de las operaciones."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Restablecer el informe financiero data mart restablecer después de una base de datos

Este tema describe cómo restablecer el informe financiero data mart después de restaurar un Microsoft Dynamics 365 de la base de datos de las operaciones. 

Existen varias situaciones donde pueda necesitar restablecer su Dynamics 365 de la base de datos de las operaciones de una copia de seguridad o copiar la base de datos de otro entorno. Si esto ocurre, también necesitará seguir los pasos adecuados para garantizar que el informe financiero data mart correctamente usa Dynamics restaurada 365 de la base de datos de las operaciones. Si tiene preguntas sobre restablecer el informe financiero data mart para motivos fuera de una restablecer Dynamics 365 de la base de datos de operaciones, consulte a [restableciendo el generador data mart (https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/)] de la gestión de casos para obtener más información. Tenga en cuenta que los pasos de este procedimiento se llevan para Dynamics 365 operación para la liberación de mayo de 2016 (compilar la aplicación 7.0.1265.23014 y el informe financiero compilar 7.0.10000.4) y nuevos más versiones. Si tiene una versión anterior de Dynamics 365 para las operaciones, contacte con nosotros a nuestro equipo admiten para obtener ayuda.

## <a name="export-report-definitions"></a>Exporte las definiciones de informe
En primer lugar, exporte los diseños de informe encuentran en el Diseñador de informes, mediante los pasos siguientes:

1.  En el Diseñador de informes, se toman ** empresa ** &gt; ** los grupos de bloque de creación **.
2.  Seleccione el grupo de bloque de creación, para exportar y haga clic en ** ** exportación. ** Nota: ** Para Dynamics 365 para las operaciones, se admite sólo un grupo de bloque de creación, ** valor predeterminado **.
3.  Seleccione las definiciones de informe para exportar:
    -   Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla CTRL para seleccionar varios elementos en una pestaña. Al seleccionar informes para exportar, seleccione las filas, las columnas, los árboles, y los conjuntos de dimensión asociados.

4.  Haga clic en ** ** exportación.
5.  Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.
6.  Click **Save**.

El archivo se puede copiar o cargar en una ubicación segura, que sea importada en un entorno diferente en otra hora. La información sobre el uso de una cuenta de almacenamiento de Microsoft Azure puede ser encontrada [en los datos de la transferencia con el programa de línea de comandos de AzCopy] (https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). ** Nota: ** Microsoft no proporciona una cuenta de almacenamiento como parte de su Dynamics 365 para el acuerdo de las operaciones. Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción blanco ciela independiente. ** Importante: ** Tenga en cuenta del comportamiento de la unidad de D en Azure Virtual Machines. No retener sus grupos exportados del bloque de creación aquí eliminan permanentemente. Para obtener más información acerca de unidades temporales, vea entendiendo [la unidad de tiempo situada en Windows Azure Virtual Machines] (https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Detener servicios
Use Escritorio remoto para conectar todos los equipos del entorno y detener los servicios de Windows mediante services.msc siguientes:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Microsoft Dynamics 365 para el servicio de lote de gestión de las operaciones (en equipos AOS de fuera del privado sólo)
-   Servicio de proceso de 2012 generador de administración (en equipos de BI solamente)

Estos servicios tendrán conexiones abierto a Dynamics 365 de la base de datos de las operaciones.

## <a name="reset"></a>Restablecer
#### <a name="locate-the-latest-dataupgradezip-package"></a>Localice el último paquete de DataUpgrade.zip

Localice el último paquete de DataUpgrade.zip mediante las direcciones que se encuentra en [descarga la secuencia de comandos de DataUpgrade.zip] (. \ \ migración- actualización upgrade-data-to-latest-update.md). Las direcciones se explica cómo encontrar la versión correcta de embalaje de la actualización de datos para su entorno.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Ejecutar las secuencias de comandos con las Dynamics 365 de la base de datos de las operaciones

Ejecutar las secuencias de comandos con siguientes Dynamics 365 de la base de datos de las operaciones (no con la base de datos del informe financiero).

-   Volver a\\ConfigureAxReportingIntegration.sql de DataUpgrade.zip\\\\AosService
-   Volver a\\GrantAzViewChangeTracking.sql de DataUpgrade.zip\\\\AosService

Estas secuencias de comandos garantizan que los usuarios, las funciones, parámetros de seguimiento y de cambios son correctos.

#### <a name="execute-powershell-command-to-reset-database"></a>Ejecute el comando PowerShell que restablecer de la base de datos

Ejecute el siguiente comando, directamente en el equipo AOS, de restablecer la integración entre Dynamics 365 de operaciones y del informe financiero:

1.  Abre Windows PowerShell como administrador.
2.  Ejecutese: F:
3.  Ejecutese: F del CD:\\MRApplicationService\\MRInstallDirectory
4.  Ejecutese: Importación-módulo. Servidor MRDeploy\\\\MRDeploy.psd1\\
5.  Ejecutese: - Razona ELSE - ReasonDetail restablecido - Mi DatamartIntegration “&lt;motivo para restablecer&gt;”
    -   Se le solicitará que introducir “y” al confirmar.

Explicación de parámetros:

-   Los valores válidos - para el motivo es: MANTENIMIENTO, BADDATA, ELSE.
-   - El parámetro de ReasonDetail es factura de servicios.
-   El motivo y el reasonDetail se registrarán en telemetría/el seguimiento del entorno.

## <a name="start-services"></a>Servicios de inicio
Use services.msc para reiniciar los servicios que ha detenido anterior:

-   Servicio de publicación de la World Wide Web (en todos los equipos AOS)
-   Microsoft Dynamics 365 para el servicio de lote de gestión de las operaciones (en equipos AOS de fuera del privado sólo)
-   Servicio de proceso de 2012 generador de administración (en equipos de BI solamente)

## <a name="import-report-definitions"></a>Importar definiciones de informe
Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación:

1.  En el Diseñador de informes, se toman ** empresa ** &gt; ** los grupos de bloque de creación **.
2.  Seleccione el grupo de bloque de creación, para exportar y haga clic en ** ** exportación. ** Nota: ** Para Dynamics 365 para las operaciones, se admite sólo un grupo de bloque de creación, ** valor predeterminado **.
3.  Seleccione ** valor predeterminado ** el bloque de creación y haga clic en ** ** importación.
4.  Seleccione el archivo que contiene las definiciones de informe y haga clic exportados ** Abrir **.
5.  En el cuadro de diálogo Importar, seleccione las definiciones del informe que desea importar:
    -   Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.

6.  Click **Import**.



