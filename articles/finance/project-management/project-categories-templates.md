---
title: Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Microsoft Dynamics 365 Finance y Dynamics 365 Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770321"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Dynamics 365 Finance y Dynamics 365 Project Service Automation.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles la versión 8.0.
> - La integración de los reales está disponible en la versión 8.0.1 o posterior.
> - Si utiliza Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance"></a>Flujo de datos de Project Service Automation y Finance

La solución de integración de Project Service Automation y Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Finance y Project Service Automation.

Si las categorías de gastos del proyecto se dominan en Finance, el flujo de integración se realiza primero desde Finance hasta Project Service Automation. Los identificadores de integración de las categorías de gastos de proyecto se actualizan mediante la sincronización de Project Service Automation a Finance.

Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance. Las categorías de proyecto deben estar ya configuradas en Finance antes de sincronizar desde Project Service Automation. A continuación sincronice desde Finance hasta Project Service Automation y desde Project Service Automation hasta Finance. De este modo, ayuda a garantizar que las categorías estén vinculadas y que no se creen duplicados.

> [!NOTE]
> Normalmente, las categorías de gastos del proyecto se dominan en Finance. Sin embargo, si no se han creado o si ya se han creado categorías de gastos en Project Service Automation, primero debe realizar la sincronización utilizando la plantilla Categorías de transacción de gastos de proyecto (PSA a Fin and Ops). Se sincronizan mediante la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA). A continuación, deberá ejecutar la sincronización desde Project Service Automation a Finance una vez más.
>
> Si sincroniza primero desde Project Service Automation, deben cumplirse los siguientes requisitos en Finance antes de que se ejecute la sincronización:
>
> - Debe existir la categoría compartida que coincida con la categoría de proyecto establecida en Project Service Automation y debe estar habilitada tanto **Proyecto** como para **Gastos**.
> - Para cada entidad jurídica de Finance con la que deba integrarse, deben existir las siguientes categorías de proyecto:
>
>     - **Categoría de proyecto** existe. 
>     - **Usar en gasto** está habilitado.
>     - **Activo en el diario** está habilitado.
>     - **Tipo de transacción** se ha configurado en **Gasto**.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.

[![Flujo de datos para la integración de Project Service Automation con Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a>Sincronización de categorías de gastos de proyecto de Finance a Project Service Automation

### <a name="template-and-task"></a>Plantilla y tarea

Para obtener acceso a la plantilla, en el centro de administración de Microsoft Power Apps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance hasta Project Service Automation:

- **Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)
- **Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA

### <a name="entity-set"></a>Conjunto de entidades

| Finanzas                           | Project Service Automation |
|-----------------------------------|----------------------------|
| Entidad de integración para categorías | Categorías de transacciones     |

### <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance y después se sincronizan con Project Service Automation como categorías de transacción.

### <a name="power-query"></a>Power Query

Al sincronizar a Project Service Automation, debe usar Microsoft Power Query for Excel para establecer el tipo de facturación en la categoría de transacción. La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) proporciona una columna predeterminada y una asignación. Si crea su propia plantilla, debe agregar una columna condicional en Power Query. Siga estos pasos:

1. Haga clic en la flecha para abrir la asignación de la tarea de categorías de gastos de proyecto en la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).
2. Haga clic en el vínculo **Consulta y filtrado avanzados** para abrir Power Query.
2. Seleccione **Agregar columna condicional**.
3. Especifique un nombre para la nueva columna, como **BillingType**.
4. Especifique la siguiente condición: **if CATEGORYID not equal to null then 19235001, Otherwise null**.
5. En la columna, haga clic en **Aceptar**.
6. Asegúrese de asignar esta nueva columna en la página de la asignación.

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Finance a Project Service Automation.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a>Sincronización de categorías de gastos de proyecto de Project Service Automation a Finance

### <a name="template-and-task"></a>Plantilla y tarea

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto de Project Service Automation a Finance:

- **Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de PSA a Fin and Ops)
- **Nombre de la tarea en el proyecto:** sincronizar categorías con Fin Ops

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finanzas                           |
|----------------------------|-----------------------------------|
| Categorías de transacciones     | Entidad de integración para categorías |

### <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance y después se sincronizan con Project Service Automation como categorías de transacción. La sincronización con Finance actualiza la categoría de proyectos en Finance con el identificador de integración de Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.

> [!NOTE]
> La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)
