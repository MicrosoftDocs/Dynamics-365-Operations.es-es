---
title: Registrar trabajos en sitios externos profesionales desde Attract
description: Este tema explica cómo usar Dynamics 365 for Talent - Attract para registrar trabajos en sitios de contratación externos
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9c27d1810a89ed7d7a7745e41c5f118dbdfe5dda
ms.sourcegitcommit: cadce85ca3004d53caf6bc49147a524c1bfd421f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "1590491"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="6033e-103">Registrar trabajos en sitios externos profesionales desde Attract</span><span class="sxs-lookup"><span data-stu-id="6033e-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6033e-104">Usted quiere presentar sus vacantes a tantos candidatos cualificados como sea posible.</span><span class="sxs-lookup"><span data-stu-id="6033e-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="6033e-105">Los sitios de contratación como Broadbean se lleva a cabo este objetivo.</span><span class="sxs-lookup"><span data-stu-id="6033e-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="6033e-106">Microsoft Dynamics 365 Talent: Attract ahora le permite registrar trabajos en Broadbean y Microsoft proporciona constantemente nuevas ofertas en esta área.</span><span class="sxs-lookup"><span data-stu-id="6033e-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="6033e-107">Registrar trabajos en Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="6033e-108">Antes de poder registrar trabajos en Broadbean debe configurar la integración con Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="6033e-109">Para registrar trabajos en los sitios externos, debe tener el [Complemento de contratación completo](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="6033e-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="6033e-110">Para registrar trabajos a en Broadbean a través de Attract, debe tener una suscripción de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-110">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="6033e-111">Esta característica está actualmente en vista previa.</span><span class="sxs-lookup"><span data-stu-id="6033e-111">This feature is currently in preview.</span></span> <span data-ttu-id="6033e-112">Si desea probarlo, debe [activarlo en la configuración de administrador de Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="6033e-112">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="6033e-113">Configurar integración de Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-113">Configure Broadbean integration</span></span>

1. <span data-ttu-id="6033e-114">Iniciar sesión en Attract como administrador.</span><span class="sxs-lookup"><span data-stu-id="6033e-114">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="6033e-115">Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha de la página y a continuación seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="6033e-115">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="6033e-116">En la pestaña **Configuración de oportunidades de trabajo** , en la sección **Integración de Broadbean**, active la integración.</span><span class="sxs-lookup"><span data-stu-id="6033e-116">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="6033e-117">Póngase en contacto con Broadbean y introduzca su información en **Nombre de usuario, identificador de cliente, token de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="6033e-117">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="6033e-118">Sus credenciales de Broadbean son importantes y confidenciales.</span><span class="sxs-lookup"><span data-stu-id="6033e-118">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="6033e-119">Por lo tanto, almacénelas y compártalas de forma responsable.</span><span class="sxs-lookup"><span data-stu-id="6033e-119">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="6033e-120">Cualquiera que tenga un rol de administrador en Attract puede ver estas credenciales.</span><span class="sxs-lookup"><span data-stu-id="6033e-120">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="6033e-121">Microsoft y Attract no están involucradas en crear y mantener estos valores.</span><span class="sxs-lookup"><span data-stu-id="6033e-121">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="6033e-122">Es su responsabilidad mantenerlas actualizadas en Attract y trabajar con Broadbean para resolver los problemas relacionados con sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6033e-122">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="6033e-123">Registrar un trabajo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-123">Post a job to Broadbean</span></span>

<span data-ttu-id="6033e-124">Una vez Broadbean está activado, los reclutadores y los administradores pueden registrar un trabajo.</span><span class="sxs-lookup"><span data-stu-id="6033e-124">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="6033e-125">Debe tener una URL de solicitud para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="6033e-125">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="6033e-126">En Attract, abra el trabajo que desee registrar en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-126">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="6033e-127">En la sección **Registros**, seleccione el botón **Registrar ahora** que corresponde a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-127">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="6033e-128">Siga las instrucciones en la ventana de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-128">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="6033e-129">Attract pasa la siguiente información a Broadbean:</span><span class="sxs-lookup"><span data-stu-id="6033e-129">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="6033e-130">Id. de solicitud</span><span class="sxs-lookup"><span data-stu-id="6033e-130">Request ID</span></span>
- <span data-ttu-id="6033e-131">Cargo laboral</span><span class="sxs-lookup"><span data-stu-id="6033e-131">Job title</span></span>
- <span data-ttu-id="6033e-132">Descripción del trabajo</span><span class="sxs-lookup"><span data-stu-id="6033e-132">Job description</span></span>
- <span data-ttu-id="6033e-133">Ubicación de trabajo</span><span class="sxs-lookup"><span data-stu-id="6033e-133">Job location</span></span>
- <span data-ttu-id="6033e-134">URL de la solicitud</span><span class="sxs-lookup"><span data-stu-id="6033e-134">Apply URL</span></span>
- <span data-ttu-id="6033e-135">Información del contratante</span><span class="sxs-lookup"><span data-stu-id="6033e-135">Recruiter information</span></span>

