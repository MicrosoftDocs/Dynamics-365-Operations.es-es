---
title: Módulo de información de recogida
description: En este tema se trata el modulo de información de recogida y se describe la forma de agregarlo a las páginas de finalización de la compra en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 222e8ad79b30e5197f7140958309d442b284f286
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263189"
---
# <a name="pickup-information-module"></a><span data-ttu-id="b1b22-103">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="b1b22-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b1b22-104">En este tema se trata el modulo de información de recogida y se describe la forma de agregarlo a las páginas de finalización de la compra en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b1b22-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b1b22-105">El módulo de información de recogida se puede utilizar en un módulo de finalización del pedido para mostrar la información de recogida de pedidos.</span><span class="sxs-lookup"><span data-stu-id="b1b22-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="b1b22-106">Los clientes pueden ver las fechas de recogida disponibles y los intervalos de tiempo, y luego seleccionar una hora adecuada para recoger su pedido.</span><span class="sxs-lookup"><span data-stu-id="b1b22-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="b1b22-107">Por ejemplo, un cliente puede elegir recoger un pedido a las 15:00 horas del 21 de marzo en la tienda de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="b1b22-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="b1b22-108">Las franjas horarias de recogida para las tiendas adecuadas deben configurarse en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="b1b22-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="b1b22-109">Para obtener más información, vea [Crear y actualizar franjas horarias para la recogida del cliente](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="b1b22-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="b1b22-110">Si se crea un módulo de información de recogida en una página de finalización del pedido, pero no se definen franjas horarias para la tienda seleccionada para la recogida, el módulo mostrará información, pero el usuario no podrá seleccionar ninguna franja horaria.</span><span class="sxs-lookup"><span data-stu-id="b1b22-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="b1b22-111">Los intervalos de tiempo son opcionales y no son necesarios para realizar un pedido.</span><span class="sxs-lookup"><span data-stu-id="b1b22-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="b1b22-112">Si se seleccionan varios artículos para recoger en varias tiendas, el módulo de información de recogida permitirá al usuario seleccionar un intervalo de tiempo para cada tienda, siempre que haya franjas horarias disponibles para ello.</span><span class="sxs-lookup"><span data-stu-id="b1b22-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b22-113">El soporte para franjas horarias y el módulo de información de recogida de la página de finalización del pedido está disponible en Dynamics 365 Commerce, versión 10.0.15 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="b1b22-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="b1b22-114">La siguiente ilustración muestra un ejemplo de selección de franjas horarias a través del módulo de información de recogida en una página de finalización del pedido.</span><span class="sxs-lookup"><span data-stu-id="b1b22-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Ejemplo de módulo de información de la recogida en una página de finalización de compra](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="b1b22-116">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="b1b22-116">Module properties</span></span>

- <span data-ttu-id="b1b22-117">**Encabezado**: especifique un encabezado para el módulo.</span><span class="sxs-lookup"><span data-stu-id="b1b22-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="b1b22-118">Mostrar información sobre la franja horaria después de realizar un pedido</span><span class="sxs-lookup"><span data-stu-id="b1b22-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="b1b22-119">Después de realizar un pedido, la información sobre la franja horaria seleccionada se puede ver en el [módulo de confirmación del pedido](order-confirmation-module.md) y el [módulo de detalles del pedido](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="b1b22-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="b1b22-120">Ambos módulos tienen una propiedad **Mostrar información de franja horaria**.</span><span class="sxs-lookup"><span data-stu-id="b1b22-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="b1b22-121">Antes de que puedan mostrar la franja horaria seleccionada durante el proceso del pedido, esta propiedad debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="b1b22-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="b1b22-122">Añadir un módulo de información de recogida para la finalización de compra</span><span class="sxs-lookup"><span data-stu-id="b1b22-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="b1b22-123">Para obtener instrucciones sobre cómo agregar un módulo de información de recogida a una página de finalización de la compra y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="b1b22-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="b1b22-124">La siguiente ilustración muestra un ejemplo de una página de finalización de compra de comercio electrónico que incluye franjas horarias para artículos de línea de recogida.</span><span class="sxs-lookup"><span data-stu-id="b1b22-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Ejemplo de una página de finalización de compra de comercio electrónico que incluye franjas horarias para artículos de línea de recogida.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="b1b22-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b1b22-126">Additional resources</span></span>

[<span data-ttu-id="b1b22-127">Crear y actualizar franjas horarias para la recogida del cliente</span><span class="sxs-lookup"><span data-stu-id="b1b22-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="b1b22-128">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="b1b22-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="b1b22-129">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="b1b22-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="b1b22-130">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="b1b22-130">Order details module</span></span>](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]