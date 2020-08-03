---
title: País de origen
description: Muchas organizaciones emiten certificados a sus proveedores para garantizar que los productos cumplan con estándares de certificación específicos. Estos certificados dependen a menudo del país de origen. Este tema proporciona información sobre la función del país de origen, lo que le permite vincular un producto a su país de origen y realizar un seguimiento de sus certificaciones de producto.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fd234c57bf9893e9b8bcfa5ada7439a642f7a288
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596274"
---
# <a name="country-of-origin"></a><span data-ttu-id="8fe17-105">País de origen</span><span class="sxs-lookup"><span data-stu-id="8fe17-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fe17-106">Muchas organizaciones emiten certificados a sus proveedores para garantizar que los productos cumplan con estándares de certificación específicos.</span><span class="sxs-lookup"><span data-stu-id="8fe17-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="8fe17-107">Estos certificados dependen a menudo del país de origen.</span><span class="sxs-lookup"><span data-stu-id="8fe17-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="8fe17-108">La característica de país de origen le permite vincular un producto a su país de origen y realizar un seguimiento de sus certificaciones de producto.</span><span class="sxs-lookup"><span data-stu-id="8fe17-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="8fe17-109">Configurar países de origen y destino</span><span class="sxs-lookup"><span data-stu-id="8fe17-109">Configure source and destination countries</span></span>

<span data-ttu-id="8fe17-110">Antes de emitir un certificado para un producto, debe vincular el producto a su país de destino y su país de origen.</span><span class="sxs-lookup"><span data-stu-id="8fe17-110">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="8fe17-111">Vaya a **Gestión de la información de productos \> Configuración \> Conformidad de producto \> País de origen \> Reglas del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-111">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="8fe17-112">Seleccione una configuración de país existente que quiera editar o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de país.</span><span class="sxs-lookup"><span data-stu-id="8fe17-112">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="8fe17-113">Establezca los siguientes valores para el país seleccionado o uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="8fe17-113">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="8fe17-114">Campo</span><span class="sxs-lookup"><span data-stu-id="8fe17-114">Field</span></span> | <span data-ttu-id="8fe17-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fe17-115">Description</span></span> |
    |---|---|
    | <span data-ttu-id="8fe17-116">código de artículo</span><span class="sxs-lookup"><span data-stu-id="8fe17-116">Item number</span></span> | <span data-ttu-id="8fe17-117">Seleccione el número de artículo del producto.</span><span class="sxs-lookup"><span data-stu-id="8fe17-117">Select the item number of the product.</span></span> |
    | <span data-ttu-id="8fe17-118">País de destino</span><span class="sxs-lookup"><span data-stu-id="8fe17-118">Destination country</span></span> | <span data-ttu-id="8fe17-119">Seleccione el país al que va a enviar el producto.</span><span class="sxs-lookup"><span data-stu-id="8fe17-119">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="8fe17-120">País de origen</span><span class="sxs-lookup"><span data-stu-id="8fe17-120">Origin country</span></span> | <span data-ttu-id="8fe17-121">Seleccione el país desde el que va a enviar el producto.</span><span class="sxs-lookup"><span data-stu-id="8fe17-121">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="8fe17-122">El propósito de esta configuración es ayudarle a generar un informe de lista de materiales (L. MAT) en el que puede incluir el país de origen de cada pieza para la que se especifican los países de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="8fe17-122">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="8fe17-123">Este informe le ayudará a obtener una vista integral de dónde provienen sus piezas y hacia dónde van.</span><span class="sxs-lookup"><span data-stu-id="8fe17-123">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="8fe17-124">Mantener un seguimiento de los certificados de proveedor</span><span class="sxs-lookup"><span data-stu-id="8fe17-124">Keep track of vendor certificates</span></span>

