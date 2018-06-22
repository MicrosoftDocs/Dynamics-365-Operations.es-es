---
title: Sincronizar las tareas de proyectos de Project Service Automation
description: En este tema se describen la plantilla y la tarea subyacente que se usa para sincronizar directamente las tareas de proyectos de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.
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
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: es-es
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Sincronizar las tareas de proyectos directamente desde Project Service Automation a actividades de proyectos de Finance and Operations

En este tema se describen la plantilla y la tarea subyacente que se usa para sincronizar directamente las tareas de proyectos de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.

> [!NOTE]
> La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Flujo de datos de Project Service Automation a Finance and Operations

La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations. La plantilla de integración disponible con la función de integración de datos habilita el flujo de datos sobre las tareas de proyecto desde Project Service Automation a Finance and Operations.

La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.

[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Plantilla y tarea

Para obtener acceso a la plantilla, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.

La plantilla y la tarea subyacente siguientes se usan para sincronizar las tareas del proyecto desde Project Service Automation hasta Finance and Operations:

-**Nombre de la plantilla en la integración de datos:** Tareas del proyecto (de PSA a Fin and Ops) -**Nombre de la tarea en el proyecto:** Tareas del proyecto

Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.

## <a name="entity-set"></a>Conjunto de entidades

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Tareas de proyecto                           | Entidad de integración para tarea de proyecto.   |

## <a name="entity-flow"></a>Flujo de la entidad

Las tareas de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como actividades de proyectos.

## <a name="prerequisites-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.

## <a name="power-query"></a>Power Query

Debe usar Microsoft Power Query para filtrar los datos si se cumplen estas condiciones:

- Tiene registros específicos de recursos dentro de una tarea de proyecto.

Si debe usar Power Query, siga estas instrucciones:

- La plantilla de las tareas de proyecto (PSA a Fin and Ops) tiene un filtro predeterminado para excluir registros específicos de recursos de dentro de una tarea de proyecto estableciendo el filtro de **IsLineTask** en **Falso**. Si crea su propia plantilla, debe agregar este filtro.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

La siguiente ilustración muestra un ejemplo de las asignaciones de tarea de plantilla en integración de datos. La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.

[![Asignación de la plantilla](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


