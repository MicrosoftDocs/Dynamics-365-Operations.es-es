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
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0471785991a307de11147e9773d9abe1e02941d6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436517"
---
# <a name="country-of-origin"></a><span data-ttu-id="cfc19-105">País de origen</span><span class="sxs-lookup"><span data-stu-id="cfc19-105">Country of origin</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="cfc19-106">Muchas organizaciones emiten certificados a sus proveedores para garantizar que los productos cumplan con estándares de certificación específicos.</span><span class="sxs-lookup"><span data-stu-id="cfc19-106">Many organizations issue certificates to their vendors to ensure that products meet specific certification standards.</span></span> <span data-ttu-id="cfc19-107">Estos certificados dependen a menudo del país de origen.</span><span class="sxs-lookup"><span data-stu-id="cfc19-107">These certificates often depend on the country of origin.</span></span> <span data-ttu-id="cfc19-108">La característica de país de origen le permite vincular un producto a su país de origen y realizar un seguimiento de sus certificaciones de producto.</span><span class="sxs-lookup"><span data-stu-id="cfc19-108">The country of origin feature lets you link a product to its country of origin and keep track of its product certifications.</span></span>

## <a name="turn-on-the-country-of-origin-feature"></a><span data-ttu-id="cfc19-109">Activar la característica de país de origen</span><span class="sxs-lookup"><span data-stu-id="cfc19-109">Turn on the country of origin feature</span></span>

<span data-ttu-id="cfc19-110">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="cfc19-110">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="cfc19-111">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="cfc19-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="cfc19-112">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="cfc19-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="cfc19-113">**Módulo:** *Gestión de información de productos*</span><span class="sxs-lookup"><span data-stu-id="cfc19-113">**Module:** *Product information management*</span></span>
- <span data-ttu-id="cfc19-114">**Nombre de la característica**: *Característica de administración del país de origen*</span><span class="sxs-lookup"><span data-stu-id="cfc19-114">**Feature name:** *Country of origin management feature*</span></span>

## <a name="configure-source-and-destination-countries"></a><span data-ttu-id="cfc19-115">Configurar países de origen y destino</span><span class="sxs-lookup"><span data-stu-id="cfc19-115">Configure source and destination countries</span></span>

<span data-ttu-id="cfc19-116">Antes de emitir un certificado para un producto, debe vincular el producto a su país de destino y su país de origen.</span><span class="sxs-lookup"><span data-stu-id="cfc19-116">Before you issue a certificate for a product, you must link the product to its destination country and its country of origin.</span></span>

1. <span data-ttu-id="cfc19-117">Vaya a **Gestión de la información de productos \> Configuración \> Conformidad de producto \> País de origen \> Reglas del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-117">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin rules**.</span></span>
2. <span data-ttu-id="cfc19-118">Seleccione una configuración de país existente que quiera editar o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de país.</span><span class="sxs-lookup"><span data-stu-id="cfc19-118">Select an existing country setup to edit, or select **New** on the Action Pane to create a new country setup.</span></span>
3. <span data-ttu-id="cfc19-119">Establezca los siguientes valores para el país seleccionado o uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="cfc19-119">Set the following values for the selected or new country.</span></span>

    | <span data-ttu-id="cfc19-120">Campo</span><span class="sxs-lookup"><span data-stu-id="cfc19-120">Field</span></span> | <span data-ttu-id="cfc19-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfc19-121">Description</span></span> |
    |---|---|
    | <span data-ttu-id="cfc19-122">código de artículo</span><span class="sxs-lookup"><span data-stu-id="cfc19-122">Item number</span></span> | <span data-ttu-id="cfc19-123">Seleccione el número de artículo del producto.</span><span class="sxs-lookup"><span data-stu-id="cfc19-123">Select the item number of the product.</span></span> |
    | <span data-ttu-id="cfc19-124">País de destino</span><span class="sxs-lookup"><span data-stu-id="cfc19-124">Destination country</span></span> | <span data-ttu-id="cfc19-125">Seleccione el país al que va a enviar el producto.</span><span class="sxs-lookup"><span data-stu-id="cfc19-125">Select the country that you're sending the product to.</span></span> |
    | <span data-ttu-id="cfc19-126">País de origen</span><span class="sxs-lookup"><span data-stu-id="cfc19-126">Origin country</span></span> | <span data-ttu-id="cfc19-127">Seleccione el país desde el que va a enviar el producto.</span><span class="sxs-lookup"><span data-stu-id="cfc19-127">Select the country that you're shipping the product from.</span></span> |

