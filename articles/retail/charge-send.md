---
title: Enviar un pedido de otra tienda
description: "Este tema describe la característica de envío Cargo."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 7612935c42ee7b28e1d1e24b22801e31114dc675
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---

# <a name="ship-an-order-from-a-different-store"></a><span data-ttu-id="0a415-103">Enviar un pedido de otra tienda</span><span class="sxs-lookup"><span data-stu-id="0a415-103">Ship an order from a different store</span></span>

<span data-ttu-id="0a415-104">Con la característica de envío Cargo de Dynamics 365 for Retail, los pedidos del cliente se pueden realizar en una tienda y enviar desde otra tienda.</span><span class="sxs-lookup"><span data-stu-id="0a415-104">With the Charge send feature in Dynamics 365 for Retail, customer orders can be placed in one store and shipped from another store.</span></span> <span data-ttu-id="0a415-105">Los pedidos de clientes en el cliente de punto de venta (PDV) admiten varias opciones de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0a415-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="0a415-106">Algunos ejemplos de opciones de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="0a415-106">Some examples of fulfillment options include:</span></span>
-   <span data-ttu-id="0a415-107">Recogida en la misma tienda en otra fecha.</span><span class="sxs-lookup"><span data-stu-id="0a415-107">Pick up from the same store on a different date.</span></span>
-   <span data-ttu-id="0a415-108">Recogida en la misma tienda en la misma o en otra fecha.</span><span class="sxs-lookup"><span data-stu-id="0a415-108">Pick up from a different store on the same date or a different date.</span></span>
-   <span data-ttu-id="0a415-109">Envío del almacén de envío predeterminado que está asignado a la tienda, y entrega en una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="0a415-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="0a415-110">La característica de envío Cargo utiliza las siguientes operaciones de PDV: Envío de todos los productos y Envío de productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="0a415-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="0a415-111">Esto permite que el empleado de la tienda seleccione el “envío desde" la ubicación desde la que se puede cumplir el pedido o la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="0a415-111">This allows the store clerk to select the “ship from” location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="0a415-112">De forma predeterminada, la ubicación de “envío desde" es el almacén de envío asociado al almacén.</span><span class="sxs-lookup"><span data-stu-id="0a415-112">By default, the “ship from” location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="0a415-113">Sin embargo, el empleado de la tienda puede cambiar esta ubicación y seleccionar cualquier tienda que esté definida en el grupo de localizadores de tiendas asignado a la tienda.</span><span class="sxs-lookup"><span data-stu-id="0a415-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span> 

<span data-ttu-id="0a415-114">La capacidad para seleccionar direcciones de “envío a” se mantiene sin cambio.</span><span class="sxs-lookup"><span data-stu-id="0a415-114">The ability to select “ship to” addresses remains unchanged.</span></span> 

<span data-ttu-id="0a415-115">Los métodos de envío que se pueden usar para cumplir la línea de pedido se basan en la configuración de modos válidos de entrega de productos y direcciones.</span><span class="sxs-lookup"><span data-stu-id="0a415-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="0a415-116">Dado que las reglas sobre modos válidos de entrega sólo se mantienen en Central Retail, el cliente de PDV realiza una llamada en tiempo real para capturar los modos de entrega válidos para una línea de envío.</span><span class="sxs-lookup"><span data-stu-id="0a415-116">Because the rules about valid of modes of delivery are maintained only in the Retail headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span> 


