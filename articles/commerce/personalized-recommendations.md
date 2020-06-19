---
title: Habilitar recomendaciones de productos personalizadas
description: Este tema describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0e49b4db17ffd792e8dd536a1671773253c74d71
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404149"
---
# <a name="enable-personalized-recommendations"></a><span data-ttu-id="9e7a7-103">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9e7a7-103">Enable personalized recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9e7a7-104">Este tema describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-104">This topic describes how to make personalized product recommendations available for customers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9e7a7-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9e7a7-105">Overview</span></span>

<span data-ttu-id="9e7a7-106">En Dynamics 365 Commerce, los minoristas pueden hacer que estén disponibles recomendaciones de productos personalizadas (lo que también se conoce como personalización).</span><span class="sxs-lookup"><span data-stu-id="9e7a7-106">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="9e7a7-107">De esta manera, se pueden incorporar recomendaciones personalizadas en la experiencia del cliente en línea y en el punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="9e7a7-107">In this way, personalized recommendations can be incorporated into the customer experience online and at the point of sale (POS).</span></span> <span data-ttu-id="9e7a7-108">Cuando se activa la funcionalidad de personalización, el sistema puede asociar la compra de un usuario y la información del producto para generar recomendaciones de productos individualizadas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-108">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

## <a name="personalization-prerequisites"></a><span data-ttu-id="9e7a7-109">Requisitos previos de personalización</span><span class="sxs-lookup"><span data-stu-id="9e7a7-109">Personalization prerequisites</span></span>

