---
title: "Métodos de cálculo de impuestos en el campo Origen"
description: "Este artículo explica las opciones del campo Origen en la página de códigos de impuestos y cómo se calculan los impuestos en función de la opción seleccionada para un código de impuestos."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: f5683b8b3e5457a05e5039876eed40357ae84e4b
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="a77e5-103">Métodos de cálculo de impuestos en el campo Origen</span><span class="sxs-lookup"><span data-stu-id="a77e5-103">Sales tax calculation methods in the Origin field</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="a77e5-104">Este artículo explica las opciones del campo Origen en la página de códigos de impuestos y cómo se calculan los impuestos en función de la opción seleccionada para un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="a77e5-105">Para cada código de impuestos que cree en la página de códigos de impuestos, debe seleccionar el método de cálculo que se aplica al importe base del impuesto en el campo Origen.</span><span class="sxs-lookup"><span data-stu-id="a77e5-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="a77e5-106">Porcentaje del importe neto</span><span class="sxs-lookup"><span data-stu-id="a77e5-106">Percentage of net amount</span></span>
<span data-ttu-id="a77e5-107">El método de cálculo de porcentaje del importe neto es el valor predeterminado del campo Origen.</span><span class="sxs-lookup"><span data-stu-id="a77e5-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="a77e5-108">Los impuestos se calculan como un porcentaje del importe de compra o de venta, sin incluir otros impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="a77e5-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a77e5-109">Example</span></span>

<span data-ttu-id="a77e5-110">El índice de impuestos es 25%.</span><span class="sxs-lookup"><span data-stu-id="a77e5-110">The tax rate is 25%.</span></span> <span data-ttu-id="a77e5-111">La línea de factura muestra una cantidad de 10 artículos a 1,00 cada uno, y al cliente se le ofrece un descuento de línea del 10%.</span><span class="sxs-lookup"><span data-stu-id="a77e5-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="a77e5-112">Importe neto: (10 x 1,00) - 10% = 9,00 Impuestos: 9,00 x 25 % = 2,25 Importe total: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="a77e5-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="a77e5-113"> Porcentaje del importe bruto</span><span class="sxs-lookup"><span data-stu-id="a77e5-113">Percentage of gross amount</span></span>
<span data-ttu-id="a77e5-114">Si selecciona el método de porcentaje del importe bruto, los impuestos se calculan como un porcentaje del importe bruto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="a77e5-115">El importe bruto es el importe neto de línea más todos los impuestos y las cuotas para la línea, excepto impuestos con origen = porcentaje del importe bruto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="a77e5-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a77e5-116">Example</span></span>

<span data-ttu-id="a77e5-117">La autoridad fiscal ha impuesto aranceles especiales sobre un artículo.</span><span class="sxs-lookup"><span data-stu-id="a77e5-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="a77e5-118">Los importes de aranceles se agregan al importe neto antes de calcular los impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="a77e5-119">Dados los códigos de impuestos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a77e5-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="a77e5-120">ARANCEL 1 = 10 %, con el método de cálculo de porcentaje del importe neto</span><span class="sxs-lookup"><span data-stu-id="a77e5-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="a77e5-121">ARANCEL 2 = 20 %, con el método de cálculo de porcentaje del importe neto</span><span class="sxs-lookup"><span data-stu-id="a77e5-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="a77e5-122">IMPUESTOS = 25 %, con el método de cálculo de porcentaje del importe bruto</span><span class="sxs-lookup"><span data-stu-id="a77e5-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="a77e5-123">Si el importe neto es 10,00, entonces ARANCEL 1 es 1,00 (10,00 x 10 %) y ARANCEL 2 = 2,00 (10,00 x 20 %).</span><span class="sxs-lookup"><span data-stu-id="a77e5-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="a77e5-124">Los importes serían los siguientes: Importe bruto: Importe neto + Importe ARANCEL 1 + Importe ARANCEL 2 (10,00 + 1,00 + 2,00) = 13,00 IMPUESTOS = 13,00 x 25 % = 3,25 Total de ARANCELES e IMPUESTOS: 1,00 + 2,00 + 3,25 = 6,25 Importe total: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="a77e5-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>
| <span data-ttu-id="a77e5-125">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a77e5-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a77e5-126">Solo un código de impuestos con origen = el porcentaje del importe bruto se puede usar para una transacción.</span><span class="sxs-lookup"><span data-stu-id="a77e5-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="a77e5-127">Si se determina más de un código de impuesto de este tipo para una transacción, se mostrará un error acerca de que los impuestos no se pueden calcular.</span><span class="sxs-lookup"><span data-stu-id="a77e5-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |

 
<a name="percentage-of-sales-tax"></a><span data-ttu-id="a77e5-128">Porcentaje de impuestos</span><span class="sxs-lookup"><span data-stu-id="a77e5-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="a77e5-129">Al seleccionar Porcentaje de impuestos en el campo Origen, los impuestos se calculan como un porcentaje de los impuestos seleccionados en el campo Impuestos sobre impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="a77e5-130">Los impuestos seleccionados en el campo Impuestos sobre impuestos se calculan en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a77e5-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="a77e5-131">Los segundos impuestos se calculan a continuación en función del primer importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="a77e5-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a77e5-132">Example</span></span>

