---
title: Restablecer trabajos por lotes bloqueados
description: Este tema explica cómo resolver problemas con trabajos por lotes que están atascados.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d0b12908993070a41d21ac57d6fb504fc6e3b06a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053524"
---
# <a name="reset-stuck-batch-jobs"></a>Restablecer trabajos por lotes bloqueados

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Emitir

Microsoft Dynamics 365 Human Resources puede experimentar problemas con los trabajos por lotes que se atascan en estado **Ejecución** o **Cancelación** y no se completan.

## <a name="resolution"></a>Resolución

Cuando un trabajo por lotes se atasca en un estado **Ejecución** o **Cancelación**, puede restablecer el estado forzando la cancelación del trabajo. Después de cancelarlo, puede restablecer el trabajo por lotes configurándolo en un estado **Esperando**. A continuación, se volverá a recoger para su ejecución en la siguiente ejecución por lotes programada.

1. En el espacio de trabajo **Administracion del sistema**, seleccione la página **Vínculos** y elija **Trabajos por lotes**.

2. En la página de lista **Trabajo por lotes**, seleccione el trabajo que necesita restablecerse.

3. En la cinta de acciones, seleccione **Forzar cancelación** y confirme la acción.

   > [!NOTE]
   > La acción **Forzar cancelación** solo está disponible cuando el trabajo por lotes seleccionado tiene un estado de **Ejecutando** o **Cancelando** y no se están ejecutando procesos de cancelación o ejecución por lotes para el trabajo.

4. En la cinta de acciones, seleccione **Cambiar estado**.

5. En la página **Seleccionar nuevo estado**, seleccione **Esperando** y luego seleccione **Aceptar**.

   ![Seleccionar un nuevo estado de trabajo por lotes](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Consulte también

[Optimizar el rendimiento programando trabajos por lotes fuera del horario laboral](hr-admin-troubleshooting-batch-jobs.md)<br>
[Optimizar el rendimiento con tareas automáticas de limpieza](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
