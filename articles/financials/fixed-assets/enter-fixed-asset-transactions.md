---
title: Opciones de transacciones de activos fijos
description: "Este artículo describe los diferentes métodos disponibles para crear transacciones de activos fijos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2a7fa7a28437e29f390efdf566e946c6a1082370
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="d7e88-103">Opciones de transacciones de activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-103">Fixed asset transaction options</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="d7e88-104">Este artículo describe los diferentes métodos disponibles para crear transacciones de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="d7e88-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="d7e88-105">Puede configurar los activos fijos de la integración con los proveedores, clientes, adquisición y abastecimiento y contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="d7e88-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="d7e88-106">También puede transferir los artículos en gestión de inventarios a los activos fijos si desea usar dichos artículos internamente.</span><span class="sxs-lookup"><span data-stu-id="d7e88-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="d7e88-107">Proveedores</span><span class="sxs-lookup"><span data-stu-id="d7e88-107">Accounts payable</span></span>
<span data-ttu-id="d7e88-108">Puede especificar transacciones de activos fijos en la página Asiento del diario.</span><span class="sxs-lookup"><span data-stu-id="d7e88-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="d7e88-109">Esta página se puede abrir desde la página Diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="d7e88-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="d7e88-110">También puede abrir la página Asiento del diario en la página Diario de aprobación de facturas.</span><span class="sxs-lookup"><span data-stu-id="d7e88-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="d7e88-111">En el campo Cuenta de contrapartida, seleccione Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="d7e88-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="d7e88-112">A continuación, en el campo Cuenta de contrapartida, seleccione un número de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="d7e88-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="d7e88-113">En la ficha de Activos fijos, especifique valores en los campos Tipo de transacción y Libro.</span><span class="sxs-lookup"><span data-stu-id="d7e88-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="d7e88-114">Clientes</span><span class="sxs-lookup"><span data-stu-id="d7e88-114">Accounts receivable</span></span>
<span data-ttu-id="d7e88-115">Puede especificar transacciones de activos fijos en la página Factura de servicios.</span><span class="sxs-lookup"><span data-stu-id="d7e88-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="d7e88-116">En la página Factura de servicios, en la cuadrícula Líneas de factura, seleccione un artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="d7e88-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="d7e88-117">Haga clic en la ficha desplegable Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="d7e88-117">Click the Line details FastTab.</span></span> <span data-ttu-id="d7e88-118">Especifique el número de activo fijo y el libro para la transacción de cancelación.</span><span class="sxs-lookup"><span data-stu-id="d7e88-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="d7e88-119">Para facturas de servicio, el tipo de transacción de activos fijos es siempre Venta.</span><span class="sxs-lookup"><span data-stu-id="d7e88-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="d7e88-120">Adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="d7e88-120">Procurement and sourcing</span></span>
<span data-ttu-id="d7e88-121">Puede especificar transacciones de activos fijos en la página Pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d7e88-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="d7e88-122">Especifique información adicional necesaria para crear un pedido de compra y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="d7e88-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="d7e88-123">En la página Pedido de compra, haga clic en la ficha desplegable Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="d7e88-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="d7e88-124">A continuación, en la pestaña Activos fijos, especifique información sobre el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="d7e88-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="d7e88-125">Para registrar una transacción de adquisición para un activo fijo existente, especifique el número de activo fijo, el libro y el tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="d7e88-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="d7e88-126">El activo fijo no se puede registrar si falta alguno de estos datos.</span><span class="sxs-lookup"><span data-stu-id="d7e88-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="d7e88-127">Para registrar una transacción de adquisición para un nuevo activo fijo, seleccione la opción Nuevo activo fijo y, a continuación, seleccione el grupo de activos fijos al que se debe asignar el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="d7e88-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="d7e88-128">No obstante, ninguno de los campos de activo fijo estarán disponibles para una línea si el artículo se encuentra en un grupo de modelos de inventario que usa un modelo de inventario de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="d7e88-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="d7e88-129">Además, las opciones que se definen en la página de parámetros Activos fijos determinan si se pueden registrar transacciones de adquisición de los módulos de compra.</span><span class="sxs-lookup"><span data-stu-id="d7e88-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="d7e88-130">Cuando se usa un pedido de compra o el Inventario en diario de activos fijos para adquirir activos fijos, el valor del inventario se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="d7e88-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="d7e88-131">Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="d7e88-131">General ledger</span></span>
<span data-ttu-id="d7e88-132">Cualquier tipo de transacción de activos fijos se puede registrar en la página Diario general.</span><span class="sxs-lookup"><span data-stu-id="d7e88-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="d7e88-133">También puede usar diarios de activos fijos para registrar transacciones de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="d7e88-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="d7e88-134">Opciones para especificar los tipos de transacción de activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="d7e88-135">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="d7e88-135">Transaction type</span></span>                    | <span data-ttu-id="d7e88-136">Módulo</span><span class="sxs-lookup"><span data-stu-id="d7e88-136">Module</span></span>                   | <span data-ttu-id="d7e88-137">Opciones</span><span class="sxs-lookup"><span data-stu-id="d7e88-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="d7e88-138">Adquisición, ajuste de adquisición</span><span class="sxs-lookup"><span data-stu-id="d7e88-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="d7e88-139">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-139">Fixed assets</span></span>             | <span data-ttu-id="d7e88-140">Activos fijos, Inventario a activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="d7e88-141">Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="d7e88-141">General ledger</span></span>           | <span data-ttu-id="d7e88-142">Diario general</span><span class="sxs-lookup"><span data-stu-id="d7e88-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="d7e88-143">Proveedores</span><span class="sxs-lookup"><span data-stu-id="d7e88-143">Accounts payable</span></span>         | <span data-ttu-id="d7e88-144">Diario de facturas, Diario de aprobación de facturas</span><span class="sxs-lookup"><span data-stu-id="d7e88-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="d7e88-145">Adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="d7e88-145">Procurement and sourcing</span></span> | <span data-ttu-id="d7e88-146">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="d7e88-146">Purchase order</span></span>                            |
| <span data-ttu-id="d7e88-147">Depreciación</span><span class="sxs-lookup"><span data-stu-id="d7e88-147">Depreciation</span></span>                        | <span data-ttu-id="d7e88-148">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-148">Fixed assets</span></span>             | <span data-ttu-id="d7e88-149">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="d7e88-150">Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="d7e88-150">General ledger</span></span>           | <span data-ttu-id="d7e88-151">Diario general</span><span class="sxs-lookup"><span data-stu-id="d7e88-151">General journal</span></span>                           |
| <span data-ttu-id="d7e88-152">Cancelación</span><span class="sxs-lookup"><span data-stu-id="d7e88-152">Disposal</span></span>                            | <span data-ttu-id="d7e88-153">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-153">Fixed assets</span></span>             | <span data-ttu-id="d7e88-154">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="d7e88-154">Fixed assets</span></span>                              |
| <span data-ttu-id="d7e88-155">** **</span><span class="sxs-lookup"><span data-stu-id="d7e88-155">** **</span></span>                               | <span data-ttu-id="d7e88-156">Contabilidad general</span><span class="sxs-lookup"><span data-stu-id="d7e88-156">General ledger</span></span>           | <span data-ttu-id="d7e88-157">Diario general</span><span class="sxs-lookup"><span data-stu-id="d7e88-157">General journal</span></span>                           |
| <span data-ttu-id="d7e88-158">** **</span><span class="sxs-lookup"><span data-stu-id="d7e88-158">** **</span></span>                               | <span data-ttu-id="d7e88-159">Clientes</span><span class="sxs-lookup"><span data-stu-id="d7e88-159">Accounts receivable</span></span>      | <span data-ttu-id="d7e88-160">Factura de servicios</span><span class="sxs-lookup"><span data-stu-id="d7e88-160">Free text invoice</span></span>                         |



<span data-ttu-id="d7e88-161">Para obtener más información, consulte [Integración de activos fijos](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="d7e88-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




