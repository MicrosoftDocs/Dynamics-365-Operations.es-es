---
title: "Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales"
description: "Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: e311b0becbb243cebdc265eccf3059eb46217dee
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="d83cc-103">Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="d83cc-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d83cc-104">Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="d83cc-105">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="d83cc-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="d83cc-106">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="d83cc-107">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="d83cc-108">La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="d83cc-109">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="d83cc-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d83cc-110">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="d83cc-110">Templates and tasks</span></span>

<span data-ttu-id="d83cc-111">Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="d83cc-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="d83cc-112">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="d83cc-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="d83cc-113">La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del pedido de ventas de Finance and Operations a Sales:</span><span class="sxs-lookup"><span data-stu-id="d83cc-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="d83cc-114">**Nombre de la plantilla en la integración de datos:** Pedidos de ventas (Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="d83cc-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="d83cc-115">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="d83cc-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="d83cc-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="d83cc-116">OrderHeader</span></span>
    - <span data-ttu-id="d83cc-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="d83cc-117">OrderLine</span></span>

<span data-ttu-id="d83cc-118">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:</span><span class="sxs-lookup"><span data-stu-id="d83cc-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="d83cc-119">Productos (de Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="d83cc-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="d83cc-120">Cuentas (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="d83cc-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="d83cc-121">Contactos a Clientes (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="d83cc-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="d83cc-122">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="d83cc-122">Entity set</span></span>

| <span data-ttu-id="d83cc-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d83cc-123">Finance and Operations</span></span>  | <span data-ttu-id="d83cc-124">Ventas</span><span class="sxs-lookup"><span data-stu-id="d83cc-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="d83cc-125">Encabezados de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="d83cc-125">CDS sales order headers</span></span> | <span data-ttu-id="d83cc-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="d83cc-126">SalesOrders</span></span>       |
| <span data-ttu-id="d83cc-127">Líneas de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="d83cc-127">CDS sales order lines</span></span>   | <span data-ttu-id="d83cc-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="d83cc-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="d83cc-129">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="d83cc-129">Entity flow</span></span>

<span data-ttu-id="d83cc-130">Los pedidos de ventas se crean en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="d83cc-131">Los filtros de la plantilla ayudan a garantizar que solo se incluyan en la sincronización los pedidos de ventas más importantes:</span><span class="sxs-lookup"><span data-stu-id="d83cc-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="d83cc-132">En el pedido de ventas, tanto el cliente de pedidos como el cliente de facturación que se originan en Sales se incluirán en la sincronización.</span><span class="sxs-lookup"><span data-stu-id="d83cc-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="d83cc-133">En Finance and Operations, los campos **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para realizar el seguimiento de la sincronización en las entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="d83cc-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="d83cc-134">Debe confirmar el pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="d83cc-135">Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de **Enviado** o **Facturado**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="d83cc-136">Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="d83cc-137">Solo se sincronizarán con Sales los pedidos de ventas en los que se calculan las ventas totales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="d83cc-138">Actualmente, los impuestos relacionados con los gastos en cabecera de pedidos de ventas no se incluyen en la sincronización de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="d83cc-139">Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="d83cc-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="d83cc-140">Sin embargo, los impuestos relacionados con cargos en el nivel de línea se incluyen en la sincronización.</span><span class="sxs-lookup"><span data-stu-id="d83cc-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d83cc-141">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="d83cc-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="d83cc-142">Se han agregado nuevos campos a la entidad **Pedido** y se muestran en la página:</span><span class="sxs-lookup"><span data-stu-id="d83cc-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="d83cc-143">**Se mantiene externamente** – Establezca esta opción en **Sí** cuando el pedido proviene de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="d83cc-144">**Estado de procesamiento** – Este campo muestra el estado de procesamiento del pedido en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="d83cc-145">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="d83cc-145">The following values are available:</span></span>

    - <span data-ttu-id="d83cc-146">Activos</span><span class="sxs-lookup"><span data-stu-id="d83cc-146">Active</span></span>
    - <span data-ttu-id="d83cc-147">Confirmado</span><span class="sxs-lookup"><span data-stu-id="d83cc-147">Confirmed</span></span>
    - <span data-ttu-id="d83cc-148">Albarán</span><span class="sxs-lookup"><span data-stu-id="d83cc-148">Packing Slip</span></span>
    - <span data-ttu-id="d83cc-149">Facturado</span><span class="sxs-lookup"><span data-stu-id="d83cc-149">Invoiced</span></span>
    - <span data-ttu-id="d83cc-150">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="d83cc-150">Picked</span></span>
    - <span data-ttu-id="d83cc-151">Parcialmente seleccionado</span><span class="sxs-lookup"><span data-stu-id="d83cc-151">Partially Picked</span></span>
    - <span data-ttu-id="d83cc-152">Parcialmente empaquetado</span><span class="sxs-lookup"><span data-stu-id="d83cc-152">Partially Packed</span></span>
    - <span data-ttu-id="d83cc-153">Enviados</span><span class="sxs-lookup"><span data-stu-id="d83cc-153">Shipped</span></span>
    - <span data-ttu-id="d83cc-154">Parcialmente enviado</span><span class="sxs-lookup"><span data-stu-id="d83cc-154">Partially Shipped</span></span>
    - <span data-ttu-id="d83cc-155">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="d83cc-155">Partially Invoiced</span></span>
    - <span data-ttu-id="d83cc-156">Cancelado</span><span class="sxs-lookup"><span data-stu-id="d83cc-156">Cancelled</span></span>

<span data-ttu-id="d83cc-157">La configuración **Solo tiene productos mantenidos externamente** se usa en otros escenarios del pedido de ventas (por ejemplo, sincronización de Sales a Finance and Operations) para realizar un seguimiento constante de si un pedido de ventas está enteramente compuesto de productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="d83cc-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="d83cc-158">Si un pedido de ventas solo contiene productos mantenidos externamente, los productos se mantienen en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="d83cc-159">Este ajuste ayuda a garantizar que no intenta sincronizar las líneas de pedido de ventas que tienen productos desconocidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="d83cc-160">Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan para los pedidos mantenidos de forma externa, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="d83cc-161">No se puede editar la página del pedido porque la información del pedido de ventas se sincronizará desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="d83cc-162">El estado de un pedido de ventas permanecerá **Activo** para ayudar a garantizar que los cambios de Finance and Operations se incluyen en el pedido de ventas de Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="d83cc-163">Para controlar este comportamiento, establezca el valor del **Código de estado \[Status\]** en **Activo** en el proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="d83cc-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d83cc-164">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="d83cc-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="d83cc-165">Antes de sincronizar pedidos de ventas, es importante actualizar la configuración siguiente en los sistemas:</span><span class="sxs-lookup"><span data-stu-id="d83cc-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="d83cc-166">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="d83cc-166">Setup in Sales</span></span>

- <span data-ttu-id="d83cc-167">Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión de Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="d83cc-168">Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo.</span><span class="sxs-lookup"><span data-stu-id="d83cc-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="d83cc-169">Si el equipo tampoco tiene derechos de administrador, cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.</span><span class="sxs-lookup"><span data-stu-id="d83cc-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="d83cc-170">Vaya a **Configuración** > **Seguridad** > **Equipos,** seleccione el equipo adecuado, seleccione **Gestionar roles** y seleccione un rol que tenga los permisos deseados, por ejemplo, **Administrador de sistema**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="d83cc-171">Vaya a **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, y asegúrese de que se utilicen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d83cc-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="d83cc-172">La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="d83cc-173">El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="d83cc-174">Configuración en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d83cc-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="d83cc-175">Vaya a **Ventas y marketing** > **Tareas periódicas** > **Calcular ventas totales**, y configure el trabajo para ejecutar como un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="d83cc-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="d83cc-176">Establezca la opción **Calcular totales para pedidos de ventas** como **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="d83cc-177">Este paso es importante, porque solo se sincronizan con Sales los pedidos de ventas en los que se calculan las ventas totales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="d83cc-178">La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="d83cc-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="d83cc-179">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="d83cc-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="d83cc-180">Tarea de SalesHeader</span><span class="sxs-lookup"><span data-stu-id="d83cc-180">SalesHeader task</span></span>

- <span data-ttu-id="d83cc-181">Asegúrese de que existe la asignación necesaria para **InvoiceCountryRegionId** como **BillingAddress\_Country** y para **DeliveryCountryRegionId** como **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="d83cc-182">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.</span><span class="sxs-lookup"><span data-stu-id="d83cc-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="d83cc-183">Una lista de precios es necesaria para poder crear pedidos en Sales.</span><span class="sxs-lookup"><span data-stu-id="d83cc-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="d83cc-184">Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="d83cc-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="d83cc-185">Puede usar la lista de precios predeterminada para una sola divisa.</span><span class="sxs-lookup"><span data-stu-id="d83cc-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="d83cc-186">Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="d83cc-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="d83cc-187">El valor de la plantilla predeterminada de **pricelevelid.name \[Nombre de la lista de precios\]** es **CRM Service USA (ejemplo).**</span><span class="sxs-lookup"><span data-stu-id="d83cc-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="d83cc-188">Tarea de SalesLine</span><span class="sxs-lookup"><span data-stu-id="d83cc-188">SalesLine task</span></span>

- <span data-ttu-id="d83cc-189">Asegúrese de que la asignación requerida existe para **DeliveryCountryRegionId** como **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="d83cc-190">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.</span><span class="sxs-lookup"><span data-stu-id="d83cc-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="d83cc-191">Asegúrese de que la asignación de valores requerida para **SalesUnitSymbol** existe en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="d83cc-192">Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="d83cc-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d83cc-193">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="d83cc-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="d83cc-194">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d83cc-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="d83cc-195">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="d83cc-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="d83cc-196">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="d83cc-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="d83cc-197">La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d83cc-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="d83cc-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="d83cc-198">OrderHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="d83cc-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="d83cc-200">OrderLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="d83cc-202">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d83cc-202">Related topics</span></span>

[<span data-ttu-id="d83cc-203">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="d83cc-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="d83cc-204">Sincronizar directamente cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d83cc-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="d83cc-205">Sincronizar directamente productos de Finance and Operations con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="d83cc-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="d83cc-206">Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d83cc-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="d83cc-207">Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="d83cc-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




