---
title: Sincronizar las estimaciones de proyectos directamente desde Project Service Automation a previsiones de proyectos de Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente las estimaciones de horas y de gastos de proyectos directamente de Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations.
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Sincronizar las estimaciones de proyectos directamente desde Project Service Automation a previsiones de proyectos de Finance and Operations

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente las estimaciones de horas y de gastos de proyectos directamente de Microsoft Dynamics 365 for Project Service Automation a Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flujo de datos de Project Service Automation a Finance and Operations

La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos sobre las estimaciones de horas y las estimaciones de gastos de proyecto desde Project Service Automation a Finance and Operations.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar las estimaciones de horas de proyectos desde Project Service Automation hasta Finance and Operations:

-  **Nombre de la plantilla en la integración de datos:** estimaciones de horas del proyecto (PSA a Fin and Ops)

-  **Nombre de las tareas en el proyecto:** 
    - Relaciones de transacción 
    - Estimaciones de gastos

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Tareas de proyecto                   | Entidad de integración para estimaciones de horas de proyecto   |

## <a name="entity-flow"></a>Flujo de la entidad

Las estimaciones de horas de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como previsiones de horas de proyectos.

## <a name="preconditions"></a>Condiciones previas

Antes de que se puedan producir las estimaciones de horas del proyecto, debe sincronizar proyectos, tareas de proyecto, y categorías de transacción de gastos del proyecto.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query en la plantilla de estimaciones de horas de proyecto para:
- Establecer el **Identificador del modelo de previsión** que se usará cuando la integración cree nuevas previsiones de horas.
- Filtrar todos los registros específicos de recursos dentro de la tarea que darán un resultado erróneo en la integración en previsiones de horas.
- Filtrar todas las filas de categoría de transacciones vacías. Si no ejecuta esta operación puede provocar previsiones de horas incorrectas.

### <a name="forecast-model-id"></a>Id. de modelo de previsión
Para actualizar el ID de modelo de previsión predeterminado en la plantilla, haga clic en la flecha **Mapa** para abrir la asignación. Seleccione para abrir la consulta y el filtrado avanzados.
- Si utiliza las estimaciones de horas predeterminadas de Microsoft Project (PSA a Fin and Ops), seleccione la **Condición insertada** en la sección **Pasos aplicados**. En la entrada **Función**, reemplace **O_previsión** con el nombre del **ID de modelo de previsión** que se debe usar con la integración. La plantilla predeterminada tiene un Id del modelo de previsión de los datos de prueba.
- Si crea una nueva plantilla, debe agregar esta columna. Seleccione **Agregar columna condicional** y dé a la columna un nombre, como ModelID. Especifique una condición para la columna por la que si tarea de proyecto no es nula, entonces <enter the forecast model ID>; de lo contrario un valor nulo.

### <a name="filter-out-resource-specific-records"></a>Filtrar la salida registros específicos del recurso
La plantilla de las estimaciones de horas del proyecto (PSA a Fin and Ops) tiene un filtro predeterminado que quita cualquier registro específico del recurso. Si crea su propia plantilla, debe agregar este filtro. En el formulario de consulta avanzada y filtro, seleccione filtrar en la columna **msdyn_islinetask** para que solo incluya los registros **False**.

### <a name="filter-out-empty-transaction-category-rows"></a>Filtrar filas de categorías de transacciones vacías
Debe agregar un filtro para quitar todas las filas con categorías de transacción vacías. Esto se necesita con independencia si usa la plantilla predeterminada o si está creando su propia plantilla. Esta filtro quitará cualquier fila de resumen procedente de Project Service Automation que pueda hacer que las previsiones de horas en Finance and Operations sean incorrectas. En el formulario de consulta avanzada y filtrado, selecciona filtrar salida de los registros nulos en la columna **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

La plantilla y la tarea subyacente siguientes se usan para sincronizar las estimaciones de gastos del proyecto desde Project Service Automation hasta Finance and Operations:

-  **Nombre de la plantilla en la integración de datos:** estimaciones de gastos del proyecto (PSA a Fin and Ops)
-  **Nombre de las tareas en el proyecto:** 
     - Relaciones de transacción 
     - Estimaciones de gastos

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Conexiones de transacción         | Entidad de integración para relaciones de transacción de proyecto.   |
| Líneas de estimación                  | Entidad de integración para estimaciones de gastos de proyecto.           |

## <a name="entity-flow"></a>Flujo de la entidad

Las estimaciones de gastos de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como previsiones de gastos de proyectos.

## <a name="prerequisites"></a>Requisitos previos

Antes de que se puedan producir las estimaciones de gastos del proyecto, debe sincronizar proyectos, tareas de proyecto, y categorías de transacción de gastos del proyecto.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query en la plantilla de estimaciones de gastos de proyecto para:
- Filtro para incluir solo los registros de la línea de estimación de gastos
- Establecer el **Identificador del modelo de previsión** que se usará cuando la integración cree nuevas previsiones de horas.
- Transforme los tipos de facturación.
- Transforme los tipos de transacción.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtro para incluir solo las líneas de estimación de gastos
La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) tiene un filtro predeterminado para incluir solo las líneas de gastos en la integración. Si crea su propia plantilla, debe agregar este filtro. Seleccione la tarea de relaciones de la transacción y haga clic en la flecha **Mapa** . Seleccione **Consulta avanzada y filtrado**. Filtre la columna **msdyn_transactiontype1** para incluir solo **msdyn_estimateline**.

### <a name="forecast-model-id"></a>Id. de modelo de previsión
Para actualizar el ID de modelo de previsión predeterminado en la plantilla, para la tarea de estimaciones de gastos haga clic en la flecha **Mapa** para abrir la asignación. Seleccione para abrir la consulta y el filtrado avanzados.
- Si utiliza las estimaciones de gastos predeterminadas de Microsoft Project (PSA a Fin and Ops), seleccione primero la **Condición insertada** en la sección **Pasos aplicados**. En la entrada **Función**, reemplace **O_previsión** con el nombre del **ID de modelo de previsión** que se debe usar con la integración. La plantilla predeterminada tiene un Id del modelo de previsión de los datos de prueba.
- Si crea una nueva plantilla, debe agregar esta columna. Seleccione **Agregar columna condicional** y dé a la columna un nombre, como ModelID. Especifique la condición para la columna donde si el identificador de la línea de estimación no es nulo, entonces < especificar el identificador del modelo de previsión >; de lo contrario nulo.

### <a name="transform-the-billing-types"></a>Transformar los tipos de facturación
La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) tiene una columna condicional agregada para transformar los tipos de la facturación recibidos desde Project Service Automation durante la integración.
- Si crea su propia plantilla, debe agregar esta columna condicional. En el formulario de consulta avanzada y filtrado, seleccione **Agregar columna condicional**. Dé a nueva columna un nombre, como "BillingType". La condición que debe especificarse es como la siguiente:

    If **msdyn_billingtype** = 192350000, then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**

### <a name="transform-the-transaction-types"></a>Transformación de los tipos de transacción
La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) tiene una columna condicional agregada para transformar los tipos de transacción recibidos desde Project Service Automation durante la integración.
- Si crea su propia plantilla, debe agregar esta columna condicional. En el formulario de consulta avanzada y filtrado, seleccione **Agregar columna condicional**. Dé a nueva columna un nombre, como "TransactionType". La condición que se introduce es la siguiente: If **msdyn_transactiontypecode** = 192350000, then **Cost** else if **msdyn_transactiontypecode** = 192350005, then **Sales** else **null**

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Asignación de la plantilla](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




