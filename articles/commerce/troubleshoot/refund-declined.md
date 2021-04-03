---
title: Se rechaza el reembolso de un pedido de devolución
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se rechaza un reembolso en un pedido de devolución porque la tarjeta de crédito que se usa para la facturación es diferente de la tarjeta que se usó durante la autorización de pago original.
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
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585525"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="a4c5f-103">Se rechaza el reembolso de un pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="a4c5f-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4c5f-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se rechaza un reembolso en un pedido de devolución porque la tarjeta de crédito que se usa para la facturación es diferente de la tarjeta que se usó durante la autorización de pago original.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="a4c5f-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4c5f-105">Description</span></span>

<span data-ttu-id="a4c5f-106">Se rechaza un reembolso cuando la tarjeta de crédito que se utiliza para facturar un pedido de devolución difiere de la tarjeta que se utilizó durante la autorización de pago original.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="a4c5f-107">Recibirá el siguiente mensaje de error: "Algunos pagos no están en el estado correcto para su registro.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="a4c5f-108">Vuelva a validar el estado de todos los pagos antes de la facturación".</span><span class="sxs-lookup"><span data-stu-id="a4c5f-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="a4c5f-109">Los detalles de la autorización de pago incluirán el siguiente mensaje de error: "La puerta de enlace de Adyen SendRequest () falló con estado 'InternalServerError'.22144; se devolvió una respuesta vacía desde Adyen.(22001);"</span><span class="sxs-lookup"><span data-stu-id="a4c5f-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Se rechaza el reembolso de un error de pedido de devolución](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="a4c5f-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="a4c5f-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="a4c5f-112">Habilitar devoluciones ciegas en Adyen</span><span class="sxs-lookup"><span data-stu-id="a4c5f-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="a4c5f-113">Para habilitar las devoluciones ciegas, siga los pasos de [Solucionar problemas de del conector de Dynamics 365 Payment para problemas de Adyen](adyen-support.md) para ponerse en contacto con el equipo de soporte de Adyen y solicitar que se habiliten las devoluciones ciegas en su cuenta de comerciante de Adyen.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4c5f-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a4c5f-114">Additional resources</span></span>

[<span data-ttu-id="a4c5f-115">Conector de pago de Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="a4c5f-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="a4c5f-116">Configurar el conector de pago de Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a4c5f-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
