---
title: El tipo de pago debe ser un error de tarjeta de crédito en la página del pedido de ventas
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se muestra un mensaje de error en la página del pedido de ventas después de sincronizar un pedido.
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
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585520"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a><span data-ttu-id="9c56b-103">Error "El tipo de pago debe ser tarjeta de crédito" en la página del pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="9c56b-103">"Payment type must be credit card" error on the sales order page</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9c56b-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se muestra un mensaje de error en la página del pedido de ventas después de sincronizar un pedido.</span><span class="sxs-lookup"><span data-stu-id="9c56b-104">This topic provides troubleshooting guidance that can help when an error message is shown on the sales order page after an order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="9c56b-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c56b-105">Description</span></span>

<span data-ttu-id="9c56b-106">Cuando abre la página de pedido de ventas después de sincronizar un pedido, recibe el siguiente mensaje de error: "El tipo de pago debe ser tarjeta de crédito, ya que se ha especificado el número de tarjeta de crédito".</span><span class="sxs-lookup"><span data-stu-id="9c56b-106">When you open the sales order page after you sync an order, you receive the following error message: "The payment type must be credit card, since the credit card number has been specified."</span></span>

![Error de que El tipo de pago debe ser tarjeta de crédito](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a><span data-ttu-id="9c56b-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="9c56b-108">Resolution</span></span>

### <a name="set-the-payment-type-in-commerce-headquarters"></a><span data-ttu-id="9c56b-109">Establezca el tipo de pago en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="9c56b-109">Set the payment type in Commerce headquarters</span></span>

1. <span data-ttu-id="9c56b-110">Vaya a **Clientes \> Configuración de pagos \> Condiciones de pago**.</span><span class="sxs-lookup"><span data-stu-id="9c56b-110">Go to **Accounts receivable \> Payment setup \> Terms of payment**.</span></span>
1. <span data-ttu-id="9c56b-111">En la zona de navegación de la izquierda, seleccione sus términos de pago.</span><span class="sxs-lookup"><span data-stu-id="9c56b-111">In the left navigation, select your terms of payment.</span></span>
1. <span data-ttu-id="9c56b-112">En el campo **Tipo de pago**, asegúrese de que **Tarjeta de crédito** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9c56b-112">In the **Payment type** field, make sure that **Credit card** is selected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c56b-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9c56b-113">Additional resources</span></span>

[<span data-ttu-id="9c56b-114">Registro de ventas y pagos en línea</span><span class="sxs-lookup"><span data-stu-id="9c56b-114">Posting of online sales and payments</span></span>](../tasks/posting-online-sales-payments.md)
