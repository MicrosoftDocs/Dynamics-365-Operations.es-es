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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805667"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="93452-103">Configurar parámetros de Administración de prestaciones por empresa</span><span class="sxs-lookup"><span data-stu-id="93452-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="93452-104">Para cada organización que ofrece prestaciones, debe definir la configuración para los correos electrónicos de confirmación de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="93452-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="93452-105">Configurar opciones de correo electrónico de confirmación</span><span class="sxs-lookup"><span data-stu-id="93452-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="93452-106">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="93452-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="93452-107">En la pestaña **Administración de prestaciones**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="93452-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="93452-108">Campo</span><span class="sxs-lookup"><span data-stu-id="93452-108">Field</span></span> | <span data-ttu-id="93452-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="93452-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="93452-110">**Enviar un correo de confirmación**</span><span class="sxs-lookup"><span data-stu-id="93452-110">**Send confirmation email**</span></span> | <span data-ttu-id="93452-111">Cuando esta característica está activada, se enviará un correo electrónico de confirmación a los empleados cuando comprueben de la experiencia de inscripción de prestaciones en Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="93452-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="93452-112">**Plantilla de correo de confirmación**</span><span class="sxs-lookup"><span data-stu-id="93452-112">**Confirmation email template**</span></span> | <span data-ttu-id="93452-113">Seleccione la plantilla de correo electrónico de la organización que se usará al enviar la confirmación de inscripción.</span><span class="sxs-lookup"><span data-stu-id="93452-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="93452-114">Si no selecciona una plantilla, se enviará el siguiente correo electrónico genérico:</span><span class="sxs-lookup"><span data-stu-id="93452-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="93452-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="93452-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="93452-116">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="93452-116">Congratulations!</span></span> <span data-ttu-id="93452-117">Ha completado correctamente la inscripción a las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="93452-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="93452-118">Gracias,</span><span class="sxs-lookup"><span data-stu-id="93452-118">Thank you,</span></span><br><span data-ttu-id="93452-119">Prestaciones de <Company/Org name>.</span><span class="sxs-lookup"><span data-stu-id="93452-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="93452-120">**Dirección predeterminada de correo del remitente**</span><span class="sxs-lookup"><span data-stu-id="93452-120">**Default email sender address**</span></span> | <span data-ttu-id="93452-121">La dirección de correo electrónico que se usará al enviar el correo electrónico de confirmación.</span><span class="sxs-lookup"><span data-stu-id="93452-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="93452-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="93452-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]