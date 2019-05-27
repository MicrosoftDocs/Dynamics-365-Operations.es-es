---
title: Sincronizar las estimaciones de proyectos directamente desde Project Service Automation a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cálculos de horas de proyectos y cálculos de gastos de proyectos directamente de Microsoft Dynamics 365 for Project Service Automation en Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 21338b889e0377dbfd5adfd461ea81b39a75baf8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556561"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizar las estimaciones de proyectos directamente desde Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cálculos de horas de proyectos y cálculos de gastos de proyectos directamente desde Microsoft Dynamics 365 for Project Service Automation en Dynamics 365 for Finance and Operations.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles en Microsoft Dynamics 365 for Finance and Operations versión 8.0.
> - La integración de los reales está disponible en Microsoft Dynamics 365 for Finance and Operations versión 8.0.1 o posterior.
> - Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flujo de datos de Project Service Automation a Finance and Operations

La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos sobre las estimaciones de horas y las estimaciones de gastos de proyecto desde Project Service Automation a Finance and Operations.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Estimaciones de horas de proyecto

### <a name="template-and-tasks"></a>Plantilla y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar las estimaciones de horas de proyectos desde Project Service Automation hasta Finance and Operations:

- **Nombre de la plantilla en la integración de datos:** estimaciones de horas del proyecto (PSA a Fin and Ops)
- **Nombre de las tareas en el proyecto:**

    - Relaciones de transacción
    - Estimaciones de gastos

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations                        |
|----------------------------|-----------------------------------------------|
| Tareas de proyecto              | Entidad de integración para estimaciones de horas de proyecto |

### <a name="entity-flow"></a>Flujo de la entidad

Las estimaciones de horas de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como previsiones de horas de proyectos.

### <a name="prerequisites"></a>Requisitos previos

Antes de que se puedan producir las estimaciones de horas del proyecto, debe sincronizar proyectos, tareas de proyecto, y categorías de transacción de gastos del proyecto.

### <a name="power-query"></a>Power Query

En la plantilla de estimaciones de horas de proyecto, debe utilizar Microsoft Power Query for Excel para completar estas tareas:

- Establecer el Identificador del modelo de previsión predeterminado que se usará cuando la integración cree nuevas previsiones de horas.
- Filtrar todos los registros específicos de recursos dentro de la tarea que darán un resultado erróneo en la integración en previsiones de horas.
- Filtrar todas las filas de categoría de transacciones vacías. Si no completa esta tarea puede provocar previsiones de horas incorrectas.

#### <a name="set-the-default-forecast-model-id"></a>Establecer el identificador de modelo de previsión predeterminado

Para actualizar el ID de modelo de previsión predeterminado en la plantilla, haga clic en la flecha **Mapa** para abrir la asignación. A continuación, seleccione el vínculo **Consulta y filtrado avanzados**.

- Si utiliza las estimaciones de horas predeterminadas de Project (PSA a Fin and Ops), seleccione la **Condición insertada** en la lista de **Pasos aplicados**. En la entrada **Función**, reemplace **O\_previsión** con el nombre del identificador de modelo de previsión que se debe usar con la integración. La plantilla predeterminada tiene un Id del modelo de previsión de los datos de prueba.
- Si crea una nueva plantilla, debe agregar esta columna. En Power Query, seleccione **Agregar columna condicional** e introduzca un nombre para la nueva columna, como **ModelID**. Especifique la condición para la columna donde, si la tarea de proyecto no es nula, entonces \<especificar el identificador del modelo de previsión\>; de lo contrario, nulo.

#### <a name="filter-out-resource-specific-records"></a>Filtrar la salida registros específicos del recurso

La plantilla Estimaciones de horas del proyecto (PSA a Fin and Ops) tiene un filtro predeterminado que elimina cualquier registro específico del recurso. Si crea su propia plantilla, debe agregar este filtro. Seleccione el vínculo **Consulta y filtro avanzados** para filtrar en la columna **msdyn\_islinetask** de modo que solo se incluyan los registros **False**.

#### <a name="filter-out-empty-transaction-category-rows"></a>Filtrar filas de categorías de transacciones vacías

Debe agregar un filtro para quitar todas las filas que tengan categorías de transacción vacías. Esta tarea es obligatoria, con independencia de si usa la plantilla predeterminada o si está creando su propia plantilla. Esta filtro quita cualquier fila de resumen de Project Service Automation que pueda hacer que las previsiones de horas en Finance and Operations sean incorrectas. Seleccione el vínculo **Consulta y filtrado avanzados** para filtrar la salida de los registros nulos en la columna **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Estimaciones de gastos de proyecto

