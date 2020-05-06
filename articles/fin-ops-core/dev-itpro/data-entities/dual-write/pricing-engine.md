---
title: Sincronizar con el motor de precios bajo demanda Dynamics 365 Supply Chain Management
description: Este tema describe cómo usar el motor de precios en Microsoft Dynamics 365 Supply Chain Management de Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 5ffc0358ff58b2a05aa84b4467a27d88b5e1ec42
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270345"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a><span data-ttu-id="40503-103">Sincronizar con el motor de precios bajo demanda Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="40503-103">Sync with the Dynamics 365 Supply Chain Management pricing engine on demand</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="40503-104">Microsoft Dynamics 365 Supply Chain Management incluye un motor de precios que gestiona acuerdos comerciales, listas de precios, programas de fidelización de clientes, promociones y descuentos.</span><span class="sxs-lookup"><span data-stu-id="40503-104">Microsoft Dynamics 365 Supply Chain Management includes a pricing engine that handles trade agreements, price lists, customer loyalty programs, promotions, and discounts.</span></span> <span data-ttu-id="40503-105">El motor de fijación de precios utiliza reglas complejas para determinar el mejor precio para un presupuesto o pedido determinado.</span><span class="sxs-lookup"><span data-stu-id="40503-105">The pricing engine uses complex rules to determine the best price for a given quotation or order.</span></span> <span data-ttu-id="40503-106">Cuando usa doble escritura, usa precios estáticos o el motor de precios de Dynamics 365 Supply Chain Management en las páginas de Presupuesto y Pedido en Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="40503-106">When you use dual-write, you use either static pricing or the pricing engine from Dynamics 365 Supply Chain Management on the Quote and Order pages in Dynamics 365 Sales.</span></span>

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a><span data-ttu-id="40503-107">Usar el motor de precios de Supply Chain Management en Sales</span><span class="sxs-lookup"><span data-stu-id="40503-107">Use the pricing engine from Supply Chain Management in Sales</span></span>

1. <span data-ttu-id="40503-108">En Sales, vaya a **Ventas \> Pedidos**.</span><span class="sxs-lookup"><span data-stu-id="40503-108">In Sales, go to **Sales \> Orders**.</span></span>
2. <span data-ttu-id="40503-109">Seleccione **Nuevo** para crear un pedido nuevo o seleccione uno ya existente en la lista **Mis pedidos**.</span><span class="sxs-lookup"><span data-stu-id="40503-109">Select **New** to create a new order, or select an existing order in the **My Orders** list.</span></span>
3. <span data-ttu-id="40503-110">Agregar una línea de pedido nueva.</span><span class="sxs-lookup"><span data-stu-id="40503-110">Add a new order line.</span></span>
4. <span data-ttu-id="40503-111">Si está creando un nuevo pedido, seleccione **Precio de pedido** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="40503-111">If you're creating a new order, select **Price Order** on the Action Pane.</span></span> <span data-ttu-id="40503-112">Si está actualizando un pedido ya existente, seleccione **Recalcular** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="40503-112">If you're updating an existing order, select **Recalculate** on the Action Pane.</span></span>

    <span data-ttu-id="40503-113">Los siguientes campos se rellenan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="40503-113">The following fields are automatically filled in:</span></span>

    + <span data-ttu-id="40503-114">Detalles del importe</span><span class="sxs-lookup"><span data-stu-id="40503-114">Detail Amount</span></span>
    + <span data-ttu-id="40503-115">% de descuento</span><span class="sxs-lookup"><span data-stu-id="40503-115">Discount %</span></span>
    + <span data-ttu-id="40503-116">Descuento</span><span class="sxs-lookup"><span data-stu-id="40503-116">Discount</span></span>
    + <span data-ttu-id="40503-117">Importe previo al flete</span><span class="sxs-lookup"><span data-stu-id="40503-117">Pre-Freight Amount</span></span>
    + <span data-ttu-id="40503-118">Importe del flete</span><span class="sxs-lookup"><span data-stu-id="40503-118">Freight Amount</span></span>
    + <span data-ttu-id="40503-119">Impuestos totales</span><span class="sxs-lookup"><span data-stu-id="40503-119">Total Tax</span></span>
    + <span data-ttu-id="40503-120">Importe total</span><span class="sxs-lookup"><span data-stu-id="40503-120">Total Amount</span></span>
    