<span data-ttu-id="9e7a7-110">Antes de poner a disposición de los clientes las recomendaciones de productos personalizadas, tenga en cuenta que las recomendaciones de productos solo se admiten para los usuarios de Commerce que han migrado su almacenamiento a Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-110">Before you make personalized product recommendations available for customers, note that product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Store.</span></span> <span data-ttu-id="9e7a7-111">Antes de que los clientes puedan recibir recomendaciones personalizadas de productos, los minoristas deben [activar las recomendaciones de productos](enable-product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9e7a7-111">Before customers can receive personalized product recommendations, retailers must [turn on product recommendations](enable-product-recommendations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9e7a7-112">Al activar recomendaciones de productos, también activa la personalización.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-112">By turning on product recommendations, you also turn on personalization.</span></span> <span data-ttu-id="9e7a7-113">Sin embargo, si desactiva la personalización, no desactiva los demás tipos de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-113">However, if you turn off personalization, you don't turn off the other types of product recommendations.</span></span>

<span data-ttu-id="9e7a7-114">Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="9e7a7-114">For more information about product recommendations, see the [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="turn-on-personalization"></a><span data-ttu-id="9e7a7-115">Desactivar la personalización</span><span class="sxs-lookup"><span data-stu-id="9e7a7-115">Turn on personalization</span></span>

<span data-ttu-id="9e7a7-116">Para activar la personalización, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-116">To turn on personalization, follow these steps.</span></span>

1. <span data-ttu-id="9e7a7-117">Vaya a **Retail y Commerce \> Recomendaciones de producto \> Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-117">Go to **Retail and commerce \> Product recommendations \> Recommendation parameters**.</span></span>
1. <span data-ttu-id="9e7a7-118">En la lista de parámetros compartidos de Retail, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-118">In the list of Retail shared parameters, select **Recommendation lists**.</span></span>
1. <span data-ttu-id="9e7a7-119">Establezca la opción **Habilitar personalización** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-119">Set the **Enable personalization** option to **Yes**.</span></span>

![Activación de la personalización](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="9e7a7-121">Cuando activa la personalización, se inicia el proceso de generar listas de recomendaciones de productos personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-121">When you turn on personalization, the process of generating personalized product recommendation lists is started.</span></span> <span data-ttu-id="9e7a7-122">Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en el PDV.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-122">Up to one day might be required before these lists are available and visible online and at the POS.</span></span>

## <a name="personalized-lists"></a><span data-ttu-id="9e7a7-123">Listas personalizadas</span><span class="sxs-lookup"><span data-stu-id="9e7a7-123">Personalized lists</span></span>

<span data-ttu-id="9e7a7-124">Además de permitir la personalización de las listas generadas por máquina existentes, el servicio de recomendaciones permite la personalización de la experiencia de detección de productos tanto en línea como en el PDV.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-124">In addition to allowing for personalization of existing machine-generated lists, the recommendations service allows for personalization of the product discovery experience both online and at the POS.</span></span>

<span data-ttu-id="9e7a7-125">Después de que se active la personalización, los minoristas pueden mostrar a los compradores listas personalizadas de "Picking para usted" o listas de "Recomendado para el cliente" en los terminales del PDV.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-125">After personalization is turned on, retailers can show shoppers personalized "Picks for you" lists online or "Recommended for customer" lists on POS terminals.</span></span> <span data-ttu-id="9e7a7-126">Además, los minoristas pueden aplicar la personalización a las listas de recomendaciones de productos existentes y proporcionar experiencias de exclusión voluntaria del Reglamento general de protección de datos (RGPD) para usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-126">Additionally, retailers can apply personalization to existing product recommendation lists and provide General Data Protection Regulation (GDPR) opt-out experiences for authenticated users.</span></span> <span data-ttu-id="9e7a7-127">Si desactiva la personalización, también desactiva estas características.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-127">If you turn off personalization, you also turn off these features.</span></span>

### <a name="online-picks-for-you-lists"></a><span data-ttu-id="9e7a7-128">Listas en línea de "Picking para usted"</span><span class="sxs-lookup"><span data-stu-id="9e7a7-128">Online "Picks for you" lists</span></span>

<span data-ttu-id="9e7a7-129">Una lista de "Picking para usted" es una lista de inteligencia artificial-aprendizaje automático (AI-ML) que muestra a un usuario autenticado una lista personalizada de productos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-129">A "Picks for you" list is an artificial intelligence-machine learning (AI-ML) list that shows an authenticated user a personalized list of suggested products.</span></span> <span data-ttu-id="9e7a7-130">Esta lista se basa en el historial de compras omnicanal del usuario.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-130">This list is based on the user's omnichannel purchase history.</span></span> <span data-ttu-id="9e7a7-131">Las recomendaciones personalizadas se actualizan dinámicamente a medida que el usuario realiza más compras.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-131">Personalized recommendations are dynamically updated as the user makes more purchases.</span></span> <span data-ttu-id="9e7a7-132">Este tipo de lista también admite el filtrado de categorías, para que los minoristas puedan mostrar las mejores opciones, en función de las jerarquías de navegación.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-132">This type of list also supports category filtering, so that retailers can show top picks, based on navigational hierarchies.</span></span>

<span data-ttu-id="9e7a7-133">Antes de que la lista "Picking para usted" pueda aparecer en cualquier página de comercio electrónico, se deben cumplir los siguientes requisitos de usuario:</span><span class="sxs-lookup"><span data-stu-id="9e7a7-133">Before the "Picks for you" list can appear on any e-Commerce page, the following user requirements must be met:</span></span>

- <span data-ttu-id="9e7a7-134">Los usuarios deben haber iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-134">Users must be signed in.</span></span> <span data-ttu-id="9e7a7-135">Los usuarios anónimos no verán recomendaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-135">Anonymous users won't see personalized recommendations.</span></span>
- <span data-ttu-id="9e7a7-136">Los usuarios deben tener al menos una compra en su cuenta.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-136">Users must have at least one purchase on their account.</span></span>
- <span data-ttu-id="9e7a7-137">Los usuarios deben optar por recibir recomendaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-137">Users must opt in to receive personalized recommendations.</span></span>

<span data-ttu-id="9e7a7-138">La siguiente ilustración muestra un ejemplo de una lista de "Picking para usted" en la página de una tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-138">The following illustration shows an example of a "Picks for you" list on an online store page.</span></span>

![Listas en línea de Picking para usted](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a><span data-ttu-id="9e7a7-140">Listas de "Recomendado para el cliente" en el PDV</span><span class="sxs-lookup"><span data-stu-id="9e7a7-140">"Recommended for customer" lists at the POS</span></span>

<span data-ttu-id="9e7a7-141">Para mejorar la experiencia de la relación con los clientes, los minoristas pueden personalizar las páginas de detalles de clientes existentes agregando una lista contextual "Recomendado para el cliente".</span><span class="sxs-lookup"><span data-stu-id="9e7a7-141">To enhance their clienteling experience, retailers can personalize existing customer details pages by adding a contextual "Recommended for customer" list.</span></span>

<span data-ttu-id="9e7a7-142">La siguiente ilustración muestra un ejemplo de una lista de "Recomendado para el cliente" en un terminal del PDV.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-142">The following illustration shows an example of a "Recommended for customer" list on a POS terminal.</span></span>

![Lista Recomendado para el cliente en el PDV](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a><span data-ttu-id="9e7a7-144">Aplicar personalización a listas de recomendaciones existentes</span><span class="sxs-lookup"><span data-stu-id="9e7a7-144">Apply personalization to existing recommendation lists</span></span>

<span data-ttu-id="9e7a7-145">Los minoristas pueden aplicar la personalización a listas de recomendaciones existentes, como "Nuevo", "Tendencias", "Más vendidos", "A la gente también le gustó" y "Los usuarios que compraron este artículo también compraron".</span><span class="sxs-lookup"><span data-stu-id="9e7a7-145">Retailers can apply personalization to existing recommendation lists, such as "New," "Trending," "Best selling," "People also like," and "Frequently bought together."</span></span> <span data-ttu-id="9e7a7-146">Cuando se aplica la personalización a las listas existentes, los elementos que compró previamente un usuario que haya iniciado sesión se eliminan de esas listas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-146">When personalization is applied to existing lists, items that a signed-in user previously bought are removed from those lists.</span></span> <span data-ttu-id="9e7a7-147">Tanto para usuarios anónimos como para usuarios que optaron por no recibir recomendaciones personalizadas, se muestran versiones predeterminadas de las listas existentes.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-147">For both anonymous users and users who opted out of receiving personalized recommendations, default versions of the existing lists are shown.</span></span> <span data-ttu-id="9e7a7-148">Por lo tanto, los minoristas no tienen que mantener manualmente experiencias de página independientes.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-148">Therefore, retailers don't have to manually maintain separate page experiences.</span></span>

<span data-ttu-id="9e7a7-149">Por ejemplo, un usuario que haya iniciado sesión ya compró el reloj negro y las botas de trabajo marrones que aparecen en la lista "Tendencias - predeterminado" en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-149">For example, a signed-in user has already bought the black watch and the brown work boots that appear in the "Trending - default" list in the following illustration.</span></span> <span data-ttu-id="9e7a7-150">Por lo tanto, el usuario verá nuevos productos en lugar de esos, como se muestra en la lista "Tendencias - personalizado".</span><span class="sxs-lookup"><span data-stu-id="9e7a7-150">Therefore, the user will see new products instead of those products, as shown in the "Trending - personalized" list.</span></span>

![Aplicación de la personalización](./media/applypersonalization.png)

<span data-ttu-id="9e7a7-152">Para aplicar la personalización a una lista de recomendaciones existente en el generador de sitios de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-152">To apply personalization to an existing recommendation list in the Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="9e7a7-153">Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de colección de productos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-153">Open an existing site builder page that contains a product collection module.</span></span>
1. <span data-ttu-id="9e7a7-154">En el panel de navegación de la izquierda, seleccione el módulo de colección de productos.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-154">In the left navigation pane, select the product collection module.</span></span>
1. <span data-ttu-id="9e7a7-155">En el panel de navegación de la derecha, debajo de **Productos**, seleccione la lista.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-155">In the right navigation pane, under **Products**, select the list.</span></span>
1. <span data-ttu-id="9e7a7-156">En el cuadro de diálogo **Seleccionar la configuración de la lista de productos**, debajo de **Tipo**, seleccione el tipo de lista.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-156">In the **Select product list configuration** dialog box, under **Type**, select the list type.</span></span>
1. <span data-ttu-id="9e7a7-157">Selecciona la casilla **Aplicar personalización** y luego elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-157">Select the **Apply Personalization** check box, and then select **OK**.</span></span>

    ![Aplicación de la personalización a una lista de tendencias](./media/ApplyPersonalizationToTrending.PNG)

1. <span data-ttu-id="9e7a7-159">Guarde la página, termine de editarla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-159">Save the page, finish editing it, and then publish it.</span></span> <span data-ttu-id="9e7a7-160">Una vez publicada la página, los usuarios que hayan iniciado sesión verán listas de tendencias personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9e7a7-160">After the page is published, signed-in users will see personalized trending lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e7a7-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9e7a7-161">Additional resources</span></span>

[<span data-ttu-id="9e7a7-162">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="9e7a7-162">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9e7a7-163">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9e7a7-163">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="9e7a7-164">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="9e7a7-164">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9e7a7-165">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9e7a7-165">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9e7a7-166">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="9e7a7-166">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9e7a7-167">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="9e7a7-167">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="9e7a7-168">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="9e7a7-168">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9e7a7-169">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="9e7a7-169">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9e7a7-170">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="9e7a7-170">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9e7a7-171">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="9e7a7-171">Product recommendations FAQ</span></span>](faq-recommendations.md)
