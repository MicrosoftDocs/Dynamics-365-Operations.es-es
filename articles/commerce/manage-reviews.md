---
title: Administrar clasificaciones y revisiones
description: En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e9becdce5ae36ac637043b9d0febfbbff2392aa9
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698035"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="d9229-103">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="d9229-103">Manage ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d9229-104">En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d9229-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="d9229-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="d9229-105">Overview</span></span>

<span data-ttu-id="d9229-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service para moderar automáticamente el texto de revisión redactando palabras profanas.</span><span class="sxs-lookup"><span data-stu-id="d9229-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="d9229-107">Además, los moderadores pueden usar la herramienta de moderación de clasificaciones y revisiones para las siguientes tareas manuales:</span><span class="sxs-lookup"><span data-stu-id="d9229-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="d9229-108">Moderar revisiones respondiendo a ellas o quitándolas.</span><span class="sxs-lookup"><span data-stu-id="d9229-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="d9229-109">Eliminar la revisión de un cliente en la solicitud del cliente.</span><span class="sxs-lookup"><span data-stu-id="d9229-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="d9229-110">Realizar la importación masiva de datos de clasificaciones y revisiones para todos los productos en una plantilla de Microsoft Power BI, para poder analizar las tendencias para las clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="d9229-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="d9229-111">Leer una revisión</span><span class="sxs-lookup"><span data-stu-id="d9229-111">Read a review</span></span> 

1. <span data-ttu-id="d9229-112">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="d9229-112">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d9229-113">Use el campo de búsqueda de la parte superior derecha de la página para filtrar las revisiones que se muestran por id. de producto, nombre del producto o texto de la revisión.</span><span class="sxs-lookup"><span data-stu-id="d9229-113">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="d9229-114">Los filtros adicionales le permiten limitar las revisiones por período, calificación, canal o estado de preocupación (retirado, respondido o notificado).</span><span class="sxs-lookup"><span data-stu-id="d9229-114">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Página principal de moderación](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="d9229-116">Respuesta a una revisión</span><span class="sxs-lookup"><span data-stu-id="d9229-116">Respond to a review</span></span> 

<span data-ttu-id="d9229-117">A veces, los clientes que compraron un producto expresan su satisfacción, o descontento o no entienden cómo utilizar el producto.</span><span class="sxs-lookup"><span data-stu-id="d9229-117">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="d9229-118">Como moderador, puede registrar una respuesta en una revisión.</span><span class="sxs-lookup"><span data-stu-id="d9229-118">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="d9229-119">Esta respuesta aparece junto con la revisión en el sitio.</span><span class="sxs-lookup"><span data-stu-id="d9229-119">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="d9229-120">Para responder a una revisión, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9229-120">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="d9229-121">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="d9229-121">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d9229-122">Busque y seleccione la revisión que requiere una respuesta.</span><span class="sxs-lookup"><span data-stu-id="d9229-122">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="d9229-123">En el panel de propiedades de la derecha, seleccione **Agregar una respuesta**.</span><span class="sxs-lookup"><span data-stu-id="d9229-123">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="d9229-124">Escriba el texto de la respuesta y el nombre que se debe mostrar para el respondedor.</span><span class="sxs-lookup"><span data-stu-id="d9229-124">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="d9229-125">El nombre predeterminado del respondedor es **Moderador**.</span><span class="sxs-lookup"><span data-stu-id="d9229-125">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="d9229-126">Cuando haya terminado, seleccione **Publicar respuesta**.</span><span class="sxs-lookup"><span data-stu-id="d9229-126">When you've finished, select **Post response**.</span></span>

