---
title: Configurar eventos de vida futuros
description: En este tema se describe cómo programar eventos de vida futuros en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 441ccc478f78f76b80ac9138dc62592634f005bd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693210"
---
# <a name="configure-future-life-events"></a>Configurar eventos de vida futuros

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede programar eventos de vida futuros en Dynamics 365 Human Resources.

1. En el espacio de trabajo de **Administración de prestaciones**, en **Configuración**, seleccione **Eventos de vida futuros**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | Fecha de evento de vida | El sistema procesa todos los eventos durante el periodo de inscripción que ocurren hasta esta fecha. |
   | Evento de vida registrado | Se registra la fecha y la hora del evento de vida. |
   | Tipo de registro | Muestra si la acción es una de las siguientes:</br></br>- **Actualizar**: un cambio en un registro existente que sigue eventos de vida</br></br>- **Insertar**: la creación de un nuevo registro de eventos de vida |
   | Identificador del tipo de evento de vida | El identificador único del tipo de evento de vida. |
   | Tipo de evento de vida | Un catalizador para actualizar la inscripción de prestaciones de un empleado. Para obtener más detalles, consulte la sección de activadores de eventos de vida. |
   | Estado | Si se ha procesado el evento de vida o no. |
   | Línea | El número de línea del evento de vida futuro. |

4. Seleccione **Guardar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
