---
title: Configurar los impuestos para pedidos en línea
description: Este tema proporciona una descripción general de la selección de grupos de impuestos para diferentes tipos de pedidos en línea en Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031798"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="87a79-103">Configurar los impuestos para pedidos en línea</span><span class="sxs-lookup"><span data-stu-id="87a79-103">Configure sales tax for online orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87a79-104">Este tema proporciona una descripción general de la selección de grupos de impuestos para diferentes tipos de pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="87a79-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="87a79-105">Es posible que su canal de comercio electrónico desee admitir opciones como la entrega o la recogida para pedidos en línea.</span><span class="sxs-lookup"><span data-stu-id="87a79-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="87a79-106">La aplicabilidad de los impuestos se basa en la opción seleccionada por sus usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="87a79-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="87a79-107">Cuando un cliente del sitio elige comprar un artículo en línea y lo envía a una dirección, el impuesto se determina según la configuración del grupo de impuestos de la dirección de envío del cliente.</span><span class="sxs-lookup"><span data-stu-id="87a79-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="87a79-108">Cuando un cliente opta por recoger un artículo comprado en una tienda, el impuesto se determina según la configuración del grupo de impuestos de la tienda de recogida.</span><span class="sxs-lookup"><span data-stu-id="87a79-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="87a79-109">Pedidos enviados a la dirección de un cliente</span><span class="sxs-lookup"><span data-stu-id="87a79-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="87a79-110">En general, los impuestos para los pedidos en línea que se envían a las direcciones de los clientes quedan definidos según el destino.</span><span class="sxs-lookup"><span data-stu-id="87a79-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="87a79-111">Cada grupo de impuestos sobre tiene una configuración del impuesto basada en el destino comercial donde su empresa puede definir detalles de destino como provincia, región, estado, localidad y ciudad en una forma jerárquica.</span><span class="sxs-lookup"><span data-stu-id="87a79-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="87a79-112">Cuando se realiza un pedido en línea, el motor de impuestos de Commerce utiliza la dirección de entrega de cada artículo de línea del pedido y busca grupos de impuestos que coincidan con los criterios de impuestos basados en el destino.</span><span class="sxs-lookup"><span data-stu-id="87a79-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="87a79-113">Por ejemplo, para un pedido en línea con una dirección de entrega de artículos de línea para San Francisco, California, el motor de impuestos buscará el grupo de impuestos y el código de impuestos para California y luego calculará los impuestos para cada artículo de línea en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="87a79-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="87a79-114">Grupos de impuestos basados en el cliente</span><span class="sxs-lookup"><span data-stu-id="87a79-114">Customer-based tax groups</span></span>

<span data-ttu-id="87a79-115">En la sede central de Commerce, hay dos lugares donde se configuran los grupos de impuestos de clientes:</span><span class="sxs-lookup"><span data-stu-id="87a79-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="87a79-116">**Perfil del cliente**</span><span class="sxs-lookup"><span data-stu-id="87a79-116">**Customer's profile**</span></span>
- <span data-ttu-id="87a79-117">**Dirección de envío del cliente**</span><span class="sxs-lookup"><span data-stu-id="87a79-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="87a79-118">Si el perfil de un cliente tiene un grupo fiscal configurado</span><span class="sxs-lookup"><span data-stu-id="87a79-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="87a79-119">El registro del perfil de un cliente en la sede central puede tener configurado un grupo de impuestos; sin embargo, para los pedidos en línea, el motor de impuestos no utilizará el grupo de impuestos configurado en el perfil de un cliente.</span><span class="sxs-lookup"><span data-stu-id="87a79-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="87a79-120">Si la dirección de envío de un cliente tiene un grupo fiscal configurado</span><span class="sxs-lookup"><span data-stu-id="87a79-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="87a79-121">Si el registro de la dirección de envío de un cliente tiene un grupo de impuestos configurado y un pedido en línea (o artículo de línea) se envía a la dirección de envío del cliente, el motor de impuestos utilizará el grupo de impuestos configurado en el registro de la dirección del cliente para los cálculos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="87a79-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="87a79-122">Configurar un grupo fiscal para el registro de la dirección de envío de un cliente</span><span class="sxs-lookup"><span data-stu-id="87a79-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="87a79-123">Para configurar un grupo de impuestos para el registro de la dirección de envío de un cliente en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="87a79-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="87a79-124">Vaya a **Todos los clientes** y luego seleccione el cliente deseado.</span><span class="sxs-lookup"><span data-stu-id="87a79-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="87a79-125">En la ficha desplegable **Direcciones**, seleccione la dirección deseada y luego seleccione **Más opciones \> Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="87a79-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="87a79-126">En la pestaña **General** en la página **Administrar direcciones**, configure el valor del impuesto según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="87a79-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="87a79-127">El grupo de impuestos se define utilizando la dirección de entrega de la línea de pedido y los impuestos basados en el destino se configuran en el propio grupo fiscal.</span><span class="sxs-lookup"><span data-stu-id="87a79-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="87a79-128">Para más información, vea [Configurar impuestos para tiendas en línea según el destino](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="87a79-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="87a79-129">Recogida de pedidos en tienda</span><span class="sxs-lookup"><span data-stu-id="87a79-129">Order pickup in store</span></span>

<span data-ttu-id="87a79-130">Para las líneas de pedido con recogida en la tienda o recogida en un punto de entrega especificado, se aplicará el grupo fiscal de la tienda de recogida seleccionada.</span><span class="sxs-lookup"><span data-stu-id="87a79-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="87a79-131">Para obtener detalles sobre cómo configurar el grupo fiscal para una tienda determinada, consulte [Establecer otras opciones de impuestos para tiendas](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="87a79-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="87a79-132">Cuando se recoge una línea de pedido en una tienda, el motor de impuestos ignorará la configuración de impuestos de la dirección de un cliente (si está configurada) y se aplicará la configuración de impuestos de la tienda de recogida.</span><span class="sxs-lookup"><span data-stu-id="87a79-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="87a79-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87a79-133">Additional resources</span></span>

[<span data-ttu-id="87a79-134">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="87a79-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="87a79-135">Métodos de cálculo de impuestos en el campo Origen</span><span class="sxs-lookup"><span data-stu-id="87a79-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="87a79-136">Asignación de impuestos y anulaciones</span><span class="sxs-lookup"><span data-stu-id="87a79-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="87a79-137">Importe completo y opciones de cálculo de Intervalo para los códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="87a79-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="87a79-138">Cálculo de exención de impuestos</span><span class="sxs-lookup"><span data-stu-id="87a79-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 