<span data-ttu-id="cfc19-128">El propósito de esta configuración es ayudarle a generar un informe de lista de materiales (L. MAT) en el que puede incluir el país de origen de cada pieza para la que se especifican los países de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="cfc19-128">The purpose of this setup is to help you generate a bill of materials (BOM) report where you can include the country of origin for each part that source and destination countries are specified for.</span></span> <span data-ttu-id="cfc19-129">Este informe le ayudará a obtener una vista integral de dónde provienen sus piezas y hacia dónde van.</span><span class="sxs-lookup"><span data-stu-id="cfc19-129">This report will help you get a holistic picture of where your parts come from and where they are going.</span></span>

## <a name="keep-track-of-vendor-certificates"></a><span data-ttu-id="cfc19-130">Mantener un seguimiento de los certificados de proveedor</span><span class="sxs-lookup"><span data-stu-id="cfc19-130">Keep track of vendor certificates</span></span>

<span data-ttu-id="cfc19-131">Puede usar la página **Certificados de proveedores del país de origen** para realizar un seguimiento de los certificados que emite a los proveedores.</span><span class="sxs-lookup"><span data-stu-id="cfc19-131">You can use the **Country of origin vendor certificates** page to keep track of certificates that you issue to vendors.</span></span>

<span data-ttu-id="cfc19-132">Debe decidir qué documentos de certificado está emitiendo y cómo informará de ellos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="cfc19-132">You must decide which certificate documents you're issuing and how you will report them to customers.</span></span> <span data-ttu-id="cfc19-133">Esta característica le ayuda a realizar un seguimiento de sus certificados.</span><span class="sxs-lookup"><span data-stu-id="cfc19-133">This feature helps you keep track of your certificates.</span></span> <span data-ttu-id="cfc19-134">También le permite elegir si los números de certificado pertinentes aparecen en las facturas, albaranes o confirmaciones de pedidos.</span><span class="sxs-lookup"><span data-stu-id="cfc19-134">It also lets you choose whether the relevant certificate numbers appear on invoices, packing slips, and/or order confirmations.</span></span>

<span data-ttu-id="cfc19-135">Siga estos pasos para configurar su información del certificado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-135">To set up your certificate information, follow these steps.</span></span>

1. <span data-ttu-id="cfc19-136">Vaya a **Gestión de la información del producto \> Configuración \> Conformidad del producto \> País de origen \> Certificados de proveedores del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-136">Go to **Product information management \> Setup \> Product compliance \> Country of origin \> Country of origin vendor certificates**.</span></span>
2. <span data-ttu-id="cfc19-137">Seleccione una configuración de certificado existente para editarla o seleccione **Nuevo** en el Panel de acciones para crear una nueva configuración de certificado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-137">Select an existing certificate setup to edit, or select **New** on the Action Pane to create a new certificate setup.</span></span>
3. <span data-ttu-id="cfc19-138">Establezca la siguiente configuración para el certificado seleccionado o uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="cfc19-138">Set the following settings for the selected or new certificate.</span></span>

    | <span data-ttu-id="cfc19-139">Campo</span><span class="sxs-lookup"><span data-stu-id="cfc19-139">Field</span></span> | <span data-ttu-id="cfc19-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfc19-140">Description</span></span> |
    |---|---|
    | <span data-ttu-id="cfc19-141">Cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="cfc19-141">Vendor account</span></span> | <span data-ttu-id="cfc19-142">Seleccione el proveedor al que emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-142">Select the vendor that you issued the certificate to.</span></span> |
    | <span data-ttu-id="cfc19-143">código de artículo</span><span class="sxs-lookup"><span data-stu-id="cfc19-143">Item number</span></span> | <span data-ttu-id="cfc19-144">Seleccione artículo para el cual se emitió el certificado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-144">Select the item that you issued the certificate for.</span></span> |
    | <span data-ttu-id="cfc19-145">País/región</span><span class="sxs-lookup"><span data-stu-id="cfc19-145">Country/region</span></span> | <span data-ttu-id="cfc19-146">El país o región de destino donde se debe usar este certificado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-146">The destination country or region where you must use this certificate.</span></span> |
    | <span data-ttu-id="cfc19-147">Número de certificado</span><span class="sxs-lookup"><span data-stu-id="cfc19-147">Certificate number</span></span> | <span data-ttu-id="cfc19-148">Introduzca el número de identificación del certificado que emitió.</span><span class="sxs-lookup"><span data-stu-id="cfc19-148">Enter the identification number of the certificate that you issued.</span></span> |
    | <span data-ttu-id="cfc19-149">Vigencia</span><span class="sxs-lookup"><span data-stu-id="cfc19-149">Effective</span></span> | <span data-ttu-id="cfc19-150">Seleccione la primera fecha en la que el certificado actual es válido.</span><span class="sxs-lookup"><span data-stu-id="cfc19-150">Select the first date when the current certificate is valid.</span></span>|
    | <span data-ttu-id="cfc19-151">Caducidad</span><span class="sxs-lookup"><span data-stu-id="cfc19-151">Expiration</span></span> | <span data-ttu-id="cfc19-152">Seleccione la última fecha en la que el certificado actual es válido.</span><span class="sxs-lookup"><span data-stu-id="cfc19-152">Select the last date when the current certificate is valid.</span></span> |
    | <span data-ttu-id="cfc19-153">Imprimir en factura</span><span class="sxs-lookup"><span data-stu-id="cfc19-153">Print on invoice</span></span> | <span data-ttu-id="cfc19-154">Seleccione esta casilla para imprimir el número de certificado en las facturas que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-154">Select this check box to print the certificate number on invoices that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="cfc19-155">Imprimir en albarán</span><span class="sxs-lookup"><span data-stu-id="cfc19-155">Print on packing slip</span></span> | <span data-ttu-id="cfc19-156">Seleccione esta casilla para imprimir el número de certificado en los albaranes que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-156">Select this check box to print the certificate number on packing slips that are addressed to the specified country during the specified date range.</span></span> |
    | <span data-ttu-id="cfc19-157">Imprimir en pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="cfc19-157">Print on sales order</span></span> | <span data-ttu-id="cfc19-158">Seleccione esta casilla para imprimir el número de certificado en los pedidos de ventas que se dirigen al país especificado durante el intervalo de fechas indicado.</span><span class="sxs-lookup"><span data-stu-id="cfc19-158">Select this check box to print the certificate number on sales orders that are addressed to the specified country during the specified date range.</span></span> |

