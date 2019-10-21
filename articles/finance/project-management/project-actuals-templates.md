---
title: Permite sincronizar los valores reales directamente del Project Service Automation al diario de integración del proyecto para el registro en Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar reales de un proyecto directamente de Microsoft Dynamics 365 Project Service Automation a Finance and Operations.
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 0aeaa1ee4c35ca42a5382b3c7ff3519cba52996c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250539"
---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Permite sincronizar los valores reales directamente del Project Service Automation al diario de integración del proyecto para el registro en Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar reales de un proyecto directamente de Dynamics 365 Project Service Automation a Dynamics 365 Finance.

La plantilla sincroniza las transacciones de Project Service Automation a una tabla de ensayo en Finance. Una vez completada la sincronización, **debe** importar los datos desde la tabla de ensayo al diario de integración.

> [!NOTE]
> - La integración de los reales de un proyecto está disponible a partir de la versión 8.0.1.
> - Si utiliza Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.
> - Si está usando la versión 7.3.0 y trae transacciones de cuotas de Project Service Automation, debe instalar KB 4345320 para incluir esas cuotas en la factura del proyecto.
> - Si especifica importes de impuestos a tiempo o las transacciones de gastos en Project Service Automation, debe instalar la actualización 7 de Project Service Automation. De lo contrario, los valores reales de impuestos no se vincularán con los valores reales de tiempo o gasto asociados y no se sincronizarán con Finance. Para obtener más información, póngase en contacto con soporte técnico.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flujo de datos de Project Service Automation a Finance

La solución de integración de Project Service Automation a Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance. Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos sobre los valores reales de proyecto desde Project Service Automation a Finance.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Valores reales de proyecto de Project Service Automation

### <a name="template-and-tasks"></a>Plantilla y tareas

Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y las tareas subyacentes siguientes se usan para sincronizar las tareas del proyecto desde Project Service Automation a Finance:

- **Nombre de la plantilla en la integración de datos:** valores reales del proyecto (PSA a Fin and Ops)
- **Nombre de las tareas en el proyecto:**

    - Reales
    - TransactionConnections

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finanzas                                   |
|----------------------------|----------------------------------------------------------|
| Reales                    | Entidad de integración para valores reales de proyecto                   |
| Conexiones de transacción    | Entidad de integración para relaciones de transacción de proyecto |

### <a name="entity-flow"></a>Flujo de la entidad

Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con el diario de integración del proyecto en Finance. Las contabilidad se aplicará según dimensiones financieras predeterminadas y la configuración de registro.

### <a name="prerequisites"></a>Requisitos previos

Antes de que la sincronización de valores reales pueda producirse, debe configurar los parámetros de integración de Project Service Automation y sincronizar proyectos, tareas de proyecto y categorías de transacción de gastos del proyecto.

### <a name="power-query"></a>Power Query

En la plantilla de valores reales de proyecto, debe utilizar Microsoft Power Query for Excel para completar estas tareas:

- Transformar el tipo de transacción de Project Service Automation en el tipo de transacción correcto de Finance. Esta transformación ya está definida en la plantilla de valores reales de proyecto (PSA a Fin and Ops).
- Transformar el tipo de facturación en Project Service Automation al tipo de facturación correcto en Finance. Esta transformación ya está definida en la plantilla de valores reales de proyecto (PSA a Fin and Ops). El tipo de facturación se asigna a la propiedad de línea basándose en la configuración indicada en la página **Parámetros de integración de Project Service Automation**.
- Filtrar en unidades organizativas de recursos determinadas que deben sincronizarse con esta plantilla.
- Si los valores reales de gastos de empresas vinculadas o de tiempo de empresas vinculadas se van a sincronizar con Finance, debe transformar la unidad organizativa del contrato en la entidad jurídica correcta en Finance. En la plantilla de los valores reales del proyecto (PSA a Fin and Ops) se define una columna condicional basada en datos de demostración. Debe actualizar la columna condicional insertada en último lugar con las entidades jurídicas correctas. De lo contrario, podría producirse un error de integración o podrían importarse transacciones reales incorrectas a Finance.
- Si los valores reales de tiempo de empresas vinculadas o de gastos de empresas vinculadas no se sincronizan con Finance, debe eliminar de la plantilla la columna condicional insertada en último lugar. De lo contrario, podría producirse un error de integración o podrían importarse transacciones reales incorrectas a Finance.

