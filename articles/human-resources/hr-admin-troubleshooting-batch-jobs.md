---
title: Optimice el rendimiento programando trabajos por lotes tras el horario laboral
description: Este tema explica cómo resolver problemas de rendimiento con Microsoft Dynamics 365 Human Resources programando trabajos por lotes de larga duración tras el horario laboral.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a5aeaeb7311d87a154882b7058b6da430900bd56
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053476"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optimice el rendimiento programando trabajos por lotes tras el horario laboral

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Emitir

Microsoft Dynamics 365 Human Resources puede experimentar problemas de rendimiento si los trabajos por lotes de larga duración se ejecutan durante el horario comercial habitual.

## <a name="resolution"></a>Resolución

Programe los siguientes trabajos por lotes fuera del horario laboral. También recomendamos revisar la frecuencia de los trabajos por lotes que se ejecutan con frecuencia. Si es posible, reduzca la recurrencia del trabajo por lotes. En muchos casos, la frecuencia predeterminada es suficiente.

Los siguientes trabajos por lotes deben ejecutarse por la noche o tras las horas laborales. Asegúrese de verificar la zona horaria para estos trabajos por lotes recurrentes. Algunos trabajos por lotes pueden usar la hora estándar del Pacífico (PST).

| Trabajo por lotes | Ocurrencia predeterminada |
| --- | --- |
| Limpieza del historial de trabajos por lotes | 1 vez al mes |
| Limpieza de ubicación provisional de exportación | 1 vez al día |
| Sincronización de solicitud omitida de integración Common Data Service | 1 vez al día |
| Trabajo del sistema de compresión de base de datos que necesita ejecutarse regularmente fuera del horario laboral | 1 vez al día |
| Trabajo del sistema de reconstrucción del índice de base de datos que necesita ejecutarse regularmente fuera del horario laboral | 1 vez al día |

1. En Human Resources, seleccione **Administración del sistema**.

2. En la barra **Buscar**, busque uno de los trabajos por lotes anteriores.

3. Seleccione **Funcionamiento en segundo plano** y después **Periodicidad**.

   ![Establezca la periodicidad](media/talent-batch-history-cleanup-recurrence.png)

4. En **Definir periodicidad**, establezca la **Fecha inicial** y **Hora de inicio** para tener lugar durante los fines de semana o fuera del horario laboral. Seleccionar **Sin fecha final**. 

   ![Defina la fecha y hora de la periodicidad](media/talent-batch-history-cleanup-define-recurrence.png)

5. Seleccione **Aceptar**.

6. Si hace falta, cambie cualquier otro parámetro en **Funcionamiento en segundo plano** y, a continuación seleccione **Aceptar**.

## <a name="additional-resources"></a>Recursos adicionales

[Optimizar el rendimiento con tareas automáticas de limpieza](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]