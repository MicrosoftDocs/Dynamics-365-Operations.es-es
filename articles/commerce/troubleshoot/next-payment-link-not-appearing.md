---
title: La opción Guardar para mi próximo pago no aparece
description: Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla Guardar para mi próximo pago no aparece en Método de pago en la página de pago de un sitio de comercio electrónico.
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
ms.openlocfilehash: 3a4fbcd522651ed1b82b72b751ff6ead44c94a71
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585521"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="0112e-103">La opción "Guardar para mi próximo pago" no aparece</span><span class="sxs-lookup"><span data-stu-id="0112e-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0112e-104">Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla **Guardar para mi próximo pago** no aparece en **Método de pago** en la página de pago de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="0112e-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="0112e-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="0112e-105">Description</span></span>

<span data-ttu-id="0112e-106">La casilla **Guardar para mi próximo pago** no aparece en la sección **Método de pago** de la página de pago de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="0112e-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="0112e-107">La siguiente ilustración muestra un ejemplo de una página de pago que incluye la casilla **Guardar para mi próximo pago**.</span><span class="sxs-lookup"><span data-stu-id="0112e-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Casilla Guardar para mi próximo pago en el módulo Pagos](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="0112e-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="0112e-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="0112e-110">Verifique que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="0112e-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="0112e-111">Para verificar que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0112e-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="0112e-112">Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="0112e-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="0112e-113">Seleccione la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="0112e-113">Select the online store.</span></span>
1. <span data-ttu-id="0112e-114">En la ficha desplegable **Cuentas de pago**, asegúrese de que el campo **Permitir guardar información de pago en comercio electrónico** esté establecido en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="0112e-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Permitir guardar información de pago en el campo de comercio electrónico en la sede de Commerce](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="0112e-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0112e-116">Additional resources</span></span>

[<span data-ttu-id="0112e-117">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="0112e-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="0112e-118">Guardar los instrumentos de pago en línea con el conector de Adyen</span><span class="sxs-lookup"><span data-stu-id="0112e-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
