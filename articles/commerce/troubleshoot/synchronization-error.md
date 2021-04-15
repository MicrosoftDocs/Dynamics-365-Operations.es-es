---
title: Error de sincronización de pedidos relacionado con el servicio de pago predeterminado
description: Este tema proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.
author: Reza-Assadi
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
ms.openlocfilehash: 45eeae751051b58e1c9e725eb4ed4b5240026e7f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801444"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="8bded-103">Error de sincronización de pedidos relacionado con el servicio de pago predeterminado</span><span class="sxs-lookup"><span data-stu-id="8bded-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8bded-104">Este tema proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="8bded-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="8bded-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bded-105">Description</span></span>

<span data-ttu-id="8bded-106">Cuando sincroniza un pedido en línea, recibe el siguiente mensaje de error: "Debe haber un servicio de pago predeterminado para procesar transacciones con tarjeta de crédito".</span><span class="sxs-lookup"><span data-stu-id="8bded-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Error del servicio de pago predeterminado que falta](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="8bded-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="8bded-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="8bded-109">Confirmar o configurar el servicio de pago en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="8bded-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="8bded-110">Para confirmar o configurar el servicio de pago en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bded-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="8bded-111">Vaya a **Clientes \> Configuración de pagos \> Servicios de pago**.</span><span class="sxs-lookup"><span data-stu-id="8bded-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="8bded-112">Asegúrese de que la opción **Procesador predeterminado para nuevas tarjetas de crédito** esté configurada en **Sí** para un servicio de pago.</span><span class="sxs-lookup"><span data-stu-id="8bded-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bded-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8bded-113">Additional resources</span></span>

[<span data-ttu-id="8bded-114">Configuración, autorización y captura de tarjetas de crédito</span><span class="sxs-lookup"><span data-stu-id="8bded-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
