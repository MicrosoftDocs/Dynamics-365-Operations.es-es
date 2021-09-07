---
title: Procesar cambios de tipo
description: En este tema se explica cómo procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa94584749e72cab7aa3466814ed8ea9d59665da
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417516"
---
# <a name="process-rate-changes"></a>Procesar cambios de tipo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se explica cómo procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad. Si se crea una nueva regla de idoneidad y se asigna al plan, esto lleva al sistema a volver a ejecutar la idoneidad de los trabajadores para verificar si los trabajadores ahora son idóneos para el plan en función de las nuevas opciones de idoneidad. 

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de actualización de tasas de cambios**.

2. En el cuadro de diálogo **Ejecutar proceso de actualización de tasas de cambios**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Período de inscripción** | El periodo de inscripción para procesar tasas de cambios. |

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
