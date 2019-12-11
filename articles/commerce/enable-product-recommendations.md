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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770148"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="f3233-103">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="f3233-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f3233-104">Este tema explica cómo hacer recomendaciones de productos que se basan en la inteligencia artificial-aprendizaje automático (AI-ML) disponible para clientes de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3233-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="f3233-105">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="f3233-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="f3233-106">Recomendaciones previas a la comprobación</span><span class="sxs-lookup"><span data-stu-id="f3233-106">Recommendations pre-check</span></span>
<span data-ttu-id="f3233-107">Antes de habilitar, tenga en cuenta que las recomendaciones de productos solo se admiten para clientes de F&O que admiten la compilación 10.0.6 y han migrado su almacenamiento para usar BDL.</span><span class="sxs-lookup"><span data-stu-id="f3233-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="f3233-108">Además, asegúrese de que se han habilitado las medidas de RetailSale.</span><span class="sxs-lookup"><span data-stu-id="f3233-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="f3233-109">Para obtener más información acerca de este proceso de configuración, vaya [aquí.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="f3233-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="f3233-110">Activar recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f3233-110">Turn on recommendations</span></span>

<span data-ttu-id="f3233-111">Para activar recomendaciones de productos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f3233-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="f3233-112">Vaya a **Retail** &gt; **Recomendaciones de producto** &gt; **Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="f3233-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="f3233-113">En la lista de parámetros compartidos comerciales, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="f3233-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="f3233-114">Establezca la opción **Habilitar recomendaciones** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f3233-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![habilitar recomendaciones de producto](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="f3233-116">Este procedimiento inicia el proceso de generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="f3233-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="f3233-117">Es posible que se requieran varias horas antes de que las listas estén disponibles y puedan verse en el punto de venta (PDV) o en Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3233-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="f3233-118">Configurar parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="f3233-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="f3233-119">De forma predeterminada, la lista de recomendaciones de productos según AI-ML ofrece valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="f3233-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="f3233-120">Puede cambiar los valores sugeridos predeterminados para adaptarlos al flujo de su negocio.</span><span class="sxs-lookup"><span data-stu-id="f3233-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="f3233-121">Para obtener más información acerca de cómo cambiar los parámetros predeterminados, vaya a [Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="f3233-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="f3233-122">Mostrar recomendaciones en dispositivos PDV</span><span class="sxs-lookup"><span data-stu-id="f3233-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="f3233-123">Tras habilitar recomendaciones en la oficina administrativa, el panel de recomendaciones se debe agregar a la pantalla de PDV de control mediante la herramienta de diseño.</span><span class="sxs-lookup"><span data-stu-id="f3233-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="f3233-124">Para obtener información acerca de este proceso, vaya [aquí.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="f3233-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="f3233-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f3233-125">Additional resources</span></span>

[<span data-ttu-id="f3233-126">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="f3233-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="f3233-127">Agregar listas de recomendaciones a páginas</span><span class="sxs-lookup"><span data-stu-id="f3233-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="f3233-128">Para agregar el panel de recomendaciones a dispositivos de PDV</span><span class="sxs-lookup"><span data-stu-id="f3233-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