5. <span data-ttu-id="40503-121">Para garantizar que el sistema considera los acuerdos comerciales y de ventas para calcular el precio:</span><span class="sxs-lookup"><span data-stu-id="40503-121">To ensure that the system considers trade and sales agreements to calculate the price:</span></span>
    1. <span data-ttu-id="40503-122">Navegue a su entorno de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40503-122">Navigate to your Supply Chain Management environment.</span></span>
    2. <span data-ttu-id="40503-123">Navegue a **Clientes \> Configuración \> Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="40503-123">Navigate to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
    3. <span data-ttu-id="40503-124">Seleccione la pestaña **Precios** en la barra de navegación lateral.</span><span class="sxs-lookup"><span data-stu-id="40503-124">Select the **Prices** tab in the side navigation bar.</span></span>
    4. <span data-ttu-id="40503-125">Bajo la ficha desplegable **Evaluación de acuerdos comerciales**, desmarque la opción **Entrada manual**.</span><span class="sxs-lookup"><span data-stu-id="40503-125">Under the **Trade agreement evaluation** fastab, uncheck the **Manual entry** option.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="40503-126">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="40503-126">How it works</span></span>

<span data-ttu-id="40503-127">Cuando selecciona **Precio del pedido** en Sales, la función **Totales** en la pestaña **Pedido de ventas \> Ver** en Supply Chain Management se llama para el pedido de ventas asociado.</span><span class="sxs-lookup"><span data-stu-id="40503-127">When you select **Price Order** in Sales, the **Totals** function on the **Sales Order \> View** tab in Supply Chain Management is called for the associated sales order.</span></span> <span data-ttu-id="40503-128">Los valores en el total del pedido en Sales se utilizan para completar los campos correspondientes en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40503-128">The values in the order total in Sales are used to fill in the corresponding fields in Supply Chain Management.</span></span>

<span data-ttu-id="40503-129">Cuando se calcula el total del pedido de ventas en Supply Chain Management, el cálculo evalúa los acuerdos comerciales existentes y los acuerdos de ventas para el cliente y los productos que figuran en el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="40503-129">When the sales order total is calculated in Supply Chain Management, the calculation evaluates the existing trade agreements and sales agreements for the customer and the products that are listed in the sales order.</span></span> <span data-ttu-id="40503-130">Esta información se usa para calcular los totales.</span><span class="sxs-lookup"><span data-stu-id="40503-130">This information is used to calculate the totals.</span></span> <span data-ttu-id="40503-131">Cuando **Precio del pedido** está seleccionado, Sales refleja automáticamente toda la configuración que se ha realizado en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40503-131">When **Price Order** is selected, Sales automatically reflects all the setup that has been done in Supply Chain Management.</span></span>

## <a name="limitations"></a><span data-ttu-id="40503-132">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="40503-132">Limitations</span></span>

<span data-ttu-id="40503-133">Cuando se completan los campos en Sales, se aplican las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="40503-133">When the fields in Sales are filled in, the following limitations apply:</span></span>

+ <span data-ttu-id="40503-134">La configuración de cargos y asignaciones de cargos en Supply Chain Management no se replica en Sales.</span><span class="sxs-lookup"><span data-stu-id="40503-134">The setup of charges and charge allocations in Supply Chain Management isn't replicated in Sales.</span></span>
+ <span data-ttu-id="40503-135">El precio no considera precios minoristas especiales que se especifican en el campo **Canal minorista** en la página de línea de pedido de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="40503-135">Pricing doesn't consider special retail pricing that is specified in the **Retail Channel** field on the sales order line page in Supply Chain Management.</span></span>
+ <span data-ttu-id="40503-136">Descuentos que se definen en la sección **Gestión de permisos comerciales** de Supply Chain Management no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="40503-136">Discounts that are defined in the **Trade Allowance Management** section of Supply Chain Management aren't considered.</span></span>
