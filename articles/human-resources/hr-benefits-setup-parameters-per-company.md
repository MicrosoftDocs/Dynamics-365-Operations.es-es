---
title: Configurar parámetros de Administración de prestaciones por empresa
description: Configure los parámetros para la Administración de prestaciones por empresa en Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c0f9f31006ca83082ddc61da5927841855077737289e31f66708ade6d66acaf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732810"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurar parámetros de Administración de prestaciones por empresa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Para cada organización que ofrece prestaciones, debe definir la configuración para los correos electrónicos de confirmación de prestaciones.

## <a name="configure-confirmation-email-settings"></a>Configurar opciones de correo electrónico de confirmación

1. En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.

2. En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos: 

   | Campo | Descripción |
   | --- | --- |
   | **Enviar un correo de confirmación** | Cuando esta característica está activada, se enviará un correo electrónico de confirmación a los empleados cuando comprueben de la experiencia de inscripción de prestaciones en Autoservicio para empleados. |
   | **Plantilla de correo de confirmación** | Seleccione la plantilla de correo electrónico de la organización que se usará al enviar la confirmación de inscripción. Si no selecciona una plantilla, se enviará el siguiente correo electrónico genérico:<br><br>%EmployeeFirstName%,<br><br>¡Enhorabuena! Ha completado correctamente la inscripción a las prestaciones.<br><br>Gracias,<br>Prestaciones de <Company/Org name>. |
   | **Dirección predeterminada de correo del remitente** | La dirección de correo electrónico que se usará al enviar el correo electrónico de confirmación. |

3. Seleccione **Guardar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]