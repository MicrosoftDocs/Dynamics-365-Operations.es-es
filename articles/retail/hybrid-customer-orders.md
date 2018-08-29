---
title: "Pedidos de cliente híbridos"
description: "Un pedido híbrido de cliente es pedido único que contiene al mismo tiempo productos que el cliente puede llevarse y otros que pueden recogerse o enviarse después."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 88d12641fa05953f7082158303237b7ba40c3fe2
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="hybrid-customer-orders"></a><span data-ttu-id="68d63-103">Pedidos de cliente híbridos</span><span class="sxs-lookup"><span data-stu-id="68d63-103">Hybrid customer orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="68d63-104">Un pedido híbrido de cliente es pedido único que contiene al mismo tiempo productos que el cliente puede llevarse y otros que pueden recogerse o enviarse después.</span><span class="sxs-lookup"><span data-stu-id="68d63-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="68d63-105">En Microsoft Dynamics 365 for Retail, puede seleccionar enviar todos los productos o enviar solo los productos seleccionados de un pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="68d63-105">In Microsoft Dynamics 365 for Retail, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="68d63-106">Las líneas de productos marcadas para llevar a cabo se facturan automáticamente después de crear el pedido. Es lo mismo que sucede para un pedido que va a recoger después de crear el pedido.</span><span class="sxs-lookup"><span data-stu-id="68d63-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="68d63-107">El importe pendiente de pago en pedidos híbridos se determina agregando el porcentaje de depósito en las líneas de recogida y envío de productos con el importe total de las líneas finalizadas.</span><span class="sxs-lookup"><span data-stu-id="68d63-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="68d63-108">Para los pedidos híbridos, el sistema alterna entre el modo de pedido de cliente y el modo de pago en efectivo sin entrega a domicilio, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="68d63-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

-   <span data-ttu-id="68d63-109">Si todos los productos del carro se definen como **Ejecutar entrega**, el pedido se gestionará como una transacción al contado sin entrega a domicilio.</span><span class="sxs-lookup"><span data-stu-id="68d63-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
-   <span data-ttu-id="68d63-110">Si alguna de las líneas del carro está definida como **Recogida** o **Envío**, el pedido será gestionado como una transacción de pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="68d63-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="68d63-111">Si hay una línea del carro definida como **Recoger selección**, **Enviar selección** o **Ejecutar selección**, solo se definirá con ese método de entrega la línea específica del carro.</span><span class="sxs-lookup"><span data-stu-id="68d63-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="68d63-112">En ese caso, el flujo descendente de la operación continúa de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="68d63-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="68d63-113">Sin embargo, si se elige **Recoger selección**, **Enviar selección** o **Ejecutar selección** sin haber seleccionado ninguna línea, se abre una nueva página que enumera todas las líneas del carro.</span><span class="sxs-lookup"><span data-stu-id="68d63-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="68d63-114">En esa pantalla, puede seleccionar varias líneas inmediatamente para definir el método de entrega.</span><span class="sxs-lookup"><span data-stu-id="68d63-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="68d63-115">Al utilizar este método para seleccionar líneas, se sustituirá cualquier método de entrega anterior que se hubiera asignado a la línea.</span><span class="sxs-lookup"><span data-stu-id="68d63-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

<a name="additional-resources"></a><span data-ttu-id="68d63-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="68d63-116">Additional resources</span></span>
--------

[<span data-ttu-id="68d63-117">Visión general de pedidos de cliente</span><span class="sxs-lookup"><span data-stu-id="68d63-117">Customer orders overview</span></span>](customer-orders-overview.md)