<span data-ttu-id="a77e5-133">Dados los códigos de impuestos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a77e5-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="a77e5-134">ARANCEL 1 = 10 %, con el método de porcentaje del importe neto</span><span class="sxs-lookup"><span data-stu-id="a77e5-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="a77e5-135">ARANCEL 2 = 20 %, con el método de porcentaje de impuestos, con Arancel 1 en el campo Impuestos sobre impuestos</span><span class="sxs-lookup"><span data-stu-id="a77e5-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="a77e5-136">IMPUESTOS = 25 %, con el método de porcentaje del importe bruto</span><span class="sxs-lookup"><span data-stu-id="a77e5-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="a77e5-137">Importe neto: 10,00 ARANCEL 1: 10,00 x 10 % = 1,00 ARANCEL 2: 1,00 x 20 % = 0,20 Importe bruto: 10,00 + 1,00 + 0,20 = 11,20 IMPUESTOS: 11,20 x 25 % = 2,80 Total de ARANCELES e IMPUESTOS: 1,00 + 0,20 + 2,80 = 4,00 Importe total: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="a77e5-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>
| <span data-ttu-id="a77e5-138">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a77e5-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a77e5-139">Los impuestos de varios niveles en los cálculos de los impuestos no son posibles.</span><span class="sxs-lookup"><span data-stu-id="a77e5-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="a77e5-140">Los impuestos no se pueden calcular sobre un impuesto que ya se ha calculado sobre otro impuesto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="a77e5-141">Los impuestos de un único nivel dentro de códigos de impuestos se pueden calcular en una transacción.</span><span class="sxs-lookup"><span data-stu-id="a77e5-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="a77e5-142"> Importe por unidad</span><span class="sxs-lookup"><span data-stu-id="a77e5-142">Amount per unit</span></span>
<span data-ttu-id="a77e5-143">Cuando selecciona Importe por unidad en el campo Origen, los impuestos se calculan como un importe fijo por unidad multiplicado por la cantidad especificada en la línea del documento.</span><span class="sxs-lookup"><span data-stu-id="a77e5-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="a77e5-144">Tiene que seleccionar una unidad en el campo Unidad.</span><span class="sxs-lookup"><span data-stu-id="a77e5-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="a77e5-145">El importe por unidad se especifica en la página de valores de código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="a77e5-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="a77e5-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a77e5-146">Example</span></span>

<span data-ttu-id="a77e5-147">El código de impuestos se configura como: 1,20 dólares por unidad = cuadro En una línea de factura de venta se venden 25 cajas de un artículo Los impuestos se calculan como 25 x 1,20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="a77e5-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>
| <span data-ttu-id="a77e5-148">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a77e5-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a77e5-149">Si la transacción se ha especificado en otra unidad distinta de la unidad especificada en el código de impuestos, se convierte automáticamente en función de las conversiones de unidades que se configuran en la página de conversiones de unidades.</span><span class="sxs-lookup"><span data-stu-id="a77e5-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="a77e5-150"> Importe por unidad, opción adicional</span><span class="sxs-lookup"><span data-stu-id="a77e5-150">Amount per unit, additional option</span></span>

<span data-ttu-id="a77e5-151">En la ficha Cálculo, puede seleccionar si un impuesto calculado por importe de unidad se calcula antes que otros códigos de impuestos y se suma al importe neto antes de calcular otros códigos de impuestos con Origen = Porcentaje del importe neto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="a77e5-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a77e5-152">Examples</span></span>

<span data-ttu-id="a77e5-153">Supongamos que calculamos 2 códigos de impuestos en una transacción:</span><span class="sxs-lookup"><span data-stu-id="a77e5-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="a77e5-154">ARANCEL: Origen = Importe por unidad e impuestos, el valor se establece en 5,00 por unidad = uds</span><span class="sxs-lookup"><span data-stu-id="a77e5-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="a77e5-155">IMPUESTOS: Origen = tal y como se muestra en los ejemplos siguientes, el valor se establece en 25 %</span><span class="sxs-lookup"><span data-stu-id="a77e5-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="a77e5-156">Vendemos 1 unidad de un artículo a un precio unitario de 10,00</span><span class="sxs-lookup"><span data-stu-id="a77e5-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="a77e5-157">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a77e5-157">Example 1</span></span>

