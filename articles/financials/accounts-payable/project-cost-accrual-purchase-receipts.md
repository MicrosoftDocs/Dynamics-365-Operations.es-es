---
title: "Acumulación de costes de proyectos en recibos de compra"
description: "Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f7355dc856d97a19d0f7558061b3e2d9902dab65
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---

# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="54492-103">Acumulación de costes de proyectos en recibos de compra</span><span class="sxs-lookup"><span data-stu-id="54492-103">Project cost accrual on purchase receipts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="54492-104">Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="54492-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> 

<span data-ttu-id="54492-105">Las facturas para un proyecto suelen llegar después de prestar los bienes y servicios, lo cual puede tener un impacto significativo impacto en los indicadores de rendimiento clave (KPI) del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="54492-106">Es importante poder controlar estas transacciones mediante informes financieros y del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="54492-107">En el siguiente supuesto de ejemplo se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="54492-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="54492-108">Contoso Consulting ha iniciado un nuevo proyecto de implementación en la nube.</span><span class="sxs-lookup"><span data-stu-id="54492-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="54492-109">Se crea un pedido de compra para comprar un equipo para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="54492-110">El equipo costará 1500 $ y los servicios de instalación costarán 150 $.</span><span class="sxs-lookup"><span data-stu-id="54492-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="54492-111">El proveedor ha entregado e instalado el equipo, pero Contoso Consulting aún no ha recibido la factura.</span><span class="sxs-lookup"><span data-stu-id="54492-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="54492-112">El director del proyecto desea ver la acumulación de costes de proyecto de 1650 $ antes de que se entregue la factura.</span><span class="sxs-lookup"><span data-stu-id="54492-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="54492-113">Este coste también se debe reflejar en los informes financieros de final de mes de la empresa.</span><span class="sxs-lookup"><span data-stu-id="54492-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="54492-114">El coste acumulado tiene que registrarse en el nivel financiero y en el nivel del proyecto a efectos de notificación.</span><span class="sxs-lookup"><span data-stu-id="54492-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="54492-115">En Finance and Operations, la actualización financiera de la recepción del producto se puede controlar para las categorías de artículo y compras.</span><span class="sxs-lookup"><span data-stu-id="54492-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="54492-116">Para los artículos, en la página **Parámetros de proveedores**, seleccione la opción **Publicar recepciones de producto en la contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="54492-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="54492-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="54492-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="54492-118">Para las categorías de compras, en la página **Regla de directivas de categorías**, seleccione Directivas de **compra** y luego seleccione **Acumular gasto de compra en recepción** para cada categoría de compras.</span><span class="sxs-lookup"><span data-stu-id="54492-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="54492-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="54492-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="54492-120">Las cuentas **Gasto de compra no facturado** y **Acumulación de compras** en **Configuración del registro** se utilizarán cuando se registren los asientos relacionados con la recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="54492-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="54492-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="54492-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="54492-122">Con esta mismo escenario, vea cómo el registro de una recepción de producto afectará a la contabilidad general y la información del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="54492-123">**Paso 1:** Crear y confirmar un nuevo pedido de compra para el proyecto para registrar la compra de un equipo de 1500 $ y de unos servicios de instalación de 150 $.</span><span class="sxs-lookup"><span data-stu-id="54492-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="54492-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="54492-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="54492-125">Cuando se confirma el pedido de compra, se crean las transacciones para el gasto comprometido para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="54492-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="54492-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="54492-127">Las transacciones para el gasto comprometido tendrán el campo **Origen de transacción** establecido en **Pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="54492-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="54492-128">La creación y confirmación de un pedido de compra no crea transacciones para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="54492-129">**Paso 2:** Se registran los bienes y servicios entregados y una recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="54492-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="54492-130">El registro de una recepción de producto generará y registrará un asiento en la contabilidad.</span><span class="sxs-lookup"><span data-stu-id="54492-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="54492-131">El asiento cargará los gastos de compra, la cuenta no facturada y la cuenta de acumulación de abono de compras.</span><span class="sxs-lookup"><span data-stu-id="54492-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="54492-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="54492-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="54492-133">El registro de una recepción de producto utilizará la configuración de registro para las categorías de compras y productos, y no la configuración de registro para las categorías de proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="54492-134">Para reflejar correctamente el impacto financiero de las acumulaciones de compras, esta configuración tiene que estar alineada.</span><span class="sxs-lookup"><span data-stu-id="54492-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="54492-135">Es posible asignar categorías de compras a las categorías de proyecto en la página **Categoría de compras**.</span><span class="sxs-lookup"><span data-stu-id="54492-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="54492-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="54492-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="54492-137">**Paso 3:** Crear un borrador de factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="54492-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="54492-138">En Finance and Operations, el registro de una recepción de producto no afecta a la información del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="54492-139">Como solución alternativa, podría generar un borrador de factura de proveedor justo después de registrar la recepción de compra.</span><span class="sxs-lookup"><span data-stu-id="54492-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="54492-140">Vaya a la página **Pedido de compra** &gt; **ficha Factura** &gt; **Generar** &gt; **Factura**.</span><span class="sxs-lookup"><span data-stu-id="54492-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="54492-141">Esto crea un documento de factura pendiente que actualiza la información de proyecto.</span><span class="sxs-lookup"><span data-stu-id="54492-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="54492-142">Crear un borrador de factura de proveedor generará transacción de proyectos pendientes.</span><span class="sxs-lookup"><span data-stu-id="54492-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="54492-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="54492-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="54492-144">En la página **Gasto comprometido**, los registros creados en el paso 1 se cerrarán y se crearán nuevos registros para reflejar el compromiso de coste procedente de la factura de proveedor pendiente.</span><span class="sxs-lookup"><span data-stu-id="54492-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="54492-145">El campo **Origen de transacción** para el gasto comprometido se enviará a **Factura de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="54492-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="54492-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="54492-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="54492-147">La factura de proveedor seguirá en estado de pendiente hasta que llegue la factura de proveedor real.</span><span class="sxs-lookup"><span data-stu-id="54492-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>




