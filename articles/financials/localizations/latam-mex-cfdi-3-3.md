---
title: "Versión 3.3 del diseño CFDI"
description: "Este tema proporciona información sobre la versión 3.3 del diseño Comprobante Fiscal Digital por Internet (CFDI) para México."
author: sndray
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, VendParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2017-12-01
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 149103c7e5fd579b230f49bf26ca4ac838c68431
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="cfdi-layout-version-33"></a><span data-ttu-id="60888-103">Versión 3.3 del diseño CFDI</span><span class="sxs-lookup"><span data-stu-id="60888-103">CFDI layout version 3.3</span></span>

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoice-parameters"></a><span data-ttu-id="60888-104">Parámetros de facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="60888-104">Electronic invoice parameters</span></span>

<span data-ttu-id="60888-105">Si su organización utiliza facturas electrónicas que son validadas y certificadas por un proveedor de servicios de firma digital de terceros (PAC), habilite la facturación electrónica mediante los campos del área **CFDI** de la página **Parámetros de factura electrónica**.</span><span class="sxs-lookup"><span data-stu-id="60888-105">If your organization uses electronic invoices that are validated and certified by a third-party digital signature service provider (PAC), you enable electronic invoicing by using the fields in the **CFDI** area of the **Electronic invoice parameters** page.</span></span>

<span data-ttu-id="60888-106">Los siguientes cambios se introducen en la versión 3.3 del diseño Comprobante Fiscal Digital por Internet (CFDI):</span><span class="sxs-lookup"><span data-stu-id="60888-106">The following changes are introduced in version 3.3 of the Comprobante Fiscal Digital por Internet (CFDI) layout:</span></span>

- <span data-ttu-id="60888-107">**Versión CFDI:** ahora está disponible la versión 3.3.</span><span class="sxs-lookup"><span data-stu-id="60888-107">**CFDI version:** Version 3.3 is now available.</span></span>
- <span data-ttu-id="60888-108">**Algoritmo de codificación de CFDI:** SHA-256.</span><span class="sxs-lookup"><span data-stu-id="60888-108">**CFDI digest algorithm:** SHA-256.</span></span>
- <span data-ttu-id="60888-109">**Archivo de esquema XML de pago de CFDI:** la ruta y el nombre del archivo de esquema que se usa para validar el complemento de pago de CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-109">**CFDI payment XML schema file:** The path and name of the schema file that is used to validate the CFDI payment complement.</span></span>
- <span data-ttu-id="60888-110">**Límites del importe total:** especifica los límites del importe total de entrada y salida que requieren un número de confirmación.</span><span class="sxs-lookup"><span data-stu-id="60888-110">**Total amount limits:** Specify the incoming and outgoing total amount limits that require a confirmation number.</span></span>
- <span data-ttu-id="60888-111">**Códigos de clasificación predeterminados del gobierno:**</span><span class="sxs-lookup"><span data-stu-id="60888-111">**Default government classification codes:**</span></span>

    - <span data-ttu-id="60888-112">**Código de producto SAT:** use esta clasificación para los escenarios donde no se identifica el código de artículo.</span><span class="sxs-lookup"><span data-stu-id="60888-112">**SAT product code** – Use this classification for scenarios where the item code isn't identified.</span></span>
    - <span data-ttu-id="60888-113">**Código de unidad SAT:** use esta clasificación para los escenarios donde no se identifica la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="60888-113">**SAT unit code** – Use this classification for scenarios where the unit of measure isn't identified.</span></span>

## <a name="sat-catalogs"></a><span data-ttu-id="60888-114">Catálogos SAT</span><span class="sxs-lookup"><span data-stu-id="60888-114">SAT catalogs</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="60888-115">Catálogo SAT</span><span class="sxs-lookup"><span data-stu-id="60888-115">SAT catalog</span></span></th>
<th><span data-ttu-id="60888-116">Asignación de Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="60888-116">Microsoft Dynamics 365 for Finance and Operations mapping</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="60888-117">cUsoCFDI</span><span class="sxs-lookup"><span data-stu-id="60888-117">cUsoCFDI</span></span></td>
<td><span data-ttu-id="60888-118">Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Propósito de CFDI</strong> para especificar la lista de clasificaciones de propósito de CFDI definidas por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-118">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Einvoice</strong> &gt; <strong>SAT classifications</strong> &gt; <strong>CFDI purpose</strong> to enter the list of CFDI purpose classifications that are defined by the government.</span></span> <span data-ttu-id="60888-119">Puede especificar la siguiente información: la clasificación de códigos de las autoridades fiscales mexicanas (SAT), la descripción, la versión vigente y la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="60888-119">You can enter the following information: Mexican tax authorities (SAT) code classification, description, effective version, and expiration date.</span></span>

