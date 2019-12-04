---
title: Descuentos basados en forma de pago
description: Este tema proporciona una visión general de la funcionalidad que permite a minoristas configurar descuentas para tipos de forma de pago específicos.
author: bebeale
manager: AnnBe
ms.date: 10/30/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: ed17b43ac16ebcd310716271b84bbbd904a3253a
ms.sourcegitcommit: dc31a0f0d9216aa05be76046ac7410702b20706f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "2692232"
---
# <a name="tender-based-discounts"></a><span data-ttu-id="60743-103">Descuentos basados en forma de pago</span><span class="sxs-lookup"><span data-stu-id="60743-103">Tender-based discounts</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="60743-104">Es un una práctica común entre minoristas emitir tarjetas de crédito con marca, privadas.</span><span class="sxs-lookup"><span data-stu-id="60743-104">It's a common practice among retailers to release private, branded credit cards.</span></span> <span data-ttu-id="60743-105">Los minoristas se benefician porque obtienen tasas preferidas de los bancos.</span><span class="sxs-lookup"><span data-stu-id="60743-105">The retailers benefit because they get preferred rates from the banks.</span></span> <span data-ttu-id="60743-106">Además, ya que estas tarjetas de crédito pueden animar a los clientes a visitar el almacén más con frecuencia, ayudan a mejorar el balance del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="60743-106">Additionally, because these credits cards can encourage customers to visit the store more often, they help improve the retailer's bottom line.</span></span> <span data-ttu-id="60743-107">Por lo tanto, los minoristas tienen el incentivo de aumentar el uso por parte del cliente de tarjetas de crédito con marca.</span><span class="sxs-lookup"><span data-stu-id="60743-107">Therefore, retailers have an incentive to increase customer use of their branded credit cards.</span></span> <span data-ttu-id="60743-108">Para lograr este objetivo, con frecuencia proporcionan una descuentos adicionales a los clientes que usan estas tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="60743-108">To achieve this goal, they often provide additional discounts to customers who use these credit cards.</span></span>

<span data-ttu-id="60743-109">Como alternativa, los minoristas que no proporcionan tarjetas de crédito de la marca pueden estar interesados en animar a los clientes a pagar con otros tipos de forma de pago, como efectivo, tarjetas regalo, o puntos de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="60743-109">Alternatively, retailers who don't provide branded credit cards might want to encourage customers to pay by using other tender types, such as cash, gift cards, or loyalty points.</span></span> <span data-ttu-id="60743-110">De esta manera, ayudan reducir el gasto de tarifas de tramitación de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="60743-110">In this way, they can help reduce the expense of credit card processing fees.</span></span> <span data-ttu-id="60743-111">Por lo tanto, los minoristas pueden proporcionar descuentos a los clientes que usan estos tipos de forma de pago alternativos.</span><span class="sxs-lookup"><span data-stu-id="60743-111">Therefore, retailers might provide discounts to customers who use these alternative tender types.</span></span>

<span data-ttu-id="60743-112">En Microsoft Dynamics 365 Retail 365, los minoristas pueden configurar un porcentaje de descuento que se aplica a las líneas elegibles si el cliente paga mediante el tipo de forma de pago preferido.</span><span class="sxs-lookup"><span data-stu-id="60743-112">In Microsoft Dynamics 365 Retail, retailers can configure a discount percentage that is applied to qualified lines if the customer pays by using the preferred tender type.</span></span> <span data-ttu-id="60743-113">El cliente podrá decidir si desea hacer un pago parcial o un pago completo, y Retail determina el importe de descuento adecuado.</span><span class="sxs-lookup"><span data-stu-id="60743-113">The customer can decide whether to do a partial payment or a full payment, and Retail determines the appropriate discount amount.</span></span> <span data-ttu-id="60743-114">Tenga en cuenta que el descuento siempre se da sobre el importe de antes de impuestos de los artículos elegibles.</span><span class="sxs-lookup"><span data-stu-id="60743-114">Note that the discount is always given on the pre-tax amount of the qualified items.</span></span>

