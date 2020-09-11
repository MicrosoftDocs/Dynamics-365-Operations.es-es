---
title: Procesar tasas de cambios
description: Procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: da42ef6ea91b95903316e35b551b222b8ff3b946
ms.sourcegitcommit: 9723b5ff40c84677316d71e185cf862556b32cf9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2020
ms.locfileid: "3741468"
---
# <a name="process-rate-changes"></a>Procesar tasas de cambios

Procesar cambios en la tasa de prestaciones en Microsoft Dynamics 365 Human Resources cuando un plan de prestaciones nuevo o existente tiene un cambio en la configuración de las reglas de idoneidad. Si se crea una nueva regla de idoneidad y se asigna al plan, esto lleva al sistema a volver a ejecutar la idoneidad de los trabajadores para verificar si los trabajadores ahora son idóneos para el plan en función de las nuevas opciones de idoneidad. 

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
