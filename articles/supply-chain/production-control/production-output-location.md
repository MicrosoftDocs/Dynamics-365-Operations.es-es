---
title: Ubicación de salida de producción
description: Este tema describe la jerarquía que se usa para identificar la ubicación de salida de producción.
author: johanhoffmann
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8fa4f7d844c178ee603778fa2f1def6bfc33db97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209452"
---
# <a name="production-output-location"></a><span data-ttu-id="29913-103">Ubicación de salida de producción</span><span class="sxs-lookup"><span data-stu-id="29913-103">Production output location</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29913-104">Este tema describe la jerarquía que se usa para identificar la ubicación de salida de producción.</span><span class="sxs-lookup"><span data-stu-id="29913-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="29913-105">La ubicación de salida de producción es la ubicación en la que un producto terminado se almacena por primera vez después de que produzca.</span><span class="sxs-lookup"><span data-stu-id="29913-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="29913-106">Normalmente, esta ubicación está cerca del proceso de producción que produce el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="29913-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="29913-107">La ubicación de salida de producción se usa como almacenamiento intermedio para el material antes de que se traslade al área de envío, una ubicación de almacenamiento, una ubicación de entrada de producción para un proceso de producción descendente, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="29913-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="29913-108">Una ubicación de salida de producción predeterminada se establece cuando el producto terminado se notifica en un pedido de producción o un pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="29913-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="29913-109">La siguiente jerarquía se usa para identificar esta ubicación de salida:</span><span class="sxs-lookup"><span data-stu-id="29913-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="29913-110">Use la ubicación de salida que se define en el encabezado del pedido de producción o pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="29913-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="29913-111">Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el recurso que utiliza la última operación definida en la ruta de producción.</span><span class="sxs-lookup"><span data-stu-id="29913-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="29913-112">Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el grupo de recursos que utiliza el recurso para la última operación definida en la ruta de producción.</span><span class="sxs-lookup"><span data-stu-id="29913-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="29913-113">Si no encuentra ninguna ubicación ahí, use la ubicación de salida definida en el almacén definido para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="29913-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="29913-114">Una ubicación de salida de producción predeterminada se establece únicamente para productos que se configuran mediante procesos de almacén avanzados.</span><span class="sxs-lookup"><span data-stu-id="29913-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="29913-115">Cuando este tipo de artículo se notifica como finalizado, se crea el trabajo de almacén del tipo **Ubicación de bienes terminados** o **Ubicación de coproducto y producto derivado**.</span><span class="sxs-lookup"><span data-stu-id="29913-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="29913-116">Este tipo de trabajo usa la ubicación de salida de producción como la ubicación de selección.</span><span class="sxs-lookup"><span data-stu-id="29913-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="29913-117">La localización de ubicació viene determinada por las directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="29913-117">The put-away location is determined by the location directives.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]