---
title: La página de entrada de la tarjeta de crédito muestra un error al finalizar la compra
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando la sección Método de pago no está cargada y muestra un mensaje de error.
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
ms.openlocfilehash: f0751fc76e6eb4320f766886b4c1efcb1042e996
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585514"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="b2730-103">La página de entrada de la tarjeta de crédito muestra un error al finalizar la compra</span><span class="sxs-lookup"><span data-stu-id="b2730-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b2730-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando la sección **Método de pago** no está cargada y muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b2730-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="b2730-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2730-105">Description</span></span>

<span data-ttu-id="b2730-106">Cuando abre la página de pago de una tienda en línea, la sección **Método de pago** no está cargada y se muestra el siguiente mensaje de error: "Algo salió mal.</span><span class="sxs-lookup"><span data-stu-id="b2730-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="b2730-107">Vuelva a intentarlo más tarde".</span><span class="sxs-lookup"><span data-stu-id="b2730-107">Please try again later."</span></span>

![Error de módulo de pago](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="b2730-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="b2730-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="b2730-110">Espere a que expire la caché de Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="b2730-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="b2730-111">La configuración del servicio de pago en la página de pago de la tienda en línea se almacena en caché en Commerce Scale Unit y puede tardar hasta 15 minutos en aparecer en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="b2730-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="b2730-112">Esta configuración del servicio de pago incluye cambios en el id. de la cuenta del comerciante, la clave de API en la nube y varias opciones de configuración relacionadas con el método de pago.</span><span class="sxs-lookup"><span data-stu-id="b2730-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2730-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b2730-113">Additional resources</span></span>

[<span data-ttu-id="b2730-114">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="b2730-114">Set up an online channel</span></span>](../channel-setup-online.md)