<span data-ttu-id="6033e-136">Una vez que Broadbean complete con éxito correctamente el registro, la sección **Registros** del trabajo en Attract muestra el estado de Broadbean como **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="6033e-136">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="6033e-137">Broadbean requiere el campo **Sector**.</span><span class="sxs-lookup"><span data-stu-id="6033e-137">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="6033e-138">Actualmente este cambo está establecido **TI** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6033e-138">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="6033e-139">Sin embargo, puede cambiar el valor al sector correcto en la ventana para la oferta de empleo de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-139">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="6033e-140">Broadbean necesitará algo de tiempo para terminar de registrar su trabajo en todas las bolsas de empleo que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6033e-140">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="6033e-141">Por lo tanto, puede haber un retraso leve antes de que Attract proporcione una actualización del estado del empleo.</span><span class="sxs-lookup"><span data-stu-id="6033e-141">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="6033e-142">Ver un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-142">View a Broadbean job posting</span></span>

<span data-ttu-id="6033e-143">Después de registrar un trabajo en Broadbean, podrá verlo desde Attract.</span><span class="sxs-lookup"><span data-stu-id="6033e-143">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="6033e-144">En Attract, abra el trabajo que desee ver en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-144">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="6033e-145">En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="6033e-145">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="6033e-146">El registro de empleo de la Broadbean aparece en una ventana nueva.</span><span class="sxs-lookup"><span data-stu-id="6033e-146">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="6033e-147">Actualizar un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-147">Update a Broadbean job posting</span></span>

<span data-ttu-id="6033e-148">Puede actualizar una oferta de empleo en Broadbean de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="6033e-148">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="6033e-149">En Attract, abra el trabajo que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="6033e-149">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="6033e-150">En la sección **Registros**, seleccione el botón **Actualizar registro** que corresponde a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-150">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="6033e-151">Edite el registro en la ventana de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-151">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="6033e-152">O bien</span><span class="sxs-lookup"><span data-stu-id="6033e-152">–or–</span></span>

1. <span data-ttu-id="6033e-153">En Attract, abra el trabajo que desee ver en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="6033e-153">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="6033e-154">En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="6033e-154">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="6033e-155">En la ventana de Broadbean, editar los detalles del trabajo y, a continuación registre de nuevo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="6033e-155">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="6033e-156">Los detalles del trabajo en Attract no se modifican.</span><span class="sxs-lookup"><span data-stu-id="6033e-156">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="6033e-157">Eliminar un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-157">Remove a Broadbean job posting</span></span>

<span data-ttu-id="6033e-158">Puede quitar una oferta de trabajo de Broadbean según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6033e-158">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="6033e-159">En Attract, abra el trabajo que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="6033e-159">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="6033e-160">En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Eliminar registro**.</span><span class="sxs-lookup"><span data-stu-id="6033e-160">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="6033e-161">Una vez que Broadbean quite el trabajo, el artículo de Broadbean en Attract tendrá un botón **Registrar ahora**.</span><span class="sxs-lookup"><span data-stu-id="6033e-161">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="6033e-162">La presencia de este botón indica que el trabajo se ha quitado y se puede volver a registrar.</span><span class="sxs-lookup"><span data-stu-id="6033e-162">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="6033e-163">Solución de problemas de la integración con Broadbean</span><span class="sxs-lookup"><span data-stu-id="6033e-163">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="6033e-164">Si está teniendo problemas registrando un trabajo en Broadbean, intente estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6033e-164">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="6033e-165">Compruebe que las credenciales de Broadbean que ha especificado en Attract son válidas y correctas.</span><span class="sxs-lookup"><span data-stu-id="6033e-165">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="6033e-166">Si las credenciales son válidas y correctas, contacte con el [Soporte técnico de Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="6033e-166">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="6033e-167">Si el problema continúa, contacte con el [Soporte técnico de Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="6033e-167">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
