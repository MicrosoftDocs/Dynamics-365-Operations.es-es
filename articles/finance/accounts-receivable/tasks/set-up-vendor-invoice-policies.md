---
title: Configurar directivas de factura de proveedor
description: En este tema se explica cómo configurar políticas de facturas de proveedor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 678ef8f0b7df00aec615af26cbcadec984331060
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220068"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="3f324-103">Configurar directivas de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="3f324-103">Set up vendor invoice policies</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f324-104">En este tema se explica cómo configurar políticas de facturas de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3f324-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="3f324-105">Las directivas de factura de proveedor se ejecutan al registrar una factura de proveedor mediante la página Factura de proveedor y al abrir la página de infracciones de directiva de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3f324-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="3f324-106">También puede configurar el flujo de trabajo de la factura de proveedor para ejecutar las directivas de factura de proveedor cada vez que envíe una factura al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f324-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="3f324-107">Las directivas de facturas de proveedor no se aplican a las facturas creadas en el registro de facturas o el diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="3f324-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="3f324-108">La validación de conciliación de facturas no usa directivas de factura de proveedor, sino que se configura en la página Parámetros de proveedores.</span><span class="sxs-lookup"><span data-stu-id="3f324-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="3f324-109">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="3f324-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="3f324-110">El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3f324-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="3f324-111">Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f324-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="3f324-112">Preparación de la creación de directivas de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3f324-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="3f324-113">Vaya a **Panel de exploración > Módulos > Proveedores > Configuración > Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="3f324-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="3f324-114">Seleccione la pestala **Validación de factura**.</span><span class="sxs-lookup"><span data-stu-id="3f324-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="3f324-115">Active o desactive la casilla **Actualizar estado de encabezado de factura automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="3f324-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="3f324-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-116">Select **OK**.</span></span>
5. <span data-ttu-id="3f324-117">En el campo **Registrar factura con discrepancias**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3f324-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="3f324-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f324-118">Close the page.</span></span>
7. <span data-ttu-id="3f324-119">Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="3f324-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="3f324-120">Seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="3f324-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="3f324-121">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-121">Select **Add**.</span></span>
10. <span data-ttu-id="3f324-122">Cierre la página para regresar a la página principal.</span><span class="sxs-lookup"><span data-stu-id="3f324-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="3f324-123">Crear tipos de regla de directivas para facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3f324-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="3f324-124">Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Tipos de reglas de directivas de facturas de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="3f324-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="3f324-125">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f324-125">Select **New**.</span></span>
3. <span data-ttu-id="3f324-126">Escriba valores en los campos **Nombre de regla** y **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="3f324-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="3f324-127">En el campo **Nombre de consulta**, seleccione el botón de la lista desplegable para abrir la búsqueda y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="3f324-127">In the **Query name** field, select the drop-down button to open the lookup, then select the desired record.</span></span>
5. <span data-ttu-id="3f324-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-128">Select **Save**.</span></span>
6. <span data-ttu-id="3f324-129">Cierre la página para regresar a la página principal.</span><span class="sxs-lookup"><span data-stu-id="3f324-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="3f324-130">Definir una directiva de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="3f324-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="3f324-131">Vaya a **Panel de navegación > Módulos > Proveedores > Configuración de directivas > Directivas de facturas de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="3f324-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="3f324-132">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3f324-132">Select **New**.</span></span>
3. <span data-ttu-id="3f324-133">Escriba valores en los campos **Nombre** y **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="3f324-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="3f324-134">Expanda o contraiga la sección **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="3f324-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="3f324-135">En el árbol, seleccione **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="3f324-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="3f324-136">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-136">Select **Add**.</span></span>
7. <span data-ttu-id="3f324-137">Expanda o contraiga la sección **Reglas de directivas**.</span><span class="sxs-lookup"><span data-stu-id="3f324-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="3f324-138">Seleccione **Crear regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="3f324-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="3f324-139">En el campo **Descripción de regla de directivas**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f324-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="3f324-140">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3f324-140">Select **Filter**.</span></span>
11. <span data-ttu-id="3f324-141">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-141">Select **Add**.</span></span> <span data-ttu-id="3f324-142">Seleccione el registro que desee.</span><span class="sxs-lookup"><span data-stu-id="3f324-142">Select the desired record.</span></span>
12. <span data-ttu-id="3f324-143">En **Tabla**, **Tabla derivada** y **Campo**, seleccione o introduzca opciones de los menús desplegables.</span><span class="sxs-lookup"><span data-stu-id="3f324-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="3f324-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f324-144">Close the page.</span></span>
14. <span data-ttu-id="3f324-145">En el campo **Criterios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f324-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="3f324-146">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-146">Select **OK**.</span></span>
16. <span data-ttu-id="3f324-147">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3f324-147">Select **OK**.</span></span>
17. <span data-ttu-id="3f324-148">Cierre las páginas para regresar a la página principal.</span><span class="sxs-lookup"><span data-stu-id="3f324-148">Close the pages to return to the home page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]