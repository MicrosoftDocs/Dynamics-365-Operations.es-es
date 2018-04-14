---
title: Distribuciones contables y asientos del subdiario contable para las facturas de proveedor
description: "Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor. Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 510e3ac8bbec891436eaf6849dfe00b68ba2eb40
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a><span data-ttu-id="509d9-104">Distribuciones contables y asientos del subdiario contable para las facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="509d9-104">Accounting distributions and subledger journal entries for vendor invoices</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="509d9-105">Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="509d9-106">Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables.</span><span class="sxs-lookup"><span data-stu-id="509d9-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="509d9-107">Distribuciones contables</span><span class="sxs-lookup"><span data-stu-id="509d9-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="509d9-108">Puede usar los siguientes botones de la página Factura de proveedor para ver y para modificar probablemente las distribuciones contables de cada importe de la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="509d9-109">**Distribuir importes**: permite ver y modificar las distribuciones contables de una línea individual y todas las líneas secundarias, como impuestos o gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="509d9-110">También puede ver y modificar distribuciones contables para la línea secundaria directamente desde la página Transacciones de impuestos o la página Transacciones de gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="509d9-111">Modifique los importes de encabezado de la factura del proveedor, como gastos o importes de redondeo de divisa.</span><span class="sxs-lookup"><span data-stu-id="509d9-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="509d9-112">Modifique los importes de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="509d9-113">**Ver distribuciones**: permite ver las distribuciones contables para todas las líneas del documento.</span><span class="sxs-lookup"><span data-stu-id="509d9-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="509d9-114">No se pueden modificar las distribuciones contables desde esta vista.</span><span class="sxs-lookup"><span data-stu-id="509d9-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="509d9-115">Permite ver los importes de línea y encabezado.</span><span class="sxs-lookup"><span data-stu-id="509d9-115">View header and line amounts.</span></span>

