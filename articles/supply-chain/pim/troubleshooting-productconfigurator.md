---
title: Solucionar problemas del configurador de productos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con configurador del producto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d17d9f16f01a68da724751273b7d137a0f0f14de
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248772"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="b3e6b-103">Solucionar problemas del configurador de productos</span><span class="sxs-lookup"><span data-stu-id="b3e6b-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="b3e6b-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con el configurador del producto.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="b3e6b-105">El texto del artículo se sobrescribe cuando configuro un producto en una línea de orden de venta.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b3e6b-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b3e6b-106">Issue description</span></span>

<span data-ttu-id="b3e6b-107">Este problema ocurre cuando crea una línea de orden de venta para un artículo configurable y luego modifica el texto del artículo.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="b3e6b-108">Cuando configura el elemento y luego selecciona **Aceptar**, el texto se sobrescribe con el texto estándar.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b3e6b-109">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="b3e6b-109">Issue resolution</span></span>

<span data-ttu-id="b3e6b-110">Este comportamiento es esperado.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-110">This behavior is expected.</span></span> <span data-ttu-id="b3e6b-111">El campo de texto incluye el nombre de la variante, que se completa solo después de configurar la línea.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="b3e6b-112">Por lo tanto, debe cambiar el texto después de haber configurado la línea, no antes.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="b3e6b-113">Los atributos enteros se redondean incorrectamente cuando se calculan los modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b3e6b-114">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="b3e6b-114">Issue description</span></span>

<span data-ttu-id="b3e6b-115">Este problema puede ocurrir cuando realiza la siguiente serie de acciones:</span><span class="sxs-lookup"><span data-stu-id="b3e6b-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="b3e6b-116">Configure los siguientes atributos en un modelo de configuración de producción:</span><span class="sxs-lookup"><span data-stu-id="b3e6b-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="b3e6b-117">Entrada (entero)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-117">Input (integer)</span></span>
    - <span data-ttu-id="b3e6b-118">Porcentaje (decimal)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-118">Percent (decimal)</span></span>
    - <span data-ttu-id="b3e6b-119">Resultado (entero)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-119">Result (integer)</span></span>

2. <span data-ttu-id="b3e6b-120">Cree un cálculo que tenga la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="b3e6b-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="b3e6b-121">*Resultado* = *Entrada* × *Porcentaje* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="b3e6b-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="b3e6b-122">En este caso, el resultado entero no siempre se redondea correctamente.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="b3e6b-123">Por ejemplo, la entrada es 1000 y el porcentaje es 2,40.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="b3e6b-124">Por lo tanto, espera que el resultado entero sea 24, porque el 2,40 por ciento de 1000 es 24 (o 24,00 en forma decimal).</span><span class="sxs-lookup"><span data-stu-id="b3e6b-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="b3e6b-125">En cambio, el resultado se muestra como 23.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="b3e6b-126">Sin embargo, cuando el porcentaje es 2,39, el cálculo se redondea a 24 en lugar de 23.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="b3e6b-127">Cuando el porcentaje es 2,50, el cálculo se redondea a 25, como era previsto.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b3e6b-128">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="b3e6b-128">Issue resolution</span></span>

<span data-ttu-id="b3e6b-129">Este problema se produce debido a la forma en que Microsoft Solver Foundation representa internamente números usando fracciones.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="b3e6b-130">Para el ejemplo anterior, el resultado del cálculo donde el porcentaje es 2,40 se representa como 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="b3e6b-131">Cuando .NET lanza este valor como un número entero, devolverá 23.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="b3e6b-132">Este comportamiento no cambiará, porque otros escenarios dependen de él.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="b3e6b-133">Para el ejemplo anterior, puede solucionar el problema introduciendo un atributo decimal adicional y un cálculo.</span><span class="sxs-lookup"><span data-stu-id="b3e6b-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="b3e6b-134">Por ejemplo, puede configurar los siguientes atributos en un modelo de configuración de producción:</span><span class="sxs-lookup"><span data-stu-id="b3e6b-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="b3e6b-135">Entrada (entero)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-135">Input (integer)</span></span>
- <span data-ttu-id="b3e6b-136">Porcentaje (decimal)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-136">Percent (decimal)</span></span>
- <span data-ttu-id="b3e6b-137">ResultDecimal (decimal)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="b3e6b-138">ResultInteger (entero)</span><span class="sxs-lookup"><span data-stu-id="b3e6b-138">ResultInteger (integer)</span></span>

<span data-ttu-id="b3e6b-139">A continuación, puede agregar los siguientes cálculos:</span><span class="sxs-lookup"><span data-stu-id="b3e6b-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="b3e6b-140">*ResultDecimal* = *Entrada* × *Porcentaje* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="b3e6b-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="b3e6b-141">*ResultInteger* = *ResultDecimal*</span><span class="sxs-lookup"><span data-stu-id="b3e6b-141">*ResultInteger* = *ResultDecimal*</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]