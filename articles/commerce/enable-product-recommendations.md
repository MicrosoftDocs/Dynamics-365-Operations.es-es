---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127891"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="51b4e-103">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="51b4e-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="51b4e-104">Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="51b4e-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="51b4e-105">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="51b4e-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="51b4e-106">Recomendaciones previas a la comprobación</span><span class="sxs-lookup"><span data-stu-id="51b4e-106">Recommendations pre-check</span></span>

<span data-ttu-id="51b4e-107">Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="51b4e-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="51b4e-108">Para conocer los pasos para habilitar ADLS, vea [Cómo habilitar ADLS en un entorno de Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="51b4e-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="51b4e-109">Además, asegúrese de que se han habilitado las medidas de RetailSale.</span><span class="sxs-lookup"><span data-stu-id="51b4e-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="51b4e-110">Para obtener más información acerca de este proceso de configuración, vaya [aquí.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="51b4e-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="51b4e-111">Activar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="51b4e-111">Turn on recommendations</span></span>

<span data-ttu-id="51b4e-112">Para activar recomendaciones de productos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="51b4e-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="51b4e-113">Vaya a **Retail y Commerce &gt; Recomendaciones de producto &gt; Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="51b4e-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="51b4e-114">En la lista de parámetros compartidos, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="51b4e-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="51b4e-115">Establezca la opción **Habilitar recomendaciones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="51b4e-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![habilitar recomendaciones de producto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="51b4e-117">Este procedimiento inicia el proceso de generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="51b4e-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="51b4e-118">Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="51b4e-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="51b4e-119">Configurar parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="51b4e-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="51b4e-120">De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="51b4e-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="51b4e-121">Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio.</span><span class="sxs-lookup"><span data-stu-id="51b4e-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="51b4e-122">Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="51b4e-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="51b4e-123">Mostrar recomendaciones en dispositivos PDV</span><span class="sxs-lookup"><span data-stu-id="51b4e-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="51b4e-124">Tras habilitar recomendaciones en la oficina administrativa de Commerce, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño.</span><span class="sxs-lookup"><span data-stu-id="51b4e-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="51b4e-125">Para conocer este proceso, vea [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="51b4e-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="51b4e-126">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="51b4e-126">Enable personalized recommendations</span></span>

<span data-ttu-id="51b4e-127">Para obtener más información sobre cómo recibir recomendaciones personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="51b4e-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51b4e-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="51b4e-128">Additional resources</span></span>

[<span data-ttu-id="51b4e-129">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="51b4e-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="51b4e-130">Habilitar ADLS en un entorno de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="51b4e-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="51b4e-131">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="51b4e-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="51b4e-132">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="51b4e-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="51b4e-133">Agregar listas de recomendaciones de producto a un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="51b4e-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="51b4e-134">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="51b4e-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="51b4e-135">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="51b4e-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="51b4e-136">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="51b4e-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="51b4e-137">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="51b4e-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="51b4e-138">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="51b4e-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="51b4e-139">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="51b4e-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

