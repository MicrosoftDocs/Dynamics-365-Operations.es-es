---
title: Los impuestos sobre los pedidos en línea se calculan incorrectamente
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los impuestos sobre los pedidos en línea se calculan incorrectamente o cuando el grupo de impuestos en la línea de ventas no está configurado correctamente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021112"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="c25eb-103">Los impuestos sobre los pedidos en línea se calculan incorrectamente</span><span class="sxs-lookup"><span data-stu-id="c25eb-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c25eb-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los impuestos sobre los pedidos en línea se calculan incorrectamente o cuando el grupo de impuestos en la línea de ventas no está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c25eb-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="c25eb-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="c25eb-105">Description</span></span>

<span data-ttu-id="c25eb-106">Cuando se realiza un pedido de comercio electrónico, los impuestos se calculan incorrectamente o el grupo de impuestos en la línea de ventas está configurado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="c25eb-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="c25eb-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="c25eb-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="c25eb-108">Configurar el impuesto para una tienda minorista en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="c25eb-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="c25eb-109">Para configurar el impuesto para una tienda minorista en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c25eb-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c25eb-110">Vaya a **Retail y Commerce \> Canales \> Todas las tiendas**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="c25eb-111">Seleccione la tienda para la que desea configurar el impuesto.</span><span class="sxs-lookup"><span data-stu-id="c25eb-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="c25eb-112">En la ficha desplegable **General**, en la sección **Impuesto**, configure la información del impuesto para la tienda.</span><span class="sxs-lookup"><span data-stu-id="c25eb-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="c25eb-113">Para la recolección de productos en una tienda, el grupo de impuestos proviene de la tienda seleccionada para la recogida.</span><span class="sxs-lookup"><span data-stu-id="c25eb-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="c25eb-114">Para obtener más información, consulte [Definir otras opciones tributarias para tiendas](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="c25eb-114">For more information, see [Set other tax options for stores](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="c25eb-115">Configurar el impuesto para una dirección de cliente en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="c25eb-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="c25eb-116">Para configurar el impuesto para una dirección de cliente en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c25eb-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c25eb-117">Vaya a **Clientes \> Clientes \> Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="c25eb-118">Seleccione el cliente para el que se va a configurar el impuesto.</span><span class="sxs-lookup"><span data-stu-id="c25eb-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="c25eb-119">En la ficha desplegable **Direcciones**, seleccione la dirección para la que desea configurar los impuestos, seleccione **Más opciones** y luego seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="c25eb-120">En la ficha desplegable **General**, seleccione el **Grupo de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="c25eb-121">En el campo **Impuesto**, seleccione el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="c25eb-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="c25eb-122">Para envíos que implican impuestos en la dirección del cliente, la dirección de entrega de la línea determina el grupo de impuestos para la línea.</span><span class="sxs-lookup"><span data-stu-id="c25eb-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="c25eb-123">Si el cliente realiza un envío a una dirección existente que tiene un grupo de impuestos que ya está configurado, se utilizará el grupo de impuestos existente.</span><span class="sxs-lookup"><span data-stu-id="c25eb-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="c25eb-124">De forma predeterminada, las direcciones no tienen un grupo de impuestos al crearse.</span><span class="sxs-lookup"><span data-stu-id="c25eb-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="c25eb-125">Configurar grupos generales de impuestos en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="c25eb-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="c25eb-126">Para configurar grupos de impuestos generales en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c25eb-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c25eb-127">Vaya a **Impuestos \> Impuestos indirectos \> Impuestos \> Grupos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="c25eb-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="c25eb-128">En la zona de navegación de la izquierda, seleccione el grupo de impuestos a configurar.</span><span class="sxs-lookup"><span data-stu-id="c25eb-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="c25eb-129">En la ficha desplegable **Impuesto basado en el destino minorista**, configure los impuestos para el grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c25eb-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="c25eb-130">Para los envíos que no implican impuestos en la dirección del cliente, la dirección de entrega de la línea y los impuestos basados en el destino que están configurados para el grupo de impuestos determinan el grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c25eb-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="c25eb-131">Para más información, vea [Configurar impuestos para tiendas en línea según el destino](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="c25eb-131">For more information, see [Set up taxes for online stores based on destination](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c25eb-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c25eb-132">Additional resources</span></span>

[<span data-ttu-id="c25eb-133">Configurar los impuestos para pedidos en línea</span><span class="sxs-lookup"><span data-stu-id="c25eb-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)