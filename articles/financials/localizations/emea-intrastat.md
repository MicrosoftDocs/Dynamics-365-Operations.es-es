---
title: intrastat
description: "Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE). Proporciona una visión general del proceso de informes y describe la configuración y los requisitos previos necesarios."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7c713f3a1cb5aa4758a72a7cc42c73c57b602219
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="intrastat"></a><span data-ttu-id="42327-104">intrastat</span><span class="sxs-lookup"><span data-stu-id="42327-104">Intrastat</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="42327-105">Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="42327-105">This article provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="42327-106">Proporciona una visión general del proceso de informes y describe la configuración y los requisitos previos necesarios.</span><span class="sxs-lookup"><span data-stu-id="42327-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="42327-107">Intrastat es el sistema de recopilación de información y generación de estadísticas sobre comercio de bienes entre países y regiones de la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="42327-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="42327-108">Siempre que un producto cruce la frontera de otro país o región de la UE. hace falta presentar un informe Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="42327-109">En varios países y regiones, los informes Intrastat también son obligatorios para los servicios.</span><span class="sxs-lookup"><span data-stu-id="42327-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="42327-110">Los informes Intrastat pueden incluir elementos necesarios y opcionales.</span><span class="sxs-lookup"><span data-stu-id="42327-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="42327-111">Los elementos siguientes son obligatorios: el número de IVA de la parte responsable de proporcionar información, el período de referencia, el flujo (recepción o distribución), el código de mercancía de ocho dígitos, el estado miembro socio (estado miembro de envío en recepción y el estado miembro de destino en distribución), el valor de las mercancías, la cantidad de las mercancías (masa neta y unidad suplementaria) y la naturaleza de la transacción.</span><span class="sxs-lookup"><span data-stu-id="42327-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="42327-112">Los países y regiones también pueden recopilar elementos opcionales bajo distintas condiciones.</span><span class="sxs-lookup"><span data-stu-id="42327-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="42327-113">Algunos elementos opcionales son el país o la región de origen, las condiciones de entrega, el modo de transporte, un código de mercancía más detallado que el CN8, la región de origen en distribución y la región de destino en llegadas, el procedimiento estadístico, el valor estadístico, una descripción de las mercancías y el puerto o el aeropuerto de carga y descarga.</span><span class="sxs-lookup"><span data-stu-id="42327-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="42327-114">Visión general del proceso de informes Intrastat</span><span class="sxs-lookup"><span data-stu-id="42327-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="42327-115">En las secciones siguientes se describe el flujo de información general en los informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="42327-116">1. Especificación de transacción transfronteriza a otro país o región de la UE</span><span class="sxs-lookup"><span data-stu-id="42327-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="42327-117">Una factura de cliente, una factura de texto libre, una factura de compra, una factura de proyecto, un albarán del cliente, una recepción de producto del proveedor o un pedido de transferencia se transfiere al diario de Intrastat si el tipo de país o región de destino (en distribuciones) o de envío (en llegadas) es **UE**.</span><span class="sxs-lookup"><span data-stu-id="42327-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="42327-118">Esta función se ha ampliado para Microsoft Dynamics 365 for Operations (1611) y permite especificar una dirección de embarque para una transacción de comercio intracomunitario.</span><span class="sxs-lookup"><span data-stu-id="42327-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="42327-119">Si una dirección de embarque difiere de una dirección empresarial del proveedor (o la dirección empresarial del cliente para el pedido de devolución), los informes Intrastat operarán con esta información.</span><span class="sxs-lookup"><span data-stu-id="42327-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="42327-120">Al crear un pedido de ventas, una factura de servicios, un pedido de compra, una factura de proveedor, una factura de proyecto o un pedido de transferencia, algunos campos relacionados con comercio exterior tienen valores predeterminados en el encabezado del documento o en la línea.</span><span class="sxs-lookup"><span data-stu-id="42327-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="42327-121">El código de transacción predeterminado se toma del campo correspondiente en la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-122">El código de mercancía predeterminado, el país o la región de origen y el estado o la provincia se toman del artículo.</span><span class="sxs-lookup"><span data-stu-id="42327-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="42327-123">Puede cambiar los valores predeterminados y también puede completar otra información de comercio exterior: las estadísticas procedimiento, método de transporte y puerto.</span><span class="sxs-lookup"><span data-stu-id="42327-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="42327-124">2. Utilice el diario de Intrastat para generar información sobre el comercio entre los países y regiones de la UE.</span><span class="sxs-lookup"><span data-stu-id="42327-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="42327-125">Para fines estadísticos, se genera información sobre el comercio entre países y regiones de la UE cada mes.</span><span class="sxs-lookup"><span data-stu-id="42327-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="42327-126">Puede transferir transacciones desde una factura de texto libre, una factura de cliente, un albarán de cliente, una factura de proveedor, un albarán de proveedor, una factura de proyecto o un pedido de transferencia, según los criterios de transferencia que se hayan configurado en la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-127">También puede especificar transacciones manualmente.</span><span class="sxs-lookup"><span data-stu-id="42327-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="42327-128">Puede actualizar manualmente las transacciones transferidas en el diario de Intrastat, si se requieren actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="42327-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="42327-129">En determinadas condiciones configuradas en la página **Compresión de Intrastat**, puede comprimir las transacciones en el diario de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="42327-130">Algunos países y regiones le permiten aplicar un pequeño umbral de transacción.</span><span class="sxs-lookup"><span data-stu-id="42327-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="42327-131">A continuación puede informar de transacciones por debajo de dicho umbral bajo el código de mercancía especificado.</span><span class="sxs-lookup"><span data-stu-id="42327-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="42327-132">Puede actualizar el código de mercancía en las correspondientes líneas del diario de Intrastat, en el ajuste **Límite mínimo** de la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-133">También puede comprimir esas transacciones, según el ajuste **Compresión de Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="42327-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="42327-134">Puede validar la finalización de las transacciones en el diario de Intrastat, según el ajuste **Comprobar configuración** en la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-135">Se puede validar la cumplimentación de los datos en los campos correspondientes: país o región, estado o provincia, peso, código de mercancía, código de transacción, unidad adicional, puerto, origen, términos de entrega, método de transporte y número de identificación fiscal (NIF).</span><span class="sxs-lookup"><span data-stu-id="42327-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="42327-136">Las transacciones que no se hayan completado se marcarán como no válidas.</span><span class="sxs-lookup"><span data-stu-id="42327-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="42327-137">3. Utilice el diario de Intrastat para informar sobre el comercio entre los países y regiones de la UE.</span><span class="sxs-lookup"><span data-stu-id="42327-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="42327-138">Para fines estadísticos, se informa sobre el comercio entre países y regiones de la UE cada mes.</span><span class="sxs-lookup"><span data-stu-id="42327-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="42327-139">Puede imprimir el informe Intrastat, según los ajustes **Asignación de formato de informe** en la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-140">También puede generar un archivo electrónico según los ajustes **Asignación de formato de archivo** en la página **Parámetros de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="42327-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="42327-141">Para obtener más información acerca de los informes Intrastat, incluidos los requisitos previos necesarios, consulte las grabaciones de tareas de informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="42327-142">Generar una declaración de Intrastat de la UE,</span><span class="sxs-lookup"><span data-stu-id="42327-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="42327-143">Transferir transacciones a Intrastat,</span><span class="sxs-lookup"><span data-stu-id="42327-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="42327-144">Especificación de una dirección de embarque para una transacción intracomunitaria.</span><span class="sxs-lookup"><span data-stu-id="42327-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42327-145">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42327-145">Prerequisites</span></span>
<span data-ttu-id="42327-146">La tabla siguiente muestra los requisitos previos para los informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42327-147">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="42327-147">Prerequisite</span></span></th>
<th><span data-ttu-id="42327-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="42327-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="42327-149">Configuración de dirección</span><span class="sxs-lookup"><span data-stu-id="42327-149">Address setup</span></span></td>
<td><span data-ttu-id="42327-150">Configure códigos ISO (organización internacional para la estandarización) para los países y regiones.</span><span class="sxs-lookup"><span data-stu-id="42327-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-151">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="42327-151">Legal entity</span></span></td>
<td><span data-ttu-id="42327-152">Configure números de identificación fiscal (NIF) para importación y exportación, la extensión del número de sucursal de importación o exportación y el código de Intrastat asignado a la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="42327-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-153">Jerarquía de categorías de productos (jerarquía de ventas, jerarquía de compras)</span><span class="sxs-lookup"><span data-stu-id="42327-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="42327-154">Asigne los códigos de mercancías de Intrastat a los nodos de categorías en la ficha <strong>Códigos de mercancía</strong> de la página <strong>Jerarquía de categoría</strong>.</span><span class="sxs-lookup"><span data-stu-id="42327-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="42327-155">Cuando se asigna un código de mercancía a un nodo de categoría principal, dicho código se aplica a todos los nodos de categorías secundarias.</span><span class="sxs-lookup"><span data-stu-id="42327-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="42327-156">Los códigos de mercancía seleccionados estarán disponibles en la vista <strong>Seleccionado</strong> al seleccionar un código de mercancía en los detalles de los productos emitidos y en el pedido de ventas, el pedido de compra y las líneas de pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="42327-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-157">Detalles de producto emitido</span><span class="sxs-lookup"><span data-stu-id="42327-157">Released product details</span></span></td>
<td><span data-ttu-id="42327-158">Configure los siguientes datos de comercio exterior para los productos emitidos:</span><span class="sxs-lookup"><span data-stu-id="42327-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="42327-159"><strong>Código de mercancía</strong>: seleccione un código en la lista de mercancías seleccionadas recuperadas de las categorías de productos asignadas o en la lista completa de códigos de mercancías de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="42327-160"><strong>Porcentaje de gastos estadístico</strong></span><span class="sxs-lookup"><span data-stu-id="42327-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="42327-161"><strong>País/región de origen</strong>: seleccione el país o la región predeterminado donde se obtiene o se producen las mercancías.</span><span class="sxs-lookup"><span data-stu-id="42327-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="42327-162"><strong>Comunidad autónoma/provincia de origen/destino</strong>: seleccione la comunidad autónoma o la provincia de destino predeterminados para las llegadas y la comunidad autónoma o la provincia de origen para distribuciones.</span><span class="sxs-lookup"><span data-stu-id="42327-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="42327-163"><strong>Peso neto en kg</strong></span><span class="sxs-lookup"><span data-stu-id="42327-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-164">Clientes</span><span class="sxs-lookup"><span data-stu-id="42327-164">Customers</span></span></td>
<td><span data-ttu-id="42327-165">Configure la dirección de entrega del cliente en el país o la región de la UE.</span><span class="sxs-lookup"><span data-stu-id="42327-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-166">Proveedores</span><span class="sxs-lookup"><span data-stu-id="42327-166">Vendors</span></span></td>
<td><span data-ttu-id="42327-167">Configure la dirección del proveedor en el país o la región de la UE.</span><span class="sxs-lookup"><span data-stu-id="42327-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-168">Cargos varios</span><span class="sxs-lookup"><span data-stu-id="42327-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="42327-169">Configure el código de gastos varios que incluir en el importe de la factura, el importe estadístico, o ambos.</span><span class="sxs-lookup"><span data-stu-id="42327-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="42327-170">En la página <strong>Códigos de gastos</strong>, en la ficha <strong>Comercio exterior</strong>, active <strong>Valor de la factura de Intrastat</strong> para incluir el importe de gastos en el valor de la factura, y active <strong>Valor estadístico de Intrastat</strong> para incluir el importe de gastos en el valor estadístico.</span><span class="sxs-lookup"><span data-stu-id="42327-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-171">Informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="42327-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="42327-172">Realice configuraciones de informes electrónicos para exportar los datos de Intrastat en un archivo electrónico con el formato requerido por las autoridades relevantes, y ver los datos de Intrastat en un formato sencillo y legible (por ejemplo, en Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="42327-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-173">Almacenes</span><span class="sxs-lookup"><span data-stu-id="42327-173">Warehousing</span></span></td>
<td><span data-ttu-id="42327-174">Cuentas de proveedor asociadas con los códigos de almacén para rellenar el número de identificación fiscal al transferir el pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="42327-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="42327-175">Configuración</span><span class="sxs-lookup"><span data-stu-id="42327-175">Setup</span></span>
<span data-ttu-id="42327-176">Las siguientes secciones describen los ajustes necesarios para los informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="42327-177">Configuración de todas las listas relacionadas con Intrastat necesarias</span><span class="sxs-lookup"><span data-stu-id="42327-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42327-178">Lista</span><span class="sxs-lookup"><span data-stu-id="42327-178">List</span></span></th>
<th><span data-ttu-id="42327-179">Información adicional</span><span class="sxs-lookup"><span data-stu-id="42327-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="42327-180">Códigos de mercancías</span><span class="sxs-lookup"><span data-stu-id="42327-180">Commodity codes</span></span></td>
<td><span data-ttu-id="42327-181">Configure una jerarquía de categorías de tipo <strong>Código de mercancía</strong> y especifique todos los códigos de mercancía en función de la lista de nomenclatura combinada.</span><span class="sxs-lookup"><span data-stu-id="42327-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="42327-182">Para cada mercancía se configura la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="42327-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="42327-183">El nombre de la mercancía y su código.</span><span class="sxs-lookup"><span data-stu-id="42327-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="42327-184">El nombre descriptivo y/o traducido.</span><span class="sxs-lookup"><span data-stu-id="42327-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="42327-185">Configuración para informar de unidades (suplementarias) adicionales en la pestaña <strong>Comercio exterior</strong>. Puede seleccionar la unidad adicional en la lista de la unidad.</span><span class="sxs-lookup"><span data-stu-id="42327-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="42327-186">También puede especificar si el peso de las mercancías se debe notificar además de la unidad adicional seleccionada.</span><span class="sxs-lookup"><span data-stu-id="42327-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-187">Códigos de transacción</span><span class="sxs-lookup"><span data-stu-id="42327-187">Transaction codes</span></span></td>
<td><span data-ttu-id="42327-188">Configure la naturaleza de la transacción de acuerdo con los requisitos del país o la región.</span><span class="sxs-lookup"><span data-stu-id="42327-188">Set up the nature of the transaction according to your country's/region's requirements.</span></span> <span data-ttu-id="42327-189">Para cada código de transacción que haya configurado, debe configurar las reglas para calcular los importes de factura y los importes estadísticos para pedidos de transferencia y pedidos de venta o compra.</span><span class="sxs-lookup"><span data-stu-id="42327-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="42327-190">Para los pedidos de transferencia, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:</span><span class="sxs-lookup"><span data-stu-id="42327-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="42327-191"><strong>Vacío</strong>: el importe será 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="42327-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="42327-192"><strong>Importe de coste financiero</strong>: el importe será igual al coste financiero.</span><span class="sxs-lookup"><span data-stu-id="42327-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="42327-193"><strong>Coste total</strong>: el importe será igual al coste total de la transacción.</span><span class="sxs-lookup"><span data-stu-id="42327-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="42327-194"><strong>Manual</strong>: el importe será igual al importe que se especifique manualmente en la línea de pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="42327-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="42327-195">Para los pedidos de venta y de compra, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:</span><span class="sxs-lookup"><span data-stu-id="42327-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="42327-196"><strong>Vacío</strong>: el importe será 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="42327-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="42327-197"><strong>Importe de factura</strong>: el importe será igual al importe facturado para la mercancía.</span><span class="sxs-lookup"><span data-stu-id="42327-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="42327-198"><strong>Importe base</strong>: el importe será igual al importe que será facturado antes de aplicar descuentos.</span><span class="sxs-lookup"><span data-stu-id="42327-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-199">Métodos de transporte</span><span class="sxs-lookup"><span data-stu-id="42327-199">Transport methods</span></span></td>
<td><span data-ttu-id="42327-200">Configure el modo de transporte de acuerdo con los requisitos del país o la región.</span><span class="sxs-lookup"><span data-stu-id="42327-200">Set up the transport mode according to your country's/region's requirements.</span></span> <span data-ttu-id="42327-201">Para cada modo de entrega, puede configurar un método de transporte predeterminado en la ficha <strong>Comercio exterior</strong>.</span><span class="sxs-lookup"><span data-stu-id="42327-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-202">Puertos</span><span class="sxs-lookup"><span data-stu-id="42327-202">Ports</span></span></td>
<td><span data-ttu-id="42327-203">Configure el puerto o el aeropuerto de carga y descarga si esta información la recopila su país o región.</span><span class="sxs-lookup"><span data-stu-id="42327-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-204">Procedimientos de estadísticas</span><span class="sxs-lookup"><span data-stu-id="42327-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="42327-205">Configure el procedimiento estadístico si esta información la recopila su país o región.</span><span class="sxs-lookup"><span data-stu-id="42327-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="42327-206">Configuración de reglas para comprimir transacciones de Intrastat</span><span class="sxs-lookup"><span data-stu-id="42327-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="42327-207">En la página **Compresión de Intrastat**, puede seleccionar los campos que se usarán para la compresión.</span><span class="sxs-lookup"><span data-stu-id="42327-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="42327-208">Todas las transacciones que tienen la misma combinación de valores para los campos seleccionados en el diario de Intrastat se comprimirán en una única transacción al ejecutar la función Comprimir en el diario de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="42327-209">Configurar parámetros de comercio exterior</span><span class="sxs-lookup"><span data-stu-id="42327-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="42327-210">Use la página **Parámetros de comercio exterior** para configurar los parámetros en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="42327-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42327-211">Tabulación</span><span class="sxs-lookup"><span data-stu-id="42327-211">Tab</span></span></th>
<th><span data-ttu-id="42327-212">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42327-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="42327-213">General</span><span class="sxs-lookup"><span data-stu-id="42327-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="42327-214"><strong>General</strong>: especifique la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="42327-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="42327-215">El códigos de transacción predeterminados para los pedidos de ventas y de compra, las notas de abono y los pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="42327-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="42327-216">El código de transacción que se configura para las notas de abono también se usa como el código para la devolución de mercancías físicas y se usa para devoluciones físicas de desviación frente a notas de abono de corrección.</span><span class="sxs-lookup"><span data-stu-id="42327-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span></li>
<li><span data-ttu-id="42327-217">El empleado responsable de preparar los informes Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-217">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="42327-218"><strong>Límite mínimo</strong>: especifique los ajustes para actualizar las transacciones que se encuentran por debajo del umbral:</span><span class="sxs-lookup"><span data-stu-id="42327-218"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="42327-219">El importe del umbral y el peso.</span><span class="sxs-lookup"><span data-stu-id="42327-219">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="42327-220">El código de mercancía que aplicar a las transacciones bajo el umbral.</span><span class="sxs-lookup"><span data-stu-id="42327-220">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="42327-221"><strong>Transferencia</strong>: especifique los criterios para transferir transacciones al diario de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-221"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="42327-222">Puede especificar que las transacciones se transfieran solo cuando los artículos cumplan uno o todos los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="42327-222">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="42327-223">Los artículos no son artículos de servicio.</span><span class="sxs-lookup"><span data-stu-id="42327-223">The items aren't service items.</span></span></li>
<li><span data-ttu-id="42327-224">Los artículos tienen un código de mercancía.</span><span class="sxs-lookup"><span data-stu-id="42327-224">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="42327-225">Los artículos tienen un peso.</span><span class="sxs-lookup"><span data-stu-id="42327-225">The items have a weight.</span></span></li>
<li><span data-ttu-id="42327-226">Los artículos tienen unidades adicionales.</span><span class="sxs-lookup"><span data-stu-id="42327-226">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="42327-227"><strong>Comprobar configuración</strong>: especifique las reglas para validar si los datos de Intrastat se han completado.</span><span class="sxs-lookup"><span data-stu-id="42327-227"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="42327-228">Puede seleccionar qué datos se validarán.</span><span class="sxs-lookup"><span data-stu-id="42327-228">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="42327-229"><strong>Reglas de redondeo</strong>: especifique las opciones siguientes para redondear importes y pesos en los informes Intrastat:</span><span class="sxs-lookup"><span data-stu-id="42327-229"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="42327-230">La de regla de redondeo (precisión).</span><span class="sxs-lookup"><span data-stu-id="42327-230">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="42327-231">El método de redondeo: hacia arriba, hacia abajo o normal.</span><span class="sxs-lookup"><span data-stu-id="42327-231">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="42327-232">El número de decimales en importes y pesos.</span><span class="sxs-lookup"><span data-stu-id="42327-232">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="42327-233">Instrucciones para redondear pesos inferiores a 1 kilogramo (kg): hasta 1 kg, normal o sin redondeo.</span><span class="sxs-lookup"><span data-stu-id="42327-233">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="42327-234"><strong>Informes electrónicos</strong>: especifique referencias a configuraciones de informes electrónicos, de manera que pueda generar un archivo y un informe electrónico.</span><span class="sxs-lookup"><span data-stu-id="42327-234"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="42327-235"><strong>Jerarquía de códigos de mercancías</strong>: especifique la jerarquía de categorías del tipo <strong>Código de mercancía</strong> que representa el código de mercancía Intrastat CN8.</span><span class="sxs-lookup"><span data-stu-id="42327-235"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-236">Información de contacto del agente</span><span class="sxs-lookup"><span data-stu-id="42327-236">Agent contact information</span></span></td>
<td><span data-ttu-id="42327-237">Especifique el nombre del agente, la dirección, el número de identificación fiscal (NIF), el número de teléfono y el número de fax.</span><span class="sxs-lookup"><span data-stu-id="42327-237">Specify the agent's name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="42327-238">Propiedades de país / región</span><span class="sxs-lookup"><span data-stu-id="42327-238">Country/region properties</span></span></td>
<td><span data-ttu-id="42327-239">Defina el país o región de la entidad jurídica actual en <strong>Nacional</strong>.</span><span class="sxs-lookup"><span data-stu-id="42327-239">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="42327-240">Defina los países o regiones de la UE que participe en comercio de la UE con la entidad jurídica actual en <strong>UE</strong>.</span><span class="sxs-lookup"><span data-stu-id="42327-240">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="42327-241">Para cada país o región, también debe identificar el código de país o región para comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="42327-241">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="42327-242">Secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="42327-242">Number sequence</span></span></td>
<td><span data-ttu-id="42327-243">Especifique la secuencia numérica para el diario de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="42327-243">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>

 