<span data-ttu-id="60888-120">Esta información debe especificarse en el campo <strong>Propósito de CFDI</strong> en el encabezado de transacción de la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-120">This information must be entered in the <strong>CFDI purpose</strong> field on the sales invoice transaction header.</span></span> <span data-ttu-id="60888-121">También puede definir un propósito de CFDI predeterminado por cliente seleccionando <strong>Clientes</strong> y mediante la opción <strong>Factura y entrega</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-121">You can also define a default CFDI purpose per customer by selecting <strong>Customers</strong> and using the <strong>Invoice and delivery</strong> option.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-122">c_Aduana</span><span class="sxs-lookup"><span data-stu-id="60888-122">c_Aduana</span></span></td>
<td><span data-ttu-id="60888-123">No aplicable</span><span class="sxs-lookup"><span data-stu-id="60888-123">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-124">c_ClaveProdServ</span><span class="sxs-lookup"><span data-stu-id="60888-124">c_ClaveProdServ</span></span></td>
<td><span data-ttu-id="60888-125">Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Producto y servicios</strong> para especificar la lista de clasificaciones de códigos de artículos definidas por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-125">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Einvoice</strong> &gt; <strong>SAT classifications</strong> &gt; <strong>Product and services</strong> to enter the list of item code classifications that are defined by the government.</span></span> <span data-ttu-id="60888-126">Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="60888-126">You can enter the following information: SAT code classification, description, effective version, and expiration date.</span></span>

<span data-ttu-id="60888-127">Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:</span><span class="sxs-lookup"><span data-stu-id="60888-127">After the list is created or updated, you can map the related classification in the following master data:</span></span>
<ul>
<li><span data-ttu-id="60888-128"><strong>Parámetros de facturas electrónicas</strong> en clasificaciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="60888-128"><strong>Electronic invoice parameters</strong> in default classifications</span></span></li>
<li><span data-ttu-id="60888-129"><strong>Información del producto</strong> &gt; <strong>Productos emitidos</strong> &gt; <strong>General</strong> &gt; <strong>Facturas electrónicas</strong></span><span class="sxs-lookup"><span data-stu-id="60888-129"><strong>Product information</strong> &gt; <strong>Released products</strong> &gt; <strong>General</strong> &gt; <strong>Electronic invoices</strong></span></span></li>
<li><span data-ttu-id="60888-130"><strong>Clientes</strong> &gt; <strong>Configuración</strong> &gt; <strong>Gastos</strong> &gt; <strong>Código de gastos</strong></span><span class="sxs-lookup"><span data-stu-id="60888-130"><strong>Accounts receivable</strong> &gt; <strong>Setup</strong> &gt; <strong>Charges</strong> &gt; <strong>Charges code</strong></span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="60888-131">c_ClaveUnidad</span><span class="sxs-lookup"><span data-stu-id="60888-131">c_ClaveUnidad</span></span></td>
<td><span data-ttu-id="60888-132">Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Unidad de medida</strong> para especificar la lista de clasificaciones de unidad de medida definidas por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-132">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Einvoice</strong> &gt; <strong>SAT classifications</strong> &gt; <strong>Unit of measures</strong> to enter the list of unit of measure classifications that are defined by the government.</span></span> <span data-ttu-id="60888-133">Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="60888-133">You can enter the following information: SAT code classification, description, effective version, and expiration date.</span></span>

<span data-ttu-id="60888-134">Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:</span><span class="sxs-lookup"><span data-stu-id="60888-134">After the list is created or updated, you can map the related classification in the following master data:</span></span>
<ul>
<li><span data-ttu-id="60888-135"><strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Unidades</strong> &gt; <strong>Unidades</strong> &gt; <strong>Facturas electrónicas</strong></span><span class="sxs-lookup"><span data-stu-id="60888-135"><strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Units</strong> &gt; <strong>Units</strong> &gt; <strong>Electronic invoices</strong></span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="60888-136">c_CodigoPostal</span><span class="sxs-lookup"><span data-stu-id="60888-136">c_CodigoPostal</span></span></td>
<td><span data-ttu-id="60888-137">Esta información se identifica mediante el código postal en el código de dirección del cliente, la empresa u otra dirección relacionada.</span><span class="sxs-lookup"><span data-stu-id="60888-137">This information is identified by the ZIP Code/postal code in the address code of the customer, company, or other related address.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-138">c_FormaPago</span><span class="sxs-lookup"><span data-stu-id="60888-138">c_FormaPago</span></span></td>
<td><span data-ttu-id="60888-139">Se utiliza la información existente en <strong>Clientes</strong> &gt; <strong>Configuración</strong> &gt; <strong>Pago</strong> &gt; <strong>Forma de pago</strong> &gt; <strong>Pago SAT</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-139">Existing information at <strong>Accounts receivable</strong> &gt; <strong>Setup</strong> &gt; <strong>Payment</strong> &gt; <strong>Method of Payment</strong> &gt; <strong>SAT payment</strong> is used.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-140">c_Impuesto</span><span class="sxs-lookup"><span data-stu-id="60888-140">c_Impuesto</span></span></td>
<td><span data-ttu-id="60888-141">Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="60888-141">This information is determined by the <strong>Tax type</strong> value in the sales tax code setup.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-142">c_MetodoPago</span><span class="sxs-lookup"><span data-stu-id="60888-142">c_MetodoPago</span></span></td>
<td><span data-ttu-id="60888-143">Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Forma de pago</strong> para especificar la lista de formas de pago definidas por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-143">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Einvoice</strong> &gt; <strong>SAT classifications</strong> &gt; <strong>Method of payment</strong> to enter the list of methods of payment that are defined by the government.</span></span>

