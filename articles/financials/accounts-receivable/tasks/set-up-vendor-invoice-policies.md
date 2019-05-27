---
title: Configurar directivas de factura de proveedor
description: Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b424eee7c91ef1085c98828c0d5e5cf674717a81
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559673"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="026be-103">Configurar directivas de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="026be-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="026be-104">Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="026be-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="026be-105">También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="026be-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="026be-106">Las directivas de facturas de proveedor no se aplican a las facturas creadas en el registro de facturas o el diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="026be-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="026be-107">La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="026be-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="026be-108">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="026be-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="026be-109">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="026be-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="026be-110">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="026be-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="026be-111">Preparación de la creación de directivas de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="026be-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="026be-112">Vaya a Proveedores > Configuración > Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="026be-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="026be-113">Haga clic en la ficha Validación de factura.</span><span class="sxs-lookup"><span data-stu-id="026be-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="026be-114">Active o desactive la casilla Actualizar estado de encabezado de factura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="026be-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="026be-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="026be-115">Click OK.</span></span>
5. <span data-ttu-id="026be-116">En el campo Registrar factura con discrepancias, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="026be-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="026be-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-117">Close the page.</span></span>
7. <span data-ttu-id="026be-118">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="026be-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="026be-119">Haga clic en parámetros.</span><span class="sxs-lookup"><span data-stu-id="026be-119">Click Parameters.</span></span>
9. <span data-ttu-id="026be-120">Haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="026be-120">Click btnAdd.</span></span>
10. <span data-ttu-id="026be-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="026be-122">Crear tipos de regla de directivas para facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="026be-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="026be-123">Vaya a Proveedores > Configuración de directivas > Regla de directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="026be-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="026be-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="026be-124">Click New.</span></span>
3. <span data-ttu-id="026be-125">En el campo Nombre de regla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="026be-126">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="026be-127">En el campo Nombre de consulta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="026be-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="026be-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="026be-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="026be-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="026be-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="026be-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="026be-130">Click Save.</span></span>
9. <span data-ttu-id="026be-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="026be-132">Definir una directiva de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="026be-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="026be-133">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="026be-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="026be-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="026be-134">Click New.</span></span>
3. <span data-ttu-id="026be-135">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="026be-136">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="026be-137">Expanda o contraiga la sección Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="026be-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="026be-138">En el árbol, seleccione "Contoso Entertainment System USA".</span><span class="sxs-lookup"><span data-stu-id="026be-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="026be-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="026be-139">Click Add.</span></span>
8. <span data-ttu-id="026be-140">Expanda o contraiga la sección Reglas de directivas.</span><span class="sxs-lookup"><span data-stu-id="026be-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="026be-141">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="026be-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="026be-142">En el campo Descripción de regla de directivas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="026be-143">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="026be-143">Click Filter.</span></span>
12. <span data-ttu-id="026be-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="026be-144">Click Add.</span></span>
13. <span data-ttu-id="026be-145">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="026be-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="026be-146">En el campo Tabla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="026be-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="026be-147">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="026be-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="026be-148">En el campo Tabla derivada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="026be-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="026be-149">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="026be-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="026be-150">En el campo Campo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="026be-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="026be-151">En el campo Campo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="026be-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-152">Close the page.</span></span>
21. <span data-ttu-id="026be-153">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="026be-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="026be-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="026be-154">Click OK.</span></span>
23. <span data-ttu-id="026be-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="026be-155">Click OK.</span></span>
24. <span data-ttu-id="026be-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-156">Close the page.</span></span>
25. <span data-ttu-id="026be-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="026be-157">Close the page.</span></span>

