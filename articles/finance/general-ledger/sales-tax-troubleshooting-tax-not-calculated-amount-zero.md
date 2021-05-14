---
title: El impuesto no está calculado o el importe del impuesto es cero
description: Este tema proporciona información para la resolución de problemas que puede resultar útil cuando el importe del impuesto es 0 (cero) o no se calcula el impuesto.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ead979081692d4dcee9812c89f5f10c7879d3f7e
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947704"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="e50a2-103">El impuesto no está calculado o el importe del impuesto es cero</span><span class="sxs-lookup"><span data-stu-id="e50a2-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e50a2-104">Una transacción puede tener un importe de línea que no sea 0 (cero), pero puede ser que el impuesto no se ha calculado o que el importe del impuesto calculado es 0.</span><span class="sxs-lookup"><span data-stu-id="e50a2-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="e50a2-105">Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e50a2-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="e50a2-106">Verifique que los códigos de impuestos estén seleccionados correctamente por la transacción</span><span class="sxs-lookup"><span data-stu-id="e50a2-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="e50a2-107">Si la transacción no selecciona los códigos de impuestos correctos, o si no selecciona ningún código de impuestos, los impuestos no se calcularán sobre ella.</span><span class="sxs-lookup"><span data-stu-id="e50a2-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="e50a2-108">Siga estos pasos para verificar que los códigos de impuestos estén seleccionados correctamente por la transacción.</span><span class="sxs-lookup"><span data-stu-id="e50a2-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="e50a2-109">En la línea de transacción, en la ficha desplegable **Detalles de línea**, en la pestaña **Configuración**, en la sección **Impuesto**, verifique que los grupos de impuestos correctos estén seleccionados en los campos **Grupo de impuestos de artículos** y **Grupo de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="e50a2-110">Si no están seleccionados los grupos de impuestos correctos, selecciónelos.</span><span class="sxs-lookup"><span data-stu-id="e50a2-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="e50a2-111">[![Campos Grupos de impuestos de artículos y Grupo de impuestos](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="e50a2-112">Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="e50a2-113">Seleccione el grupo de impuestos apropiado y luego, en la ficha desplegable **Configuración**, anote el código de impuestos en el campo **Código de impuesto**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="e50a2-114">[![Página de grupos de impuestos](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="e50a2-115">Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos de artículos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="e50a2-116">Seleccione el grupo de impuestos del artículo apropiado y, a continuación, en la ficha desplegable **Configuración**, verifique que el código de impuestos del campo **Código de impuesto** coincide con el código de impuestos del grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e50a2-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="e50a2-117">[![Página de grupos de impuestos de artículos](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="e50a2-118">Si los códigos de impuestos no coinciden, actualice el código de impuestos para uno de los grupos.</span><span class="sxs-lookup"><span data-stu-id="e50a2-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="e50a2-119">Verificar que los códigos de impuestos seleccionados no sean de tipo exento y que tengan el valor de tipo impositivo correcto</span><span class="sxs-lookup"><span data-stu-id="e50a2-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="e50a2-120">Si los códigos de impuestos son de tipo exento o si el tipo impositivo es 0 (cero), el resultado del cálculo de impuestos será 0.</span><span class="sxs-lookup"><span data-stu-id="e50a2-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="e50a2-121">Siga estos pasos para determinar si los códigos de impuestos seleccionados están exentos y para verificar que se les aplique el tipo impositivo correcto.</span><span class="sxs-lookup"><span data-stu-id="e50a2-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="e50a2-122">Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="e50a2-123">Seleccione el grupo de impuestos apropiado y luego, en la ficha desplegable **Configuración**, verifique que está desactivada la casilla **Exento**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="e50a2-124">Si está seleccionado, elimínelo.</span><span class="sxs-lookup"><span data-stu-id="e50a2-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="e50a2-125">[![Casilla de exento en la página de grupos de impuestos](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="e50a2-126">Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="e50a2-127">Seleccione el código de impuesto apropiado y luego verifique que el valor del tipo impositivo en el campo **Valor** no sea 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="e50a2-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="e50a2-128">Si es 0, actualice el campo para que esté configurado con ell tipo impositivo correcto.</span><span class="sxs-lookup"><span data-stu-id="e50a2-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="e50a2-129">[![Campo Valor en la página de valores de código de impuesto](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="e50a2-130">Determinar si cero es el importe de impuestos correcto</span><span class="sxs-lookup"><span data-stu-id="e50a2-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="e50a2-131">En algunos escenarios, un importe de 0 (cero) es correcto.</span><span class="sxs-lookup"><span data-stu-id="e50a2-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="e50a2-132">Siga estos pasos para determinar si 0 es el importe de impuestos correcto para su transacción.</span><span class="sxs-lookup"><span data-stu-id="e50a2-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="e50a2-133">Vaya a **Contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de Contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="e50a2-134">En la pestaña **Impuesto**, en el campo **Método de cálculo**, verifique que está seleccionado **Total**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="e50a2-135">[![Campo de método de cálculo en la página Parámetros de contabilidad general](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="e50a2-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="e50a2-136">Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="e50a2-137">Seleccione el código de impuesto apropiado, seleccione **Cálculo** \> **Base marginal** y verifique que la base marginal esté establecida en **Importe neto del saldo de la factura** o **Total de factura incluidos otros importes de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="e50a2-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="e50a2-138">Para obtener más información, consulte el [Total de factura incluidos otros importes de impuestos](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="e50a2-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="e50a2-139">Si están establecidos los valores correctos en los pasos 2 y 4, determine si el importe total de la transacción es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="e50a2-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="e50a2-140">Si el importe total es 0, el resultado esperado es un importe de impuestos de 0.</span><span class="sxs-lookup"><span data-stu-id="e50a2-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="e50a2-141">Debido a que el cálculo de impuestos se basa en el importe total del saldo de la factura, y ese importe no va línea por línea, el importe de impuestos de 0 se asignará a cada línea después del cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e50a2-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="e50a2-142">Determinar si existe personalización</span><span class="sxs-lookup"><span data-stu-id="e50a2-142">Determine whether customization exists</span></span>

<span data-ttu-id="e50a2-143">Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización.</span><span class="sxs-lookup"><span data-stu-id="e50a2-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="e50a2-144">Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.</span><span class="sxs-lookup"><span data-stu-id="e50a2-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