<span data-ttu-id="60888-144">Esta información debe especificarse en el campo <strong>Tipo de pago</strong> en el encabezado de transacción de la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-144">This information must be entered in the <strong>Payment type</strong> field on the sales invoice transaction header.</span></span> <span data-ttu-id="60888-145">También puede definir el tipo de pago predeterminado por cliente seleccionando <strong>Clientes</strong> y mediante la opción <strong>Factura y entrega</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-145">You can also define the default payment type per customer by selecting <strong>Customers</strong> and using the <strong>Invoice and delivery</strong> option.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-146">cMoneda</span><span class="sxs-lookup"><span data-stu-id="60888-146">cMoneda</span></span></td>
<td><span data-ttu-id="60888-147">Esta información se identifica mediante el valor <strong>Código de divisa</strong> que se configura en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="60888-147">This information is identified by the <strong>Currency code</strong> value that is configured in Finance and Operations.</span></span>

<span data-ttu-id="60888-148">El gobierno define la variación del tipo de cambio que se permite.</span><span class="sxs-lookup"><span data-stu-id="60888-148">The government defines the exchange rate variation that is allowed.</span></span> <span data-ttu-id="60888-149">Este valor debe configurarse en <strong>Contabilidad general</strong> &gt; <strong>Configuración</strong> &gt; <strong>Divisas</strong> &gt; <strong>Facturas electrónicas</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-149">This value must be configured at <strong>General ledger</strong> &gt; <strong>Setup</strong> &gt; <strong>Currencies</strong> &gt; <strong>Electronic invoices</strong>.</span></span> <span data-ttu-id="60888-150">Puede especificar el valor <strong>Límite de variación de tipo de cambio</strong> por divisa.</span><span class="sxs-lookup"><span data-stu-id="60888-150">You can enter the <strong>Exchange rate variation limit</strong> value per currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-151">c_NumPedimentoAduana</span><span class="sxs-lookup"><span data-stu-id="60888-151">c_NumPedimentoAduana</span></span></td>
<td><span data-ttu-id="60888-152">Se utiliza la información existente en el campo <strong>Número personalizado</strong> en la línea de transacción de la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-152">Existing information in the <strong>Custom Number</strong> field on the sales invoice transaction line is used.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-153">cPais</span><span class="sxs-lookup"><span data-stu-id="60888-153">cPais</span></span></td>
<td><span data-ttu-id="60888-154">Esta información se identifica mediante el valor <strong>Código de país</strong> que se configura en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="60888-154">This information is identified by the <strong>Country code</strong> value that is configured in Finance and Operations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-155">c_PatenteAduanal</span><span class="sxs-lookup"><span data-stu-id="60888-155">c_PatenteAduanal</span></span></td>
<td><span data-ttu-id="60888-156">No aplicable</span><span class="sxs-lookup"><span data-stu-id="60888-156">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-157">cRegimenFiscal</span><span class="sxs-lookup"><span data-stu-id="60888-157">cRegimenFiscal</span></span></td>
<td><span data-ttu-id="60888-158">Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Régimen de impuestos</strong> para especificar la lista de clasificaciones de régimen de impuestos definidas por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-158">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Einvoice</strong> &gt; <strong>SAT classifications</strong> &gt; <strong>Tax regime</strong> to enter the list of tax regime classifications that are defined by the government.</span></span> <span data-ttu-id="60888-159">Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="60888-159">You can enter the following information: SAT code classification, description, effective version, and expiration date.</span></span>

