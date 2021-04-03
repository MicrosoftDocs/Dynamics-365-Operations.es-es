---
title: Habilitar recomendaciones de productos personalizadas
description: Este tema describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: be460ec5ce8a9a625dc1a80f761bea9e2ab2f632
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477669"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="f2265-103">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2265-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2265-104">Este tema describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2265-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f2265-105">En Dynamics 365 Commerce, los minoristas pueden hacer que estén disponibles recomendaciones de productos personalizadas (lo que también se conoce como personalización).</span><span class="sxs-lookup"><span data-stu-id="f2265-105">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="f2265-106">De esta manera, se pueden incorporar recomendaciones personalizadas en la experiencia del cliente en línea y en el punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="f2265-106">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="f2265-107">Cuando se activa la funcionalidad de personalización, el sistema puede asociar la compra de un usuario y la información del producto para generar recomendaciones de productos individualizadas.</span><span class="sxs-lookup"><span data-stu-id="f2265-107">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="f2265-108">Requisitos previos de personalización</span><span class="sxs-lookup"><span data-stu-id="f2265-108">Personalization prerequisites</span></span>

<span data-ttu-id="f2265-109">Antes de poner a disposición de los clientes las recomendaciones de productos personalizadas, tenga en cuenta que las recomendaciones de productos solo se admiten para los usuarios de Commerce que han migrado su almacenamiento a Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="f2265-109">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="f2265-110">Antes de que los clientes puedan recibir recomendaciones personalizadas de productos, los minoristas deben [activar las recomendaciones de productos](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="f2265-110">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f2265-111">Al activar recomendaciones de productos, también activa la personalización.</span><span class="sxs-lookup"><span data-stu-id="f2265-111">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="f2265-112">Sin embargo, si desactiva la personalización, no desactiva los demás tipos de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="f2265-112">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="f2265-113">Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="f2265-113">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="f2265-114">Desactivar la personalización</span><span class="sxs-lookup"><span data-stu-id="f2265-114">Turn on personalization</span></span>

<span data-ttu-id="f2265-115">Para activar la personalización, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f2265-115">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="f2265-116">En la central de Commerce, busque **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="f2265-116">In Commerce headquarters, search for **Feature Management**.</span></span>
1. <span data-ttu-id="f2265-117">Seleccione **Todas** para ver una lista de funciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2265-117">Select **All** to see a list of available features.</span></span> 
1. <span data-ttu-id="f2265-118">En el cuadro de búsqueda, introduzca **Recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="f2265-118">In the search box, enter **Recommendations**.</span></span>
1. <span data-ttu-id="f2265-119">Seleccione la característica **Recomendaciones de productos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="f2265-119">Select the **Personalized product recommendations** feature.</span></span>
1. <span data-ttu-id="f2265-120">En el panel de propiedades **Recomendaciones de productos personalizados**, seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f2265-120">In the **Personalized product recommendations** properties pane, select **Enable now**.</span></span>

![Activación de la personalización](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> <span data-ttu-id="f2265-122">Cuando activa la personalización, se inicia el proceso de generar listas de recomendaciones de productos personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2265-122">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="f2265-123">Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en el PDV.</span><span class="sxs-lookup"><span data-stu-id="f2265-123">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="f2265-124">Listas personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2265-124">Personalized lists</span></span>

<span data-ttu-id="f2265-125">Además de permitir la personalización de las listas generadas por máquina existentes, el servicio de recomendaciones permite la personalización de la experiencia de detección de productos tanto en línea como en el PDV.</span><span class="sxs-lookup"><span data-stu-id="f2265-125">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="f2265-126">Después de que se active la personalización, los minoristas pueden mostrar a los compradores listas personalizadas de "Picking para usted" o listas de "Recomendado para el cliente" en los terminales del PDV.</span><span class="sxs-lookup"><span data-stu-id="f2265-126">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="f2265-127">Además, los minoristas pueden aplicar la personalización a las listas de recomendaciones de productos existentes y proporcionar experiencias de exclusión voluntaria del Reglamento general de protección de datos (RGPD) para usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="f2265-127">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="f2265-128">Si desactiva la personalización, también desactiva estas características.</span><span class="sxs-lookup"><span data-stu-id="f2265-128">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="f2265-129">Listas en línea de "Picking para usted"</span><span class="sxs-lookup"><span data-stu-id="f2265-129">Online "Picks for you" lists</span></span>

<span data-ttu-id="f2265-130">Una lista de "Picking para usted" es una lista de inteligencia artificial-aprendizaje automático (AI-ML) que muestra a un usuario autenticado una lista personalizada de productos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="f2265-130">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="f2265-131">Esta lista se basa en el historial de compras omnicanal del usuario.</span><span class="sxs-lookup"><span data-stu-id="f2265-131">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="f2265-132">Las recomendaciones personalizadas se actualizan dinámicamente a medida que el usuario realiza más compras.</span><span class="sxs-lookup"><span data-stu-id="f2265-132">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="f2265-133">Este tipo de lista también admite el filtrado de categorías, para que los minoristas puedan mostrar las mejores opciones, en función de las jerarquías de navegación.</span><span class="sxs-lookup"><span data-stu-id="f2265-133">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="f2265-134">Antes de que la lista "Picking para usted" pueda aparecer en cualquier página de comercio electrónico, se deben cumplir los siguientes requisitos de usuario:</span><span class="sxs-lookup"><span data-stu-id="f2265-134">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="f2265-135">Los usuarios deben haber iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="f2265-135">Users must be signed in.</span></span> <span data-ttu-id="f2265-136">Los usuarios anónimos no verán recomendaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2265-136">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="f2265-137">Los usuarios deben tener al menos una compra en su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f2265-137">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="f2265-138">Los usuarios deben optar por recibir recomendaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2265-138">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="f2265-139">La siguiente ilustración muestra un ejemplo de una lista de "Picking para usted" en la página de una tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="f2265-139">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Listas en línea de Picking para usted](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="f2265-141">Listas de "Recomendado para el cliente" en el PDV</span><span class="sxs-lookup"><span data-stu-id="f2265-141">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="f2265-142">Para mejorar la experiencia de la relación con los clientes, los minoristas pueden personalizar las páginas de detalles de clientes existentes agregando una lista contextual "Recomendado para el cliente".</span><span class="sxs-lookup"><span data-stu-id="f2265-142">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="f2265-143">La siguiente ilustración muestra un ejemplo de una lista de "Recomendado para el cliente" en un terminal del PDV.</span><span class="sxs-lookup"><span data-stu-id="f2265-143">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Recomendado para el cliente en el PDV](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="f2265-145">Aplicar personalización a listas de recomendaciones existentes</span><span class="sxs-lookup"><span data-stu-id="f2265-145">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="f2265-146">Los minoristas pueden aplicar la personalización a listas de recomendaciones existentes, como "Nuevo", "Tendencias", "Más vendidos", "A la gente también le gustó" y "Los usuarios que compraron este artículo también compraron".</span><span class="sxs-lookup"><span data-stu-id="f2265-146">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="f2265-147">Cuando se aplica la personalización a las listas existentes, los elementos que compró previamente un usuario que haya iniciado sesión se eliminan de esas listas.</span><span class="sxs-lookup"><span data-stu-id="f2265-147">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="f2265-148">Tanto para usuarios anónimos como para usuarios que optaron por no recibir recomendaciones personalizadas, se muestran versiones predeterminadas de las listas existentes.</span><span class="sxs-lookup"><span data-stu-id="f2265-148">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="f2265-149">Por lo tanto, los minoristas no tienen que mantener manualmente experiencias de página independientes.</span><span class="sxs-lookup"><span data-stu-id="f2265-149">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="f2265-150">Por ejemplo, un usuario que haya iniciado sesión ya compró el reloj negro y las botas de trabajo marrones que aparecen en la lista "Tendencias - predeterminado" en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="f2265-150">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="f2265-151">Por lo tanto, el usuario verá nuevos productos en lugar de esos, como se muestra en la lista "Tendencias - personalizado".</span><span class="sxs-lookup"><span data-stu-id="f2265-151">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Aplicación de la personalización](./media/applypersonalization.png)

<span data-ttu-id="f2265-153">Para aplicar la personalización a una lista de recomendaciones existente en el generador de sitios de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f2265-153">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="f2265-154">Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de colección de productos.</span><span class="sxs-lookup"><span data-stu-id="f2265-154">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="f2265-155">En el panel de navegación de la izquierda, seleccione el módulo de colección de productos.</span><span class="sxs-lookup"><span data-stu-id="f2265-155">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="f2265-156">En el panel de navegación de la derecha, debajo de **Productos**, seleccione la lista.</span><span class="sxs-lookup"><span data-stu-id="f2265-156">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="f2265-157">En el cuadro de diálogo **Seleccionar la configuración de la lista de productos**, debajo de **Tipo**, seleccione el tipo de lista.</span><span class="sxs-lookup"><span data-stu-id="f2265-157">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="f2265-158">Selecciona la casilla **Aplicar personalización** y luego elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f2265-158">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Aplicación de la personalización a una lista de tendencias](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="f2265-160">Guarde la página, termine de editarla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="f2265-160">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="f2265-161">Una vez publicada la página, los usuarios que hayan iniciado sesión verán listas de tendencias personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f2265-161">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2265-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f2265-162">Additional resources</span></span>

[<span data-ttu-id="f2265-163">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="f2265-163">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="f2265-164">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f2265-164">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="f2265-165">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="f2265-165">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="f2265-166">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="f2265-166">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="f2265-167">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2265-167">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="f2265-168">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="f2265-168">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="f2265-169">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="f2265-169">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="f2265-170">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="f2265-170">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="f2265-171">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="f2265-171">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="f2265-172">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="f2265-172">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="f2265-173">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="f2265-173">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