#### <a name="contract-organizational-unit"></a>Unidad organizativa de contrato
Para actualizar la columna condicional insertada en la plantilla, haga clic en la flecha **Mapa** para abrir la asignación. Seleccione el vínculo **Consulta y filtrado avanzados** para abrir Power Query.

- Si utiliza los valores reales predeterminados de Project (PSA a Fin and Ops), en Power Query, seleccione la última **Condición insertada** de la sección **Pasos aplicados**. En la entrada **Función**, reemplace **USSI** por el nombre de la entidad jurídica que se debe usar con la integración. Agregue condiciones adicionales a la entrada **Función** según sea necesario y actualice la condición **else** de **USMF** por la entidad jurídica correcta.
- Si crea una nueva plantilla, debe agregar la columna para dar soporte a los gatos y el tiempo de las empresas vinculadas. Seleccione **Agregar columna condicional** y especifique un nombre para la columna, como **LegalEntity**. Introduzca una condición para la columna en la que, si **msdyn\_contractororganizationalunitid.msdyn\_name** es una \<unidad organizativa\>, entonces \<introducir la entidad jurídica\>; de lo contrario, nulo.

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.

[![Asignación de la plantilla](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Asignación de la plantilla](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importar desde la tabla de ensayo después de la integración desde Project Service Automation

La importación desde el proceso periódico de la tabla de prueba se debe ejecutar después de la sincronización de los valores reales desde Project Service Automation a Finance. Este proceso importará las transacciones de proyecto de la tabla de ensayo al diario de integración de Project Service Automation, donde se aplica la contabilidad y se pueden registrar las transacciones importadas. Recomendamos que ejecute este proceso en modo de lotes; se puede configurar opcionalmente para ejecutarlo como lote periódico.

## <a name="update-actuals-from-finance"></a>Actualizar datos reales desde Finance

### <a name="template-and-tasks"></a>Plantilla y tareas

La plantilla y las tareas subyacentes siguientes se usan para sincronizar el número de asiento y los impuestos de las transacciones de proyecto registradas desde Finance hasta Project Service Automation:

- **Nombre de la plantilla en la integración de datos:** actualización de los valores reales del proyecto (de Fin Ops a PSA)
- **Nombre de las tareas en el proyecto:**

    - Reales 
    - TransactionConnections

### <a name="entity-set"></a>Conjunto de entidades

| Finanzas                                                  | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Entidad de integración para valores reales de proyecto                   | Reales                    |
| Entidad de integración para relaciones de transacción de proyecto | Conexiones de transacción    |

### <a name="entity-flow"></a>Flujo de la entidad

Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con el diario de integración del proyecto en Finance. Después de que los valores reales se registren en Finance, se actualizan en Project Service Automation con el número de asiento de Finance. Si los impuestos se han agregado en Finance, los nuevos valores reales se crean en Project Service Automation.

### <a name="power-query"></a>Power Query

En la plantilla de actualización de valores reales de proyecto, debe utilizar Power Query para completar estas tareas:

- Transformar el tipo de transacción en Finance en el tipo de transacción correcto de Project Service Automation. Esta transformación ya está definida en la plantilla de actualización de valores reales de proyecto (Fin and Ops a PSA).
- Transformar el tipo de facturación en Finance al tipo de facturación correcto en Project Service Automation. Esta transformación ya está definida en la plantilla de actualización de valores reales de proyecto (Fin and Ops a PSA).

### <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos. La asignación muestra la información de campo que se sincronizará de Finance a Project Service Automation.

[![Asignación de la plantilla](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Asignación de la plantilla](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)