<span data-ttu-id="a77e5-158">IMPUESTOS: Origen = médodo de porcentaje del importe bruto El cálculo anterior a la opción de impuestos no tiene efecto, ya que IMPUESTOS se calcula como porcentaje del importe bruto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="a77e5-159">ARANCEL: 1 x 5,00 = 5,00 Importe bruto: 10,00 + 5,00 = 15,00 IMPUESTOS: 15,00 x 25 % = 3,75 Total de impuestos: 5,00 + 3,75 = 8,75 Importe total: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="a77e5-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="a77e5-160">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a77e5-160">Example 2</span></span>

<span data-ttu-id="a77e5-161">IMPUESTOS: Origen = Porcentaje del importe neto El cálculo anterior a la opción de impuestos no se selecciona para el cálculo del ARANCEL.</span><span class="sxs-lookup"><span data-stu-id="a77e5-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="a77e5-162">Importe neto: 10,00 ARANCEL: 1 x 5,00 = 5,00 IMPUESTOS: 10,00 x 25 % = 2,50 Total de impuestos: 5,00 + 2,50 = 7,50 Importe total: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="a77e5-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="a77e5-163">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="a77e5-163">Example 3</span></span>

<span data-ttu-id="a77e5-164">IMPUESTOS: Origen = Porcentaje del importe neto El cálculo anterior a la opción de impuestos se selecciona para el cálculo del ARANCEL.</span><span class="sxs-lookup"><span data-stu-id="a77e5-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="a77e5-165">Importe neto: 10,00 ARANCEL: 1 x 5,00 = 5,00 IMPUESTOS: (10,00 + 5,00) x 25 % = 3,75 Total de impuestos: 5,00 + 3,75 = 8,75 Importe total: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="a77e5-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="a77e5-166">Ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="a77e5-166">Example 4</span></span>

<span data-ttu-id="a77e5-167">El resultado del ejemplo 3 y el ejemplo 1 es el mismo, ya que sólo hay un arancel.</span><span class="sxs-lookup"><span data-stu-id="a77e5-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="a77e5-168">Suponga que tiene dos ARANCELES y solo uno de ellos se incluye en el importe neto para el cálculo de impuestos: ARANCEL 1: 5,00, con el método de importe por unidad y se selecciona la opción Calcular antes de impuestos ARANCEL 2: 2,50, con el método de importe por unidad y no se selecciona la opción Calcular antes de impuestos Impuestos: el 25 %, con el método de porcentaje del importe neto Importe neto: 10,00 ARANCEL 1: 1 x 5,00 = 5,00 ARANCEL 2: 1 x 2,50 = 2,50 Importe neto sujeto a impuestos: 10,00 + 5,00 = 15,00 IMPUESTOS: 15,00 x 25 % = 3,75 Total de impuestos, incluidos los aranceles: 5,00 + 2,50 + 3,75 = 11,25 Importe total: 10,00 + 11,25 = 21,25 Se calcula el 25 % de IMPUESTOS para la suma del importe neto (10,00) + el ARANCEL 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="a77e5-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="a77e5-169">El ARANCEL 2 se agrega al importe del impuesto tras calcular el impuesto.</span><span class="sxs-lookup"><span data-stu-id="a77e5-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="a77e5-170"> Porcentaje calculado del importe neto</span><span class="sxs-lookup"><span data-stu-id="a77e5-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="a77e5-171">El porcentaje calculado del importe neto maneja el cálculo del impuesto de manera diferente en función de la configuración del parámetro Importe impuestos incluidos para el documento o el diario.</span><span class="sxs-lookup"><span data-stu-id="a77e5-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="a77e5-172">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a77e5-172">Example 1</span></span>

<span data-ttu-id="a77e5-173">El documento o el diario se establecen en Importe impuestos incluidos = Sí Importe de la línea de transacción: 10,00 Índice de impuestos: 25% Impuestos: Importe de la línea de transacción x índice de impuestos (10,00 x 25 %) = 2,50 Importe base impuestos (importe de origen): Importe de la línea de transacción - impuestos (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="a77e5-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="a77e5-174">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a77e5-174">Example 2</span></span>

<span data-ttu-id="a77e5-175">El documento o el diario se establecen en Importe impuestos incluidos = No Importe de la línea de transacción: 10,00 Índice de impuestos: 25% Impuestos: (Importe de la línea de transacción x índice de impuestos) / (100 - índice de impuestos) (10,00 x 25 %) / (100 % - 25 %) = 3,33 Importe base impuestos (importe de origen): Importe de la línea de transacción = 10,00</span><span class="sxs-lookup"><span data-stu-id="a77e5-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="see-also"></a><span data-ttu-id="a77e5-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a77e5-176">See also</span></span>
--------

[<span data-ttu-id="a77e5-177">Determinación de los índices de impuestos de ventas en función de los campos Base marginal y Método de cálculo</span><span class="sxs-lookup"><span data-stu-id="a77e5-177">Determining sale tax rates based on the Marginal base and Calculation method fields</span></span>](marginal-base-field.md)

[<span data-ttu-id="a77e5-178">Importe completo y opciones de cálculo de intervalo para los códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="a77e5-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)




