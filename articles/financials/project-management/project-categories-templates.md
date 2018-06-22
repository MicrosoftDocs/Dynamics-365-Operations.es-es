---
title: "Sincronizar las categorías de gastos de proyectos de Project Service Automation"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Dynamics 365 for Project Service Automation.

> [!NOTE]
> La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Flujo de datos de Project Service Automation y Finance and Operations

La solución de integración de Project Service Automation y Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Project Service Automation y Finance and Operations.

Si las categorías de gastos de proyectos se dominan en Finance and Operations, el flujo de integración se realiza primero desde Finance and Operations hasta Project Service Automation y después se actualizan los id. de integración de las categorías de gastos de proyectos sincronizando desde Project Service Automation hasta Finance and Operations.

Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance and Operations. Las categorías de proyecto deben estar ya configuradas en Finance and Operations antes de sincronizar desde Project Service Automation. A continuación sincronice desde Finance and Operations hasta Project Service Automation y desde Project Service Automation hasta Finance and Operations. Esto garantiza que las categorías estén vinculadas y que no se creen duplicados.

> [!NOTE]
> Normalmente, las categorías de gastos del proyecto se dominan en Finance and Operations. Si esta no es su situación o ya tiene categorías de gastos creadas en Project Service Automation, primero debe efectuar la sincronización usando las categorías de transacción de gastos del proyecto (de PSA a Fin and Ops) y después realizar la sincronización usando categorías de transacción de gastos del proyecto (de Fin and Ops a PSA). A continuación debe ejecutar la sincronización desde PSA a Fin and Ops una vez más.

> Si sincroniza primero desde Project Service Automation, las categorías de proyecto deben estar ya configuradas en Finance and Operations y todas las categorías de proyecto que es necesario que se sincronicen con las categorías de transacción de Project Service Automation se deben configurar para ser **Activas en diarios**.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance and Operations hasta Project Service Automation:

-  **Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)
-  **Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Entidad de integración para categorías    | Categorías de transacciones        |

## <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query para establecer el tipo de facturación en la categoría de transacción al sincronizar a Project Service Automation. La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) tiene una columna predeterminada y una asignación ya proporcionada. Si crea su propia plantilla, debe agregar una columna condicional en Power Query.
- Abra el formulario de consulta avanzada y filtrado desde dentro de la asignación de la tarea de categorías de gastos de proyectos.
- Seleccione **Agregar columna condicional**.
- Dé a nueva columna un nombre, como BillingType.
- Especifique la siguiente condición: si **CATEGORYID not equal to null then 19235001, Otherwise null**.
- En la columna, haga clic en **Aceptar**.
- Asegúrese de asignar esta nueva columna en la página de la asignación.

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Project Service Automation hasta Finance and Operations:

-**Nombre de la plantilla en la integración de datos:** Categorías de transacción de gastos del proyecto (de PSA a Fin and Ops) -**Nombre de la tarea en el proyecto:** Sincronización de categorías a Fin and Ops

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Categorías de transacciones          | Entidad de integración para categorías  | 

## <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción. La sincronice a Finance and Operations actutaliza el ID de integración desde Project Service Automation en la categoría de proyecto de Finance and Operations.

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.

> [!NOTE]
> La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

