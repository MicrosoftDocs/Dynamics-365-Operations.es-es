---
title: Referencias a facturas originales en notas de crédito
description: Este tema explica cómo configurar e imprimir los números de factura originales en notas de crédito relacionadas.
author: ilkond
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d7f32c5d3d29be8d1d2742c4017c1719cbd47a8
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897341"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="1690a-103">Referencias a facturas originales en notas de crédito</span><span class="sxs-lookup"><span data-stu-id="1690a-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1690a-104">En algunos países y regiones, existe un requisito legal de que las notas de crédito impresas incluyan referencias a las facturas originales.</span><span class="sxs-lookup"><span data-stu-id="1690a-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="1690a-105">Este tema explica cómo configurar e imprimir los números de factura originales en notas de crédito relacionadas.</span><span class="sxs-lookup"><span data-stu-id="1690a-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1690a-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1690a-106">Prerequisites</span></span>

- <span data-ttu-id="1690a-107">En espacio de trabajo **Administración de características**, active la característica **Diseño de facturación de crédito para informes de facturas de ventas y proyectos**.</span><span class="sxs-lookup"><span data-stu-id="1690a-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="1690a-108">Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1690a-108">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="1690a-109">Los formatos imprimibles de los documentos necesarios deben configurarse en la Administración de impresión.</span><span class="sxs-lookup"><span data-stu-id="1690a-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="1690a-110">La funcionalidad que se describe en este tema se aplica a los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="1690a-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="1690a-111">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="1690a-111">**Accounts receivable**</span></span>

- <span data-ttu-id="1690a-112">Nota de abono de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="1690a-112">Free text credit note</span></span>
- <span data-ttu-id="1690a-113">Nota de abono de cliente</span><span class="sxs-lookup"><span data-stu-id="1690a-113">Customer credit note</span></span>

<span data-ttu-id="1690a-114">**Gestión y contabilidad de proyectos**</span><span class="sxs-lookup"><span data-stu-id="1690a-114">**Project management and accounting**</span></span>

- <span data-ttu-id="1690a-115">Nota de abono de proyecto</span><span class="sxs-lookup"><span data-stu-id="1690a-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="1690a-116">Configurar los parámetros de clientes</span><span class="sxs-lookup"><span data-stu-id="1690a-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="1690a-117">Siga estos pasos para configurar el parámetro que controla si las referencias a las facturas originales se imprimen en notas de crédito relacionadas.</span><span class="sxs-lookup"><span data-stu-id="1690a-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="1690a-118">Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="1690a-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="1690a-119">En la pestaña **Actualizaciones**, en la ficha desplegable **Factura**, establezca la opción **Aplicar el diseño de facturación de crédito en informes de facturas de proyectos y ventas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1690a-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Configurar los parámetros de clientes](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="1690a-121">Definir referencias a facturas originales</span><span class="sxs-lookup"><span data-stu-id="1690a-121">Define references to original invoices</span></span>

<span data-ttu-id="1690a-122">Utilice los siguientes procedimientos para definir referencias a facturas originales, según el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="1690a-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="1690a-123">Nota de abono de texto sin formato</span><span class="sxs-lookup"><span data-stu-id="1690a-123">Free text credit note</span></span>

1. <span data-ttu-id="1690a-124">Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="1690a-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="1690a-125">Cree una nota de abono nueva o seleccione una nota de abono existente.</span><span class="sxs-lookup"><span data-stu-id="1690a-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="1690a-126">Abra la factura.</span><span class="sxs-lookup"><span data-stu-id="1690a-126">Open the invoice.</span></span>
4. <span data-ttu-id="1690a-127">En el panel de acciones, en la ficha **Factura**, en el grupo **Funciones**, seleccione **Factura rectificativa**.</span><span class="sxs-lookup"><span data-stu-id="1690a-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="1690a-128">Introduzca la referencia a la factura original y seleccione el motivo de la corrección.</span><span class="sxs-lookup"><span data-stu-id="1690a-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definición de la referencia para una factura de servicios](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="1690a-130">Nota de abono de cliente</span><span class="sxs-lookup"><span data-stu-id="1690a-130">Customer credit note</span></span>

1. <span data-ttu-id="1690a-131">Vaya a **Clientes** \> **Pedidos** \> **Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1690a-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="1690a-132">Seleccione y abra el pedido de ventas facturado que hay que corregir.</span><span class="sxs-lookup"><span data-stu-id="1690a-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="1690a-133">En el panel de acciones en la ficha **Vender**, en el grupo **Nota de abono**, seleccione **Nota de abono**.</span><span class="sxs-lookup"><span data-stu-id="1690a-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="1690a-134">Especifique el motivo de la corrección.</span><span class="sxs-lookup"><span data-stu-id="1690a-134">Enter the reason for the correction.</span></span> <span data-ttu-id="1690a-135">La referencia a la factura original se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1690a-135">The reference to the original invoice is automatically established.</span></span>

![Definición de la referencia para un pedido de ventas](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="1690a-137">Nota de abono de proyecto</span><span class="sxs-lookup"><span data-stu-id="1690a-137">Project credit note</span></span>

1. <span data-ttu-id="1690a-138">Vaya a **Gestión y contabilidad de proyectos** \> **Facturas del proyecto** \> **Facturas del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="1690a-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="1690a-139">Seleccione y abra la factura de proyecto que hay que corregir.</span><span class="sxs-lookup"><span data-stu-id="1690a-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="1690a-140">En el panel de acciones, en la ficha **Factura de proyecto**, en el grupo **Funciones**, seleccione **Seleccionar para nota de abono**.</span><span class="sxs-lookup"><span data-stu-id="1690a-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="1690a-141">Seleccione **Factura rectificativa**.</span><span class="sxs-lookup"><span data-stu-id="1690a-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="1690a-142">Especifique el motivo de la corrección.</span><span class="sxs-lookup"><span data-stu-id="1690a-142">Enter the reason for the correction.</span></span> <span data-ttu-id="1690a-143">La referencia a la factura original se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1690a-143">The reference to the original invoice is automatically established.</span></span>

![Definición de la referencia para una factura de proyecto](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="1690a-145">Imprimir notas de abono</span><span class="sxs-lookup"><span data-stu-id="1690a-145">Printing credit notes</span></span>

<span data-ttu-id="1690a-146">Al imprimir notas de abono de texto libre, clientes y proyectos, incluirán la referencia a la factura original y el motivo de la corrección.</span><span class="sxs-lookup"><span data-stu-id="1690a-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Nota de abono impresa](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="1690a-148">Asegúrese de que los formatos imprimibles de los documentos estén configurados correctamente, asumiendo que se imprimirán referencias a facturas originales.</span><span class="sxs-lookup"><span data-stu-id="1690a-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]