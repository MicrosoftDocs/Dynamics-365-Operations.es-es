---
title: Funcionalidad del centro de llamadas
description: "Este tema proporciona una visión general de la funcionalidad de ventas del centro de llamadas en Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: dd35e895cdfe402b9d22e710c7b0166eadf412ff
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="call-center-functionality"></a><span data-ttu-id="aa84a-103">Funcionalidad del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="aa84a-103">Call center functionality</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="aa84a-104">Este artículo proporciona una visión general de la funcionalidad de ventas del centro de llamadas en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="aa84a-104">This article provides an overview of the call center sales functionality in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="aa84a-105">Dynamics 365 for Retail también admite los centro de llamadas como tipo de canal comercial.</span><span class="sxs-lookup"><span data-stu-id="aa84a-105">Dynamics 365 for Retail supports call centers as a type of retail channel.</span></span> <span data-ttu-id="aa84a-106">En un centro de llamadas, los trabajadores realizan pedidos de clientes por teléfono y crean pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="aa84a-106">In a call center, workers take orders from customers over the phone and create sales orders.</span></span> <span data-ttu-id="aa84a-107">La funcionalidad del centro de llamadas incluye características que diseñadas para facilitar la realización de pedidos por teléfono y la gestión del servicio al cliente en el proceso del pedido.</span><span class="sxs-lookup"><span data-stu-id="aa84a-107">Call center functionality includes features that are designed to make it easier to take phone orders and handle customer service throughout the order fulfillment process.</span></span> <span data-ttu-id="aa84a-108">Por ejemplo, los trabajadores de los centros de llamadas pueden especificar la información de pago directamente en el pedido de ventas y pueden ver un resumen detallado de gastos y de pagos antes de enviar el pedido.</span><span class="sxs-lookup"><span data-stu-id="aa84a-108">For example, call center workers can enter payment information directly into the sales order, and can view a detailed summary of charges and payments before they submit the order.</span></span> <span data-ttu-id="aa84a-109">Los trabajadores tienen opciones para controlar precios, y pueden acceder a distintos datos sobre los clientes, productos y precios desde la página **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="aa84a-109">Workers also have options for controlling pricing, and can access various data about customers, products, and prices from the **Sales order** page.</span></span> <span data-ttu-id="aa84a-110">Los centros de llamadas también tienen la funcionalidad mejorada para el seguimiento del historial y el estado del pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="aa84a-110">Additionally, call centers have enhanced functionality for tracking customer history and order status.</span></span> <span data-ttu-id="aa84a-111">Cada centro de llamadas puede tener sus propios usuarios, métodos de pago, grupos de precios, dimensiones financieras y modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="aa84a-111">Each call center can have its own users, payment methods, price groups, financial dimensions, and modes of delivery.</span></span> <span data-ttu-id="aa84a-112">Puede configurar estas opciones cuando crea el centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa84a-112">You can configure these options when you create the call center.</span></span> <span data-ttu-id="aa84a-113">Además, puede usar la página **Centro de llamadas** para habilitar o deshabilitar los siguientes grupos de funcionalidades que son únicas a los centros de llamadas:</span><span class="sxs-lookup"><span data-stu-id="aa84a-113">Additionally, you can use the **Call center** page to enable or disable the following groups of features that are unique to call centers:</span></span>

-   <span data-ttu-id="aa84a-114">**Finalización del pedido:** este grupo incluye características relacionadas con los pagos y la finalización del pedido en la página **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="aa84a-114">**Order completion** – This group includes features that are related to payments and order completion on the **Sales order** page.</span></span>
-   <span data-ttu-id="aa84a-115">**Venta dirigida:** este grupo incluye características relacionadas con los códigos fuente, las secuencias de comandos las y solicitudes del catálogo.</span><span class="sxs-lookup"><span data-stu-id="aa84a-115">**Directed selling** – This group includes features that are related to source codes, scripts, and catalog requests.</span></span>

<span data-ttu-id="aa84a-116">Cuando se activan estas funciones de la configuración del centro de llamadas, están disponibles en la página **Pedido de ventas** para los usuarios que estén asociados con el centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa84a-116">After you enable these features in the call center settings, they are available on the **Sales order** page to users who are associated with the call center.</span></span> <span data-ttu-id="aa84a-117">La mayoría de ellas requieren configuración adicional antes de que se puedan usar.</span><span class="sxs-lookup"><span data-stu-id="aa84a-117">Most of these features require additional setup before they can be used.</span></span> <span data-ttu-id="aa84a-118">Para que los usuarios puedan crear pedidos del centro de llamadas, debe agregar a dichos usuarios al centro de llamadas como usuarios del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa84a-118">Before users can create call center orders, you must add those users to the call center as call center users.</span></span> <span data-ttu-id="aa84a-119">Este paso permite la configuración y la funcionalidad específicas al canal de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa84a-119">This step enables the call center channel-specific configuration and functionality.</span></span> <span data-ttu-id="aa84a-120">A continuación se muestran algunos ejemplos de la funcionalidad que está disponible:</span><span class="sxs-lookup"><span data-stu-id="aa84a-120">Here are some examples of the functionality that becomes available:</span></span>

-   <span data-ttu-id="aa84a-121">La venta dirigida proporciona opciones de configuración para que los scripts y las imágenes de los productos de venta por teléfono ayuden y dirijan a los vendedores mientras que toman pedidos.</span><span class="sxs-lookup"><span data-stu-id="aa84a-121">Guided selling provides configuration options for tele-sales scripts and product images to help and guide sales clerks while they take orders.</span></span>
-   <span data-ttu-id="aa84a-122">Los pedidos no se pueden completar hasta que los vendedores hayan capturado al menos un método de pago.</span><span class="sxs-lookup"><span data-stu-id="aa84a-122">Orders can't be completed until sales clerks have captured at least one payment method.</span></span>
-   <span data-ttu-id="aa84a-123">Se pueden configurar reglas de sobreventa y venta cruzada para que los vendedores promocionen productos concretos para el cliente.</span><span class="sxs-lookup"><span data-stu-id="aa84a-123">Upsell and cross-sell rules can be configured to prompt sales clerks to promote specific products to the customer.</span></span>
-   <span data-ttu-id="aa84a-124">Los vendedores pueden capturar el código fuente para el catálogo del cual un cliente está realizando el pedido.</span><span class="sxs-lookup"><span data-stu-id="aa84a-124">Sales clerks can capture the source code for the catalog that a customer is ordering from.</span></span>
-   <span data-ttu-id="aa84a-125">Los vendedores pueden agregar los vales de un minorista al pedido.</span><span class="sxs-lookup"><span data-stu-id="aa84a-125">Sales clerks can add a retailer's coupons to the order.</span></span>
-   <span data-ttu-id="aa84a-126">Los vendedores pueden vender programas de continuidad.</span><span class="sxs-lookup"><span data-stu-id="aa84a-126">Sales clerks can sell continuity programs.</span></span>
-   <span data-ttu-id="aa84a-127">Los pedidos se pueden poner en espera manual o automáticamente, para indicar que es necesaria una investigación adicional antes de que el pedido pueda ser procesado.</span><span class="sxs-lookup"><span data-stu-id="aa84a-127">Orders can be put on hold manually or automatically, to indicate that additional investigation is required before the order can be processed.</span></span>





