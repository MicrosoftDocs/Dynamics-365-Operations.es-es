---
title: Guía de solución de problemas para integración de datos
description: Este tema proporciona información para solución de problemas de integración de datos entre Microsoft Dynamics 365 for Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797284"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guía de solución de problemas para integración de datos

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Habilitar el seguimiento de complementos en Common Data Service y comprobar los detalles del error en el complemento de escritura dual

Si tiene un problema o se produce un error en relación con la sincronización de la escritura dual, puede inspeccionar los errores en el registro de seguimiento:

1. Antes de que pueda inspeccionar los errores, debe habilitar el seguimiento de complementos según las instrucciones en [Complemento de registro](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) para habilitar el seguimiento de complementos. Ahora ya puede inspeccionar errores.
2. Inicie sesión en Dynamics 365 for Sales.
3. Haga clic en el icono de configuración (un engranaje) y seleccione **Opciones avanzadas**.
4. En el menú **Configuración** , seleccione **Personalización > REgistro de seguimiento de complementos**.
5. Haga clic en el nombre del tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** para mostrar los detalles de error.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Comprobar los errores de sincronización de escritura dual en Finance and Operations

Puede comprobar los errores durante las pruebas siguiendo estos pasos:

+ Inicie sesión en LifeCycle Services (LCS).
+ Abra el proyecto LCS que seleccionó para realizar la prueba de escritura dual.
+ Vaya a Entornos hospedados en la nube.
+ Escritorio remoto a VM Finance and Operations mediante la cuenta local que se muestra en LCS.
+ Abra el visor de eventos. 
+ Vaya **Registros de aplicaciones y servicios > Microsoft > Dynamics > AX-DualWriteSync > Operacional**. Se muestran los errores y los detalles.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Cómo desvincular y vincular otro entorno Common Data Service de Finance and Operations

Puede actualizar los vínculos siguiendo estos pasos:

+ Navegue al entorno de Finance and Operations.
+ Abra Administración de datos.
+ Hag clic en **Vínculo a CDS para aplicaciones**.
+ Seleccione todas las asignaciones en funcionamiento haga click en **Detener**. 
+ Seleccione todas las asignaciones y haga click en **Eliminar**.

    > [!NOTE]
    > La opción **Eliminar** no aparecerá si se selecciona la plantilla **CustomerV3-Account** . Anule su selección si es necesario. **CustomerV3-Account** es una antigua plantilla y funciona con la solución Prospect to Cash. Dado que el lanzamiento es global, aparecerá bajo todas las plantillas.

+ Haga click en **Desvincular entorno**.
+ Haga click en **Sí** como confirmación.
+ Para vincular el nuevo entorno, siga los pasos de la [guía de instalación](https://aka.ms/dualwrite-docs).

