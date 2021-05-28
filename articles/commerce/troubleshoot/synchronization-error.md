---
title: Error de sincronización de pedidos relacionado con el servicio de pago predeterminado
description: Este tema proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021136"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="fc787-103">Error de sincronización de pedidos relacionado con el servicio de pago predeterminado</span><span class="sxs-lookup"><span data-stu-id="fc787-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc787-104">Este tema proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="fc787-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="fc787-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc787-105">Description</span></span>

<span data-ttu-id="fc787-106">Cuando sincroniza un pedido en línea, recibe el siguiente mensaje de error: "Debe haber un servicio de pago predeterminado para procesar transacciones con tarjeta de crédito".</span><span class="sxs-lookup"><span data-stu-id="fc787-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Error del servicio de pago predeterminado que falta](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="fc787-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="fc787-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="fc787-109">Confirmar o configurar el servicio de pago en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="fc787-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="fc787-110">Para confirmar o configurar el servicio de pago en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fc787-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="fc787-111">Vaya a **Clientes \> Configuración de pagos \> Servicios de pago**.</span><span class="sxs-lookup"><span data-stu-id="fc787-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="fc787-112">Asegúrese de que la opción **Procesador predeterminado para nuevas tarjetas de crédito** esté configurada en **Sí** para un servicio de pago.</span><span class="sxs-lookup"><span data-stu-id="fc787-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc787-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fc787-113">Additional resources</span></span>

[<span data-ttu-id="fc787-114">Configuración, autorización y captura de tarjetas de crédito</span><span class="sxs-lookup"><span data-stu-id="fc787-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)