<span data-ttu-id="60743-115">Los descuentos basados en la forma de pago no compiten con los descuentos basados en artículos, como los descuentos periódicos o manuales.</span><span class="sxs-lookup"><span data-stu-id="60743-115">Tender-based discounts don't compete with item-based discounts, such as periodic or manual discounts.</span></span> <span data-ttu-id="60743-116">Se componen siempre sobre los descuentos de artículos.</span><span class="sxs-lookup"><span data-stu-id="60743-116">They are always compounded over the item discounts.</span></span> <span data-ttu-id="60743-117">Por lo tanto, incluso si un descuento periódico exclusivo se aplica a un artículo, el descuento basado en la forma de pago se seguirá aplicando encima del descuento periódico exclusivo.</span><span class="sxs-lookup"><span data-stu-id="60743-117">Therefore, even if an exclusive periodic discount is applied to an item, the tender-based discount is still applied on top of the exclusive periodic discount.</span></span> <span data-ttu-id="60743-118">Del mismo modo, si un descuento de umbral se aplica a la transacción, y el descuento basado en la forma de pago reduce el total por debajo del umbral, el descuento de umbral se seguirá aplicando a la transacción.</span><span class="sxs-lookup"><span data-stu-id="60743-118">Likewise, if a threshold discount is applied to the transaction, and the tender-based discount reduces the total below the threshold, the threshold discount is still applied to the transaction.</span></span>

<span data-ttu-id="60743-119">Aunque los descuentos basados en formas de pago reducen el subtotal de la transacción, los cargos automáticos que se aplican a la transacción no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="60743-119">Even though tender-based discounts reduce the subtotal of the transaction, automatic charges that are applied to the transaction aren't affected.</span></span> <span data-ttu-id="60743-120">Por ejemplo, si los gastos de entrega se calculan como $5 porque el subtotal era más de $100, y el descuento basado en formas de pago reduce el importe de modo que sea inferior a $100, los gastos de entrega seguirán siendo $5.</span><span class="sxs-lookup"><span data-stu-id="60743-120">For example, if the delivery charges are calculated as $5 because the subtotal was more than $100, and the tender-based discount reduces the amount so that it's less than $100, the delivery charges are still $5 for the order.</span></span>


> [!NOTE]
> <span data-ttu-id="60743-121">Los descuentos basados en formas de pago se distribuyen proporcionalmente a las líneas de ventas elegibles y reducen el importe de antes de impuestos de las líneas individuales.</span><span class="sxs-lookup"><span data-stu-id="60743-121">Tender-based discounts are proportionally distributed to the qualified sales lines and reduce the pre-tax amount of the individual lines.</span></span> <span data-ttu-id="60743-122">Si varios descuentos basados en forma de pago están configurados para un tipo de forma de pago (por ejemplo, efectivo), sólo se aplicará el mejor descuento basado en forma de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-122">If multiple tender-based discounts are configured for a tender type (for example, cash), only the best tender-based discount is applied.</span></span>

<span data-ttu-id="60743-123">Los descuentos basados en forma de pago solo se pueden aplicar a las líneas de ventas donde los precios no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="60743-123">Tender-based discounts can be applied only to sales lines where the prices aren't locked.</span></span> <span data-ttu-id="60743-124">Si nuevas líneas de ventas se agregan a un pedido, el descuento basado en la forma de pago se aplica a las nuevas líneas de ventas sólo durante el pago.</span><span class="sxs-lookup"><span data-stu-id="60743-124">If new sales lines are added to an order, the tender-based discount is applied to the new sales lines only during payment.</span></span> <span data-ttu-id="60743-125">Mientras se efectúa un pedido de cliente para su recogida o envío, el descuento basado en la forma de pago sólo se aplica al importe del depósito.</span><span class="sxs-lookup"><span data-stu-id="60743-125">While a customer order for pickup or shipment is being placed, the tender-based discount is applied only to the deposit amount.</span></span> <span data-ttu-id="60743-126">Una vez que el pedido se haya realizado, durante su ejecución, los precios de las líneas de ventas se bloquean.</span><span class="sxs-lookup"><span data-stu-id="60743-126">After the order is placed, during fulfillment, the prices of the sales lines are locked.</span></span> <span data-ttu-id="60743-127">Por lo tanto, no se aplica ningún descuento basado en la forma de pago a ningún saldo que se pague durante la recogida o se autorice durante el envío.</span><span class="sxs-lookup"><span data-stu-id="60743-127">Therefore, no tender-based discount is applied to any balance that is paid during pickup or authorized during shipment.</span></span> <span data-ttu-id="60743-128">El descuento basado en la forma de pago se puede aplicar al importe completo de un pedido del cliente únicamente si el minorista obtiene el importe completo como depósito mientras se realiza el pedido.</span><span class="sxs-lookup"><span data-stu-id="60743-128">The tender-based discount can be applied to the whole amount of a customer order only if the retailer collects the whole amount as a deposit while the order is being placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60743-129">En Retail, los descuentos basados en la forma de pago están limitados a dos tipos de pago: tarjetas de crédito y efectivo.</span><span class="sxs-lookup"><span data-stu-id="60743-129">In Retail, tender-based discounts are currently limited to two payment types: credit cards and cash.</span></span>

