---
title: Registrar trabajos en sitios externos profesionales desde Attract
description: Este tema explica cómo usar Dynamics 365 Talent - Attract para registrar trabajos en sitios de contratación externos
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
ms.openlocfilehash: 2c822a1f799144bb9240fc0cbdeb6c5441e278af
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551412"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="c0383-103">Registrar trabajos en sitios externos profesionales desde Attract</span><span class="sxs-lookup"><span data-stu-id="c0383-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0383-104">Microsoft Dynamics 365 Talent: Attract ayuda a obtener el talento que necesita dejándole enviar sus trabajos directamente de Attract a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-104">Microsoft Dynamics 365 Talent: Attract helps you get the talent you need by letting you post your jobs directly from Attract to Broadbean.</span></span> <span data-ttu-id="c0383-105">Tras [crear un trabajo](./creating-jobs-attract.md) sólo tiene que hacer clic en un botón para poner el trabajo delante de todos los candidatos potenciales en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-105">After you [create a job](./creating-jobs-attract.md), all you have to do is click a button to put your job in front of all the potential job candidates on Broadbean.</span></span>

<span data-ttu-id="c0383-106">Enviar trabajos a Broadbean requiere una licencia adecuada de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-106">Posting jobs to Broadbean requires an appropriate Broadbean license.</span></span> <span data-ttu-id="c0383-107">Broadbean proporciona diversos productos y planes.</span><span class="sxs-lookup"><span data-stu-id="c0383-107">Broadbean offers various products and plans.</span></span> <span data-ttu-id="c0383-108">Para obtener más información acerca de licencias y precios de Broadbean, [póngase en contacto con Broadbean](https://www.broadbean.com/contact-us/).</span><span class="sxs-lookup"><span data-stu-id="c0383-108">For more information about Broadbean licensing and pricing, [contact Broadbean](https://www.broadbean.com/contact-us/).</span></span>

