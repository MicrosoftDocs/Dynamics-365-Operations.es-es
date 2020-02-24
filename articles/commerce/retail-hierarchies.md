---
title: Jerarquías comerciales
description: Este artículo describe jerarquías comerciales de Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cf8db2c828f99dfd4c220966e31894dcd6eda572
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023969"
---
# <a name="retail-hierarchies"></a><span data-ttu-id="2b64e-103">Jerarquías comerciales</span><span class="sxs-lookup"><span data-stu-id="2b64e-103">Retail hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b64e-104">Este artículo describe jerarquías de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b64e-104">This article describes hierarchies in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2b64e-105">Puede crear una jerarquía de categoría para organizar los productos que vende a través de los canales.</span><span class="sxs-lookup"><span data-stu-id="2b64e-105">You can create a category hierarchy to organize the products that you sell through your channels.</span></span> <span data-ttu-id="2b64e-106">Puede usar jerarquías de productos para categorizar o agrupar productos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-106">You can use product hierarchies to categorize or group products.</span></span> <span data-ttu-id="2b64e-107">Puede usar estos productos para crear selecciones de productos y programas de fidelización de clientes.</span><span class="sxs-lookup"><span data-stu-id="2b64e-107">You can then use these products to create product assortments and customer loyalty programs.</span></span> <span data-ttu-id="2b64e-108">También puede asignar propiedades y atributos de productos, asignar una estructura de precios, incluir los productos en las promociones de producto y usar los productos para crear informes.</span><span class="sxs-lookup"><span data-stu-id="2b64e-108">You can also assign product attributes and properties, assign a pricing structure, include the products in product promotions, and use the products for reporting.</span></span> <span data-ttu-id="2b64e-109">Puede crear una jerarquía de categoría para representar todos los productos y categorías de la organización y, a continuación, usar esa jerarquía de categoría para varios propósitos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-109">You can create one category hierarchy to represent all the products and categories in your organization, and then use that category hierarchy for multiple purposes.</span></span> <span data-ttu-id="2b64e-110">Como alternativa, puede crear varias jerarquías de categoría para fines especiales, tales como promociones de productos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-110">Alternatively, you can create multiple category hierarchies for special purposes, such as product promotions.</span></span> <span data-ttu-id="2b64e-111">Al crear una jerarquía de productos, debe asignar un tipo de jerarquía de categoría para identificar el propósito de la jerarquía de categoría.</span><span class="sxs-lookup"><span data-stu-id="2b64e-111">When you create a product hierarchy, you must assign a category hierarchy type to identify the purpose of the category hierarchy.</span></span> <span data-ttu-id="2b64e-112">Por ejemplo, solo se hace referencia a las jerarquías de productos que tienen el tipo **Jerarquía de navegación de Commerce** asignado al examinar productos por categoría en línea o en el punto de venta (POS).</span><span class="sxs-lookup"><span data-stu-id="2b64e-112">For example, only product hierarchies that are assigned the **Commerce navigation hierarchy** type are referenced when you browse products by category online or in point of sale (POS).</span></span>

## <a name="hierarchy-types"></a><span data-ttu-id="2b64e-113">Tipos de jerarquía</span><span class="sxs-lookup"><span data-stu-id="2b64e-113">Hierarchy types</span></span>

<span data-ttu-id="2b64e-114">La siguiente tabla enumera los tipos de jerarquías de categorías disponibles y los fines generales de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="2b64e-114">The following table lists the types of category hierarchies that are available and the general purpose of each type.</span></span>

| <span data-ttu-id="2b64e-115">Tipo de jerarquía de categorías</span><span class="sxs-lookup"><span data-stu-id="2b64e-115">Category hierarchy type</span></span>       | <span data-ttu-id="2b64e-116">Propósito</span><span class="sxs-lookup"><span data-stu-id="2b64e-116">Purpose</span></span> |
|-------------------------------|---------|
| <span data-ttu-id="2b64e-117">Jerarquía de productos</span><span class="sxs-lookup"><span data-stu-id="2b64e-117">Product hierarchy</span></span>      | <span data-ttu-id="2b64e-118">Use este tipo de jerarquía para definir la jerarquía de productos general para su organización.</span><span class="sxs-lookup"><span data-stu-id="2b64e-118">Use this hierarchy type to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="2b64e-119">Puede utilizar este tipo de jerarquía para comercialización, precios y promociones, informes y planificación de selecciones.</span><span class="sxs-lookup"><span data-stu-id="2b64e-119">You can use this hierarchy type for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="2b64e-120">Solo se puede asignar una jerarquía de productos a este tipo de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="2b64e-120">Only one product hierarchy can be assigned this hierarchy type.</span></span> |
| <span data-ttu-id="2b64e-121">Jerarquía complementaria</span><span class="sxs-lookup"><span data-stu-id="2b64e-121">Supplemental hierarchy</span></span> | <span data-ttu-id="2b64e-122">Utilice este tipo de la jerarquía para cualquier jerarquía de categoría adicional que desee crear.</span><span class="sxs-lookup"><span data-stu-id="2b64e-122">Use this hierarchy type for any additional category hierarchies that you want to create.</span></span> <span data-ttu-id="2b64e-123">Por ejemplo, en primavera, tiene una promoción de bañadores.</span><span class="sxs-lookup"><span data-stu-id="2b64e-123">For example, in the spring, you have a promotion for swimwear.</span></span> <span data-ttu-id="2b64e-124">Por lo tanto, incluye sus productos de baño en una jerarquía de categoría independiente y aplica el precio promocional a las distintas categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-124">Therefore, you include your swimwear products in a separate category hierarchy and apply the promotional pricing to the various product categories.</span></span> |
| <span data-ttu-id="2b64e-125">Jerarquía de navegación</span><span class="sxs-lookup"><span data-stu-id="2b64e-125">Navigation hierarchy</span></span>   | <span data-ttu-id="2b64e-126">Use este tipo de jerarquía para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta.</span><span class="sxs-lookup"><span data-stu-id="2b64e-126">Use this hierarchy type to group and organize products into categories so that the products can be browsed online or in POS.</span></span> |

<span data-ttu-id="2b64e-127">Si utiliza una jerarquía de categorías para dar estructura a sus productos, podrá configurar y mantener las propiedades y los atributos de los productos en el nivel de la categoría.</span><span class="sxs-lookup"><span data-stu-id="2b64e-127">By using a category hierarchy to structure your products, you can set up and maintain product attributes and properties at the category level.</span></span> <span data-ttu-id="2b64e-128">Estas propiedades y atributos incluyen valores para la configuración del punto de venta y las dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-128">These attributes and properties include settings for product dimensions and POS settings.</span></span> <span data-ttu-id="2b64e-129">Cualquier producto que asigne a las categorías heredará automáticamente las propiedades y los atributos definidos.</span><span class="sxs-lookup"><span data-stu-id="2b64e-129">Any products that you assign to the categories automatically inherit the attributes and properties that you define.</span></span> <span data-ttu-id="2b64e-130">También puede copiar la configuración de propiedad de cualquier producto en varios productos de una categoría seleccionada al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="2b64e-130">You can also copy the property settings for any product to multiple products in a selected category at the same time.</span></span>