## <a name="pos-user-experience"></a><span data-ttu-id="60743-130">Experiencia de usuario PDV</span><span class="sxs-lookup"><span data-stu-id="60743-130">POS user experience</span></span>

<span data-ttu-id="60743-131">Si el descuento basado en la forma de pago se configura para el efectivo, y el cajero del punto de venta (PDV) selecciona un botón asignado a la operación de pago en efectivo, el descuento basado en la forma de pago se aplicará automáticamente a la transacción.</span><span class="sxs-lookup"><span data-stu-id="60743-131">If the tender-based discount is set up for cash, and the cashier at the point of sale (POS) selects a button that is mapped to the Pay cash operation, the tender-based discount is automatically applied to the transaction.</span></span> <span data-ttu-id="60743-132">El importe reducido se muestra como saldo.</span><span class="sxs-lookup"><span data-stu-id="60743-132">The reduced amount is then shown as the balance.</span></span> <span data-ttu-id="60743-133">Sin embargo, si el cajero selecciona el botón **Atrás** en la pantalla de pago, se elimina el descuento, y el importe original se muestra en la pantalla de la transacción.</span><span class="sxs-lookup"><span data-stu-id="60743-133">However, if the cashier selects the **Back** button on the payment screen, the discount is removed, and the original amount is shown on the transaction screen.</span></span> <span data-ttu-id="60743-134">Se quita el descuento basado en la forma de pago si se anula la línea de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-134">The tender-based discount is removed if the payment line is voided.</span></span>

<span data-ttu-id="60743-135">Para los pagos con tarjetas, los minoristas pueden establecer un descuento basado en la forma de pago en uno o más tipos de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="60743-135">For cards payments, retailers can set the tender-based discount on one or more types of credit cards.</span></span> <span data-ttu-id="60743-136">Sin embargo, el sistema no puede comprobar el tipo de tarjeta de crédito que se utiliza a menos que se autorice la tarjeta.</span><span class="sxs-lookup"><span data-stu-id="60743-136">However, the system can't verify the type of credit card that is used unless the card is authorized.</span></span> <span data-ttu-id="60743-137">Si el descuento se aplica después de la autorización, la autorización de pago será para un importe mayor, pero la captura de pago será para un importe más pequeño.</span><span class="sxs-lookup"><span data-stu-id="60743-137">If the discount is applied after authorization, the payment authorization will be for a larger amount, but the payment capture will be for a smaller amount.</span></span>

<span data-ttu-id="60743-138">Para ayudar a evitar esta situación, si un cliente paga con una tarjeta de crédito, el cajero ve un cuadro de diálogo que enumera las tarjetas de crédito que aportarán al cliente ahorros adicionales.</span><span class="sxs-lookup"><span data-stu-id="60743-138">To help prevent this situation, if a customer pays with a credit card, the cashier sees a dialog box that lists credit cards that will bring the customer additional savings.</span></span> <span data-ttu-id="60743-139">El cajero podrá preguntar si el cliente desea usar una de las tarjetas preferidas para obtener un descuento adicional.</span><span class="sxs-lookup"><span data-stu-id="60743-139">The cashier can then ask whether the customer wants to use one of the preferred cards to get an additional discount.</span></span> <span data-ttu-id="60743-140">Si el cajero usa una tarjeta preferida, el descuento basado en la forma de pago se aplica a la transacción, y el importe reducido se muestra en la pantalla de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-140">If the cashier uses a preferred card, the tender-based discount is applied to the transaction, and the reduced amount is shown on the payment screen.</span></span> <span data-ttu-id="60743-141">La autorización será para el importe reducido.</span><span class="sxs-lookup"><span data-stu-id="60743-141">The authorization will be for the reduced amount.</span></span> <span data-ttu-id="60743-142">Si el cliente inserta una tarjeta que es diferente de la tarjeta que el cajero ha seleccionado, se verá un mensaje de error, y se anulará la autorización.</span><span class="sxs-lookup"><span data-stu-id="60743-142">If the customer inserts a card that differs from the card that the cashier selected, an error message is shown, and the authorization is voided.</span></span>


## <a name="call-center-user-experience"></a><span data-ttu-id="60743-143">Experiencia del usuario del centro de asistencia telefónica</span><span class="sxs-lookup"><span data-stu-id="60743-143">Call center user experience</span></span>