<span data-ttu-id="60888-160">Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:</span><span class="sxs-lookup"><span data-stu-id="60888-160">After the list is created or updated, you can map the related classification in the following master data:</span></span>
<ul>
<li><span data-ttu-id="60888-161">Selecciones <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Organización</strong> &gt; <strong>Entidades jurídicas</strong> &gt; <strong>Registro de impuestos</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-161">Select <strong>Organization administration</strong> &gt; <strong>Setup</strong> &gt; <strong>Organization</strong> &gt; <strong>Legal entities</strong> &gt; <strong>Tax registration</strong>.</span></span> <span data-ttu-id="60888-162">A continuación, puede seleccionar el régimen de impuestos.</span><span class="sxs-lookup"><span data-stu-id="60888-162">You can then select the tax regime.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="60888-163">cTasaCuota</span><span class="sxs-lookup"><span data-stu-id="60888-163">cTasaCuota</span></span></td>
<td><span data-ttu-id="60888-164">Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="60888-164">This information is determined by the <strong>Tax type</strong> value in the sales tax code setup.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-165">cTipodeComprobante</span><span class="sxs-lookup"><span data-stu-id="60888-165">cTipodeComprobante</span></span></td>
<td><span data-ttu-id="60888-166">Esta información se determina por el tipo de transacción de la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-166">This information is determined by the type of sales invoice transaction.</span></span> <span data-ttu-id="60888-167">Se admiten los siguientes tipos para esta función:</span><span class="sxs-lookup"><span data-stu-id="60888-167">The following types are supported for this feature:</span></span>
<ul>
<li><span data-ttu-id="60888-168">Entrante</span><span class="sxs-lookup"><span data-stu-id="60888-168">Incoming</span></span></li>
<li><span data-ttu-id="60888-169">Saliente</span><span class="sxs-lookup"><span data-stu-id="60888-169">Outgoing</span></span></li>
<li><span data-ttu-id="60888-170">Pago</span><span class="sxs-lookup"><span data-stu-id="60888-170">Payment</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="60888-171">cTipoFactor</span><span class="sxs-lookup"><span data-stu-id="60888-171">cTipoFactor</span></span></td>
<td><span data-ttu-id="60888-172">Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="60888-172">This information is determined by the <strong>Tax type</strong> value in the sales tax code setup.</span></span>

<span data-ttu-id="60888-173">La configuración del código de impuestos identifica el tipo <strong>Exento</strong> como <strong>índice de impuestos = 0.00</strong> y <strong>tipo de impuestos = IVA</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-173">The sales tax code configuration identifies the <strong>Exempt</strong> type as <strong>tax rate = 0.00</strong> and <strong>tax type = VAT</strong>.</span></span> <span data-ttu-id="60888-174">Identifica el tipo <strong>TASA</strong> como <strong>tasa fiscal &lt;&gt; 0.00</strong>.</span><span class="sxs-lookup"><span data-stu-id="60888-174">It identifies the <strong>TASA</strong> type as <strong>tax rate &lt;&gt; 0.00</strong>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="60888-175">cTipoRelacion</span><span class="sxs-lookup"><span data-stu-id="60888-175">cTipoRelacion</span></span></td>
<td><span data-ttu-id="60888-176">Se ha implementado la nueva funcionalidad de referencia CFDI que permite a los usuarios identificar los distintos tipos de relaciones entre los documentos de CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-176">New CFDI reference functionality has been implemented that lets users identify the various types of relations between CFDI documents.</span></span> <span data-ttu-id="60888-177">Algunos de estos tipos de relación se asignan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="60888-177">Some of these relation types are assigned automatically.</span></span> <span data-ttu-id="60888-178">Los usuarios pueden seleccionar manualmente otros tipos de relación en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="60888-178">Users can manually select other relationship types in specific scenarios.</span></span></td>
</tr>
</tbody>
</table>

## <a name="cfdi-reference"></a><span data-ttu-id="60888-179">Referencia CFDI</span><span class="sxs-lookup"><span data-stu-id="60888-179">CFDI reference</span></span>

<span data-ttu-id="60888-180">Según el requisito legal, los usuarios deben poder hacer referencia a una o varias facturas CFDI relacionadas en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="60888-180">Per the legal requirement, users must be able to reference one or more related CFDI invoices in specific scenarios.</span></span> <span data-ttu-id="60888-181">Por ejemplo, es posible que un cliente devuelva artículos si recibió los artículos incorrectos o si un artículo era defectuoso.</span><span class="sxs-lookup"><span data-stu-id="60888-181">For example, a customer might return items if the incorrect item was received, or if an item is defective.</span></span> <span data-ttu-id="60888-182">A continuación, debe crear un pedido de devolución, identificar la factura de ventas original que se envió, e identificar el tipo de relación (**cTipoRelacion**) definido por el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-182">You must then create a return order, identify the original sales invoice that was submitted, and identify the type of relation (**cTipoRelacion**) that is defined by the government.</span></span> <span data-ttu-id="60888-183">En este caso, la relación es **03: Devolución de mercancías**.</span><span class="sxs-lookup"><span data-stu-id="60888-183">In this case, the relation is **03: Goods return**.</span></span>

<span data-ttu-id="60888-184">Antes de registrar una factura de ventas, puede hacer referencia a la factura CFDI relacionada en **Registrar** &gt; **Configuración** &gt; **Referencia CFDI**.</span><span class="sxs-lookup"><span data-stu-id="60888-184">Before you post a sales invoice, you can reference the related CFDI invoice at **Post** &gt; **Setup** &gt; **CFDI reference**.</span></span>

