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
ms.openlocfilehash: d2c564f0dfd1cbe44566269c97218450fedf2173
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057631"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="f7be5-103">Configurar parámetros de Administración de prestaciones por empresa</span><span class="sxs-lookup"><span data-stu-id="f7be5-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f7be5-104">Para cada organización que ofrece prestaciones, debe definir la configuración para los correos electrónicos de confirmación de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7be5-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="f7be5-105">Configurar opciones de correo electrónico de confirmación</span><span class="sxs-lookup"><span data-stu-id="f7be5-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="f7be5-106">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="f7be5-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="f7be5-107">En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f7be5-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="f7be5-108">Campo</span><span class="sxs-lookup"><span data-stu-id="f7be5-108">Field</span></span> | <span data-ttu-id="f7be5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7be5-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f7be5-110">**Enviar un correo de confirmación**</span><span class="sxs-lookup"><span data-stu-id="f7be5-110">**Send confirmation email**</span></span> | <span data-ttu-id="f7be5-111">Cuando esta característica está activada, se enviará un correo electrónico de confirmación a los empleados cuando comprueben de la experiencia de inscripción de prestaciones en Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="f7be5-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="f7be5-112">**Plantilla de correo de confirmación**</span><span class="sxs-lookup"><span data-stu-id="f7be5-112">**Confirmation email template**</span></span> | <span data-ttu-id="f7be5-113">Seleccione la plantilla de correo electrónico de la organización que se usará al enviar la confirmación de inscripción.</span><span class="sxs-lookup"><span data-stu-id="f7be5-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="f7be5-114">Si no selecciona una plantilla, se enviará el siguiente correo electrónico genérico:</span><span class="sxs-lookup"><span data-stu-id="f7be5-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="f7be5-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="f7be5-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="f7be5-116">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="f7be5-116">Congratulations!</span></span> <span data-ttu-id="f7be5-117">Ha completado correctamente la inscripción a las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="f7be5-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="f7be5-118">Gracias,</span><span class="sxs-lookup"><span data-stu-id="f7be5-118">Thank you,</span></span><br><span data-ttu-id="f7be5-119">Prestaciones de <Company/Org name>.</span><span class="sxs-lookup"><span data-stu-id="f7be5-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="f7be5-120">**Dirección predeterminada de correo del remitente**</span><span class="sxs-lookup"><span data-stu-id="f7be5-120">**Default email sender address**</span></span> | <span data-ttu-id="f7be5-121">La dirección de correo electrónico que se usará al enviar el correo electrónico de confirmación.</span><span class="sxs-lookup"><span data-stu-id="f7be5-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="f7be5-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f7be5-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]