---
title: Reabastecimiento con kanbans de transporte | Microsoft Docs
description: "Este tema describe cómo el kanban de transporte se usa para el reabastecimiento para las actividades de fabricación."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: abac5e05f40132844cf1817be533151cbf238d95
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="replenishment-with-withdrawal-kanbans"></a>Reabastecimiento con kanbans de transporte

[!include[banner](../includes/banner.md)]


Este tema describe cómo el kanban de transporte se usa para el reabastecimiento para las actividades de fabricación.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>El flujo de trabajo para reabastecimiento de material que utiliza el kanban de transporte
-------------------------------------------------------------------

El kanban de transporte se puede utilizar para mover un kanban de un único artículo entre los almacenes y las ubicaciones de producción donde se consume el material. El kanban de transporte admite una solución basada en extracción para el reabastecimiento de material, donde se requiere una señal de extracción para activar un suministro para una demanda específica. 

La situación siguiente muestra el sistema de reabastecimiento basado en extracción donde una señal de extracción activa la creación de un kanban para reabastecer material para un proceso de producción. 

[![La señal de extracción activa la creación de un kanban para reabastecer material para un proceso de producción](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Kanban de transporte
2.  Ubicación "desde" kanban y ubicación de colocación para trabajo de almacén
3.  Ubicación "a" kanban y ubicación de entrada de producción
4.  Proceso de fabricación
5.  Trabajo del almacén para el picking de kanban
6.  Ubicaciones de almacén para la materia prima
7.  Almacén de material
8.  Almacén de fabricación

En esta situación, un proceso de fabricación (4) consume material de una ubicación de entrada de producción (3) en el almacén de la fabricación (8). Cuando una unidad de gestión de material (kanban) se consume, se registra como vacía. Una señal de reabastecimiento se crea para el origen del artículo y se crea un nuevo kanban (1). En este caso, origen del artículo consta de ubicaciones en el almacén de material (7). El material de kanban se selecciona y se coloca en una ubicación (2) en el mismo el almacén. Cuando se selecciona el material, está listo para su transferencia de la ubicación 2 a la ubicación de entrada de producción (3) en el almacén de fabricación (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Configurar del trabajo del almacén para el picking de kanban para el kanban de transporte

Para habilitar la selección de la materia prima para el kanban de transporte, configure las plantillas de oleada, las plantillas de trabajo y las directivas de ubicación para el tipo de pedido de trabajo **Picking de kanban** . Este tipo de pedido de trabajo no admite solo el proceso de picking para el kanban de transporte. También admite el proceso de picking para el kanban de fabricación. Sin embargo, puede configurar un proceso independiente de selección para cada tipo de kanban separando las plantillas de oleada, las plantillas de trabajo y las directivas de la ubicación. Para separar las plantillas de oleada, las plantillas de trabajo y las directivas de ubicación, establezca criterios en el tipo de actividad (**Proceso** o **Transferencia**) en las consultas de esas entidades.

## <a name="configure-the-withdrawal-kanban"></a>Configurar el kanban de transporte

La actividad de transferencia que se usa para el kanban de transporte se configura como parte de un plan de actividades activado en un flujo de producción Lean (producción ajustada). Como parte de la configuración de la actividad de transferencia, especifique las ubicaciones "desde" y "hasta" para la transferencia. Después de configurar la actividad de transferencia, puede asignarla a una regla kanban del tipo **Transporte**. La regla kanban establece las directivas y las configuraciones para el kanban de transporte. La cantidad de kanban define cuántas unidades de la unidad de manipulación tiene el kanban durante el proceso de transferencia. Se usa la cantidad de kanban fija cuando está selecciona la estrategia de reabastecimiento fija. Esta cantidad define cuántos kanbans son necesarios para impedir que las existencias o el inventario de la generación se ejecuten en el origen de la demanda. La cantidad fija se puede calcular en función de la demanda real, la demanda histórica y los niveles de servicio. Las dos casos siguientes describen cómo puede gestionar el reabastecimiento de material que utiliza el kanban de transporte.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Situación 1: Completar una ubicación de entrada de producción mediante un kanban de transporte fijo

Un proceso de fabricación consume materia prima comprada en una ubicación de entrada de producción que está en el almacén e producción. Cuando la materia prima se recibe del proveedor se almacena en ubicaciones en el almacén material. Dado que la demanda de materiales se considera estable durante un período, se configuran para suministrar la producción en un flujo de kanban de cantidad fija. Cuando un kanban se consume en la ubicación de entrada de producción, se registra una señal vacía y se crea un nuevo kanban del mismo tipo que se agrega al flujo de trabajo. 

La señal vacía se puede configurar para que se muestre automáticamente cuando un kanban se completa. O bien, la señal vacía se puede configurar como interacción manual que se proporciona desde el tablero de transferencia de kanban o desde un menú en el dispositivo de mano. El tablero de kanban de transferencia es el espacio de trabajo en la que todas las actividades en el ciclo de vida del kanban se gestionan. 

Cuando se crea el kanban, una línea de oleada para la materia prima se agrega a una oleada de kanban para el almacén de material. En la sección de la lista de selección del tablero de transferencia de kanban, el estado del material y los procesos relacionados con el almacén se pueden controlar desde la creación de la oleada hasta la creación de trabajo, hasta que el material esté disponible en la ubicación de “transferencia desde” y esté listo para transferirse a la entrada de producción. El kanban se puede completar desde el tablero de transferencia de kanban o desde un menú del dispositivo de mano. 

En esta situación, el trabajo de selección en el almacén de material se procesa como una actividad. La actividad de transferencia entre el almacén de material y el almacén de producción se procesa como actividad independiente. Este enfoque puede ser útil si, por ejemplo, hay una distancia física grande entre los dos almacenes. En este caso, la actividad de transferencia de kanban puede representar una carga del camión. 

Si la distancia entre las ubicaciones del almacén y la ubicación de entrada de producción es pequeña, es posible que sea más eficaz incluir la actividad de transferencia en el proceso de picking. A continuación, después de seleccionar el material, se puede poner directamente en la ubicación de entrada de producción. Para admitir este proceso, configure la actividad de transferencia para que se complete automáticamente cuando el trabajo de selección del kanban de transporte se procese.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Situación 2: Automáticamente complete la actividad de transferencia cuando se procesa el trabajo del picking de kanban

En el escenario siguiente, la actividad de transferencia de kanban de transporte se configura para transferir entre dos ubicaciones del mismo almacén. La actividad de la transferencia de kanban de transporte se establece para que se complete automáticamente. 

[![La actividad de la transferencia se completa automáticamente cuando se procesa el trabajo de picking](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Almacén compartido para materias primas y producción
2.  Ubicaciones de almacén para materias primas
3.  Ubicación "desde" kanban y ubicación de colocación para trabajo de almacén
4.  Kanban de transporte
5.  Ubicación de entrada de producción
6.  Proceso de fabricación

Después de consumir un kanban en la ubicación de entrada de producción, el kanban se notifica como vacío y se agrega un nuevo kanban al flujo. Cuando se crea el kanban, una línea de oleada se agrega a una oleada de kanban. Cuando se procesa la oleada de kanban, el trabajo del almacén para el picking de kanban se crea. El trabajador del almacén procesa el trabajo para el picking de kanban y el trabajo lo guía para que seleccione el material del kanban en una ubicación de almacén. Cuando este trabajador del almacén confirma la selección, el kanban se completa automáticamente y el trabajador del almacén es guiado para que coloque el material en la ubicación de entrada de producción.