<span data-ttu-id="509d9-116">Si la factura de proveedor hace referencia a un pedido de compra, puede dividir y modificar distribuciones contables para las líneas que contienen un artículo que no sea se mantiene en existencias.</span><span class="sxs-lookup"><span data-stu-id="509d9-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="509d9-117">Si la línea de factura de proveedor no hace referencia a una línea de pedido de compra, también puede eliminar una distribución contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="509d9-118">No puede dividir o eliminar líneas para gastos, impuestos y descuentos de línea.</span><span class="sxs-lookup"><span data-stu-id="509d9-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="509d9-119">Puede modificar la cuenta contable, pero no puede cambiar los importes o porcentajes.</span><span class="sxs-lookup"><span data-stu-id="509d9-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="509d9-120">Si la línea principal contiene un artículo no mantenido en existencias y se dividen las distribuciones contables, la línea secundaria se dividirá automáticamente para coincidir con las dimensiones financieras de la línea principal.</span><span class="sxs-lookup"><span data-stu-id="509d9-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="509d9-121">Las distribuciones contables de la línea secundaria no se pueden dividir o eliminar adicionalmente, pero según la configuración de la línea secundaria, es posible que pueda modificar la cuenta contable para las distribuciones contables de la línea secundaria.</span><span class="sxs-lookup"><span data-stu-id="509d9-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="509d9-122">Distribución de importes</span><span class="sxs-lookup"><span data-stu-id="509d9-122">Distributing amounts</span></span>
<span data-ttu-id="509d9-123">Cuando se especifica una factura de proveedor, cada importe se distribuirá del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="509d9-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="509d9-124">Tipo de línea de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="509d9-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="509d9-125">Orden de prioridad que determina desde dónde se muestra la cuenta principal</span><span class="sxs-lookup"><span data-stu-id="509d9-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="509d9-126">Orden de prioridad que determina que dimensión financiera se visualiza</span><span class="sxs-lookup"><span data-stu-id="509d9-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="509d9-127">Producto mantenido en existencias</span><span class="sxs-lookup"><span data-stu-id="509d9-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-128">La distribución contable para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-129">El campo Cuenta principal cuando está seleccionado Gasto de compra para el producto en la página Registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-130">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-131">Use los valores de la dimensión financiera predeterminados en la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-132">Una categoría de compras o un producto que no se mantiene en existencias</span><span class="sxs-lookup"><span data-stu-id="509d9-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-133">La distribución contable para la línea de pedido de compra, si la línea de factura de proveedor hace referencia a una línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-134">El campo Cuenta principal cuando está seleccionado Gasto de compra para gasto en la página Registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-135">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-136">Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</span><span class="sxs-lookup"><span data-stu-id="509d9-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="509d9-137">Use los valores de la dimensión financiera predeterminados en la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="509d9-138">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-139">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509d9-140">Activo fijo</span><span class="sxs-lookup"><span data-stu-id="509d9-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-141">La distribución contable para la línea de pedido de compra, si la línea de factura de proveedor hace referencia a una línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-142">Si Adquisición está seleccionado en el campo Tipo de transacción del formulario Factura de proveedor, el campo Cuenta principal cuando Adquisición está seleccionado en la página Perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="509d9-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="509d9-143">Si Ajuste de adquisición está seleccionado en el campo Tipo de transacción, el campo Cuenta principal cuando Ajuste de adquisición está seleccionado en la página Perfiles de contabilización de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="509d9-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-144">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-145">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-146">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-147">Proyecto definido en la línea de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="509d9-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-148">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-149">Si Saldo está seleccionado en el campo Registrar costes - Artículo en la página Grupos de proyectos, el campo Cuenta principal cuando Coste está seleccionado en la página Configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="509d9-150">Si Pérdidas y ganancias está seleccionado en el campo Registrar costes - Artículo en la página Grupos de proyectos, el campo Cuenta principal cuando Coste - artículo está seleccionado en la página Configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-151">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509d9-152">Descuento de línea</span><span class="sxs-lookup"><span data-stu-id="509d9-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-153">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-154">El campo Cuenta principal cuando Descuento se selecciona en la página Registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="509d9-155">Si una cuenta principal para un descuento no se define en el perfil de registro, la distribución contable del precio total de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-156">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-157">Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-158">Use los valores de dimensión financiera predeterminados para la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-159">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-160">Cargo de compra, que se especifica en la ficha Precio y descuento de la línea de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="509d9-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-161">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-162">La distribución contable del precio total de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-163">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-164">Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509d9-165">Gastos de línea</span><span class="sxs-lookup"><span data-stu-id="509d9-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-166">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-167">Si Cuenta contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de débito en la página Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="509d9-168">Si se selecciona Artículo en el campo Tipo de débito del formulario Código de gastos, la distribución contable para el precio total de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-169">Si Cliente/Proveedor contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de crédito en la página Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-170">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-171">Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-172">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-173">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-174">Impuestos, con la siguiente condición:</span><span class="sxs-lookup"><span data-stu-id="509d9-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="509d9-175">La opción Aplicar reglas impositivas de EE. UU. está seleccionada en la página Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="509d9-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="509d9-176">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-177">La distribución contable del precio total o cargo.</span><span class="sxs-lookup"><span data-stu-id="509d9-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-178">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-179">Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-180">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509d9-181">Impuestos, con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="509d9-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="509d9-182">La opción Aplicar reglas impositivas de EE. UU. está sin seleccionar en la página Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="509d9-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="509d9-183">El campo IVA de importación para el grupo de impuestos no está seleccionado en la página Grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="509d9-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="509d9-184">Si el importe de impuestos es recuperable, el campo Impuestos soportados en la página Grupos de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="509d9-185">Si el importe de impuestos no puede recuperarse, el precio total o la distribución contable para el cargo.</span><span class="sxs-lookup"><span data-stu-id="509d9-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-186">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-187">Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-188">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-189">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-190">Impuestos, con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="509d9-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="509d9-191">La opción Aplicar reglas impositivas de EE. UU. está sin seleccionar en la página Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="509d9-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="509d9-192">El campo IVA de importación para el grupo de impuestos está seleccionado en la página Grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="509d9-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="509d9-193">Si el importe de impuestos es recuperable, el campo Impuestos soportados en la página Grupos de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="509d9-194">Si el importe de impuestos no es recuperable, el campo Utilizar gasto de impuesto en la página Grupos de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-195">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-196">Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-197">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-198">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="509d9-199">Cargo de encabezado</span><span class="sxs-lookup"><span data-stu-id="509d9-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-200">Si Cuenta contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de débito en la página Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="509d9-201">Si Cliente/Proveedor contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de crédito en la página Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="509d9-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-202">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-203">Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</span><span class="sxs-lookup"><span data-stu-id="509d9-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="509d9-204">Use los valores de la plantilla predeterminada de la dimensión financiera del encabezado de la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="509d9-205">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-206">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="509d9-207">Descuento de encabezado</span><span class="sxs-lookup"><span data-stu-id="509d9-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="509d9-208">El campo Cuenta principal para el tipo de registro Descuento de factura de proveedor en la página Cuentas para transacciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="509d9-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="509d9-209">Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="509d9-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="509d9-210">Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-211">Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="509d9-212">Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="509d9-213">Distribución de impuestos</span><span class="sxs-lookup"><span data-stu-id="509d9-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="509d9-214">Las distribuciones contables para los impuestos no se pueden crear hasta que se calculen los impuestos.</span><span class="sxs-lookup"><span data-stu-id="509d9-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="509d9-215">Para calcular los impuestos, debe completar una de las tareas que se describen a continuación en la página Factura de proveedor:</span><span class="sxs-lookup"><span data-stu-id="509d9-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="509d9-216">Ver el total de la factura.</span><span class="sxs-lookup"><span data-stu-id="509d9-216">View the invoice total.</span></span>
-   <span data-ttu-id="509d9-217">Ver los impuestos.</span><span class="sxs-lookup"><span data-stu-id="509d9-217">View the sales tax.</span></span>
-   <span data-ttu-id="509d9-218">Ver el subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-218">View the subledger journal.</span></span>
-   <span data-ttu-id="509d9-219">Vea las distribuciones contables para la factura de proveedor completa.</span><span class="sxs-lookup"><span data-stu-id="509d9-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="509d9-220">Configuración de la factura de proveedor en espera.</span><span class="sxs-lookup"><span data-stu-id="509d9-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="509d9-221">Registre la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="509d9-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="509d9-222">Subdiarios contables para facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="509d9-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="509d9-223">Antes de registrar una factura de proveedor, puede ver el asiento contable completo de la factura, que incluye débitos y créditos, para comprobar que la factura se está registrando en las cuentas correctas.</span><span class="sxs-lookup"><span data-stu-id="509d9-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="509d9-224">Esta visualización del asiento contable completo se denomina subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="509d9-225">Si el asiento del subdiario contable es incorrecto cuando obtiene la vista previa antes de registrar en el diario la factura de proveedor, no puede modificar el asiento del subdiario contable.</span><span class="sxs-lookup"><span data-stu-id="509d9-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="509d9-226">En lugar de ello, se deber modificar las distribuciones contables o el perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="509d9-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="509d9-227">Las distribuciones contables se usan para definir un lado del asiento contable, el débito o el crédito.</span><span class="sxs-lookup"><span data-stu-id="509d9-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="509d9-228">El asiento contable del subdiario contable de contrapartida se crea mediante perfiles de registro, por ejemplo, de cuenta de proveedor o impuestos.</span><span class="sxs-lookup"><span data-stu-id="509d9-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>






