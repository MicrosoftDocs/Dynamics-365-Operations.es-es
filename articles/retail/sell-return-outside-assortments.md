---
title: Vender y devolver productos fuera de un surtido
description: Con Dynamics 365 for Retail, se puede vender y devolver productos de los surtidos.
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 418ee6136a5a02d343828d8eb33b1e37325e2918
ms.contentlocale: es-es
ms.lasthandoff: 01/19/2018

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="fb3ec-103">Vender y devolver productos fuera de un surtido</span><span class="sxs-lookup"><span data-stu-id="fb3ec-103">Sell and return products outside of an assortment</span></span>
<span data-ttu-id="fb3ec-104">Un escenario común para cualquier minorista es vender productos a sus clientes o aceptar devoluciones de sus clientes aunque no contienen productos concretos en su tienda (es decir los productos no se sirven a la tienda).</span><span class="sxs-lookup"><span data-stu-id="fb3ec-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="fb3ec-105">Aquí hay algunas situaciones habituales:</span><span class="sxs-lookup"><span data-stu-id="fb3ec-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="fb3ec-106">Un minorista no vende todos sus productos en una tienda específica.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="fb3ec-107">Los productos restantes se almacenan en el almacén.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="fb3ec-108">El dependiente puede ayudar al cliente buscando los productos en el almacén, agregarlos al carro, y completar la compra seleccionando un método de entrega, como envío a una dirección desde el almacén o dejar que el cliente recoja el artículo de la tienda actual o de otra tienda.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="fb3ec-109">Un minorista no vende productos específicos en la tienda o no los tiene en existencias en la tienda visitada por el cliente, pero los productos están disponibles en otras tiendas.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="fb3ec-110">El dependiente puede ayudar al cliente buscando los productos en otra tienda, agregarlos al carro y completar la compra seleccionando un método de entrega.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="fb3ec-111">Un minorista tiene muchas tiendas en una ciudad o un código postal específicos y no desea exigir a los clientes que devuelvan productos a la misma tienda en la que los compraron.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="fb3ec-112">En lugar de ello, los clientes pueden devolver productos a cualquier tienda.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="fb3ec-113">Esos escenarios comunes están disponibles para los minoristas mediante Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="fb3ec-114">Con Retail, puede:</span><span class="sxs-lookup"><span data-stu-id="fb3ec-114">With Retail, you can:</span></span>
+ <span data-ttu-id="fb3ec-115">Buscar o examinar productos en otras tiendas.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="fb3ec-116">Buscar o examinar todos los productos ofertados.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="fb3ec-117">Crear transacciones al contado o pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="fb3ec-118">Seleccionar las opciones de entrega para los pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="fb3ec-119">Recoger los productos en la tienda actual o en otra tienda.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="fb3ec-120">Cancelar un pedido en la tienda actual o en otra tienda.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="fb3ec-121">Devolver un pedido con o sin el tique en la tienda actual o en otra tienda.</span><span class="sxs-lookup"><span data-stu-id="fb3ec-121">Return an order with or without the receipt at the current store or another store.</span></span>

