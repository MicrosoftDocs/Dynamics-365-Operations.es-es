---
title: Optimizar el rendimiento con tareas automáticas de limpieza
description: Este artículo explica cómo resolver algunos problemas de rendimiento con Microsoft Dynamics 365 Human Resources limpiando el historial de trabajos por lotes.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 6a9e94e282aa8f101b42c1378ef21c6c1fe0477e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053500"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimizar el rendimiento con tareas automáticas de limpieza

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emisión**

Microsoft Dynamics 365 Human Resources pueden experimentar problemas de rendimiento si el historial de trabajos por lotes crece demasiado.

**Causa**

Los trabajos por lotes que se ejecutan con frecuencia pueden llevar al crecimiento insostenible del historial de trabajos por lotes. Esto puede provocar problemas de rendimiento. 

**Resolución**

Programe una tarea automática para limpiar el historial de trabajos por lotes. Se recomienda configurar la tarea para ejecutarse semanalmente, pero puede querer ejecutar la limpieza con más o menos frecuencia dependiendo de su entorno. El procedimiento siguiente contiene nuestros valores recomendados, pero puede cambiar estos según sus necesidades.

1. En Human Resources, seleccione **Administración del sistema**.

2. En la barra **Buscar**, especifique **Limpieza del historial de trabajos por lotes**.

   ![Busque limpieza de historial de trabajos por lotes](media/talent-batch-history-cleanup-search-bar.png)

3. En el **Límite de historial (días)**, especifique **30**.

   ![Establezca el límite del historial en 30](media/talent-batch-history-cleanup-history-limit.png)

4. Seleccione **Funcionamiento en segundo plano** y después seleccione **Periodicidad**.

   ![Establezca la periodicidad](media/talent-batch-history-cleanup-recurrence.png)

5. En **Definir frecuencia**, establezca la **Fecha inicial** y **Hora de inicio** para producir durante los fines de semana o fuera del horario de oficina y después seleccione **SIN FECHA DE FINALIZACIÓN**. 

   ![Defina la fecha y hora de la periodicidad](media/talent-batch-history-cleanup-define-recurrence.png)

6. En **PATRÓN DE PERIODICIDAD**, seleccione **Días** y establezca **REPETICIÓN DESPUÉS DEL INTERVALO ESPECIFICADO** **7**.

   ![Establezca la limpieza para repetirse semanalmente](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Seleccione **Aceptar**.

8. Modifique cualquier otro parámetro en **Funcionamiento en segundo plano** según sea necesario y, a continuación seleccione **Aceptar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]