<span data-ttu-id="60888-185">Puede seleccionar la lista de facturas CFDI disponible que se han aprobado, o puede introducir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="60888-185">You can select the available list of CFDI invoices that have been approved, or you can enter the following information:</span></span>

- <span data-ttu-id="60888-186">Identificador único universal (UUID)</span><span class="sxs-lookup"><span data-stu-id="60888-186">Universally unique identifier (UUID)</span></span>
- <span data-ttu-id="60888-187">Tipo de relación</span><span class="sxs-lookup"><span data-stu-id="60888-187">Type of relation</span></span>

<span data-ttu-id="60888-188">Cuando se genera un complemento de pago de CFDI, esta funcionalidad también está disponible en **Diarios de pagos** &gt; **Referencia CFDI**.</span><span class="sxs-lookup"><span data-stu-id="60888-188">When a CFDI payment complement is generated, this functionality is also available at **Payment journals** &gt; **CFDI reference**.</span></span> 

<span data-ttu-id="60888-189">La siguiente información describe cómo se genera un complemento de pago de CFDI cuando se obtiene el pago de un cliente y se aplica a un documento existente de factura CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-189">The following information describes how a CFDI payment complement is generated when payment is collected from a customer and applied to an existing CFDI invoice document.</span></span>

<span data-ttu-id="60888-190">Los complementos de pago CFDI se generan del diario de pagos y del proceso de liquidación bajo las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="60888-190">CFDI payment complements are generated from the payment journal and settlement process under the following conditions:</span></span>

- <span data-ttu-id="60888-191">El diario de pago se liquida con una o más facturas.</span><span class="sxs-lookup"><span data-stu-id="60888-191">The journal payment is settled with one or more invoices.</span></span>
- <span data-ttu-id="60888-192">La liquidación del diario se liquida con una o más facturas.</span><span class="sxs-lookup"><span data-stu-id="60888-192">The journal settlement is settled with one or more invoices.</span></span>
- <span data-ttu-id="60888-193">En la definición del nombre del diario, el tipo de diario se establece en **Pago de cliente**.</span><span class="sxs-lookup"><span data-stu-id="60888-193">In the journal name definition, the journal type is set to **Customer payment**.</span></span>

<span data-ttu-id="60888-194">Una vez registrado el pago del diario o la liquidación del diario, el proceso por lotes de exportación/importación se ejecuta para obtener la aprobación relacionada de PAC (software de terceros).</span><span class="sxs-lookup"><span data-stu-id="60888-194">After the journal payment or journal settlement is posted, the Export/Import batch process is run to get the related approval from PAC (third-party software).</span></span>

<span data-ttu-id="60888-195">Se requiere la siguiente información adicional para el pago de diarios, en función del método de pago que se seleccione:</span><span class="sxs-lookup"><span data-stu-id="60888-195">The following additional information is required for the journal payment, depending on the method of payment that is selected:</span></span>

- <span data-ttu-id="60888-196">Cuenta principal de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="60888-196">Offset main account.</span></span>
- <span data-ttu-id="60888-197">Cuenta bancaria de cliente tercero.</span><span class="sxs-lookup"><span data-stu-id="60888-197">Third-party customer bank account.</span></span>
- <span data-ttu-id="60888-198">Cuenta bancaria de cliente del Registro Federal de Contribuyentes (RFC).</span><span class="sxs-lookup"><span data-stu-id="60888-198">Registro Federal de Contribuyentes (RFC) customer bank account.</span></span> <span data-ttu-id="60888-199">Se ha agregado un nuevo campo a la página **Cuenta bancaria de cliente** para cumplir los requisitos legales establecidos por las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="60888-199">A new field has been added to the **Customer bank account** page to meet the legal requirements that were established by the tax authorities.</span></span>

<span data-ttu-id="60888-200">En función de la solicitud de un cliente, puede usar la consulta de la factura electrónica CFDI para ver, enviar por correo electrónico, exportar o imprimir un complemento de pago de CFDI que se generó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="60888-200">Based on a customer's request, you can use the CFDI electronic invoice inquiry to view, email, export, or print a CFDI payment complement that was previously generated.</span></span> <span data-ttu-id="60888-201">Selecione **Clientes** &gt; **Consultas e informes** &gt; **CFDI (facturas electrónicas)** y, a continuación, seleccione la pestaña **Pago**. La factura electrónica CFDI impresa incluye un código de barras bidimensional de acuerdo con el formato para códigos de respuesta rápida (códigos QR) que se describe en la norma 18004 de la Organización Internacional de Normalización (ISO)/Comisión Electrotécnica Internacional (IEC).</span><span class="sxs-lookup"><span data-stu-id="60888-201">Select **Accounts receivable** &gt; **Inquiries and reports** &gt; **CFDI (electronic invoices)**, and then select the **Payment** tab. The printed CFDI electronic invoice includes a two-dimensional barcode in accordance with the format for Quick Response Codes (QR codes) that is described in the International Organization for Standardization (ISO)/International Electrotechnical Commission (IEC) 18004 standard.</span></span>

