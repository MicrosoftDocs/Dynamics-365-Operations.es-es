---
title: Habilitar recomendaciones de producto
description: Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024965"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="e3c81-103">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="e3c81-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e3c81-104">Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e3c81-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="e3c81-105">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e3c81-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="e3c81-106">Recomendaciones previas a la comprobación</span><span class="sxs-lookup"><span data-stu-id="e3c81-106">Recommendations pre-check</span></span>

<span data-ttu-id="e3c81-107">Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="e3c81-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="e3c81-108">Para conocer los pasos para habilitar ADLS, vea [Cómo habilitar ADLS en un entorno de Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e3c81-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="e3c81-109">Además, asegúrese de que se han habilitado las medidas de RetailSale.</span><span class="sxs-lookup"><span data-stu-id="e3c81-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="e3c81-110">Para obtener más información acerca de este proceso de configuración, vaya [aquí.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="e3c81-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="e3c81-111">Activar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="e3c81-111">Turn on recommendations</span></span>

<span data-ttu-id="e3c81-112">Para activar recomendaciones de productos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e3c81-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="e3c81-113">Vaya a **Retail y Commerce &gt; Recomendaciones de producto &gt; Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="e3c81-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="e3c81-114">En la lista de parámetros compartidos, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="e3c81-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="e3c81-115">Establezca la opción **Habilitar recomendaciones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e3c81-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![habilitar recomendaciones de producto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="e3c81-117">Este procedimiento inicia el proceso de generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="e3c81-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="e3c81-118">Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e3c81-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="e3c81-119">Configurar parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="e3c81-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="e3c81-120">De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="e3c81-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="e3c81-121">Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio.</span><span class="sxs-lookup"><span data-stu-id="e3c81-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="e3c81-122">Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="e3c81-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="e3c81-123">Mostrar recomendaciones en dispositivos PDV</span><span class="sxs-lookup"><span data-stu-id="e3c81-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="e3c81-124">Tras habilitar recomendaciones en la oficina administrativa de Commerce, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño.</span><span class="sxs-lookup"><span data-stu-id="e3c81-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="e3c81-125">Para conocer este proceso, vea [Agregar un control de recomendaciones a la pantalla de transacciones en dispositivos de PDV](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="e3c81-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="e3c81-126">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="e3c81-126">Enable personalized recommendations</span></span>

<span data-ttu-id="e3c81-127">Para obtener más información sobre cómo recibir recomendaciones personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e3c81-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e3c81-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e3c81-128">Additional resources</span></span>

[<span data-ttu-id="e3c81-129">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="e3c81-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="e3c81-130">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="e3c81-130">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="e3c81-131">Agregar listas de recomendaciones a páginas</span><span class="sxs-lookup"><span data-stu-id="e3c81-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="e3c81-132">Para agregar el panel de recomendaciones a dispositivos de PDV</span><span class="sxs-lookup"><span data-stu-id="e3c81-132">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="e3c81-133">Visión general del módulo de colección de productos</span><span class="sxs-lookup"><span data-stu-id="e3c81-133">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="e3c81-134">Habilitar ADLS en el entorno de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e3c81-134">Enable ADLS in Dynamics 365 environment</span></span>](enable-ADLS-environment.md)

