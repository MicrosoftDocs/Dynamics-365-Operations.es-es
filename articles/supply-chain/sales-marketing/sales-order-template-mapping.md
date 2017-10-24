---
title: "Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 707efc97afc0679ed1fc22539789e98cbabcb581
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="5acf4-103">Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="5acf4-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5acf4-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="5acf4-105">Plantilla y tareas</span><span class="sxs-lookup"><span data-stu-id="5acf4-105">Template and tasks</span></span>

<span data-ttu-id="5acf4-106">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del pedido de ventas de Finance and Operations a Sales:</span><span class="sxs-lookup"><span data-stu-id="5acf4-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="5acf4-107">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="5acf4-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="5acf4-108">Pedidos de ventas (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="5acf4-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="5acf4-109">**Nombres de las tareas en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="5acf4-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="5acf4-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5acf4-110">OrderHeader</span></span>
    - <span data-ttu-id="5acf4-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5acf4-111">OrderLine</span></span>

<span data-ttu-id="5acf4-112">Tareas de sincronización necesarias antes de sincronizar el encabezado y las líneas de factura en Sales:</span><span class="sxs-lookup"><span data-stu-id="5acf4-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="5acf4-113">Productos (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="5acf4-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="5acf4-114">Cuentas (de Sales a Fin and Ops), si es que se usan</span><span class="sxs-lookup"><span data-stu-id="5acf4-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="5acf4-115">Contactos a Clientes (de Sales a Fin and Ops) si es que se usan</span><span class="sxs-lookup"><span data-stu-id="5acf4-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="5acf4-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="5acf4-116">Entity set</span></span>

| <span data-ttu-id="5acf4-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5acf4-117">Finance and Operations</span></span> |    <span data-ttu-id="5acf4-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="5acf4-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="5acf4-119">Ventas</span><span class="sxs-lookup"><span data-stu-id="5acf4-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="5acf4-120">Encabezados de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="5acf4-120">CDS sales order headers</span></span>| <span data-ttu-id="5acf4-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="5acf4-121">SalesOrder</span></span>     | <span data-ttu-id="5acf4-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="5acf4-122">SalesOrders</span></span> |
| <span data-ttu-id="5acf4-123">Líneas de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="5acf4-123">CDS sales order lines</span></span>  | <span data-ttu-id="5acf4-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="5acf4-124">SalesOrderLine</span></span> | <span data-ttu-id="5acf4-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="5acf4-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="5acf4-126">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="5acf4-126">Entity flow</span></span>

<span data-ttu-id="5acf4-127">Los pedidos de ventas se crean en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="5acf4-128">Los filtros de la plantilla le garantizan que solo se incluyan en la sincronización los pedidos de ventas más importantes:</span><span class="sxs-lookup"><span data-stu-id="5acf4-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="5acf4-129">Asimismo, se incluirán en la sincronización los clientes de pedidos y facturación del pedido de ventas que se creó en Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="5acf4-130">En Finance and Operations, los campos **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para realizar el seguimiento de la sincronización en las entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="5acf4-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="5acf4-131">Debe confirmar el **Pedido de ventas** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="5acf4-132">Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de Enviado o Facturado.</span><span class="sxs-lookup"><span data-stu-id="5acf4-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="5acf4-133">Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="5acf4-134">Solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="5acf4-135">Los impuestos relacionados con los gastos en **Cabecera del pedido de ventas** no se incluyen actualmente en la sincronización de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="5acf4-136">Esto se debe a que Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="5acf4-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="5acf4-137">Se incluyen los cargos relacionados con los impuestos a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="5acf4-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="5acf4-138">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="5acf4-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="5acf4-139">Los nuevos campos se agregan a la entidad **Pedido** y se muestran en la página:</span><span class="sxs-lookup"><span data-stu-id="5acf4-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="5acf4-140">**Se mantiene externamente**: establecido en **Sí** cuando el pedido proviene de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="5acf4-141">**Estado de procesamiento**: se usa para mostrar el estado de procesamiento del pedido en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="5acf4-142">Los valores son:</span><span class="sxs-lookup"><span data-stu-id="5acf4-142">Values are:</span></span>

    - <span data-ttu-id="5acf4-143">Activos</span><span class="sxs-lookup"><span data-stu-id="5acf4-143">Active</span></span>
    - <span data-ttu-id="5acf4-144">Confirmado</span><span class="sxs-lookup"><span data-stu-id="5acf4-144">Confirmed</span></span>
    - <span data-ttu-id="5acf4-145">Albarán</span><span class="sxs-lookup"><span data-stu-id="5acf4-145">Packing Slip</span></span>
    - <span data-ttu-id="5acf4-146">Facturado</span><span class="sxs-lookup"><span data-stu-id="5acf4-146">Invoiced</span></span>
    - <span data-ttu-id="5acf4-147">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="5acf4-147">Picked</span></span>
    - <span data-ttu-id="5acf4-148">Parcialmente seleccionado</span><span class="sxs-lookup"><span data-stu-id="5acf4-148">Partially Picked</span></span>
    - <span data-ttu-id="5acf4-149">Parcialmente empaquetado</span><span class="sxs-lookup"><span data-stu-id="5acf4-149">Partially Packed</span></span>
    - <span data-ttu-id="5acf4-150">Enviados</span><span class="sxs-lookup"><span data-stu-id="5acf4-150">Shipped</span></span>
    - <span data-ttu-id="5acf4-151">Parcialmente enviado</span><span class="sxs-lookup"><span data-stu-id="5acf4-151">Partially Shipped</span></span>
    - <span data-ttu-id="5acf4-152">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="5acf4-152">Partially Invoiced</span></span>
    - <span data-ttu-id="5acf4-153">Cancelado</span><span class="sxs-lookup"><span data-stu-id="5acf4-153">Cancelled</span></span>

<span data-ttu-id="5acf4-154">La configuración **Solo tiene productos mantenidos externamente** se usa en otros escenarios del pedido de ventas (sincronización de Sales a Finance and Operations) para realizar un seguimiento constante y así saber si el pedido de ventas está enteramente compuesto de **Productos mantenidos externamente**, en cuyo caso los productos se mantienen en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="5acf4-155">Gracias a ello, se puede garantizar que no intenta sincronizar las líneas de pedido de ventas con productos desconocidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="5acf4-156">Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan en los pedidos mantenidos de forma externa, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="5acf4-157">No se puede editar la página del pedido porque la información del pedido de ventas se sincronizará desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5acf4-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="5acf4-158">El **Estado del pedido de ventas** permanecerá activo para garantizar que los cambios de Finance and Operations se incluyen en el **Pedido de ventas** de Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="5acf4-159">Esta opción puede gestionarse si se configura el **código de estado [Status]** de forma predeterminada en **Activo** en el proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="5acf4-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="5acf4-160">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="5acf4-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="5acf4-161">Antes de sincronizar los pedidos de ventas, es importante actualizar los sistemas mediante la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="5acf4-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="5acf4-162">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="5acf4-162">Setup in Sales</span></span>

- <span data-ttu-id="5acf4-163">Garantice los permisos del equipo del cual forma parte el usuario (desde el **Conjunto de conexión** de Sales).</span><span class="sxs-lookup"><span data-stu-id="5acf4-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="5acf4-164">Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo.</span><span class="sxs-lookup"><span data-stu-id="5acf4-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="5acf4-165">Sin esta configuración, verá un error que indica que el equipo principal no está al ejecutar el proyecto desde el integrador de datos.</span><span class="sxs-lookup"><span data-stu-id="5acf4-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="5acf4-166">En **Configuración** > **Seguridad** > **Equipos**, seleccione el equipo adecuado, haga clic en **Gestionar roles** y seleccione un rol que tenga los permisos deseados (por ejemplo, administrador de sistema).</span><span class="sxs-lookup"><span data-stu-id="5acf4-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="5acf4-167">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Usar el sistema de cálculo del sistema de precios** está establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="5acf4-168">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Método de cálculo de descuentos** está establecida en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="5acf4-169">Configuración en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5acf4-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="5acf4-170">Establezca **Ventas y marketing** > **Tareas periódicas** > **Calcular las ventas totales** para que se ejecuten como un trabajo por lotes y establezca **Calcular los totales de los pedidos de ventas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="5acf4-171">Esto es importante, ya que solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="5acf4-172">La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="5acf4-172">The frequence of the batch job should be alligned with the frequence of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="5acf4-173">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="5acf4-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="5acf4-174">Tarea de SalesHeader</span><span class="sxs-lookup"><span data-stu-id="5acf4-174">SalesHeader task</span></span>

- <span data-ttu-id="5acf4-175">Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="5acf4-176">El valor de plantilla predeterminado de **Account_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="5acf4-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="5acf4-177">El valor de plantilla predeterminado de **InvoiceAccount_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="5acf4-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="5acf4-178">El valor de plantilla predeterminado de **Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="5acf4-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="5acf4-179">Asegúrese de que existe la asignación necesaria en el CDS **Origen** > **para InvoiceCountryRegionId a BillingAddress_Country** y para **DeliveryCountryRegionId a DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="5acf4-180">El valor de la plantilla es **ValueMap** con varios países asignados.</span><span class="sxs-lookup"><span data-stu-id="5acf4-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="5acf4-181">La **Lista de precios** es necesaria para poder crear pedidos en Sales.</span><span class="sxs-lookup"><span data-stu-id="5acf4-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="5acf4-182">Actualice el valor **ValueMap** en **CDS** > **Destino** para **pricelevelid.name [nombre de la lista de precios]** en la **lista de precios** que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="5acf4-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="5acf4-183">Puede usar la **lista de precios** predeterminada de una sola divisa o usar el valor **ValueMap** si tiene **listas de precios** en varias divisas.</span><span class="sxs-lookup"><span data-stu-id="5acf4-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="5acf4-184">El valor de la plantilla predeterminada de **pricelevelid.name [nombre de la lista de precios]** es CRM Service USA (ejemplo).</span><span class="sxs-lookup"><span data-stu-id="5acf4-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="5acf4-185">Tarea de SalesLine</span><span class="sxs-lookup"><span data-stu-id="5acf4-185">SalesLine task</span></span>

- <span data-ttu-id="5acf4-186">Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="5acf4-187">El valor de plantilla predeterminado de **SalesOrder_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="5acf4-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="5acf4-188">El valor de plantilla predeterminado de **Product_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="5acf4-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="5acf4-189">Asegúrese de que la asignación necesaria existe en **Origen** > **CDS** de **DeliveryCountryRegionId** a **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="5acf4-190">El valor de la plantilla es **ValueMap** con varios países asignados.</span><span class="sxs-lookup"><span data-stu-id="5acf4-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="5acf4-191">Asegúrese de que el valor necesario **ValueMap** de **SalesUnitSymbol** en Finance and Operations está en **Origen** > **Asignación de CDS**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="5acf4-192">El valor de la plantilla con **ValueMap** se define de **SalesUnitSymbol a Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="5acf4-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="5acf4-193">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="5acf4-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="5acf4-194">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="5acf4-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="5acf4-195">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="5acf4-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="5acf4-196">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="5acf4-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="5acf4-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5acf4-197">OrderHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="5acf4-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5acf4-200">OrderLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="5acf4-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5acf4-203">Related topics</span></span>

[<span data-ttu-id="5acf4-204">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="5acf4-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="5acf4-205">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5acf4-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="5acf4-206">Sincronizar contactos de Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5acf4-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="5acf4-207">Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5acf4-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="5acf4-208">Sincronizar encabezados y líneas de factura de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="5acf4-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