### <a name="template-and-tasks"></a>Plantilla y tareas

La plantilla y las tareas subyacentes siguientes se usan para sincronizar las estimaciones de gastos del proyecto desde Project Service Automation hasta Finance and Operations:

- **Nombre de la plantilla en la integración de datos:** estimaciones de gastos del proyecto (PSA a Fin and Ops)
- **Nombre de las tareas en el proyecto:**

    - Relaciones de transacción 
    - Estimaciones de gastos

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Conexiones de transacción    | Entidad de integración para relaciones de transacción de proyecto |
| Líneas de estimación             | Entidad de integración para estimaciones de gastos de proyecto         |

### <a name="entity-flow"></a>Flujo de la entidad

Las estimaciones de gastos de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como previsiones de gastos de proyectos.

### <a name="prerequisites"></a>Requisitos previos

Antes de que se puedan producir las estimaciones de gastos del proyecto, debe sincronizar proyectos, tareas de proyecto y categorías de transacción de gastos del proyecto.

### <a name="power-query"></a>Power Query

En la plantilla de estimaciones de gastos del proyecto, debe utilizar Power Query para completar las siguientes tareas:

- Filtrar para incluir solo los registros de la línea de estimación de gastos.
- Establecer el Identificador del modelo de previsión predeterminado que se usará cuando la integración cree nuevas previsiones de horas.
- Transforme los tipos de facturación.
- Transforme los tipos de transacción.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtro para incluir solo las líneas de estimación de gastos

La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) tiene un filtro predeterminado que incluye solo las líneas de gastos en la integración. Si crea su propia plantilla, debe agregar este filtro. Seleccione la tarea **Relaciones de la transacción** y, a continuación, haga clic en la flecha **Mapa** para abrir la asignación. Seleccione el vínculo **Consulta y filtrado avanzados**. Filtre la columna **msdyn\_transactiontype1** de modo que solo incluya **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Establecer el identificador de modelo de previsión predeterminado

Para actualizar el identificador de modelo de previsión predeterminado en la plantilla, seleccione la tarea **Estimaciones de gastos** y, a continuación, haga clic en la flecha **Mapa** para abrir la asignación. Seleccione el vínculo **Consulta y filtrado avanzados**.

- Si utiliza las estimaciones de gastos predeterminadas de Project (PSA a Fin and Ops), en Power Query, seleccione primero la **Condición insertada** de la sección **Pasos aplicados**. En la entrada **Función**, reemplace **O\_previsión** con el nombre del identificador de modelo de previsión que se debe usar con la integración. La plantilla predeterminada tiene un Id del modelo de previsión de los datos de prueba.
- Si crea una nueva plantilla, debe agregar esta columna. En Power Query, seleccione **Agregar columna condicional** e introduzca un nombre para la nueva columna, como **ModelID**. Especifique la condición para la columna donde, si el identificador de la línea de estimación no es nulo, entonces \<especificar el identificador del modelo de previsión\>; de lo contrario, nulo.

#### <a name="transform-the-billing-types"></a>Transformar los tipos de facturación

La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) incluye una columna condicional que se usa para transformar los tipos de la facturación que se han recibido desde Project Service Automation durante la integración. Si crea su propia plantilla, debe agregar esta columna condicional. Seleccione el vínculo **Consulta y filtrado avanzados** y, a continuación, seleccione **Agregar columna condicional**. Especifique un nombre para la nueva columna, como **BillingType**. A continuación, especifique la condición siguiente:

If **msdyn\_billingtype** = 192350000, then **NonChargeable**  
else if **msdyn\_billingtype** = 192350001, then **Chargeable**  
else if **msdyn\_billingtype** = 192350002, then **Complimentary**  
else **NotAvailable**

#### <a name="transform-the-transaction-types"></a>Transformación de los tipos de transacción

La plantilla de las estimaciones de gastos de proyectos (PSA a Fin and Ops) incluye una columna condicional que se usa para transformar los tipos de transacción que se han recibido desde Project Service Automation durante la integración. Si crea su propia plantilla, debe agregar esta columna condicional. Seleccione el vínculo **Consulta y filtrado avanzados** y, a continuación, seleccione **Agregar columna condicional**. Especifique un nombre para la nueva columna, como **TransactionType**. A continuación, especifique la condición siguiente:

If **msdyn\_transactiontypecode** = 192350000, then **Cost**  
else if **msdyn\_transactiontypecode** = 192350005, then **Sales**  
else **null**

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Asignación de la plantilla](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
