---
title: "Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Microsoft Dynamics 365 for Finance and Operations versión 8.0.
> - La integración de los valores reales está disponible en Microsoft Dynamics 365 for Finance and Operations versión 8.01 o posterior.
> - Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Flujo de datos de Project Service Automation y Finance and Operations

La solución de integración de Project Service Automation y Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Project Service Automation y Finance and Operations.

Si las categorías de gastos del proyecto se dominan en Finance and Operations, el flujo de integración se realiza primero desde Finance and Operations hasta Project Service Automation. Los identificadores de integración de las categorías de gastos de proyecto se actualizan mediante la sincronización de Project Service Automation a Finance and Operations.

Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance and Operations. Las categorías de proyecto deben estar ya configuradas en Finance and Operations antes de sincronizar desde Project Service Automation. A continuación sincronice desde Finance and Operations hasta Project Service Automation y desde Project Service Automation hasta Finance and Operations. De este modo, ayuda a garantizar que las categorías estén vinculadas y que no se creen duplicados.

> [!NOTE]
> Normalmente, las categorías de gastos del proyecto se dominan en Finance and Operations. Sin embargo, si no se dominan en Finance and Operations, o si ya se han creado categorías de gastos en Project Service Automation, primero debe realizar la sincronización utilizando la plantilla Categorías de transacción de gastos de proyecto (PSA a Fin and Ops). Se sincronizan mediante la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA). A continuación, deberá ejecutar la sincronización desde Project Service Automation a Finance and Operations una vez más.
>
> Si sincroniza primero desde Project Service Automation, deben cumplirse los siguientes requisitos en Finance and Operations antes de que se ejecute la sincronización:
>
> - Debe existir la categoría compartida que coincida con la categoría de proyecto establecida en Project Service Automation y debe estar habilitada tanto **Proyecto** como para **Gastos**.
> - Para cada entidad jurídica de Finance and Operations con la que deba integrarse, deben existir las siguientes categorías de proyecto:
>
>     - **Categoría de proyecto** existe. 
>     - **Usar en gasto** está habilitado.
>     - **Activo en el diario** está habilitado.
>     - **Tipo de transacción** se ha configurado en **Gasto**.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>Sincronización de categorías de gastos de proyecto de Finance and Operations a Project Service Automation

### <a name="template-and-task"></a>Plantilla y tarea

Para obtener acceso a la plantilla, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance and Operations hasta Project Service Automation:

- **Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)
- **Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA

### <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations            | Project Service Automation |
|-----------------------------------|----------------------------|
| Entidad de integración para categorías | Categorías de transacciones     |

### <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.

### <a name="power-query"></a>Power Query

Al sincronizar a Project Service Automation, debe usar Microsoft Power Query for Excel para establecer el tipo de facturación en la categoría de transacción. La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) proporciona una columna predeterminada y una asignación. Si crea su propia plantilla, debe agregar una columna condicional en Power Query. Siga estos pasos:

1. Haga clic en la flecha para abrir la asignación de la tarea de categorías de gastos de proyecto en la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).
2. Haga clic en el vínculo **Consulta y filtrado avanzados** para abrir Power Query.
2. Seleccione **Agregar columna condicional**.
3. Especifique un nombre para la nueva columna, como **BillingType**.
4. Especifique la siguiente condición: **if CATEGORYID not equal to null then 19235001, Otherwise null**.
5. En la columna, haga clic en **Aceptar**.
6. Asegúrese de asignar esta nueva columna en la página de la asignación.

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>Sincronización de categorías de gastos de proyecto de Project Service Automation a Finance and Operations

### <a name="template-and-task"></a>Plantilla y tarea

La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto de Project Service Automation a Finance and Operations:

- **Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de PSA a Fin and Ops)
- **Nombre de la tarea en el proyecto:** sincronizar categorías con Fin Ops

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations            |
|----------------------------|-----------------------------------|
| Categorías de transacciones     | Entidad de integración para categorías |

### <a name="entity-flow"></a>Flujo de la entidad

Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción. La sincronización con Finance and Operations actualiza la categoría de proyectos en Finance and Operations con el identificador de integración de Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.

> [!NOTE]
> La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

