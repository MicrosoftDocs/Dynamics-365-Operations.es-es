---
title: Visión general de la optimización de la planificación
description: Este tema proporciona una visión general de la funcionalidad de la optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: f5b51047dbfc95406ebcdda2255b58e41044a6a6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992629"
---
# <a name="planning-optimization-overview"></a>Visión general de la optimización de la planificación

[!include [banner](../../includes/banner.md)]

El complemento de la optimización de la planificación para Microsoft Dynamics 365 Supply Chain Management permite que el cálculo de la planificación maestra se produzca fuera de Dynamics 365 Supply Chain Management y de la base de datos SQL relacionada. Los beneficios que están asociados con la funcionalidad de optimización de la planificación incluyen un rendimiento mejorado y un impacto mínimo en la base de datos SQL durante las ejecuciones de la planificación maestra. Las ejecuciones rápidas de la planificación se pueden realizar incluso durante las horas de oficina, de modo que los planificadores puedan inmediatamente reaccionar a los cambios de la demanda o configuración de parámetros.

Para usar la optimización de la planificación, debe instalar el complemento de optimización de la planificación de su proyecto en Microsoft Dynamics Lifecycle Services (LCS) y activar la funcionalidad de optimización de la planificación en Supply Chain Management. Para obtener más información, consulte [Empezar a utilizar la optimización de la planificación](get-started.md).

La ilustración siguiente muestra la ventaja de ejecutar el ajuste de optimización de la planificación durante las horas de oficina.

![Ventaja de ejecutar el ajuste de optimización de la planificación durante las horas de oficina](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>rendimiento mejorado

La optimización de la planificación se puede usar en situaciones que implican planes maestros de larga ejecución. Se diseña específicamente para los cálculos muy rápidos que implican volúmenes de datos muy grandes. Dado que se ha creado como servicio para varios inquilinos con alta capacidad de escalabilidad, varias instancias pueden trabajar conjuntamente de forma simultánea para calcular el plan. Además, el servicio de planificación quita la carga de la planificación maestra del sistema y trabaja con una secuencia de datos que minimiza la carga del servidor.

La optimización de la planificación le puede servir de ayuda para lograr los objetivos siguientes:

- Mejorar el rendimiento de la planificación con un tiempo de ejecución más corto.
- Reducir el impacto en otros procesos durante la ejecución de la planificación maestra.
- Hacer ejecución de planificación más frecuentes. (No está limitado a ejecuciones durante el día).
- Esté seguro de que el crecimiento futuro del negocio no sobrecargará el sistema de planificación.

## <a name="architecture-and-data-flow"></a>Arquitectura y flujo de datos

Cuando el complemento de optimización de la planificación está instalado desde LCS, se establece una conexión segura al servicio de optimización de la planificación. El servicio se encuentra en el mismo país o región del centro de datos que la instancia relacionada de Supply Chain Management. Después de configurar la optimización de la planificación, cuando se ejecuta la planificación maestra, los datos maestros y los datos transaccionales se envían desde Supply Chain Management al servicio de optimización de la planificación.

Si se desinstala el complemento de optimización de la planificación, todos los datos relacionados en el servicio de optimización de la planificación se eliminan.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Flujo de datos de alto nivel para ejecuciones de regeneración

1. El cliente de Supply Chain Management registra una señal para solicitar una ejecución de la planificación desde la optimización de la planificación.
2. La optimización de la planificación solicita los datos necesarios mediante el conector integrado.
3. La base de datos SQL envía la información solicitada sobre la configuración, la planificación maestra y los datos transaccionales para la optimización de la planificación a través del conector. El conector traduce la información entre Supply Chain Management y el servicio de optimización de la planificación.
4. El servicio de optimización de la planificación contiene datos relacionados con la planificación en la memoria y realiza los cálculos necesarios.
5. El resultado de la planificación se envía a la base de datos de Supply Chain Management a través del conector. Los resultados incluyen información como pedidos planificados e información de diagrama de árbol. La optimización de la planificación envía una señal a Supply Chain Management para indicar que la ejecución de la planificación se ha completado. También envía mensajes y advertencias relevantes.

La ilustración siguientes muestran el flujo de datos.

![Flujo de datos para ejecuciones de regeneración](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Recursos relacionados

[Introducción a la optimización de planificación](get-started.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)
