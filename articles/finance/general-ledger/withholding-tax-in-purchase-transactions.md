---
title: Retención de impuestos en transacciones de compra
description: Para los proveedores sujetos a retención de impuestos, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Todos los proveedores**.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06c18e6b0779539a6da7ae7afbe000c4cfc78d9e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256676"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="fced2-103">Retención de impuestos en transacciones de compra</span><span class="sxs-lookup"><span data-stu-id="fced2-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="fced2-104">Para los proveedores sujetos a retención de impuestos, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="fced2-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="fced2-105">Vaya a **Panel de exploración > Módulos > Proveedores > Proveedores > Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="fced2-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="fced2-106">Haga clic en la cuenta de proveedor correspondiente y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fced2-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="fced2-107">En la pestaña **Factura y entrega**, establezca el campo **Calcular retención de impuestos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fced2-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="fced2-108">La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está activada para este proveedor en los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="fced2-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="fced2-109">Seleccione un grupo de retención de impuestos en **Grupo de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="fced2-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="fced2-110">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fced2-110">Click **Save**.</span></span>

<span data-ttu-id="fced2-111">Para artículos o servicios, que están sujetos a retención de impuestos, puede asignar el valor predeterminado **Grupo de retención de impuestos de artículos** en **Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="fced2-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="fced2-112">Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="fced2-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="fced2-113">Haga clic en el número de artículo correspondiente y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fced2-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="fced2-114">En la pestaña **Comprar**, haga clic en **Calcular retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="fced2-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="fced2-115">La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está establecida en **Sí** para este artículo en la pestaña **Comprar** de la página **Producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="fced2-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="fced2-116">Seleccione un grupo de retención de impuestos de artículos en la lista **Grupo de retención de impuestos de artículos**.</span><span class="sxs-lookup"><span data-stu-id="fced2-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="fced2-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fced2-117">Click **Save**.</span></span>

<span data-ttu-id="fced2-118">Los grupos de retención de impuestos y los grupos de retención de impuestos de artículos se pueden asignar en las páginas:</span><span class="sxs-lookup"><span data-stu-id="fced2-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="fced2-119">**Pedido de compra**</span><span class="sxs-lookup"><span data-stu-id="fced2-119">**Purchase order**</span></span>
- <span data-ttu-id="fced2-120">**Factura del proveedor**</span><span class="sxs-lookup"><span data-stu-id="fced2-120">**Vendor invoice**</span></span>
- <span data-ttu-id="fced2-121">**Diario de facturas**</span><span class="sxs-lookup"><span data-stu-id="fced2-121">**Invoice journal**</span></span>

<span data-ttu-id="fced2-122">El grupo de retención de impuestos predeterminado y el grupo de retención de impuestos de artículo se llevarán a las líneas al crear **Pedidos de compra** o **Facturas de proveedores pendientes**.</span><span class="sxs-lookup"><span data-stu-id="fced2-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="fced2-123">Para **Diario de facturas de proveedor**, puede activar **Calcular retención de impuestos** y seleccionar **Grupo de retención de impuestos de artículo** en la pestaña **General** del diario.</span><span class="sxs-lookup"><span data-stu-id="fced2-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="fced2-124">El importe temporal de retención de impuestos está disponible en el campo **Retención de impuestos ajustada** de la pestaña **Totales** de la página **Pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="fced2-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![La retención de impuestos se incluye en el pedido de compra.](media/withholding-tax-adjusted.png)

<span data-ttu-id="fced2-126">La retención de impuestos se calcula en el **Diario de pagos a proveedores**.</span><span class="sxs-lookup"><span data-stu-id="fced2-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="fced2-127">Puede ajustar manualmente los códigos de retención de impuestos aplicables, así como los importes de retención de impuestos en la pestaña **Retención de impuestos** de la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="fced2-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![La retención se puede ajustar manualmente en la página Liquidar transacciones](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="fced2-129">El importe de retención de impuestos derivado se deducirá del pago del proveedor y se publicará en la **Cuenta de retención de impuestos** en un asiento relacionado.</span><span class="sxs-lookup"><span data-stu-id="fced2-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Cuenta de retención de impuestos que muestra un asiento relacionado](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]