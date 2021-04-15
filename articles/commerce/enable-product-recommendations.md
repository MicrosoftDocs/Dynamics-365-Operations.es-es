---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial y aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 59d6b298896c92cbc0f6bbae17096ee1f027b922
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799164"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="0c441-103">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="0c441-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c441-104">Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial y aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c441-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="0c441-105">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="0c441-106">Recomendaciones previas a la comprobación</span><span class="sxs-lookup"><span data-stu-id="0c441-106">Recommendations pre-check</span></span>

<span data-ttu-id="0c441-107">Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="0c441-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="0c441-108">Las siguientes configuraciones deben estar habilitadas en el back office antes de habilitar las recomendaciones:</span><span class="sxs-lookup"><span data-stu-id="0c441-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="0c441-109">Asegúrese de que Azure Data Lake Storage se haya comprado y verificado con éxito en el entorno.</span><span class="sxs-lookup"><span data-stu-id="0c441-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="0c441-110">Para más información, consulte [Asegurarse de que Azure Data Lake Storage se haya comprado y verificado con éxito en el entorno](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="0c441-111">Asegúrese de que la actualización de la tienda de la entidad se haya automatizado.</span><span class="sxs-lookup"><span data-stu-id="0c441-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="0c441-112">Para más información, ver [Asegúrese de que la actualización de la tienda Entity se haya automatizado](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="0c441-113">Confirme que la configuración de Azure AD Identity contiene una entrada para Recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="0c441-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="0c441-114">A continuación se encuentra más información sobre cómo hacer esta acción.</span><span class="sxs-lookup"><span data-stu-id="0c441-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="0c441-115">Además, asegúrese de que se han habilitado las medidas de RetailSale.</span><span class="sxs-lookup"><span data-stu-id="0c441-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="0c441-116">Para obtener más información sobre este proceso de configuración, consulte [Trabajar con medidas](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="0c441-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="0c441-117">Configuración de Azure AD Identity</span><span class="sxs-lookup"><span data-stu-id="0c441-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="0c441-118">Este paso es necesario para todos los clientes que ejecutan una configuración de infraestructura como servicio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="0c441-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="0c441-119">Para los clientes que se ejecutan en Service Fabric (SF), este paso debe ser automático y recomendamos verificar que la configuración esté configurada como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="0c441-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="0c441-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="0c441-120">Setup</span></span>

1. <span data-ttu-id="0c441-121">Desde el back office, busque la página **aplicaciones Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0c441-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="0c441-122">Verifique si existe una entrada para "RecommendationSystemApplication-1".</span><span class="sxs-lookup"><span data-stu-id="0c441-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="0c441-123">Si la entrada no existe, agregue una nueva entrada con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0c441-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="0c441-124">**Id. de cliente** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="0c441-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="0c441-125">**Nombre** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="0c441-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="0c441-126">**Id. de usuario** - RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="0c441-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="0c441-127">Guarde y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0c441-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="0c441-128">Activar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="0c441-128">Turn on recommendations</span></span>

<span data-ttu-id="0c441-129">Para activar recomendaciones de productos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0c441-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="0c441-130">En la central de Commerce, busque **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="0c441-130">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="0c441-131">Seleccione **Todas** para ver una lista de funciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="0c441-131">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="0c441-132">En el cuadro de búsqueda, introduzca **Recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="0c441-132">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="0c441-133">Seleccione la característica **Recomendaciones de productos**.</span><span class="sxs-lookup"><span data-stu-id="0c441-133">Select the **Product recommendations** feature.</span></span>
1. <span data-ttu-id="0c441-134">En el panel de propiedades **Recomendaciones de productos**, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="0c441-134">In the **Product recommendations** properties pane, select **Enable now**.</span></span>

![Activar las recomendaciones](./media/FeatureManagement_Recommendations.PNG)

> [!NOTE]
> <span data-ttu-id="0c441-136">Este procedimiento inicia el proceso de generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="0c441-136">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="0c441-137">Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c441-137">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="0c441-138">Configurar parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="0c441-138">Configure recommendation list parameters</span></span>

<span data-ttu-id="0c441-139">De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="0c441-139">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="0c441-140">Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio.</span><span class="sxs-lookup"><span data-stu-id="0c441-140">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="0c441-141">Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-141">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="0c441-142">Mostrar recomendaciones en dispositivos PDV</span><span class="sxs-lookup"><span data-stu-id="0c441-142">Show recommendations on POS devices</span></span>

<span data-ttu-id="0c441-143">Tras habilitar recomendaciones en la oficina administrativa de Commerce, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño.</span><span class="sxs-lookup"><span data-stu-id="0c441-143">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="0c441-144">Para conocer este proceso, consulte [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-144">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="0c441-145">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0c441-145">Enable personalized recommendations</span></span>

<span data-ttu-id="0c441-146">En Dynamics 365 Commerce, los minoristas pueden hacer que estén disponibles recomendaciones de productos personalizadas (lo que también se conoce como personalización).</span><span class="sxs-lookup"><span data-stu-id="0c441-146">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="0c441-147">De esta manera, se pueden incorporar recomendaciones personalizadas en la experiencia del cliente en línea y en el punto de venta.</span><span class="sxs-lookup"><span data-stu-id="0c441-147">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="0c441-148">Cuando se activa la funcionalidad de personalización, el sistema puede asociar la compra de un usuario y la información del producto para generar recomendaciones de productos individualizadas.</span><span class="sxs-lookup"><span data-stu-id="0c441-148">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="0c441-149">Para obtener más información recomendaciones personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0c441-149">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c441-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0c441-150">Additional resources</span></span>

[<span data-ttu-id="0c441-151">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="0c441-151">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="0c441-152">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0c441-152">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="0c441-153">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0c441-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0c441-154">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="0c441-154">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="0c441-155">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0c441-155">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="0c441-156">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="0c441-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="0c441-157">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="0c441-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="0c441-158">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="0c441-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="0c441-159">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="0c441-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="0c441-160">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="0c441-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="0c441-161">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="0c441-161">Product recommendations FAQ</span></span>](faq-recommendations.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]