<span data-ttu-id="8fe17-125">Puede usar la página **Certificados de proveedores del país de origen** para realizar un seguimiento de los certificados que emite a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="8fe17-125">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="8fe17-126">Debe decidir qué documentos de certificado está emitiendo y cómo informará de ellos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="8fe17-126">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="8fe17-127">Esta característica le ayuda a realizar un seguimiento de sus certificados.</span><span class="sxs-lookup"><span data-stu-id="8fe17-127">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="8fe17-128">También le permite elegir si los números de certificado pertinentes aparecen en las facturas, albaranes o confirmaciones de pedidos.</span><span class="sxs-lookup"><span data-stu-id="8fe17-128">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="8fe17-129">Siga estos pasos para configurar su información del certificado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-129">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="8fe17-130">Vaya a **Gestión de la información del producto \> Configuración \> Conformidad del producto \> País de origen \> Certificados de proveedores del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-130">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="8fe17-131">Seleccione una configuración de certificado existente para editarla o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de certificado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-131">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="8fe17-132">Establezca la siguiente configuración para el certificado seleccionado o uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="8fe17-132">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="8fe17-133">Campo</span><span class="sxs-lookup"><span data-stu-id="8fe17-133">Field</span></span> | <span data-ttu-id="8fe17-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fe17-134">Description</span></span> |
    |---|---|
    | <span data-ttu-id="8fe17-135">Cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="8fe17-135">Vendor account</span></span> | <span data-ttu-id="8fe17-136">Seleccione el proveedor al que emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-136">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="8fe17-137">código de artículo</span><span class="sxs-lookup"><span data-stu-id="8fe17-137">Item number</span></span> | <span data-ttu-id="8fe17-138">Seleccione artículo para el cual se emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-138">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="8fe17-139">País/región</span><span class="sxs-lookup"><span data-stu-id="8fe17-139">Country/region</span></span> | <span data-ttu-id="8fe17-140">El país o región de destino donde se debe usar este certificado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-140">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="8fe17-141">Número de certificado</span><span class="sxs-lookup"><span data-stu-id="8fe17-141">Certificate number</span></span> | <span data-ttu-id="8fe17-142">Introduzca el número de identificación del certificado que emitió.</span><span class="sxs-lookup"><span data-stu-id="8fe17-142">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="8fe17-143">Vigencia</span><span class="sxs-lookup"><span data-stu-id="8fe17-143">Effective</span></span> | <span data-ttu-id="8fe17-144">Seleccione la primera fecha en la que el certificado actual es válido.</span><span class="sxs-lookup"><span data-stu-id="8fe17-144">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="8fe17-145">Caducidad</span><span class="sxs-lookup"><span data-stu-id="8fe17-145">Expiration</span></span> | <span data-ttu-id="8fe17-146">Seleccione la última fecha en la que el certificado actual es válido.</span><span class="sxs-lookup"><span data-stu-id="8fe17-146">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="8fe17-147">Imprimir en factura</span><span class="sxs-lookup"><span data-stu-id="8fe17-147">Print on invoice</span></span> | <span data-ttu-id="8fe17-148">Seleccione esta casilla para imprimir el número de certificado en las facturas que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-148">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="8fe17-149">Imprimir en albarán</span><span class="sxs-lookup"><span data-stu-id="8fe17-149">Print on packing slip</span></span> | <span data-ttu-id="8fe17-150">Seleccione esta casilla para imprimir el número de certificado en los albaranes que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-150">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="8fe17-151">Imprimir en pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="8fe17-151">Print on sales order</span></span> | <span data-ttu-id="8fe17-152">Seleccione esta casilla para imprimir el número de certificado en los pedidos de ventas que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="8fe17-152">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="8fe17-153">Incluir el país de origen en los informes de listas de materiales</span><span class="sxs-lookup"><span data-stu-id="8fe17-153">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="8fe17-154">Cuando genera un informe de L. MAT, puede incluir el país de origen para cada una de las piezas para las que especificó países de origen y destino en la página **Reglas del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-154">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="8fe17-155">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-155">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="8fe17-156">Seleccione o cree un producto para abrir su página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-156">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="8fe17-157">En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **L. MAT.**, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-157">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="8fe17-158">En la página que aparece, en el panel de acciones, seleccione **L. MAT \> Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-158">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="8fe17-159">En el cuadro de diálogo **Líneas de lista de materiales**, establezca el campo **País de destino** al país de destino que desea ver en su informe.</span><span class="sxs-lookup"><span data-stu-id="8fe17-159">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="8fe17-160">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fe17-160">Select **OK**.</span></span>

<span data-ttu-id="8fe17-161">Se genera y muestra un informe con información sobre el país de origen de cada pieza.</span><span class="sxs-lookup"><span data-stu-id="8fe17-161">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="8fe17-162">A continuación se muestra un ejemplo del informe.</span><span class="sxs-lookup"><span data-stu-id="8fe17-162">Here is an example of the report.</span></span>

<span data-ttu-id="8fe17-163">![Informe del país de origen](media/country-of-origin-report.png "Informe del país de origen")</span><span class="sxs-lookup"><span data-stu-id="8fe17-163">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
