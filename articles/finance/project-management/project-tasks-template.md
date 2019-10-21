---
title: Sincronizar las tareas de proyectos directamente desde Project Service Automation a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar tareas de proyectos directamente de Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
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
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250401"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizar las tareas de proyectos directamente desde Project Service Automation a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar tareas de proyectos directamente de Dynamics 365 Project Service Automation a Dynamics 365 Finance.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles la versión 8.0.
> - Si utiliza Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.
> - La integración de los reales está disponible en la versión 8.0.1 o posterior.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Flujo de datos de Project Service Automation a Finance

La solución de integración de Project Service Automation a Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance. La plantilla de integración disponible con la función de integración de datos habilita el flujo de datos sobre las tareas de proyecto desde Project Service Automation a Finance.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.

[![Flujo de datos para la integración de Project Service Automation con Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Plantilla y tarea

Para obtener acceso a la plantilla, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar las tareas del proyecto desde Project Service Automation a Finance:

- **Nombre de la plantilla en la integración de datos:** tareas del proyecto (PSA a Fin and Ops)
- **Nombre de la tarea en el proyecto:** tareas de proyecto

Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finanzas                             |
|----------------------------|-------------------------------------|
| Tareas de proyecto              | Entidad de integración para tarea de proyecto |

## <a name="entity-flow"></a>Flujo de la entidad

Las tareas de proyectos se administran en Project Service Automation y se sincronizan con Finance como actividades de proyectos.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query for Excel para filtrar los datos si se cumple esta condición:

- Tiene registros específicos de recursos en una tarea de proyecto.

Si debe usar Power Query, siga esta instrucción:

- La plantilla de las tareas de proyecto (PSA a Fin and Ops) tiene un filtro predeterminado que excluye registros específicos de recursos de una tarea de proyecto estableciendo el filtro de **IsLineTask** en **Falso**. Si crea su propia plantilla, debe agregar este filtro.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de las asignaciones de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.

[![Asignación de la plantilla](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)
