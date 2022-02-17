---
title: Configurar autoservicio para empleados
description: En Microsoft Dynamics 365 Human Resources, puede configurar iconos para la navegación de nivel superior en autoservicio para empleados.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 83718856a864123d7941b21c078bcdb96a62cca8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067588"
---
# <a name="configure-employee-self-service"></a>Configurar autoservicio para empleados


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En Microsoft Dynamics 365 Human Resources, puede configurar iconos para la navegación de nivel superior en **Autoservicio para empleados**. El icono del plan de prestaciones dirige a los usuarios a los planes de prestaciones a los que pueden optar.

## <a name="set-up-a-benefit-plans-tile"></a>Configurar un icono de planes de prestaciones

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de autoservicio para empleados**.

2. Seleccione la pestaña **Configuración del icono de planes de prestaciones** y luego seleccione **Nuevo**.

3. Especifique valores para los campos siguientes.

   | Campo | Description |
   | --- | --- |
   | **Código de tipo de plan** | El tipo de plan que se muestra cuando se selecciona este icono en **Autoservicio de prestaciones**. |
   | **Id. de icono** | El identificador único del icono. |
   | **Texto de etiqueta de icono** | El texto que aparecerá para el icono en **Autoservicio de prestaciones**. |
   | **Descripción** | Una descripción del icono. |
   | **Imagen de fondo de icono** | La URL de la imagen a usar para el icono (opcional). |
   | **Seguimiento de inscripción abierta** | Seleccione esta opción para realizar un seguimiento del progreso de la inscripción abierta para este tipo de plan. Por ejemplo, puede haber creado planes donde **Plan type = Other**. Estos planes pueden ser planes opcionales para los que no desea realizar un seguimiento del progreso de la inscripción. Si no selecciona este tipo de plan, este tipo de plan se ignorará al realizar un seguimiento del progreso o finalización de la inscripción en la pestaña **Inscripción abierta**. Esta configuración se aplica al tipo de plan que se selecciona para todos los períodos y entidades legales. |

4. Seleccione **Guardar**.

## <a name="set-up-a-flex-credit-plan-tile"></a>Configurar un icono de plan de crédito flexible

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de autoservicio para empleados**.

2. Seleccione la pestaña **Configuración del icono de plan de crédito flexible** y luego seleccione **Nuevo**.

3. Especifique valores para los campos siguientes.

   | Campo | Description |
   | --- | --- |
   | **Id. de crédito de prestación** | Los planes de programa de crédito flexible que se mostrarán cuando se seleccione este icono en **Autoservicio de prestaciones**. |
   | **Id. de icono** | El identificador único del icono. |
   | **Texto de etiqueta de icono** | El texto que aparecerá para el icono en **Autoservicio de prestaciones**. |
   | **Descripción** | Una descripción del icono. |
   | **Imagen de fondo de icono** | La URL de la imagen a usar para el icono (opcional). |
   | **Seguimiento de inscripción abierta** | Seleccione esta opción para realizar un seguimiento del progreso de la inscripción abierta para este tipo de plan. Por ejemplo, puede haber creado planes donde **Plan type = Other**. Estos planes pueden ser planes opcionales para los que no desea realizar un seguimiento del progreso de la inscripción. Si no selecciona este tipo de plan, este tipo de plan se ignorará al realizar un seguimiento del progreso o finalización de la inscripción en la pestaña **Inscripción abierta**. Esta configuración se aplica al tipo de plan que se selecciona para todos los períodos y entidades legales. |

4. Seleccione **Guardar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
