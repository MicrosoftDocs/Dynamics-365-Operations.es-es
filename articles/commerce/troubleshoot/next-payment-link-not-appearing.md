---
title: La opción Guardar para mi próximo pago no aparece
description: Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla Guardar para mi próximo pago no aparece en Método de pago en la página de pago de un sitio de comercio electrónico.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018443"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a><span data-ttu-id="a7c29-103">La opción "Guardar para mi próximo pago" no aparece</span><span class="sxs-lookup"><span data-stu-id="a7c29-103">"Save for my next payment" option doesn't appear</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7c29-104">Este tema proporciona una guía de solución de problemas que puede ayudar cuando la casilla **Guardar para mi próximo pago** no aparece en **Método de pago** en la página de pago de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7c29-104">This topic provides troubleshooting guidance that can help when the **Save for my next payment** check box doesn't appear under **Payment method** on an e-commerce site's checkout page.</span></span>

## <a name="description"></a><span data-ttu-id="a7c29-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7c29-105">Description</span></span>

<span data-ttu-id="a7c29-106">La casilla **Guardar para mi próximo pago** no aparece en la sección **Método de pago** de la página de pago de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="a7c29-106">The **Save for my next payment** check box doesn't appear in the **Payment method** section on an e-commerce site's checkout page.</span></span>

<span data-ttu-id="a7c29-107">La siguiente ilustración muestra un ejemplo de una página de pago que incluye la casilla **Guardar para mi próximo pago**.</span><span class="sxs-lookup"><span data-stu-id="a7c29-107">The following illustration shows an example of a checkout page that includes the **Save for my next payment** check box.</span></span>

![Casilla Guardar para mi próximo pago en el módulo Pagos](media/payment-module-save-payment.jpg)

## <a name="resolution"></a><span data-ttu-id="a7c29-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="a7c29-109">Resolution</span></span>

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a><span data-ttu-id="a7c29-110">Verifique que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="a7c29-110">Verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters</span></span>

<span data-ttu-id="a7c29-111">Para verificar que el conector de Dynamics 365 Payment para Adyen esté configurado correctamente en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a7c29-111">To verify that the Dynamics 365 Payment Connector for Adyen is correctly configured in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a7c29-112">Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="a7c29-112">Go to **Retail and Commerce \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="a7c29-113">Seleccione la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="a7c29-113">Select the online store.</span></span>
1. <span data-ttu-id="a7c29-114">En la ficha desplegable **Cuentas de pago**, asegúrese de que el campo **Permitir guardar información de pago en comercio electrónico** esté establecido en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="a7c29-114">On the **Payment accounts** FastTab, make sure that the **Allow saving payment information in e-commerce** field is set to **True**.</span></span>

![Permitir guardar información de pago en el campo de comercio electrónico en la sede de Commerce](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a><span data-ttu-id="a7c29-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a7c29-116">Additional resources</span></span>

[<span data-ttu-id="a7c29-117">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="a7c29-117">Payment module</span></span>](../payment-module.md)

[<span data-ttu-id="a7c29-118">Guardar los instrumentos de pago en línea con el conector de Adyen</span><span class="sxs-lookup"><span data-stu-id="a7c29-118">Saving online payment instruments with the Adyen connector</span></span>](../dev-itpro/adyen-connector-listPI.md)
