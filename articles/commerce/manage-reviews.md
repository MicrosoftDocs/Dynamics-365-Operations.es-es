---
title: Administrar clasificaciones y revisiones
description: En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
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
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027251"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="39944-103">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="39944-104">En este tema se explica cómo administrar clasificaciones y revisiones mediante la herramienta de moderación de clasificaciones y revisiones de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="39944-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="39944-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="39944-105">Overview</span></span>

<span data-ttu-id="39944-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service para moderar automáticamente el texto de revisión redactando palabras profanas.</span><span class="sxs-lookup"><span data-stu-id="39944-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="39944-107">Además, los moderadores pueden usar la herramienta de moderación de clasificaciones y revisiones para las siguientes tareas manuales:</span><span class="sxs-lookup"><span data-stu-id="39944-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="39944-108">Moderar revisiones respondiendo a ellas o quitándolas.</span><span class="sxs-lookup"><span data-stu-id="39944-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="39944-109">Eliminar la revisión de un cliente en la solicitud del cliente.</span><span class="sxs-lookup"><span data-stu-id="39944-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="39944-110">Realizar la importación masiva de datos de clasificaciones y revisiones para todos los productos en una plantilla de Microsoft Power BI, para poder analizar las tendencias para las clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="39944-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="39944-111">Acceder a características de moderación de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="39944-112">Para acceder a las características de moderación de clasificaciones y revisiones en la herramienta de administración del sitio de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="39944-113">Inicie sesión en [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="39944-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="39944-114">Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="39944-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="39944-115">En la sección **Entornos**, seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="39944-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="39944-116">En **Características del entorno**, seleccione **Administración de venta minorista**.</span><span class="sxs-lookup"><span data-stu-id="39944-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="39944-117">En la pestaña **Comercio electrónico** debajo de **Vínculos**, seleccione **Herramienta de administración del sitio de comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="39944-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="39944-118">Leer una revisión</span><span class="sxs-lookup"><span data-stu-id="39944-118">Read a review</span></span> 

1. <span data-ttu-id="39944-119">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="39944-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="39944-120">Use el campo de búsqueda de la parte superior derecha de la página para filtrar las revisiones que se muestran por id. de producto, nombre del producto o texto de la revisión.</span><span class="sxs-lookup"><span data-stu-id="39944-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="39944-121">Los filtros adicionales le permiten limitar las revisiones por período, calificación, canal o estado de preocupación (retirado, respondido o notificado).</span><span class="sxs-lookup"><span data-stu-id="39944-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Página principal de moderación](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="39944-123">Respuesta a una revisión</span><span class="sxs-lookup"><span data-stu-id="39944-123">Respond to a review</span></span> 

<span data-ttu-id="39944-124">A veces, los clientes que compraron un producto expresan su satisfacción, o descontento o no entienden cómo utilizar el producto.</span><span class="sxs-lookup"><span data-stu-id="39944-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="39944-125">Como moderador, puede registrar una respuesta en una revisión.</span><span class="sxs-lookup"><span data-stu-id="39944-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="39944-126">Esta respuesta aparece junto con la revisión en el sitio.</span><span class="sxs-lookup"><span data-stu-id="39944-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="39944-127">Para responder a una revisión, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="39944-128">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="39944-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="39944-129">Busque y seleccione la revisión que requiere una respuesta.</span><span class="sxs-lookup"><span data-stu-id="39944-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="39944-130">En el panel de propiedades de la derecha, seleccione **Agregar una respuesta**.</span><span class="sxs-lookup"><span data-stu-id="39944-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="39944-131">Escriba el texto de la respuesta y el nombre que se debe mostrar para el respondedor.</span><span class="sxs-lookup"><span data-stu-id="39944-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="39944-132">El nombre predeterminado del respondedor es **Moderador**.</span><span class="sxs-lookup"><span data-stu-id="39944-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="39944-133">Cuando haya terminado, seleccione **Publicar respuesta**.</span><span class="sxs-lookup"><span data-stu-id="39944-133">When you've finished, select **Post response**.</span></span>

![Respuesta a una revisión](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="39944-135">Retirar una revisión</span><span class="sxs-lookup"><span data-stu-id="39944-135">Take down a review</span></span> 

<span data-ttu-id="39944-136">A veces, hay una justificación comercial para que los moderadores retiren revisiones del cliente.</span><span class="sxs-lookup"><span data-stu-id="39944-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="39944-137">Para retirar una revisión, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="39944-138">Vaya a **Inicio \> Revisiones \> Moderación**.</span><span class="sxs-lookup"><span data-stu-id="39944-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="39944-139">Busque y seleccione la revisión que se debe retirar.</span><span class="sxs-lookup"><span data-stu-id="39944-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="39944-140">En el panel de las propiedades de la derecha, seleccione un motivo de retirada y, a continuación, **Retirar**.</span><span class="sxs-lookup"><span data-stu-id="39944-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="39944-141">Eliminar la revisión de un cliente en la solicitud del cliente</span><span class="sxs-lookup"><span data-stu-id="39944-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="39944-142">A veces, los clientes desean que los datos de clasificaciones y revisiones se eliminen de manera permanente de un sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="39944-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="39944-143">Un moderador que recibe una solicitud de eliminación de un cliente puede quitar los datos del cliente mediante la característica de eliminación de revisión.</span><span class="sxs-lookup"><span data-stu-id="39944-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="39944-144">Para buscar y eliminar los datos de un cliente, el moderador requiere la dirección de correo electrónico que el cliente utilizaba para iniciar sesión y proporcionar revisiones.</span><span class="sxs-lookup"><span data-stu-id="39944-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="39944-145">Para buscar y eliminar datos del cliente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="39944-146">Vaya a **Inicio \> Revisiones \> Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="39944-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="39944-147">En el campo **Buscar usuarios por dirección de correo electrónico**, escriba la dirección de correo electrónico del cliente y, a continuación, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="39944-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="39944-148">Si el cliente tiene algún actividad de revisión (por ejemplo, envíos de revisión, votos acerca la utilidad de revisiones de las revisiones de otro cliente, o comentarios sobre la revisión de otro cliente), se muestran los resultados.</span><span class="sxs-lookup"><span data-stu-id="39944-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="39944-149">Para cada artículo, hay un botón **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="39944-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="39944-150">Para cada artículo que se debe eliminar, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="39944-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="39944-151">Cuando se le pida confirmación, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="39944-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Eliminación de los datos de clientes](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="39944-153">Se pueden tardar hasta siete días en que los datos se eliminen por completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="39944-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="39944-154">Los moderadores deben notificar a los clientes acerca de este retraso.</span><span class="sxs-lookup"><span data-stu-id="39944-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="39944-155">Si los clientes han cambiado su nombre en la configuración de la cuenta, varios artículos pueden aparecen en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39944-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="39944-156">En este caso, para eliminar por completo los datos del cliente, el moderador debe seleccionar **Eliminar** para cada artículo.</span><span class="sxs-lookup"><span data-stu-id="39944-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="39944-157">Descargar datos de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-157">Download ratings and reviews data</span></span>

<span data-ttu-id="39944-158">La herramientas de evaluaciones y revisiones permite a los moderadores importar datos de clasificaciones y revisiones de manera masiva, de modo que puedan analizar tendencias.</span><span class="sxs-lookup"><span data-stu-id="39944-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="39944-159">Hay disponible una plantilla de Power BI que incluye métrica básica.</span><span class="sxs-lookup"><span data-stu-id="39944-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="39944-160">Los moderadores pueden utilizar esta plantilla para conectar datos importados de manera masiva y ver un panel.</span><span class="sxs-lookup"><span data-stu-id="39944-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="39944-161">No tienen que crear un panel personalizado.</span><span class="sxs-lookup"><span data-stu-id="39944-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="39944-162">Los moderadores también pueden personalizar la plantilla de Power BI para satisfacer sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="39944-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="39944-163">Para descargar los datos de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="39944-164">Vaya a **Inicio \> Revisiones \> Informes**.</span><span class="sxs-lookup"><span data-stu-id="39944-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="39944-165">Seleccione **Descargar datos de revisiones** para descargar datos de clasificaciones y revisiones de manera masiva en el formato de valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="39944-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="39944-166">Ver tendencias de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-166">View ratings and reviews trends</span></span>

<span data-ttu-id="39944-167">Los moderadores pueden descargar la plantilla de Power BI de modo que puedan ver tendencias en un panel.</span><span class="sxs-lookup"><span data-stu-id="39944-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="39944-168">Para ver tendencias de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39944-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="39944-169">Vaya a **Inicio \> Revisiones \> Informes**.</span><span class="sxs-lookup"><span data-stu-id="39944-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="39944-170">Seleccione **Plantilla de PowerBI** para descargar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="39944-170">Select **PowerBI template** to download the template.</span></span>

    ![Descarga de la plantilla de Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="39944-172">Abra la plantilla descargada mediante la aplicación Power BI.</span><span class="sxs-lookup"><span data-stu-id="39944-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="39944-173">Cierre el cuadro de diálogo **Acceso al contenido web** que aparece y cierre el mensaje de error “Actualización” que aparece.</span><span class="sxs-lookup"><span data-stu-id="39944-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="39944-174">Vaya a **Inicio**, seleccione **Editar consultas** y **Configuración del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="39944-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="39944-175">En el cuadro de diálogo **Configuración de origen de datos**, seleccione **Cambiar origen**.</span><span class="sxs-lookup"><span data-stu-id="39944-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="39944-176">En el campo **Dirección URL**, especifique la ruta de los datos de revisiones que ha descargado en el procedimiento anterior (por ejemplo, **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="39944-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Campo de dirección URL en el cuadro de diálogo Valores separados por comas](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="39944-178">Seleccione **Aceptar** y, a continuación, **Aplicar cambios**.</span><span class="sxs-lookup"><span data-stu-id="39944-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="39944-179">Se tardará de uno a dos minutos en aplicar los cambios al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="39944-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="39944-180">Seleccione **Hoja de tendencias** para ver las tendencias de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="39944-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Tendencias de clasificaciones y revisiones](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="39944-182">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="39944-182">Additional resources</span></span>

[<span data-ttu-id="39944-183">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="39944-184">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="39944-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="39944-185">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="39944-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="39944-186">Sincronizar clasificaciones de productos en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="39944-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
