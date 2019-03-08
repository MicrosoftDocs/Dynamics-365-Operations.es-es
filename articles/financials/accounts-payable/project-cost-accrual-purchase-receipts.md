---
title: Acumulación de costes de proyectos en recibos de compra
description: Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bc822652abbba68f094fe5b8a65f796165a92c4c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "340439"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="39825-103">Acumulación de costes de proyectos en recibos de compra</span><span class="sxs-lookup"><span data-stu-id="39825-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39825-104">Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39825-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="39825-105">Las facturas para un proyecto suelen llegar después de prestar los bienes y servicios, lo cual puede tener un impacto significativo impacto en los indicadores de rendimiento clave (KPI) del proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="39825-106">Es importante poder controlar estas transacciones mediante informes financieros y del proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="39825-107">En el siguiente supuesto de ejemplo se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="39825-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="39825-108">Contoso Consulting ha iniciado un nuevo proyecto de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="39825-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="39825-109">Se crea un pedido de compra para comprar un equipo para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="39825-110">El equipo costará 1500 $ y los servicios de instalación costarán 150 $.</span><span class="sxs-lookup"><span data-stu-id="39825-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="39825-111">El proveedor ha entregado e instalado el equipo, pero Contoso Consulting aún no ha recibido la factura.</span><span class="sxs-lookup"><span data-stu-id="39825-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="39825-112">El director del proyecto desea ver la acumulación de costes de proyecto de 1650 $ antes de que se entregue la factura.</span><span class="sxs-lookup"><span data-stu-id="39825-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="39825-113">Este coste también se debe reflejar en los informes financieros de final de mes de la empresa.</span><span class="sxs-lookup"><span data-stu-id="39825-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="39825-114">El coste acumulado tiene que registrarse en el nivel financiero y en el nivel del proyecto a efectos de notificación.</span><span class="sxs-lookup"><span data-stu-id="39825-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="39825-115">En Finance and Operations, la actualización financiera de la recepción del producto se puede controlar para las categorías de artículo y compras.</span><span class="sxs-lookup"><span data-stu-id="39825-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="39825-116">Para los artículos, en la página **Parámetros de proveedores**, seleccione la opción **Publicar recepciones de producto en la contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="39825-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="39825-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="39825-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="39825-118">Para las categorías de compras, en la página **Regla de directivas de categorías**, seleccione Directivas de **compra** y luego seleccione **Acumular gasto de compra en recepción** para cada categoría de compras.</span><span class="sxs-lookup"><span data-stu-id="39825-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="39825-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="39825-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="39825-120">Las cuentas **Gasto de compra no facturado** y **Acumulación de compras** en **Configuración del registro** se utilizarán cuando se registren los asientos relacionados con la recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="39825-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="39825-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="39825-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="39825-122">Con esta mismo escenario, vea cómo el registro de una recepción de producto afectará a la contabilidad general y la información del proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="39825-123">**Paso 1:** Crear y confirmar un nuevo pedido de compra para el proyecto para registrar la compra de un equipo de 1500 $ y de unos servicios de instalación de 150 $.</span><span class="sxs-lookup"><span data-stu-id="39825-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="39825-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="39825-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="39825-125">Cuando se confirma el pedido de compra, se crean las transacciones para el gasto comprometido para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="39825-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="39825-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="39825-127">Las transacciones para el gasto comprometido tendrán el campo **Origen de transacción** establecido en **Pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="39825-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="39825-128">La creación y confirmación de un pedido de compra no crea transacciones para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="39825-129">**Paso 2:** Se registran los bienes y servicios entregados y una recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="39825-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="39825-130">El registro de una recepción de producto generará y registrará un asiento en la contabilidad.</span><span class="sxs-lookup"><span data-stu-id="39825-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="39825-131">El asiento cargará los gastos de compra, la cuenta no facturada y la cuenta de acumulación de abono de compras.</span><span class="sxs-lookup"><span data-stu-id="39825-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="39825-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="39825-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="39825-133">El registro de una recepción de producto utilizará la configuración de registro para las categorías de compras y productos, y no la configuración de registro para las categorías de proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="39825-134">Para reflejar correctamente el impacto financiero de las acumulaciones de compras, esta configuración tiene que estar alineada.</span><span class="sxs-lookup"><span data-stu-id="39825-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="39825-135">Es posible asignar categorías de compras a las categorías de proyecto en la página **Categoría de compras**.</span><span class="sxs-lookup"><span data-stu-id="39825-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="39825-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="39825-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="39825-137">**Paso 3:** Crear un borrador de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="39825-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="39825-138">En Finance and Operations, el registro de una recepción de producto no afecta a la información del proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="39825-139">Como solución alternativa, podría generar un borrador de factura de proveedor justo después de registrar la recepción de compra.</span><span class="sxs-lookup"><span data-stu-id="39825-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="39825-140">Vaya a la página **Pedido de compra** &gt; **ficha Factura** &gt; **Generar** &gt; **Factura**.</span><span class="sxs-lookup"><span data-stu-id="39825-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="39825-141">Esto crea un documento de factura pendiente que actualiza la información de proyecto.</span><span class="sxs-lookup"><span data-stu-id="39825-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="39825-142">Crear un borrador de factura de proveedor generará transacción de proyectos pendientes.</span><span class="sxs-lookup"><span data-stu-id="39825-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="39825-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="39825-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="39825-144">En la página **Gasto comprometido**, los registros creados en el paso 1 se cerrarán y se crearán nuevos registros para reflejar el compromiso de coste procedente de la factura de proveedor pendiente.</span><span class="sxs-lookup"><span data-stu-id="39825-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="39825-145">El campo **Origen de transacción** para el gasto comprometido se enviará a **Factura de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="39825-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="39825-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="39825-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="39825-147">La factura de proveedor seguirá en estado de pendiente hasta que llegue la factura de proveedor real.</span><span class="sxs-lookup"><span data-stu-id="39825-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>



