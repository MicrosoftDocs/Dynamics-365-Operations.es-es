---
title: Los pagos se liquidan automáticamente antes de que se facturen o envíen los pedidos
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se liquida un pago en el portal de Adyen inmediatamente después de que se realiza un pedido, aunque el pedido de venta no se haya facturado ni enviado.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 788854a3119eb9ffaf839beb93a5bc15cdcd6387
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585519"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a><span data-ttu-id="b5044-103">Los pagos se liquidan automáticamente antes de que se facturen o envíen los pedidos</span><span class="sxs-lookup"><span data-stu-id="b5044-103">Payments are automatically settled before orders are invoiced or shipped</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5044-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se liquida un pago en el portal de Adyen inmediatamente después de que se realiza un pedido, aunque el pedido de venta no se haya facturado ni enviado.</span><span class="sxs-lookup"><span data-stu-id="b5044-104">This topic provides troubleshooting guidance that can help when a payment is settled in the Adyen portal immediately after an order is placed, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="description"></a><span data-ttu-id="b5044-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5044-105">Description</span></span>

<span data-ttu-id="b5044-106">Después de efectuado un pedido, el pago se liquida inmediatamente en el portal de Adyen, aunque el pedido de venta no se haya facturado ni enviado.</span><span class="sxs-lookup"><span data-stu-id="b5044-106">After an order is placed, the payment is immediately settled in the Adyen portal, even though the sales order hasn't been invoiced or shipped.</span></span>

## <a name="resolution"></a><span data-ttu-id="b5044-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="b5044-107">Resolution</span></span>

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a><span data-ttu-id="b5044-108">Configurar la captura manual para pagos de comercio electrónico en el portal de Adyen</span><span class="sxs-lookup"><span data-stu-id="b5044-108">Configure manual capture for e-commerce payments in the Adyen portal</span></span>

<span data-ttu-id="b5044-109">Para configurar la captura manual para pagos de comercio electrónico en el portal de Adyen, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5044-109">To configure manual capture for e-commerce payments in the Adyen portal, follow these steps.</span></span>

1. <span data-ttu-id="b5044-110">Inicie sesión en el portal de Adyen.</span><span class="sxs-lookup"><span data-stu-id="b5044-110">Sign in to the Adyen portal.</span></span>
1. <span data-ttu-id="b5044-111">En la esquina superior derecha, seleccione su cuenta de comerciante para el canal de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="b5044-111">In the upper-right corner, select your merchant account for the e-commerce channel.</span></span>
1. <span data-ttu-id="b5044-112">En la zona de navegación superior, seleccione **Cuenta** y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="b5044-112">On the top navigation, select **Account**, and then select **Settings**.</span></span>
1. <span data-ttu-id="b5044-113">En el campo **Retraso de captura**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="b5044-113">In the **Capture Delay** field, select **manual**.</span></span>

    ![Configuración de retardo de captura en el portal de Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a><span data-ttu-id="b5044-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b5044-115">Additional resources</span></span>

[<span data-ttu-id="b5044-116">Captura de pago de Adyen</span><span class="sxs-lookup"><span data-stu-id="b5044-116">Adyen payment capture</span></span>](https://docs.adyen.com/point-of-sale/capturing-payments)

[<span data-ttu-id="b5044-117">Conector de pago de Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="b5044-117">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="b5044-118">Configurar el conector de pago de Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b5044-118">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
