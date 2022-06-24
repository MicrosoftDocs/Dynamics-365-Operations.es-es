---
title: Ver el historial del plan y los registros de planificación
description: Este artículo explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación.
author: t-benebo
ms.date: 06/01/2020
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
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b2c9257fc67a06b57418b2f5b035b2b540131405
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863951"
---
# <a name="view-plan-history-and-planning-logs"></a>Ver el historial del plan y los registros de planificación

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación en Microsoft Dynamics 365 Supply Chain Management.

Para ver el historial de un plan, abra el plan; para ello, vaya a **Planificación maestra** \> **Configuración** \> **Planes** \> **Planes maestros** y seleccionando **Historial**. El historial contiene todos los trabajos para el plan seleccionado. La lista incluye los trabajos completados y trabajos.

El sistema mantiene un máximo de 60 registros de historial por plan maestro y elimina los registros que tienen más de 30 días. Cada vez que ejecuta un nuevo cálculo de la planificación maestra, el sistema agrega un nuevo registro de historial y luego limpia los registros más antiguos según sea necesario.

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