<span data-ttu-id="60743-144">Cuando el usuario seleccione **Completado** durante un pedido de centro de asistencia telefónica, se mostrará la pantalla **Totales**.</span><span class="sxs-lookup"><span data-stu-id="60743-144">When the user selects **Complete** during a call center order, the **Totals** screen is shown.</span></span> <span data-ttu-id="60743-145">Inicialmente, los totales de esta pantalla no incluyen descuentos basados en la forma de pago, ya que el método de pago todavía no se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="60743-145">At first, the totals on this screen don't include tender-based discounts, because the payment method hasn't yet been selected.</span></span> <span data-ttu-id="60743-146">En la pantalla **Agregar pago**, si el usuario selecciona el método de pago para el que el está configurado el descuento basado en la forma de pago, el importe de pago se ajustará automáticamente de modo que refleje el importe descontado.</span><span class="sxs-lookup"><span data-stu-id="60743-146">On the **Add payment** screen, if the user selects the payment method that the tender-based discount is configured for, the payment amount is automatically adjusted so that it reflects the discounted amount.</span></span> <span data-ttu-id="60743-147">Como el cliente en el PDV, el cliente del centro de asistencia telefónica puede decidir si desea pagar el pago completo o un pago parcial.</span><span class="sxs-lookup"><span data-stu-id="60743-147">Like the customer at the POS, the call center customer can decide whether to pay the full payment or a partial payment.</span></span> <span data-ttu-id="60743-148">En función del importe que se paga, el descuento basado en la forma de pago se aplica al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="60743-148">Based on the amount that is paid, the tender-based discount is applied to the sales order.</span></span>

> [!NOTE]
> <span data-ttu-id="60743-149">La validación de la tarjeta no se hace para los pedidos del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="60743-149">Card validation isn't done for call center orders.</span></span> <span data-ttu-id="60743-150">Por ejemplo, si el usuario del centro de asistencia telefónica selecciona Visa como tarjeta de crédito, pero el cliente usa Mastercard, el sistema seguirá aplicando el descuento.</span><span class="sxs-lookup"><span data-stu-id="60743-150">For example, if the call center user selects Visa as the credit card, but the customer uses Mastercard, the system still applies the discount.</span></span>

## <a name="exclude-items-from-discounts"></a><span data-ttu-id="60743-151">Excluir artículos de los descuentos</span><span class="sxs-lookup"><span data-stu-id="60743-151">Exclude items from discounts</span></span>

<span data-ttu-id="60743-152">Los minoristas eligen a menudo excluir algunos productos, como artículos nuevos o artículos con demanda, de los descuentos.</span><span class="sxs-lookup"><span data-stu-id="60743-152">Retailers often choose to exclude some products, such as new items or in-demand items, from discounts.</span></span> <span data-ttu-id="60743-153">Sin embargo, es posible que aún deseen aplicar descuentos basados en la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-153">However, they might still want to apply tender-based discounts.</span></span> <span data-ttu-id="60743-154">Por ejemplo, un minorista configura Retail para que no permita descuentos basados en artículos o descuentos manuales.</span><span class="sxs-lookup"><span data-stu-id="60743-154">For example, a retailer configures Retail so that it doesn't allow item-based discounts or manual discounts.</span></span> <span data-ttu-id="60743-155">Sin embargo, si el cliente paga mediante la forma de pago preferida, Retail aplicará el descuento basado en la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-155">However, if the customer pays by using the preferred tender, Retail still applies the tender-based discount.</span></span> <span data-ttu-id="60743-156">Para configurar Retail de esta manera, los minoristas deben ir a **Gestión de información de productos > Productos > Productos emitidos**, seleccionar el artículo y, a continuación, en la pestaña desplegable **Retail**, establecer las opciones **Evite todos los descuentos** y **Evite los descuentos basados propuesta** en **No** y las opciones **Evite los descuentos al por menor** y **Evite los descuentos manuales** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="60743-156">To set up Retail in this manner, retailers must go to **Product information management > Products > Released products**, select the item, and then, on the **Retail** FastTab, set the **Prevent all discounts** and **Prevent tender based discounts** options to **No**, and the **Prevent retail discounts** and **Prevent manual discounts** options to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="60743-157">Cuando la configuración **Evite todos los descuentos** está establecida en **Sí**, no se aplicará ningún descuento al producto.</span><span class="sxs-lookup"><span data-stu-id="60743-157">When the **Prevent all discounts** configuration is set to **Yes**, no discounts will be applied to the product.</span></span> <span data-ttu-id="60743-158">Ni siquiera se aplicarán descuentos basados en la forma de pago.</span><span class="sxs-lookup"><span data-stu-id="60743-158">Not even tender-based discounts will be applied.</span></span>