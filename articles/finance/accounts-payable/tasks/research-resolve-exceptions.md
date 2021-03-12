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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 727676d060b77633d4ff4f31dabbd7825ca19aca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971787"
---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="7b4a8-103">Investigar y resolver excepciones</span><span class="sxs-lookup"><span data-stu-id="7b4a8-103">Research or resolve exceptions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b4a8-104">Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="7b4a8-105">También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="7b4a8-106">Las directivas de facturas de proveedor no se aplican a las facturas creadas en el registro de facturas o el diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="7b4a8-107">La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="7b4a8-108">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="7b4a8-109">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="7b4a8-110">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="7b4a8-111">Preparación de la creación de directivas de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="7b4a8-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="7b4a8-112">Vaya a Proveedores > Configuración > Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="7b4a8-113">Haga clic en la ficha Validación de factura.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="7b4a8-114">Active o desactive la casilla Actualizar estado de encabezado de factura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="7b4a8-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7b4a8-115">Click OK.</span></span>
5. <span data-ttu-id="7b4a8-116">En el campo Registrar factura con discrepancias, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="7b4a8-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-117">Close the page.</span></span>
7. <span data-ttu-id="7b4a8-118">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="7b4a8-119">Haga clic en parámetros.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-119">Click Parameters.</span></span>
9. <span data-ttu-id="7b4a8-120">Haga clic en el botón Agregar.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-120">Click btnAdd.</span></span>
10. <span data-ttu-id="7b4a8-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="7b4a8-122">Crear tipos de regla de directivas para facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="7b4a8-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="7b4a8-123">Vaya a Proveedores > Configuración de directivas > Regla de directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="7b4a8-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-124">Click New.</span></span>
3. <span data-ttu-id="7b4a8-125">En el campo Nombre de regla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="7b4a8-126">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7b4a8-127">En el campo Nombre de consulta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7b4a8-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7b4a8-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7b4a8-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-130">Click Save.</span></span>
9. <span data-ttu-id="7b4a8-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="7b4a8-132">Definir una directiva de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="7b4a8-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="7b4a8-133">Vaya a Proveedores > Configuración de directivas > Directivas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="7b4a8-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-134">Click New.</span></span>
3. <span data-ttu-id="7b4a8-135">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7b4a8-136">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7b4a8-137">Expanda o contraiga la sección Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="7b4a8-138">En el árbol, seleccione "Contoso Entertainment System USA".</span><span class="sxs-lookup"><span data-stu-id="7b4a8-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="7b4a8-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-139">Click Add.</span></span>
8. <span data-ttu-id="7b4a8-140">Expanda o contraiga la sección Reglas de directivas.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="7b4a8-141">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="7b4a8-142">En el campo Descripción de regla de directivas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="7b4a8-143">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-143">Click Filter.</span></span>
12. <span data-ttu-id="7b4a8-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-144">Click Add.</span></span>
13. <span data-ttu-id="7b4a8-145">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="7b4a8-146">En el campo Tabla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="7b4a8-147">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7b4a8-148">En el campo Tabla derivada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="7b4a8-149">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="7b4a8-150">En el campo Campo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="7b4a8-151">En el campo Campo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="7b4a8-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-152">Close the page.</span></span>
21. <span data-ttu-id="7b4a8-153">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="7b4a8-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7b4a8-154">Click OK.</span></span>
23. <span data-ttu-id="7b4a8-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7b4a8-155">Click OK.</span></span>
24. <span data-ttu-id="7b4a8-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-156">Close the page.</span></span>
25. <span data-ttu-id="7b4a8-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b4a8-157">Close the page.</span></span>

