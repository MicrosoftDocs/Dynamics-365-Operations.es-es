---
title: Configurar eventos de vida futuros
description: En este artículo se describe cómo programar eventos de vida futuros en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227997"
---
# <a name="configure-future-life-events"></a>Configurar eventos de vida futuros

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

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
   | Tipo de evento de vida | Un catalizador para actualizar la inscripción de prestaciones de un empleado. Para obtener más información, consulte la sección de activadores de eventos de vida. |
   | Status | Si se ha procesado el evento de vida o no. |
   | Línea | El número de línea del evento de vida futuro. |

4. Seleccione **Guardar**. 

Puede eliminar eventos de vida futuros. Si se elimina un evento de vida futuro procesado, también se elimina el registro futuro. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
