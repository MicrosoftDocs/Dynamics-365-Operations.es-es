---
title: "Permite sincronizar los valores reales del Project Service Automation directamente al diario de integración del proyecto para el registro en Finance and Operations"
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente los valores reales de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
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
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Permite sincronizar los valores reales del Project Service Automation directamente al diario de integración del proyecto para el registro en Finance and Operations

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente los valores reales de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.

Las transacciones de sincronización de plantillas de Project Service Automation a una tabla de ensayo en Finance and Operations. Una vez completada la sincronización, debe importar desde la tabla de ensayo al diario de integración.

> [!NOTE]
> La integración de los valores reales del proyecto está disponible en Dynamics 365 para Finance and Operations versión 8.01.

> [!NOTE]
> Si especifica importes de impuestos a tiempo o las transacciones de gastos en Project Service Automation, debe instalar la actualización 7 de Project Service Automation. Si esta actualización no está instalada, los valores reales de impuestos no se vincularán a los valores reales asociados al tiempo o a los gastos y no se sincronizarán con Finance and Operations. Póngase en contacto con el servicio de atención al cliente para obtener más información.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flujo de datos de Project Service Automation a Finance and Operations

La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos sobre los valores reales de proyecto desde Project Service Automation a Finance and Operations.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Plantillas y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar los valores reales desde Project Service Automation hasta Finance and Operations:

-  **Nombre de la plantilla en la integración de datos:** valores reales del proyecto (PSA a Fin and Ops)

-  **Nombre de las tareas en el proyecto:** 
    - Reales 
    - TransactionConnections

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Reales                         | Entidad de integración para valores reales de proyecto                      |
| Conexiones de transacción         | Entidad de integración para relaciones de transacción de proyecto    |

## <a name="entity-flow"></a>Flujo de la entidad

Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con Finance and Operations en el diario de integración del proyecto. Las contabilidad se aplicará según dimensiones financieras predeterminadas y la configuración de registro.

## <a name="preconditions"></a>Condiciones previas

Antes de que la sincronización de valores reales pueda producirse, debe configurar los parámetros de integración de Project Service Automation y sincronizar proyectos, tareas de proyecto y categorías de transacción de gastos del proyecto.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query en la plantilla de los valores reales de proyecto para:
- Transformar el **tipo de transacción** de Project Service Automation en el **tipo de transacción** correcto de Finance and Operations. La plantilla de valores reales de proyecto (PSA a Fin and Ops) tiene esta transformación definida.
- Transformar el **tipo de facturación** de Project Service Automation en el **tipo de facturación** correcto de Finance and Operations. La plantilla de valores reales de proyecto (PSA a Fin and Ops) tiene esta transformación definida. El tipo de facturación se asigna a la **propiedad de línea** basándose en la configuración indicada en el formulario de integración de Dynamics 365 for Project Service Automation.
- Filtrar en **Unidades organizativas de recursos** determinadas que deben sincronizarse con esta plantilla.
- Si **los valores reales de gastos de empresas vinculadas o de tiempo de empresas vinculadas** se van a sincronizar con Finance and Operations, debe transformar la **unidad organizativa del contrato** en la **entidad jurídica** correcta en Finance and Operations. La plantilla de los valores reales del proyecto (PSA a Fin and Ops) tiene una columna condicional definida basada en datos de prueba. Debe actualizar la columna insertada en último lugar con las entidades jurídicas correctas. Si no lo hace puede provocar un error de integración o que se importen transacciones reales incorrectas a Finance and Operations.
- Si **los valores reales de tiempo de empresas vinculadas o de gastos de empresas vinculadas** no se sincroniza con Finance and Operations, debe eliminar de la plantilla la columna de condición insertada en último lugar. Si no lo hace puede provocar un error de integración o que se importen transacciones reales incorrectas a Finance and Operations.

### <a name="contract-organizational-unit"></a>Unidad organizativa de contrato
Para actualizar la columna de condición insertada en la plantilla, haga clic en la flecha **Mapa** para abrir la asignación. Seleccione para abrir la consulta y el filtrado avanzados.
- Si utiliza los valores reales predeterminados de Microsoft Project (PSA a Fin and Ops), seleccione la última **Condición insertada** en la sección **Pasos aplicados**. En la entrada **Función**, reemplace **USSI** con el nombre de la **Entidad jurídica** que se debe usar con la integración. Agregue condiciones adicionales según las necesidades a la entrada **Función** y actualice la condición **else** de **USMF** por la **Entidad jurídica** correcta.
- Si crea una nueva plantilla, debe agregar esta columna para dar soporte a los gatos y el tiempo de las empresas vinculadas. Seleccione **Agregar columna condicional** y dé a la columna un nombre, como LegalEntity. Especifique la condición para la columna donde si es msdyn_contractorganizationalunitid.msdyn_name es <organizational unit>, entonces <enter the Legal entity> es nulo.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Asignación de la plantilla](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importar desde tabla de almacenamiento provisional

El proceso de importación del proceso periódico de la tabla de prueba se debe ejecutar después de la sincronización de los valores reales desde Project Service Automation a Finance and Operations. Este proceso importará las transacciones de proyecto de la tabla de ensayo al diario de integración de Project Service Automation, donde se aplica la contabilidad y se pueden registrar las transacciones importadas. Se recomienda que ejecute este proceso en modo de lotes y se puede configurar opcionalmente para ejecutarlo como lote periódico.

## <a name="update-actuals"></a>Actualización de valores reales

La plantilla y las tareas subyacentes siguientes se usan para sincronizar el número de asiento y los impuestos de las transacciones de proyecto registradas desde Finance and Operations hasta Project Service Automation:

-  **Nombre de la plantilla en la integración de datos:** actualización de los valores reales del proyecto (de Fin Ops a PSA)
-  **Nombre de las tareas en el proyecto:** 
     - Reales 
     - TransactionConnections

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Entidad de integración para valores reales de proyecto                         | Reales                           |
| Entidad de integración para relaciones de transacción de proyecto       | Conexiones de transacción           |

## <a name="entity-flow"></a>Flujo de la entidad

Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con Finance and Operations en el diario de integración del proyecto. Una vez contabilizados en Finance and Operations, los valores reales se actualizan en Project Service Automation con el número de asiento de Finance and Operations. Si los impuestos se han agregado en Finance and Operations, los nuevos valores reales se crearán en Project Service Automation.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query en la plantilla de actualización de los valores reales de proyecto para:
- Transformar el **tipo de transacción** de Finance and Operations al **tipo de transacción** correcto de Project Service Automation. La actualización de valores reales de proyecto (de Fin Ops a PSA) ya tiene esta transformación definida.
- Transformar el **tipo de facturación** de Finance and Operations en el **tipo de facturación** correcto en Project Service Automation. La actualización de valores reales de proyecto (de Fin Ops a PSA) ya tiene esta transformación definida.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos. La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.

[![Asignación de la plantilla](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Asignación de la plantilla](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