## <a name="include-the-country-of-origin-on-bom-reports"></a><span data-ttu-id="cfc19-159">Incluir el país de origen en los informes de listas de materiales</span><span class="sxs-lookup"><span data-stu-id="cfc19-159">Include the country of origin on BOM reports</span></span>

<span data-ttu-id="cfc19-160">Cuando genera un informe de L. MAT, puede incluir el país de origen para cada una de las piezas para las que especificó países de origen y destino en la página **Reglas del país de origen**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-160">When you generate a BOM report, you can include the country of origin for each part that you specified source and destination countries for on the **Country of origin rules** page.</span></span>

1. <span data-ttu-id="cfc19-161">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-161">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="cfc19-162">Seleccione o cree un producto para abrir su página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-162">Select or create a product to open its **Released product details** page.</span></span>
1. <span data-ttu-id="cfc19-163">En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **L. MAT.**, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-163">On the Action Pane, on the **Engineer** tab, in the **BOM** group, select **Designer**.</span></span>
1. <span data-ttu-id="cfc19-164">En la página que aparece, en el panel de acciones, seleccione **L. MAT \> Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-164">On the page that appears, on the Action Pane, select **BOM \> Print**.</span></span>
1. <span data-ttu-id="cfc19-165">En el cuadro de diálogo **Líneas de lista de materiales**, establezca el campo **País de destino** al país de destino que desea ver en su informe.</span><span class="sxs-lookup"><span data-stu-id="cfc19-165">In **Bill of materials lines** dialog box, set the **Destination country** field to the destination country that you want to view on your report.</span></span>
1. <span data-ttu-id="cfc19-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cfc19-166">Select **OK**.</span></span>

<span data-ttu-id="cfc19-167">Se genera y muestra un informe con información sobre el país de origen de cada pieza.</span><span class="sxs-lookup"><span data-stu-id="cfc19-167">A report that shows information about the country of origin of each part is generated and shown.</span></span> <span data-ttu-id="cfc19-168">A continuación se muestra un ejemplo del informe.</span><span class="sxs-lookup"><span data-stu-id="cfc19-168">Here is an example of the report.</span></span>

<span data-ttu-id="cfc19-169">![Informe del país de origen](media/country-of-origin-report.png "Informe del país de origen")</span><span class="sxs-lookup"><span data-stu-id="cfc19-169">![Country of origin report](media/country-of-origin-report.png "Country of origin report")</span></span>