## <a name="customer-advance-payments"></a><span data-ttu-id="60888-202">Anticipos del cliente</span><span class="sxs-lookup"><span data-stu-id="60888-202">Customer advance payments</span></span>

<span data-ttu-id="60888-203">Esta sección describe el procesamiento y la configuración de un anticipo del cliente para poder generar y emitir una factura electrónica CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-203">This section describes the processing and setup of an advance customer payment so that a CFDI electronic invoice can be generated and issued.</span></span> <span data-ttu-id="60888-204">Según la definición del gobierno, debe seguirse un procedimiento específico cuando se obtengan anticipos de clientes.</span><span class="sxs-lookup"><span data-stu-id="60888-204">Per the government definition, a specific procedure must be followed when advance payments are collected from customers.</span></span>

1. <span data-ttu-id="60888-205">**Anticipo de CFDI:** se emite una factura electrónica al cliente para el importe del anticipo que se recibió.</span><span class="sxs-lookup"><span data-stu-id="60888-205">**CFDI advance payment** – An electronic invoice is issued to the customer for the amount of the advance that was received.</span></span>
2. <span data-ttu-id="60888-206">**Factura CFDI:** una vez que se realice la operación y se aplique el anticipo, la empresa debe emitir la factura CFDI de la operación y los detalles del UUID del anticipo de CFDI que se emitió en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="60888-206">**CFDI invoice** – After the operation is realized, and the advance payment is applied, the company must issue the CFDI invoice of operation and details of the CFDI advance payment UUID that was issued in step 1.</span></span>
3. <span data-ttu-id="60888-207">**Inversión del anticipo de CFDI:** se emite una factura electrónica para invertir el anticipo que se aplicó.</span><span class="sxs-lookup"><span data-stu-id="60888-207">**CFDI advance payment reverse** – An electronic invoice is issued to reverse the advance payment that was applied.</span></span>

<span data-ttu-id="60888-208">![Proceso de anticipo](./media/mex-advance-payments-cfdi.png "Diagrama que muestra el proceso de anticipo")</span><span class="sxs-lookup"><span data-stu-id="60888-208">![Advance payment process](./media/mex-advance-payments-cfdi.png "Diagram that shows the advance payment process")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60888-209">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="60888-209">Prerequisites</span></span>

<span data-ttu-id="60888-210">Use la funcionalidad para asientos del diario de anticipos para emitir un anticipo de CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-210">You use the functionality for prepayment journal vouchers to issue a CFDI advance payment.</span></span> <span data-ttu-id="60888-211">Antes de poder enviar el anticipo, debe completar los siguientes requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="60888-211">Before you can submit the advance payment, you must complete the following prerequisites.</span></span>

1. <span data-ttu-id="60888-212">Seleccione **Clientes** &gt; **Configuración** &gt; **Perfiles de contabilización del cliente**, y cree un perfil de contabilización para anticipos.</span><span class="sxs-lookup"><span data-stu-id="60888-212">Select **Accounts receivable** &gt; **Setup** &gt; **Customer posting profiles**, and create a posting profile for advance payments.</span></span>
2. <span data-ttu-id="60888-213">Seleccione **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes** &gt; **Impuestos y contabilidad** &gt; **Pago**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="60888-213">Select **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters** &gt; **Ledger and sales tax** &gt; **Payment**, and follow these steps:</span></span>

    1. <span data-ttu-id="60888-214">Seleccione el perfil de contabilización que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="60888-214">Select the posting profile that you created earlier.</span></span>
    2. <span data-ttu-id="60888-215">Si los impuestos se calculan y se registran cuando se registra un asiento de diario de anticipo, seleccione la casilla de verificación **Impuestos sobre el asiento del diario de anticipos**.</span><span class="sxs-lookup"><span data-stu-id="60888-215">If sales tax is calculated and posted when you post a prepayment journal voucher, select the **Sales tax on prepayment journal voucher** check box.</span></span>

## <a name="step-1-issue-a-cfdi-advance-payment"></a><span data-ttu-id="60888-216">Paso 1: Emitir un anticipo de CFDI</span><span class="sxs-lookup"><span data-stu-id="60888-216">Step 1: Issue a CFDI advance payment</span></span>