<span data-ttu-id="c0383-109">Si es administrador y necesita obtener más información sobre cómo configurar la integración de Broadbean con Attract, consulte [Especificar valores para plataformas de trabajo externas](./attract-admin-job-board-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c0383-109">If you're an admin who needs more information about how to configure Broadbean integration with Attract, see [Enter settings for external job boards](./attract-admin-job-board-settings.md).</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="c0383-110">Publicar ofertas de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="c0383-110">Post jobs to Broadbean</span></span>

<span data-ttu-id="c0383-111">Una vez Broadbean está activado, los reclutadores y los administradores pueden registrar un trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0383-111">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="c0383-112">Debe tener una URL de solicitud para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0383-112">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="c0383-113">En Attract, abra el trabajo que desee registrar en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-113">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="c0383-114">En la sección **Registros**, seleccione el botón **Registrar ahora** que corresponde a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-114">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="c0383-115">Siga las instrucciones en la ventana de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-115">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="c0383-116">Attract pasa la siguiente información a Broadbean:</span><span class="sxs-lookup"><span data-stu-id="c0383-116">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="c0383-117">Id. de solicitud</span><span class="sxs-lookup"><span data-stu-id="c0383-117">Request ID</span></span>
- <span data-ttu-id="c0383-118">Cargo laboral</span><span class="sxs-lookup"><span data-stu-id="c0383-118">Job title</span></span>
- <span data-ttu-id="c0383-119">Descripción del trabajo</span><span class="sxs-lookup"><span data-stu-id="c0383-119">Job description</span></span>
- <span data-ttu-id="c0383-120">Ubicación de trabajo</span><span class="sxs-lookup"><span data-stu-id="c0383-120">Job location</span></span>
- <span data-ttu-id="c0383-121">URL de la solicitud</span><span class="sxs-lookup"><span data-stu-id="c0383-121">Apply URL</span></span>
- <span data-ttu-id="c0383-122">Información del contratante</span><span class="sxs-lookup"><span data-stu-id="c0383-122">Recruiter information</span></span>

<span data-ttu-id="c0383-123">Una vez que Broadbean complete con éxito correctamente el registro, la sección **Registros** del trabajo en Attract muestra el estado de Broadbean como **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="c0383-123">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="c0383-124">Broadbean requiere el campo **Sector**.</span><span class="sxs-lookup"><span data-stu-id="c0383-124">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="c0383-125">Actualmente este cambo está establecido **TI** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c0383-125">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="c0383-126">Sin embargo, puede cambiar el valor al sector correcto en la ventana para la oferta de empleo de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-126">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="c0383-127">Broadbean necesitará algo de tiempo para terminar de registrar su trabajo en todas las bolsas de empleo que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c0383-127">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="c0383-128">Por lo tanto, puede haber un retraso leve antes de que Attract proporcione una actualización del estado del empleo.</span><span class="sxs-lookup"><span data-stu-id="c0383-128">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="c0383-129">Ver un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="c0383-129">View a Broadbean job posting</span></span>

<span data-ttu-id="c0383-130">Después de registrar un trabajo en Broadbean, podrá verlo desde Attract.</span><span class="sxs-lookup"><span data-stu-id="c0383-130">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="c0383-131">En Attract, abra el trabajo que desee ver en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-131">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="c0383-132">En la pestaña **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a Broadbean y, a continuación, seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="c0383-132">On the **Postings** tab, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="c0383-133">El registro de empleo de la Broadbean aparece en una ventana nueva.</span><span class="sxs-lookup"><span data-stu-id="c0383-133">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="c0383-134">Actualizar un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="c0383-134">Update a Broadbean job posting</span></span>

<span data-ttu-id="c0383-135">Puede actualizar una oferta de empleo en Broadbean de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="c0383-135">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="c0383-136">En Attract, abra el trabajo que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="c0383-136">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="c0383-137">En la sección **Registros**, seleccione el botón **Actualizar registro** que corresponde a Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-137">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="c0383-138">Edite el registro en la ventana de Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-138">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="c0383-139">O bien</span><span class="sxs-lookup"><span data-stu-id="c0383-139">–or–</span></span>

1. <span data-ttu-id="c0383-140">En Attract, abra el trabajo que desee ver en Broadbean.</span><span class="sxs-lookup"><span data-stu-id="c0383-140">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="c0383-141">En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="c0383-141">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="c0383-142">En la ventana de Broadbean, editar los detalles del trabajo y, a continuación registre de nuevo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0383-142">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="c0383-143">Los detalles del trabajo en Attract no se modifican.</span><span class="sxs-lookup"><span data-stu-id="c0383-143">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="c0383-144">Eliminar un registro de oferta de empleo en Broadbean</span><span class="sxs-lookup"><span data-stu-id="c0383-144">Remove a Broadbean job posting</span></span>

<span data-ttu-id="c0383-145">Puede quitar una oferta de trabajo de Broadbean según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c0383-145">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="c0383-146">En Attract, abra el trabajo que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="c0383-146">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="c0383-147">En la sección **Registros** , seleccione los puntos suspensivos (**…**) que corresponden a la haba y, a continuación seleccione **Eliminar registro**.</span><span class="sxs-lookup"><span data-stu-id="c0383-147">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="c0383-148">Una vez que Broadbean quite el trabajo, el artículo de Broadbean en Attract tendrá un botón **Registrar ahora**.</span><span class="sxs-lookup"><span data-stu-id="c0383-148">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="c0383-149">La presencia de este botón indica que el trabajo se ha quitado y se puede volver a registrar.</span><span class="sxs-lookup"><span data-stu-id="c0383-149">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-job-posting-to-broadbean"></a><span data-ttu-id="c0383-150">Solución de problemas de registro de trabajos en Broadbean</span><span class="sxs-lookup"><span data-stu-id="c0383-150">Troubleshoot job posting to Broadbean</span></span>

<span data-ttu-id="c0383-151">Si está teniendo problemas registrando un trabajo en Broadbean, intente estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c0383-151">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="c0383-152">Compruebe que las credenciales de Broadbean que ha especificado en Attract son válidas y correctas.</span><span class="sxs-lookup"><span data-stu-id="c0383-152">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="c0383-153">Si las credenciales son válidas y correctas, contacte con el [Soporte técnico de Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="c0383-153">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="c0383-154">Si el problema continúa, contacte con el [Soporte técnico de Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="c0383-154">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0383-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0383-155">See also</span></span>

[<span data-ttu-id="c0383-156">Crear trabajos</span><span class="sxs-lookup"><span data-stu-id="c0383-156">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="c0383-157">Especificar valores para plataformas de trabajo externas</span><span class="sxs-lookup"><span data-stu-id="c0383-157">Enter settings for external job boards</span></span>](./attract-admin-job-board-settings.md)
