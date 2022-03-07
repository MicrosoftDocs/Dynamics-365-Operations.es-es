---
title: Procesar cambios de eventos de vida
description: En este tema se explica cómo procesar cambios de eventos de vida en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb894d9886c095d760efe66abcf773a975a99caa
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067613"
---
# <a name="process-life-event-changes"></a>Procesar cambios de eventos de vida


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Procese cambios de eventos de vida en Microsoft Dynamics 365 Human Resources para dos cambios en los eventos de la vida:

- Cambios de fecha de nacimiento
- Cambios en la expiración de la anulación de la regla de idoneidad 

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de cambios de eventos de vida**.

2. En el cuadro de diálogo **Ejecutar proceso de cambio de evento de vida**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | Período de inscripción | El periodo de inscripción para procesar cambios de evento de vida. |
   | Entidad jurídica | La entidad jurídica para procesar cambios de evento de vida. |

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