1. <span data-ttu-id="60888-217">Seleccione **Clientes** &gt; **Diarios** &gt; **Pagos** &gt; **Diario de pagos** para crear el anticipo.</span><span class="sxs-lookup"><span data-stu-id="60888-217">Select **Accounts receivable** &gt; **Journals** &gt; **Payments** &gt; **Payment journal** to create the advance payment.</span></span>
2. <span data-ttu-id="60888-218">Especifique las líneas y la información relacionada.</span><span class="sxs-lookup"><span data-stu-id="60888-218">Enter the lines and the related information.</span></span> <span data-ttu-id="60888-219">Incluya la forma de pago y los códigos de impuestos como corresponda.</span><span class="sxs-lookup"><span data-stu-id="60888-219">Include the method of payment and sales tax codes as appropriate.</span></span>
3. <span data-ttu-id="60888-220">En la pestaña **Pago** , seleccione la casilla de verificación **Asiento del diario de anticipos** .</span><span class="sxs-lookup"><span data-stu-id="60888-220">On the **Payment** tab, select the **Prepayment journal voucher** check box.</span></span>
4. <span data-ttu-id="60888-221">Registre el anticipo.</span><span class="sxs-lookup"><span data-stu-id="60888-221">Post the advance payment.</span></span>
5. <span data-ttu-id="60888-222">Seleccione **Clientes** &gt; **Periódico** &gt; **Facturas electrónicas CFDI** &gt; **Proceso de exportar/importar factura electrónica** para solicitar el sello digital del anticipo de CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-222">Select **Accounts receivable** &gt; **Periodic** &gt; **CFDI electronic invoices** &gt; **Export/Import electronic invoice process** to request the digital stamp of CFDI advance payment.</span></span>
6. <span data-ttu-id="60888-223">Seleccione **Clientes** &gt; **Consulta** &gt; **Diarios** &gt; **Facturas electrónicas FDI**, y seleccione la pestaña **Pago** para consultar el estado del anticipo de CFDI.</span><span class="sxs-lookup"><span data-stu-id="60888-223">Select **Accounts receivable** &gt; **Inquire** &gt; **Journals** &gt; **CFDI electronic invoice**, and then select the **Payment** tab to inquire about the status of the CFDI advance payment.</span></span> <span data-ttu-id="60888-224">Esta transacción se clasifica en el campo **Información del tipo de documento** como **Anticipo**.</span><span class="sxs-lookup"><span data-stu-id="60888-224">This transaction is classified in the **Document type information** field as **Prepayment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="60888-225">Los siguientes criterios se utilizan para identificar las transacciones de anticipo de CFDI en el sistema:</span><span class="sxs-lookup"><span data-stu-id="60888-225">The following criteria are used to identify CFDI advance payment transactions in the system:</span></span>
    >
    > - <span data-ttu-id="60888-226">El tipo de nombre del diario se establece en **Pago de cliente**.</span><span class="sxs-lookup"><span data-stu-id="60888-226">The journal name type is set to **Customer payment**.</span></span>
    > - <span data-ttu-id="60888-227">Se selecciona la casilla de verificación **Asiento del diario de anticipos**.</span><span class="sxs-lookup"><span data-stu-id="60888-227">The **Prepayment journal voucher** check box is selected.</span></span>
    > 
    > <span data-ttu-id="60888-228">Cualquier transacción de pago que no cumpla estos criterios se considera un pago habitual.</span><span class="sxs-lookup"><span data-stu-id="60888-228">Any payment transaction that doesn't meet these criteria is considered a regular payment.</span></span>

## <a name="step-2-issue-a-cfdi-invoice-together-with-details-of-the-advance-payment-that-was-applied"></a><span data-ttu-id="60888-229">Paso 2: Emitir una factura CFDI junto con los detalles del anticipo que se aplicó</span><span class="sxs-lookup"><span data-stu-id="60888-229">Step 2: Issue a CFDI invoice together with details of the advance payment that was applied</span></span>

