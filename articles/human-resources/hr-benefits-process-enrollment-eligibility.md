---
title: Proceso de idoneidad para inscripción
description: Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0344c48460a7d1540481e09ba106526e119de72b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010413"
---
# <a name="process-enrollment-eligibility"></a>Proceso de idoneidad para inscripción

[!include [banner](includes/preview-feature.md)]

Este artículo explica cómo ejecutar el proceso de idoneidad de inscripción.

1. En el espacio de trabajo **Administración de prestaciones**, en **Procesamiento**, seleccione **Procesamiento de idoneidad para inscripción**.

2. En el cuadro de diálogo **Ejecutar proceso de idoneidad para la inscripción en prestaciones**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | Período de inscripción | El periodo de inscripción para procesar la idoneidad de inscripción. |
   | Entidad jurídica | La entidad jurídica para procesar la idoneidad de inscripción. |
   | Trabajador | El trabajador para procesar la idoneidad de inscripción. Si deja este campo en blanco, la idoneidad de inscripción se procesará para todos los trabajadores. |
   | Plan de prestaciones | El plan de prestaciones para procesar la idoneidad de inscripción.

3. Si desea ejecutar el proceso en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para proceso.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso se ejecutará con los parámetros que establezca.

4. Seleccione **Aceptar**.
