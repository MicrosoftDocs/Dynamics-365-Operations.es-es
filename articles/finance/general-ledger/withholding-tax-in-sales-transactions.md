---
title: Retención de impuestos en transacciones de ventas
description: Este tema enumera los pasos para evitar el cálculo de la retención de impuestos para clientes seleccionados. Para los clientes que especifican la retención de impuestos en sus pagos, puede asignar el grupo de retención de impuestos predeterminado.
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
ms.openlocfilehash: c50f6df1c63c91107da65f463934565f786d6ccd
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060791"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="a9739-104">Retención de impuestos en transacciones de ventas</span><span class="sxs-lookup"><span data-stu-id="a9739-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="a9739-105">Este tema enumera los pasos para evitar el cálculo de la retención de impuestos para clientes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a9739-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="a9739-106">Para los clientes que especifican la retención de impuestos en los pagos que le hacen, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="a9739-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="a9739-107">Vaya a **Panel de exploración > Módulos > Clientes > Clientes > Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="a9739-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="a9739-108">Haga clic en la cuenta de cliente correspondiente y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9739-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="a9739-109">En la pestaña **Factura y entrega**, configure el campo **Calcular retención de impuestos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9739-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="a9739-110">La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está activada para este cliente en los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="a9739-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="a9739-111">Seleccione un grupo de retención de impuestos en **Grupo de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="a9739-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="a9739-112">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9739-112">Click **Save**.</span></span>

<span data-ttu-id="a9739-113">Para artículos o servicios, que están sujetos a retención de impuestos, puede asignar el valor predeterminado **Grupo de retención de impuestos de artículos** en **Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="a9739-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="a9739-114">Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="a9739-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="a9739-115">Haga clic en el número de artículo correspondiente y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9739-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="a9739-116">En la pestaña **Vender**, haga clic en **Calcular retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="a9739-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="a9739-117">La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está establecida en **Sí** para este artículo en la pestaña **Vender** de la página **Producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="a9739-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="a9739-118">Seleccione un grupo de retención de impuestos de artículos en la lista **Grupo de retención de impuestos de artículos**.</span><span class="sxs-lookup"><span data-stu-id="a9739-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="a9739-119">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9739-119">Click **Save**.</span></span>

<span data-ttu-id="a9739-120">Los grupos de retención de impuestos y los grupos de retención de impuestos de artículos se pueden asignar en la página **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="a9739-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="a9739-121">El grupo de retención de impuestos y el grupo de retención de impuestos de artículos predeterminados se utilizarán como entradas predeterminadas en las líneas de pedido de ventas cuando se cree un nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a9739-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="a9739-122">La retención de impuestos se calcula y registra con el **Diario de pagos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="a9739-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="a9739-123">Puede ajustar manualmente el código de retención de impuestos aplicable, así como el importe real de retención de impuestos en la pestaña **Liquidar transacciones** de la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="a9739-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="a9739-124">El importe de la retención de impuestos calculada se deducirá del pago del cliente y se publicará en la cuenta de **Compensación de retención de impuestos** en un asiento relacionado.</span><span class="sxs-lookup"><span data-stu-id="a9739-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>