1. <span data-ttu-id="60888-230">Cree una transacción de factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-230">Create a sales invoice transaction.</span></span>
2. <span data-ttu-id="60888-231">Antes de registrar la factura, puede establecer el anticipo que creó en el [Paso 1: Emitir un anticipo de CFDI](#step-1-issue-a-cfdi-advance-payment).</span><span class="sxs-lookup"><span data-stu-id="60888-231">Before you post the invoice, you can settle the advance payment that you created in [Step 1: Issue a CFDI advance payment](#step-1-issue-a-cfdi-advance-payment).</span></span> <span data-ttu-id="60888-232">Para liquidar el anticipo, utilice la opción **Liquidación de transacción abierta** .</span><span class="sxs-lookup"><span data-stu-id="60888-232">To settle the advance payment, use the **Open transaction settle** option.</span></span>
3. <span data-ttu-id="60888-233">En la página **Registrar**, puede verificar la factura CFDI a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="60888-233">On the **Post** page, you can verify the referenced CFDI invoice.</span></span> <span data-ttu-id="60888-234">La factura se crea automáticamente y el tipo de relación (**cTipoRelacion**) se establece en **07**.</span><span class="sxs-lookup"><span data-stu-id="60888-234">The invoice is created automatically, and the type of relation (**cTipoRelacion**) is set to **07**.</span></span>
4. <span data-ttu-id="60888-235">Registre la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-235">Post the sales invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="60888-236">A partir de la publicación, el gobierno no ha actualizado el esquema para habilitar que **cTipoRelacion** que se establezca en **07**.</span><span class="sxs-lookup"><span data-stu-id="60888-236">As of publication, the government hasn't updated the schema to enable **cTipoRelacion** to be set to **07**.</span></span> <span data-ttu-id="60888-237">Si recibe un mensaje de error durante la validación de esquemas, puede seleccionar manualmente **01: Nota de abono** para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="60888-237">If you receive an error message during schema validation, you can manually select **01: Credit note** to solve the issue.</span></span>

## <a name="step-3-issue-a-cfdi-advance-payment-reverse"></a><span data-ttu-id="60888-238">Paso 3: Emitir una inversión de anticipo de CFDI</span><span class="sxs-lookup"><span data-stu-id="60888-238">Step 3: Issue a CFDI advance payment reverse</span></span>

<span data-ttu-id="60888-239">Una vez que la empresa emite una factura CFDI por el importe total de la operación, debe enviar una inversión de anticipo de CFDI (Egreso) para el anticipo que se liquidó.</span><span class="sxs-lookup"><span data-stu-id="60888-239">After the company issues a CFDI invoice for the total amount of the operation, it must submit a CFDI advance payment reverse (Egreso) for the advance payment that was settled.</span></span> <span data-ttu-id="60888-240">Esta inversión de anticipo de CFDI se genera automáticamente cuando recibe la aprobación de la factura CFDI que generó en el [Paso 2: Emitir una factura CFDI junto con los detalles del anticipo que se aplicó](#step-2-issue-a-cfdi-invoice-together-with-details-of-the-advance-payment-that-was-applied).</span><span class="sxs-lookup"><span data-stu-id="60888-240">This CFDI advance payment reverse is automatically generated when you receive approval for the CFDI invoice that you generated in [Step 2: Issue a CFDI invoice together with details of the advance payment that was applied](#step-2-issue-a-cfdi-invoice-together-with-details-of-the-advance-payment-that-was-applied).</span></span>

<span data-ttu-id="60888-241">En función de la solicitud de un cliente, puede usar la consulta de la factura electrónica CFDI para ver, enviar por correo electrónico, exportar o imprimir un complemento de pago de CFDI que se generó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="60888-241">Based on a customer's request, you can use the CFDI electronic invoice inquiry to view, email, export, or print a CFDI payment complement that was previously generated.</span></span> <span data-ttu-id="60888-242">Selecione **Clientes** &gt; **Consultas e informes** &gt; **CFDI (facturas electrónicas)** y, a continuación, seleccione la pestaña **Pago**. La factura electrónica CFDI impresa incluye un código de barras bidimensional de acuerdo con el formato para códigos QR que se describe en la norma 18004 ISO/IEC.</span><span class="sxs-lookup"><span data-stu-id="60888-242">Select **Accounts receivable** &gt; **Inquiries and reports** &gt; **CFDI (electronic invoices)**, and then select the **Payment** tab. The printed CFDI electronic invoice includes a two-dimensional barcode in accordance with the format for QR codes that is described in the ISO/IEC 18004 standard.</span></span>

<span data-ttu-id="60888-243">Los anticipos de CFDI se identifican mediante un tipo de documento de **Anticipo**.</span><span class="sxs-lookup"><span data-stu-id="60888-243">CFDI advance payments are identified by a document type of **Prepayment**.</span></span>

## <a name="confirmation-number"></a><span data-ttu-id="60888-244">Número de confirmación</span><span class="sxs-lookup"><span data-stu-id="60888-244">Confirmation number</span></span>

<span data-ttu-id="60888-245">Se requiere el número de confirmación en una factura CFDI cuando el importe total de la factura o la variación de tipo de cambio se encuentre fuera de los límites que ha establecido el gobierno.</span><span class="sxs-lookup"><span data-stu-id="60888-245">The confirmation number is required on a CFDI invoice when the total amount of the invoice or the exchange rate variation is outside the limits that the government has established.</span></span> <span data-ttu-id="60888-246">En esta situación, puede especificar la confirmación necesaria de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="60888-246">In this scenario, you can specify the required confirmation in two ways:</span></span>

- <span data-ttu-id="60888-247">Si la empresa sabe que se han superado los límites, puede incluir el código de confirmación en el encabezado de transacción de la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="60888-247">If the company knows that the limits have been exceeded, you can include the confirmation code on the sales invoice transaction header.</span></span>
- <span data-ttu-id="60888-248">Si recibe un rechazo de PAC porque se han superado los límites, puede establecer el código de confirmación para el proceso de aprobación en **Consulta de factura electrónica CFDI** &gt; **Funciones** &gt; **Establecer código de autorización y Volver a enviar**.</span><span class="sxs-lookup"><span data-stu-id="60888-248">If you receive a rejection from PAC because the limits have been exceeded, you can set the confirmation code for the approval process at **CFDI electronic invoice inquire** &gt; **Functions** &gt; **Set authorization code and Resend again**.</span></span>

