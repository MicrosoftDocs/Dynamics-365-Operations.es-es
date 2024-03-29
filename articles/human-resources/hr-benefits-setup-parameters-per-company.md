---
title: Configurar parámetros de administración de prestaciones por empresa
description: En este artículo se describe cómo configurar los parámetros para la administración de prestaciones por empresa en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 8/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f3f8625a8ebbe6812d2f051649ff2a608ed4b54
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323910"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurar parámetros de Administración de prestaciones por empresa


Para cada organización que ofrece prestaciones, debe definir la configuración para los correos electrónicos de confirmación de prestaciones.

## <a name="configure-confirmation-email-settings"></a>Configurar opciones de correo electrónico de confirmación

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.

2. En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos: 

   | Campo | Descripción |
   | --- | --- |
   | **Enviar un correo de confirmación** | Cuando esta función está activada, se enviará un correo electrónico de confirmación a los empleados cuando salgan de la experiencia de inscripción de prestaciones en **Autoservicio para empleados**. |
   | **Plantilla de correo de confirmación** | Seleccione la plantilla de correo electrónico de la organización que se usará al enviar la confirmación de inscripción. Si no selecciona una plantilla, se enviará el siguiente correo electrónico genérico:<br><br>%EmployeeFirstName%,<br><br>¡Enhorabuena! Ha completado correctamente la inscripción a las prestaciones.<br><br>Gracias,<br>Prestaciones de <Company/Org name>. |
   | **Dirección predeterminada de correo del remitente** | La dirección de correo electrónico que se usará al enviar el correo electrónico de confirmación. |

3. Seleccione **Guardar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
