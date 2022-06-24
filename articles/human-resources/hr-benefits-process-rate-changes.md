---
title: Procesar cambios de tipo
description: En este artículo se explica cómo procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09714c70cb00b1a1b5dbd4613bbd70ff11d35cb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882964"
---
# <a name="process-rate-changes"></a>Procesar cambios de tipo


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este artículo se explica cómo procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad. Si se crea una nueva regla de idoneidad y se asigna al plan, esto lleva al sistema a volver a ejecutar la idoneidad de los trabajadores para verificar si los trabajadores ahora son idóneos para el plan en función de las nuevas opciones de idoneidad. 

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
