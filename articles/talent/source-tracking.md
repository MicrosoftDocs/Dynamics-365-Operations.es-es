---
title: Llevar el seguimiento de orígenes de candidatos en Attract
description: Este tema proporciona información acerca realizar el seguimiento del origen de los perfiles y las solicitudes del candidato.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462458"
---
# <a name="track-candidate-sources-in-attract"></a><span data-ttu-id="05267-103">Llevar el seguimiento de orígenes de candidatos en Attract</span><span class="sxs-lookup"><span data-stu-id="05267-103">Track candidate sources in Attract</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE] 
> <span data-ttu-id="05267-104">La funcionalidad de la que se habla en este tema esta disponible como parte de una versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="05267-104">Functionality noted in this topic is available as part of a preview review release.</span></span> <span data-ttu-id="05267-105">El contenido y la funcionalidad están sujetos a cambios.</span><span class="sxs-lookup"><span data-stu-id="05267-105">The content and the functionality are subject to change.</span></span> <span data-ttu-id="05267-106">Para utilizar esta función, pida que un administrador la active usando la **Configuración de administración** en Attract.</span><span class="sxs-lookup"><span data-stu-id="05267-106">To use this feature, ask an administrator to enable it using the **Admin settings** in Attract.</span></span> <span data-ttu-id="05267-107">Una versión futura proporcionará informes de seguimiento del origen.</span><span class="sxs-lookup"><span data-stu-id="05267-107">A future release will provide source tracking reports.</span></span> <span data-ttu-id="05267-108">Para obtener más información, consulte [Acceder a las características de vista previa en Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="05267-108">For more information, see [Access preview features in Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

<span data-ttu-id="05267-109">Cuando los candidatos solicitan un trabajo, Attract automáticamente sigue el origen de sus solicitudes, proveyéndole de información valiosa para ayudarle a dirigir sus esfuerzos de contratación.</span><span class="sxs-lookup"><span data-stu-id="05267-109">When candidates apply for a job, Attract automatically tracks the source of their applications, providing you with valuable information to help you target your recruiting efforts.</span></span> <span data-ttu-id="05267-110">Los reclutadores y los administradores de contratación pueden seleccionar también un origen de la aplicación mientras agregan manualmente un candidato a un trabajo o la reserva de talentos.</span><span class="sxs-lookup"><span data-stu-id="05267-110">Recruiters and hiring managers can also select an application source while manually adding a candidate to a job or talent pool.</span></span>

<span data-ttu-id="05267-111">Puede ver el origen de la solicitud en los detalles de actividad de solicitud en la pestaña **Actividad** , así como en el historial de la solicitud disponible en **Perfil** en las reservas de talentos.</span><span class="sxs-lookup"><span data-stu-id="05267-111">You can view the application source in the application activity details under the **Activity** tab, as well as in the application history available under **Profile** in talent pools.</span></span> <span data-ttu-id="05267-112">Puede encontrar el origen del perfil de un candidato en los detalles del candidato, en la pestaña **Perfil** en solicitudes y reservas de talentos.</span><span class="sxs-lookup"><span data-stu-id="05267-112">You can find a candidate's profile source in the candidate details under the **Profile** tab in both applications and talent pools.</span></span>

> [!NOTE] 
> <span data-ttu-id="05267-113">Puede encontrar plantillas de proceso en el [Complemento de contratación completa](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring)</span><span class="sxs-lookup"><span data-stu-id="05267-113">You can find process templates in the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>

## <a name="pre-configured-sources"></a><span data-ttu-id="05267-114">Fuentes preconfiguradas</span><span class="sxs-lookup"><span data-stu-id="05267-114">Pre-configured sources</span></span>

<span data-ttu-id="05267-115">La lista de origen predeterminada contiene orígenes comunes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="05267-115">The default source list contains common application sources.</span></span> <span data-ttu-id="05267-116">Algunos tipos de origen, como **Oportunidades de trabajo** y **Red social**, tienen detalles adicionales de origen.</span><span class="sxs-lookup"><span data-stu-id="05267-116">Some source types, like **Job board** and **Social Network**, have additional source details.</span></span> <span data-ttu-id="05267-117">Por ejemplo, **Red social** incluye Facebook y Twitter.</span><span class="sxs-lookup"><span data-stu-id="05267-117">For example, **Social Network** includes Facebook and Twitter.</span></span> <span data-ttu-id="05267-118">El tipo de origen **Referencia** permite especificar un empleado interno como el origen de la referencia.</span><span class="sxs-lookup"><span data-stu-id="05267-118">The **Referral** source type allows you to specify an internal employee as the referrer.</span></span> <span data-ttu-id="05267-119">La lista de origen predeterminada incluye los siguientes orígenes preconfigurados:</span><span class="sxs-lookup"><span data-stu-id="05267-119">The default source list includes the following pre-configured sources:</span></span>

-   <span data-ttu-id="05267-120">Sitio de desarrollo profesional de Attract</span><span class="sxs-lookup"><span data-stu-id="05267-120">Attract career site</span></span>

-   <span data-ttu-id="05267-121">Agencia</span><span class="sxs-lookup"><span data-stu-id="05267-121">Agency</span></span>

-   <span data-ttu-id="05267-122">Feria de empleo</span><span class="sxs-lookup"><span data-stu-id="05267-122">Career Fair</span></span>

-   <span data-ttu-id="05267-123">Marketing de la empresa</span><span class="sxs-lookup"><span data-stu-id="05267-123">Company Marketing</span></span>

-   <span data-ttu-id="05267-124">Conferencias y ferias comerciales</span><span class="sxs-lookup"><span data-stu-id="05267-124">Conferences & Trade shows</span></span>

-   <span data-ttu-id="05267-125">Asociación profesional</span><span class="sxs-lookup"><span data-stu-id="05267-125">Professional Association</span></span>

-   <span data-ttu-id="05267-126">Página de oportunidades de trabajo</span><span class="sxs-lookup"><span data-stu-id="05267-126">Job board</span></span>

    -   <span data-ttu-id="05267-127">Indeed</span><span class="sxs-lookup"><span data-stu-id="05267-127">Indeed</span></span>

    -   <span data-ttu-id="05267-128">Seek</span><span class="sxs-lookup"><span data-stu-id="05267-128">Seek</span></span>

    -   <span data-ttu-id="05267-129">CareerBuilder</span><span class="sxs-lookup"><span data-stu-id="05267-129">CareerBuilder</span></span>

    -   <span data-ttu-id="05267-130">Google Jobs</span><span class="sxs-lookup"><span data-stu-id="05267-130">Google Jobs</span></span>

    -   <span data-ttu-id="05267-131">Xing</span><span class="sxs-lookup"><span data-stu-id="05267-131">Xing</span></span>

    -   <span data-ttu-id="05267-132">Glassdoor</span><span class="sxs-lookup"><span data-stu-id="05267-132">Glassdoor</span></span>

    -   <span data-ttu-id="05267-133">Monster Jobs</span><span class="sxs-lookup"><span data-stu-id="05267-133">Monster Jobs</span></span>

-   <span data-ttu-id="05267-134">Revistas y publicaciones</span><span class="sxs-lookup"><span data-stu-id="05267-134">Magazines & Publications</span></span>

-   <span data-ttu-id="05267-135">Red social</span><span class="sxs-lookup"><span data-stu-id="05267-135">Social Network</span></span>

    -   <span data-ttu-id="05267-136">Facebook</span><span class="sxs-lookup"><span data-stu-id="05267-136">Facebook</span></span>

    -   <span data-ttu-id="05267-137">Twitter</span><span class="sxs-lookup"><span data-stu-id="05267-137">Twitter</span></span>

-   <span data-ttu-id="05267-138">Contratación en la Universidad</span><span class="sxs-lookup"><span data-stu-id="05267-138">University Recruiting</span></span>

-   <span data-ttu-id="05267-139">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="05267-139">LinkedIn</span></span>

-   <span data-ttu-id="05267-140">Clasificados</span><span class="sxs-lookup"><span data-stu-id="05267-140">Classifieds</span></span>

-   <span data-ttu-id="05267-141">Referencia</span><span class="sxs-lookup"><span data-stu-id="05267-141">Referral</span></span>

-   <span data-ttu-id="05267-142">Agregado por el reclutador</span><span class="sxs-lookup"><span data-stu-id="05267-142">Added by Recruiter</span></span>

-   <span data-ttu-id="05267-143">Otras</span><span class="sxs-lookup"><span data-stu-id="05267-143">Other</span></span>

## <a name="customize-the-source-list"></a><span data-ttu-id="05267-144">Personalizar la lista de origen</span><span class="sxs-lookup"><span data-stu-id="05267-144">Customize the source list</span></span> 

<span data-ttu-id="05267-145">Puede ampliar la lista de origen para incluir orígenes adicionales de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="05267-145">You can extend the source list to include additional application sources.</span></span> <span data-ttu-id="05267-146">Para personalizar esta lista, siga las instrucciones en [Extender los conjuntos de opciones en Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span><span class="sxs-lookup"><span data-stu-id="05267-146">To customize this list, follow the instructions in [Extending Option Sets in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract).</span></span> <span data-ttu-id="05267-147">Edite la entidad **TalentSource** para incluir orígenes adicionales.</span><span class="sxs-lookup"><span data-stu-id="05267-147">Edit the **TalentSource** entity to include additional sources.</span></span> 

<span data-ttu-id="05267-148">Para evitar afectar negativamente a la interfaz de usuario (UI), no edite ni elimine los valores (no nombres) de la enumeración **TalentCategory** para:</span><span class="sxs-lookup"><span data-stu-id="05267-148">To avoid negatively impacting the user interface (UI), don't edit or delete the **TalentCategory** enum values (not names) for the following:</span></span>

- <span data-ttu-id="05267-149">**Referencia**</span><span class="sxs-lookup"><span data-stu-id="05267-149">**Referral**</span></span>
- <span data-ttu-id="05267-150">**LinkedIn**</span><span class="sxs-lookup"><span data-stu-id="05267-150">**LinkedIn**</span></span>
- <span data-ttu-id="05267-151">**Otras**</span><span class="sxs-lookup"><span data-stu-id="05267-151">**Other**</span></span>

<span data-ttu-id="05267-152">En su lugar, puede ampliar la enumeración **TalentSource** para agregar otros tipos de orígenes.</span><span class="sxs-lookup"><span data-stu-id="05267-152">Instead, you can extend the **TalentSource** enum to add other types of sources.</span></span>
