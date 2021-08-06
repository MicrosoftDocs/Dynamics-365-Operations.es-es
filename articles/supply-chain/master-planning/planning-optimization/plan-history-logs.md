---
title: Ver el historial del plan y los registros de planificación
description: Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 93e8f933524b34116987c9e0d91d226e21d98f4d
ms.sourcegitcommit: 5c9a5bfef507ed36f0f849ab56fa0aa8abb78d54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2021
ms.locfileid: "6646496"
---
# <a name="view-plan-history-and-planning-logs"></a>Ver el historial del plan y los registros de planificación

[!include [banner](../../includes/banner.md)]

Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación en Microsoft Dynamics 365 Supply Chain Management.

Para ver el historial de un plan, abra el plan; para ello, vaya a **Planificación maestra** \> **Configuración** \> **Planes** \> **Planes maestros** y seleccionando **Historial**. El historial contiene todos los trabajos para el plan seleccionado. La lista incluye los trabajos completados y trabajos.

El historial de trabajos para las ejecuciones de planificación maestra de Planning Optimization mantiene solo hasta 60 registros por plan maestro. Siempre que ejecuta un nuevo cálculo de planificación maestra, se elimina el registro histórico más antiguo de ese plan.

Además de ver la hora de inicio y el estado de los trabajos, puede ver el registro para un trabajo específico. El registro incluye información adicional y advertencias. No todos los trabajos tienen un registro. Para ver el registro de un trabajo, seleccione **Registro**. Las entradas del registro solo se almacenan durante 30 días después de la fecha en que finalizó el trabajo, después de eso se eliminan automáticamente.

Si la opción **Procesamiento por lotes** en la ficha desplegable **Ejecutar en segundo plano** se habilitó cuando se configuró el procesamiento de planificación maestra, el registro de trabajo por lotes muestra más información sobre las advertencias y errores que se generaron durante la ejecución de la planificación maestra. Por ejemplo, los errores de autoafirmación se capturan solo en el registro de trabajos por lotes. No se muestran en registros en la página **Historial**.

Para ver los errores de autoafirmación y otras advertencias o errores que ocurrieron durante una ejecución de planificación maestra, siga estos pasos.

1. Vaya **Administración del sistema \> Consultas \> Trabajos por lotes**.
1. Busque y seleccione el registro que representa la ejecución de planificación maestra que le interesa. (Por ejemplo, el valor del campo **Descripción del trabajo** podría comenzar con *Planificación maestra* .)
1. Siga uno de estos pasos, dependiendo de si está utilizando el *formulario mejorado* o el *formulario heredado (no mejorado)* para la página **Trabajos por lotes**:

    - Si está utilizando el formulario mejorado: en el Panel de acciones, seleccione **Historial de trabajos por lotes**. A continuación, en la página **Historial de trabajos por lotes**, en el Panel de acciones, seleccione **Registro**.
    - Si está utilizando el formulario heredado: en el Panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Registro**.

1. Seleccione **Detalles del mensaje** para abrir el panel **Detalles del mensaje**, donde puede ver todas las advertencias y errores que se capturaron durante el procesamiento.

## <a name="related-resources"></a>Recursos relacionados

- [Información general de la optimización de la planificación](planning-optimization-overview.md)
- [Introducción a la optimización de la planificación](get-started.md)
- [Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)
- [Aplicar filtros a un plan](plan-filters.md)
- [Cancelar un trabajo de planificación](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
