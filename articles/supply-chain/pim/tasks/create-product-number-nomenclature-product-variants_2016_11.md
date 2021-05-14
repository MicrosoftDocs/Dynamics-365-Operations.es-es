---
title: Crear una nomenclatura de números de producto para las variantes de producto configuradas
description: Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921020"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="156d9-103">Crear una nomenclatura de números de producto para las variantes de producto configuradas</span><span class="sxs-lookup"><span data-stu-id="156d9-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="156d9-104">Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.</span><span class="sxs-lookup"><span data-stu-id="156d9-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="156d9-105">Este procedimiento también demuestra la manera de crear una nomenclatura de la configuración para un componente del modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="156d9-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="156d9-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="156d9-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="156d9-107">La nueva nomenclatura del número de producto se asigna al producto maestro D0004.</span><span class="sxs-lookup"><span data-stu-id="156d9-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="156d9-108">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="156d9-108">This task would typically be done by a product designer.</span></span>

## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="156d9-109">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="156d9-109">Create a product number nomenclature</span></span>

1. <span data-ttu-id="156d9-110">Vaya a **Gestión de información de productos \> Configuración \> Nomenclatura de productos**.</span><span class="sxs-lookup"><span data-stu-id="156d9-110">Go to **Product information management \> Setup \> Product nomenclature**.</span></span>
1. <span data-ttu-id="156d9-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="156d9-111">Select **New**.</span></span>
1. <span data-ttu-id="156d9-112">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="156d9-113">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-113">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="156d9-114">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-114">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-115">Seleccione **Número de producto maestro**.</span><span class="sxs-lookup"><span data-stu-id="156d9-115">Select **Product master number**.</span></span>
1. <span data-ttu-id="156d9-116">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-116">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-117">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-117">Select **Text constant**.</span></span>
1. <span data-ttu-id="156d9-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-118">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-119">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-119">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="156d9-120">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-120">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-121">Seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="156d9-121">Select **Configuration**.</span></span>
1. <span data-ttu-id="156d9-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-122">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="156d9-123">Asignar la nomenclatura del número de producto a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="156d9-123">Assign the product number nomenclature to a product master</span></span>

1. <span data-ttu-id="156d9-124">Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="156d9-124">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="156d9-125">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="156d9-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="156d9-126">Por ejemplo, filtre por el campo **Número de producto** con un valor de 'D'.</span><span class="sxs-lookup"><span data-stu-id="156d9-126">For example, filter on the **Product number** field with a value of 'D'.</span></span>
1. <span data-ttu-id="156d9-127">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-127">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="156d9-128">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-128">Select **Edit**.</span></span>
1. <span data-ttu-id="156d9-129">Seleccione *Sí* en el campo **Usar nomenclatura**.</span><span class="sxs-lookup"><span data-stu-id="156d9-129">Select *Yes* in the **Use nomenclature** field.</span></span>
1. <span data-ttu-id="156d9-130">En el campo **Nomenclatura del número de variante del producto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-130">In the **Product variant number nomenclature** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-131">Close the page.</span></span>
1. <span data-ttu-id="156d9-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-132">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="156d9-133">Crear una nomenclatura para un componente de modelo de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="156d9-133">Create nomenclature for a product configuration model component</span></span>

1. <span data-ttu-id="156d9-134">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-134">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="156d9-135">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="156d9-135">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="156d9-136">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-136">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="156d9-137">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-137">Select **Edit**.</span></span>
1. <span data-ttu-id="156d9-138">Seleccione *Sí* en el campo **Usar nomenclatura de configuración**.</span><span class="sxs-lookup"><span data-stu-id="156d9-138">Select *Yes* in the **Use configuration nomenclature** field.</span></span>
1. <span data-ttu-id="156d9-139">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-139">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-140">Seleccione **Valor de atributo**.</span><span class="sxs-lookup"><span data-stu-id="156d9-140">Select **Attribute value**.</span></span>
1. <span data-ttu-id="156d9-141">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-141">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-142">En el campo **Atributo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-142">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-143">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-143">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-144">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-144">Select **Text constant**.</span></span>
1. <span data-ttu-id="156d9-145">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-145">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-146">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-146">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="156d9-147">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-147">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-148">Seleccione **Valor de atributo**.</span><span class="sxs-lookup"><span data-stu-id="156d9-148">Select **Attribute value**.</span></span>
1. <span data-ttu-id="156d9-149">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-149">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-150">En el campo **Atributo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-150">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-151">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-151">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-152">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-152">Select **Text constant**.</span></span>
1. <span data-ttu-id="156d9-153">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-153">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-154">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-154">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="156d9-155">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-155">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-156">Seleccione **Valor de atributo**.</span><span class="sxs-lookup"><span data-stu-id="156d9-156">Select **Attribute value**.</span></span>
1. <span data-ttu-id="156d9-157">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-157">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-158">En el campo **Atributo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-158">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-159">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-159">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-160">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-160">Select **Text constant**.</span></span>
1. <span data-ttu-id="156d9-161">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-161">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-162">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-162">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="156d9-163">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-163">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-164">Seleccione **Valor de atributo**.</span><span class="sxs-lookup"><span data-stu-id="156d9-164">Select **Attribute value**.</span></span>
1. <span data-ttu-id="156d9-165">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-165">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-166">En el campo **Atributo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-166">In the **Attribute** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-167">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-167">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-168">Seleccione **Constante de texto**.</span><span class="sxs-lookup"><span data-stu-id="156d9-168">Select **Text constant**.</span></span>
1. <span data-ttu-id="156d9-169">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-169">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-170">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-170">In the **Text** field, type a value.</span></span>
1. <span data-ttu-id="156d9-171">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="156d9-171">Select **Add**.</span></span>
1. <span data-ttu-id="156d9-172">Seleccione **Valor de secuencia numérica**.</span><span class="sxs-lookup"><span data-stu-id="156d9-172">Select **Number sequence value**.</span></span>
1. <span data-ttu-id="156d9-173">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="156d9-173">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="156d9-174">En el campo **Secuencia numérica**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="156d9-174">In the **Number sequence** field, enter or select a value.</span></span>
1. <span data-ttu-id="156d9-175">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-175">Close the page.</span></span>
1. <span data-ttu-id="156d9-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-176">Close the page.</span></span>
1. <span data-ttu-id="156d9-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="156d9-177">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]