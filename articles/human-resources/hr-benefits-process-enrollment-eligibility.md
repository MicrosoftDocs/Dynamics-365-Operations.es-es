---
title: Proceso de idoneidad para inscripción
description: Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bd05585f691a4c6aa55a7aec7ceaaf0273f0abcb
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323525"
---
# <a name="process-enrollment-eligibility"></a>Proceso de idoneidad para inscripción

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de idoneidad para inscripción**.

2. En el cuadro de diálogo **Ejecutar proceso de idoneidad para la inscripción en prestaciones**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Período de inscripción** | El periodo de inscripción para procesar la idoneidad de inscripción. |
   | **Entidad jurídica** | La entidad jurídica para procesar la idoneidad de inscripción. |
   | **Trabajador** | El trabajador para procesar la idoneidad de inscripción. Si deja este campo en blanco, la idoneidad de inscripción se procesará para todos los trabajadores. |
   | **Plan de beneficios** | El plan de prestaciones para procesar la idoneidad de inscripción.

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.

## <a name="view-process-results"></a>Ver resultados de proceso

Este artículo explica cómo ver los resultados del proceso de idoneidad.

1.  En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesar resultados**.

2.  En la página **Procesar resultados**, se especifican los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Id. de proceso** | El Id. único para la combinación de trabajador, entidad jurídica y ejecución del proceso. |
   | **Tipo de proceso** | Esto identifica el proceso que se ejecutó. Por ejemplo: Inscripción. |
   | **Marca de tiempo** | La hora en que se ejecutó el proceso de elegibilidad. |
   | **Entidad jurídica** | La entidad legal especificada durante el proceso de inscripción. |
   | **Trabajador** | El trabajador que se procesó. |
   | **Plan | El plan de prestaciones para el que se intentó la inscripción. |
   | **Regla de idoneidad** | La regla de elegibilidad que se procesó. Si se encontró un error antes de ejecutar la elegibilidad, estará en blanco. Por ejemplo: si no se ha definido la compensación para un trabajador, el proceso de elegibilidad no se ejecutará y este campo se dejará en blanco. |
   | **Estado de resultado** | Esto será elegible o no elegible. El estado del resultado será No elegible si el trabajador no cumplió con los criterios de la regla de elegibilidad, si el trabajador no tiene la información requerida, como una frecuencia de pago o una compensación fija, o si falta información en el plan de prestaciones que impide que los trabajadores se inscriban. |
   | **Mensaje de resultado** | Indica por qué un trabajador no es elegible para un plan de prestaciones o si se aprobó la regla de elegibilidad. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
