---
title: La opción Recoger esto no aparece en el carrito o en las páginas de detalles del producto
description: Este tema proporciona una guía de solución de problemas que puede ayudar cuando la opción de recogida en tienda no aparece en la página del carrito o en las páginas de detalles del producto.
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
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020824"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a><span data-ttu-id="1a4f8-103">La opción "Recoger esto" no aparece en el carrito o en las páginas de detalles del producto</span><span class="sxs-lookup"><span data-stu-id="1a4f8-103">"Pick this up" option doesn't appear on cart or product details pages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1a4f8-104">Este tema proporciona una guía de solución de problemas que puede ayudar cuando la opción de recogida en tienda no aparece en la página del carrito o en las páginas de detalles del producto.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-104">This topic provides troubleshooting guidance that can help when the option for in-store pickup doesn't appear on the cart page or product details pages.</span></span>

## <a name="description"></a><span data-ttu-id="1a4f8-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a4f8-105">Description</span></span>

<span data-ttu-id="1a4f8-106">El botón **Recoger esto** no aparece en el carrito o en las páginas de detalles del producto.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-106">The **Pick this up** button doesn't appear on the cart page or product details pages.</span></span>

<span data-ttu-id="1a4f8-107">La siguiente ilustración muestra un ejemplo de una página que incluye botón **Recoger esto**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-107">The following illustration shows an example of a page that includes the **Pick this up** button.</span></span>

![Botón Recoger esto](media/pickup-button-missing.jpg)

## <a name="resolution"></a><span data-ttu-id="1a4f8-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="1a4f8-109">Resolution</span></span>

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a><span data-ttu-id="1a4f8-110">Habilitar la extensión BOPIS en el creador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="1a4f8-110">Enable the BOPIS extension in Commerce site builder</span></span>

<span data-ttu-id="1a4f8-111">Para habilitar la extensión "comprar en línea, recoger en tienda" (BOPIS) en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-111">To enable the "buy online, pick up in store" (BOPIS) extension in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="1a4f8-112">Seleccione su sitio.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-112">Select your site.</span></span>
1. <span data-ttu-id="1a4f8-113">Seleccione **Configuración del sitio** y después seleccione **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-113">Select **Site settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="1a4f8-114">Asegúrese de que la opción **Desactivar BOPIS** está desactivada.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-114">Make sure that the **Disable BOPIS** option is cleared.</span></span>

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a><span data-ttu-id="1a4f8-115">Configurar modos de entrega en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="1a4f8-115">Configure modes of delivery in Commerce headquarters</span></span>

<span data-ttu-id="1a4f8-116">Para configurar los modos de entrega en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-116">To configure modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="1a4f8-117">Vaya a **Adquisiciones y abastecimiento \> Configuración \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-117">Go to **Procurement and sourcing \> Setup \> Modes of delivery**.</span></span>
1. <span data-ttu-id="1a4f8-118">Asegúrese de que se ha creado el modo de entrega **Recogida por parte del cliente** y se le han asignado productos y direcciones.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-118">Make sure that a **Customer pickup** mode of delivery has been created, and that products and addresses are assigned to it.</span></span>
1. <span data-ttu-id="1a4f8-119">Vaya a **Retail y Commerce \> Configuración de sede \> Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="1a4f8-120">En el panel de navegación izquierdo, seleccione **Pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-120">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="1a4f8-121">Asegúrese de que **Modo de recogida de entrega** está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-121">Make sure that **Pickup mode of delivery** is correctly configured.</span></span>

### <a name="configure-customer-orders-payments"></a><span data-ttu-id="1a4f8-122">Configurar pagos de pedidos de clientes</span><span class="sxs-lookup"><span data-stu-id="1a4f8-122">Configure customer orders payments</span></span>

<span data-ttu-id="1a4f8-123">Para configurar pagos de pedidos de clientes en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-123">To configure customer orders payments in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="1a4f8-124">Vaya a **Retail y Commerce \> Configuración de sede \> Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-124">Go to **Retail and Commerce \> Headquarters setup \> Parameters**.</span></span>
1. <span data-ttu-id="1a4f8-125">En el panel de navegación izquierdo, seleccione **Pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-125">In the left navigation, select **Customer orders**.</span></span>
1. <span data-ttu-id="1a4f8-126">En la ficha desplegable **Pagos**, asegúrese de que los campos **Condiciones de pago** y **Forma de pago** están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a4f8-126">On the **Payments** FastTab, make sure that the **Terms of payment** and **Method of payment** fields are correctly set.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a4f8-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1a4f8-127">Additional resources</span></span>

[<span data-ttu-id="1a4f8-128">Configurar BOPIS</span><span class="sxs-lookup"><span data-stu-id="1a4f8-128">Configure BOPIS</span></span>](../cpe-bopis.md)

[<span data-ttu-id="1a4f8-129">Habilitar varios modos de recogida de la entrega para pedidos de clientes</span><span class="sxs-lookup"><span data-stu-id="1a4f8-129">Enable multiple pickup delivery modes for customer orders</span></span>](../multiple-pickup-modes.md)

[<span data-ttu-id="1a4f8-130">Pagos de pedido de Commerce en el omnicanal</span><span class="sxs-lookup"><span data-stu-id="1a4f8-130">Omni-channel Commerce order payments</span></span>](../dev-itpro/commerce-payments.md)

[<span data-ttu-id="1a4f8-131">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="1a4f8-131">Store selector module</span></span>](../store-selector.md)