![Respuesta a una revisión](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="d9229-128">Retirar una revisión</span><span class="sxs-lookup"><span data-stu-id="d9229-128">Take down a review</span></span> 

<span data-ttu-id="d9229-129">A veces, hay una justificación comercial para que los moderadores retiren revisiones del cliente.</span><span class="sxs-lookup"><span data-stu-id="d9229-129">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="d9229-130">Para retirar una revisión, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9229-130">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="d9229-131">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="d9229-131">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="d9229-132">Busque y seleccione la revisión que se debe retirar.</span><span class="sxs-lookup"><span data-stu-id="d9229-132">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="d9229-133">En el panel de las propiedades de la derecha, seleccione un motivo de retirada y, a continuación, **Retirar**.</span><span class="sxs-lookup"><span data-stu-id="d9229-133">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="d9229-134">Eliminar la revisión de un cliente en la solicitud del cliente</span><span class="sxs-lookup"><span data-stu-id="d9229-134">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="d9229-135">A veces, los clientes desean que los datos de clasificaciones y revisiones se eliminen de manera permanente de un sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="d9229-135">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="d9229-136">Un moderador que recibe una solicitud de eliminación de un cliente puede quitar los datos del cliente mediante la característica de eliminación de revisión.</span><span class="sxs-lookup"><span data-stu-id="d9229-136">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="d9229-137">Para buscar y eliminar los datos de un cliente, el moderador requiere la dirección de correo electrónico que el cliente utilizaba para iniciar sesión y proporcionar revisiones.</span><span class="sxs-lookup"><span data-stu-id="d9229-137">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="d9229-138">Para buscar y eliminar datos del cliente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9229-138">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="d9229-139">Vaya a **Inicio \> Revisiones \> Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d9229-139">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="d9229-140">En el campo **Buscar usuarios por dirección de correo electrónico**, escriba la dirección de correo electrónico del cliente y, a continuación, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="d9229-140">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="d9229-141">Si el cliente tiene algún actividad de revisión (por ejemplo, envíos de revisión, votos acerca la utilidad de revisiones de las revisiones de otro cliente, o comentarios sobre la revisión de otro cliente), se muestran los resultados.</span><span class="sxs-lookup"><span data-stu-id="d9229-141">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="d9229-142">Para cada artículo, hay un botón **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d9229-142">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="d9229-143">Para cada artículo que se debe eliminar, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d9229-143">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="d9229-144">Cuando se le pida confirmación, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d9229-144">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Eliminación de los datos de clientes](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="d9229-146">Se pueden tardar hasta siete días en que los datos se eliminen por completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d9229-146">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="d9229-147">Los moderadores deben notificar a los clientes acerca de este retraso.</span><span class="sxs-lookup"><span data-stu-id="d9229-147">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="d9229-148">Si los clientes han cambiado su nombre en la configuración de la cuenta, varios artículos pueden aparecen en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d9229-148">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="d9229-149">En este caso, para eliminar por completo los datos del cliente, el moderador debe seleccionar **Eliminar** para cada artículo.</span><span class="sxs-lookup"><span data-stu-id="d9229-149">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="d9229-150">Descargar datos de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="d9229-150">Download ratings and reviews data</span></span>

<span data-ttu-id="d9229-151">La herramientas de evaluaciones y revisiones permite a los moderadores importar datos de clasificaciones y revisiones de manera masiva, de modo que puedan analizar tendencias.</span><span class="sxs-lookup"><span data-stu-id="d9229-151">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="d9229-152">Hay disponible una plantilla de Power BI que incluye métrica básica.</span><span class="sxs-lookup"><span data-stu-id="d9229-152">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="d9229-153">Los moderadores pueden utilizar esta plantilla para conectar datos importados de manera masiva y ver un panel.</span><span class="sxs-lookup"><span data-stu-id="d9229-153">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="d9229-154">No tienen que crear un panel personalizado.</span><span class="sxs-lookup"><span data-stu-id="d9229-154">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="d9229-155">Los moderadores también pueden personalizar la plantilla de Power BI para satisfacer sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="d9229-155">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="d9229-156">Para descargar los datos de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9229-156">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="d9229-157">Vaya a **Inicio \> Revisiones \> Informes**.</span><span class="sxs-lookup"><span data-stu-id="d9229-157">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d9229-158">Seleccione **Descargar datos de revisiones** para descargar datos de clasificaciones y revisiones de manera masiva en el formato de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="d9229-158">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="d9229-159">Ver tendencias de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="d9229-159">View ratings and reviews trends</span></span>

<span data-ttu-id="d9229-160">Los moderadores pueden descargar la plantilla de Power BI de modo que puedan ver tendencias en un panel.</span><span class="sxs-lookup"><span data-stu-id="d9229-160">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="d9229-161">Para ver tendencias de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9229-161">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="d9229-162">Vaya a **Inicio \> Revisiones \> Informes**.</span><span class="sxs-lookup"><span data-stu-id="d9229-162">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="d9229-163">Seleccione **Plantilla de PowerBI** para descargar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="d9229-163">Select **PowerBI template** to download the template.</span></span>

    ![Descarga de la plantilla de Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="d9229-165">Abra la plantilla descargada mediante la aplicación Power BI.</span><span class="sxs-lookup"><span data-stu-id="d9229-165">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="d9229-166">Cierre el cuadro de diálogo **Acceso al contenido web** que aparece y cierre el mensaje de error “Actualización” que aparece.</span><span class="sxs-lookup"><span data-stu-id="d9229-166">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="d9229-167">Vaya a **Inicio**, seleccione **Editar consultas** y **Configuración del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="d9229-167">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="d9229-168">En el cuadro de diálogo **Configuración de origen de datos**, seleccione **Cambiar origen**.</span><span class="sxs-lookup"><span data-stu-id="d9229-168">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="d9229-169">En el campo **Dirección URL**, especifique la ruta de los datos de revisiones que ha descargado en el procedimiento anterior (por ejemplo, **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="d9229-169">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Campo de dirección URL en el cuadro de diálogo Valores separados por comas](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="d9229-171">Seleccione **Aceptar** y, a continuación, **Aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="d9229-171">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="d9229-172">Se tardará de uno a dos minutos en aplicar los cambios al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d9229-172">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="d9229-173">Seleccione **Hoja de tendencias** para ver las tendencias de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="d9229-173">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendencias de clasificaciones y revisiones](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="d9229-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d9229-175">Additional resources</span></span>

[<span data-ttu-id="d9229-176">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="d9229-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="d9229-177">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="d9229-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="d9229-178">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="d9229-178">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="d9229-179">Sincronizar clasificaciones de productos en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="d9229-179">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
