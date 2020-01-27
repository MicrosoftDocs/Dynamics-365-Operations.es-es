---
title: Optimizar el rendimiento con tareas automáticas de limpieza
description: Este tema explica cómo resolver algunos problemas de rendimiento con Microsoft Dynamics 365 Talent limpiando el historial de trabajos por lotes.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: fe536ace5c25765bd9c573f9303bd92f834765f7
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897981"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimizar el rendimiento con tareas automáticas de limpieza

**Emisión**

Microsoft Dynamics 365 Talent pueden experimentar problemas de rendimiento si el historial de trabajos por lotes crece demasiado.

**Causa**

Los trabajos por lotes que se ejecutan con frecuencia pueden llevar al crecimiento insostenible del historial de trabajos por lotes. Esto puede provocar problemas de rendimiento. 

**Resolución**

Programe una tarea automática para limpiar el historial de trabajos por lotes. Se recomienda configurar la tarea para ejecutarse semanalmente, pero puede querer ejecutar la limpieza con más o menos frecuencia dependiendo de su entorno. El procedimiento siguiente contiene nuestros valores recomendados, pero puede cambiar estos según sus necesidades.

1. En Talent, seleccione **Administración del sistema**.

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

