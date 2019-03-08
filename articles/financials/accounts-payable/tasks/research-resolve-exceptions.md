---
title: Investigar y resolver excepciones
description: Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c6f8c8dcf7a301c7fb2d095658ac96cd4a24dff
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "365164"
---
# <a name="researchresolve-exceptions"></a><span data-ttu-id="3bffe-103">Investigar y resolver excepciones</span><span class="sxs-lookup"><span data-stu-id="3bffe-103">Research/Resolve exceptions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3bffe-104">Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="3bffe-105">También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3bffe-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="3bffe-106">Las directivas de facturas de proveedor no se aplican a las facturas creadas en el registro de facturas o el diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="3bffe-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="3bffe-107">La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="3bffe-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="3bffe-108">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="3bffe-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="3bffe-109">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3bffe-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="3bffe-110">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bffe-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="3bffe-111">Preparación de la creación de directivas de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3bffe-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="3bffe-112">Vaya a Proveedores > Configuración > Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="3bffe-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="3bffe-113">Haga clic en la ficha Validación de factura.</span><span class="sxs-lookup"><span data-stu-id="3bffe-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="3bffe-114">Active o desactive la casilla Actualizar estado de encabezado de factura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3bffe-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="3bffe-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bffe-115">Click OK.</span></span>
5. <span data-ttu-id="3bffe-116">En el campo Registrar factura con discrepancias, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3bffe-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="3bffe-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-117">Close the page.</span></span>
7. <span data-ttu-id="3bffe-118">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="3bffe-119">Haga clic en parámetros.</span><span class="sxs-lookup"><span data-stu-id="3bffe-119">Click Parameters.</span></span>
9. <span data-ttu-id="3bffe-120">Haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="3bffe-120">Click btnAdd.</span></span>
10. <span data-ttu-id="3bffe-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="3bffe-122">Crear tipos de regla de directivas para facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3bffe-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="3bffe-123">Vaya a Proveedores > Configuración de directivas > Regla de directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="3bffe-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3bffe-124">Click New.</span></span>
3. <span data-ttu-id="3bffe-125">En el campo Nombre de regla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="3bffe-126">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3bffe-127">En el campo Nombre de consulta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bffe-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="3bffe-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3bffe-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="3bffe-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bffe-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3bffe-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bffe-130">Click Save.</span></span>
9. <span data-ttu-id="3bffe-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="3bffe-132">Definir una directiva de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3bffe-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="3bffe-133">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="3bffe-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3bffe-134">Click New.</span></span>
3. <span data-ttu-id="3bffe-135">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="3bffe-136">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3bffe-137">Expanda o contraiga la sección Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="3bffe-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="3bffe-138">En el árbol, seleccione "Contoso Entertainment System USA".</span><span class="sxs-lookup"><span data-stu-id="3bffe-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="3bffe-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3bffe-139">Click Add.</span></span>
8. <span data-ttu-id="3bffe-140">Expanda o contraiga la sección Reglas de directivas.</span><span class="sxs-lookup"><span data-stu-id="3bffe-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="3bffe-141">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="3bffe-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="3bffe-142">En el campo Descripción de regla de directivas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="3bffe-143">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="3bffe-143">Click Filter.</span></span>
12. <span data-ttu-id="3bffe-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3bffe-144">Click Add.</span></span>
13. <span data-ttu-id="3bffe-145">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bffe-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="3bffe-146">En el campo Tabla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bffe-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="3bffe-147">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bffe-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="3bffe-148">En el campo Tabla derivada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bffe-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="3bffe-149">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3bffe-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="3bffe-150">En el campo Campo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bffe-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="3bffe-151">En el campo Campo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="3bffe-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-152">Close the page.</span></span>
21. <span data-ttu-id="3bffe-153">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3bffe-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="3bffe-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bffe-154">Click OK.</span></span>
23. <span data-ttu-id="3bffe-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bffe-155">Click OK.</span></span>
24. <span data-ttu-id="3bffe-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-156">Close the page.</span></span>
25. <span data-ttu-id="3bffe-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bffe-157">Close the page.</span></span>

