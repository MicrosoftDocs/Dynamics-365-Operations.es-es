---
title: "Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="11f25-103">Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="11f25-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="11f25-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de pedidos de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="11f25-105">Plantilla y tareas</span><span class="sxs-lookup"><span data-stu-id="11f25-105">Template and tasks</span></span>

<span data-ttu-id="11f25-106">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del pedido de ventas de Finance and Operations a Sales:</span><span class="sxs-lookup"><span data-stu-id="11f25-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="11f25-107">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="11f25-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="11f25-108">Pedidos de ventas (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="11f25-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="11f25-109">**Nombres de las tareas en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="11f25-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="11f25-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="11f25-110">OrderHeader</span></span>
    - <span data-ttu-id="11f25-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="11f25-111">OrderLine</span></span>

<span data-ttu-id="11f25-112">Tareas de sincronización necesarias antes de sincronizar el encabezado y las líneas de factura en Sales:</span><span class="sxs-lookup"><span data-stu-id="11f25-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="11f25-113">Productos (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="11f25-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="11f25-114">Cuentas (de Sales a Fin and Ops), si es que se usan</span><span class="sxs-lookup"><span data-stu-id="11f25-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="11f25-115">Contactos a Clientes (de Sales a Fin and Ops) si es que se usan</span><span class="sxs-lookup"><span data-stu-id="11f25-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="11f25-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="11f25-116">Entity set</span></span>

| <span data-ttu-id="11f25-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11f25-117">Finance and Operations</span></span> |    <span data-ttu-id="11f25-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="11f25-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="11f25-119">Ventas</span><span class="sxs-lookup"><span data-stu-id="11f25-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="11f25-120">Encabezados de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="11f25-120">CDS sales order headers</span></span>| <span data-ttu-id="11f25-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="11f25-121">SalesOrder</span></span>     | <span data-ttu-id="11f25-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="11f25-122">SalesOrders</span></span> |
| <span data-ttu-id="11f25-123">Líneas de pedido de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="11f25-123">CDS sales order lines</span></span>  | <span data-ttu-id="11f25-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="11f25-124">SalesOrderLine</span></span> | <span data-ttu-id="11f25-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="11f25-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="11f25-126">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="11f25-126">Entity flow</span></span>

<span data-ttu-id="11f25-127">Los pedidos de ventas se crean en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="11f25-128">Los filtros de la plantilla le garantizan que solo se incluyan en la sincronización los pedidos de ventas más importantes:</span><span class="sxs-lookup"><span data-stu-id="11f25-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="11f25-129">Asimismo, se incluirán en la sincronización los clientes de pedidos y facturación del pedido de ventas que se creó en Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="11f25-130">En Finance and Operations, los campos **OrderingCustomerIsExternallyMaintained** y **InvoiceCustomerIsExternallyMaintained** se usan para realizar el seguimiento de la sincronización en las entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="11f25-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="11f25-131">Debe confirmar el **Pedido de ventas** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="11f25-132">Solo se sincronizan en Sales los pedidos de ventas confirmados o los pedidos de ventas con un estado más alto de procesamiento como, por ejemplo, aquellos que tengan un estado de Enviado o Facturado.</span><span class="sxs-lookup"><span data-stu-id="11f25-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="11f25-133">Después de crear o modificar un pedido de ventas, debe ejecutar el trabajo por lotes **Calcular las ventas totales** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="11f25-134">Solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="11f25-135">Los impuestos relacionados con los gastos en **Cabecera del pedido de ventas** no se incluyen actualmente en la sincronización de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="11f25-136">Esto se debe a que Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="11f25-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="11f25-137">Se incluyen los cargos relacionados con los impuestos a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="11f25-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="11f25-138">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="11f25-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="11f25-139">Los nuevos campos se agregan a la entidad **Pedido** y se muestran en la página:</span><span class="sxs-lookup"><span data-stu-id="11f25-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="11f25-140">**Se mantiene externamente**: establecido en **Sí** cuando el pedido proviene de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="11f25-141">**Estado de procesamiento**: se usa para mostrar el estado de procesamiento del pedido en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="11f25-142">Los valores son:</span><span class="sxs-lookup"><span data-stu-id="11f25-142">Values are:</span></span>

    - <span data-ttu-id="11f25-143">Activos</span><span class="sxs-lookup"><span data-stu-id="11f25-143">Active</span></span>
    - <span data-ttu-id="11f25-144">Confirmado</span><span class="sxs-lookup"><span data-stu-id="11f25-144">Confirmed</span></span>
    - <span data-ttu-id="11f25-145">Albarán</span><span class="sxs-lookup"><span data-stu-id="11f25-145">Packing Slip</span></span>
    - <span data-ttu-id="11f25-146">Facturado</span><span class="sxs-lookup"><span data-stu-id="11f25-146">Invoiced</span></span>
    - <span data-ttu-id="11f25-147">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="11f25-147">Picked</span></span>
    - <span data-ttu-id="11f25-148">Parcialmente seleccionado</span><span class="sxs-lookup"><span data-stu-id="11f25-148">Partially Picked</span></span>
    - <span data-ttu-id="11f25-149">Parcialmente empaquetado</span><span class="sxs-lookup"><span data-stu-id="11f25-149">Partially Packed</span></span>
    - <span data-ttu-id="11f25-150">Enviados</span><span class="sxs-lookup"><span data-stu-id="11f25-150">Shipped</span></span>
    - <span data-ttu-id="11f25-151">Parcialmente enviado</span><span class="sxs-lookup"><span data-stu-id="11f25-151">Partially Shipped</span></span>
    - <span data-ttu-id="11f25-152">Parcialmente facturado</span><span class="sxs-lookup"><span data-stu-id="11f25-152">Partially Invoiced</span></span>
    - <span data-ttu-id="11f25-153">Cancelado</span><span class="sxs-lookup"><span data-stu-id="11f25-153">Cancelled</span></span>

<span data-ttu-id="11f25-154">La configuración **Solo tiene productos mantenidos externamente** se usa en otros escenarios del pedido de ventas (sincronización de Sales a Finance and Operations) para realizar un seguimiento constante y así saber si el pedido de ventas está enteramente compuesto de **Productos mantenidos externamente**, en cuyo caso los productos se mantienen en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="11f25-155">Gracias a ello, se puede garantizar que no intenta sincronizar las líneas de pedido de ventas con productos desconocidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="11f25-156">Los botones **Crear factura**, **Cancelar pedido**, **Recalcular**, **Obtener productos** y **Buscar dirección** de la página del **Pedido de ventas** se ocultan en los pedidos mantenidos de forma externa, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="11f25-157">No se puede editar la página del pedido porque la información del pedido de ventas se sincronizará desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="11f25-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="11f25-158">El **Estado del pedido de ventas** permanecerá activo para garantizar que los cambios de Finance and Operations se incluyen en el **Pedido de ventas** de Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="11f25-159">Esta opción puede gestionarse si se configura el **código de estado [Status]** de forma predeterminada en **Activo** en el proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="11f25-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="11f25-160">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="11f25-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="11f25-161">Antes de sincronizar los pedidos de ventas, es importante actualizar los sistemas mediante la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="11f25-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="11f25-162">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="11f25-162">Setup in Sales</span></span>

- <span data-ttu-id="11f25-163">Garantice los permisos del equipo del cual forma parte el usuario (desde el **Conjunto de conexión** de Sales).</span><span class="sxs-lookup"><span data-stu-id="11f25-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="11f25-164">Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo.</span><span class="sxs-lookup"><span data-stu-id="11f25-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="11f25-165">Sin esta configuración, verá un error que indica que el equipo principal no está al ejecutar el proyecto desde el integrador de datos.</span><span class="sxs-lookup"><span data-stu-id="11f25-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="11f25-166">En **Configuración** > **Seguridad** > **Equipos**, seleccione el equipo adecuado, haga clic en **Gestionar roles** y seleccione un rol que tenga los permisos deseados (por ejemplo, administrador de sistema).</span><span class="sxs-lookup"><span data-stu-id="11f25-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="11f25-167">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Usar el sistema de cálculo del sistema de precios** está establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="11f25-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="11f25-168">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Método de cálculo de descuentos** está establecida en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="11f25-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="11f25-169">Configuración en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11f25-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="11f25-170">Establezca **Ventas y marketing** > **Tareas periódicas** > **Calcular las ventas totales** para que se ejecuten como un trabajo por lotes y establezca **Calcular los totales de los pedidos de ventas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="11f25-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="11f25-171">Esto es importante, ya que solo los pedidos de ventas que tengan las ventas totales calculadas se sincronizarán en CDS y Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="11f25-172">La frecuencia del trabajo por lotes debe coincidir con la frecuencia de la sincronización del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="11f25-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="11f25-173">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="11f25-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="11f25-174">Tarea de SalesHeader</span><span class="sxs-lookup"><span data-stu-id="11f25-174">SalesHeader task</span></span>

- <span data-ttu-id="11f25-175">Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="11f25-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="11f25-176">El valor de plantilla predeterminado de **Account_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="11f25-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="11f25-177">El valor de plantilla predeterminado de **InvoiceAccount_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="11f25-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="11f25-178">El valor de plantilla predeterminado de **Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="11f25-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="11f25-179">Asegúrese de que existe la asignación necesaria en el CDS **Origen** > **para InvoiceCountryRegionId a BillingAddress_Country** y para **DeliveryCountryRegionId a DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="11f25-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="11f25-180">El valor de la plantilla es **ValueMap** con varios países asignados.</span><span class="sxs-lookup"><span data-stu-id="11f25-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="11f25-181">La **Lista de precios** es necesaria para poder crear pedidos en Sales.</span><span class="sxs-lookup"><span data-stu-id="11f25-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="11f25-182">Actualice el valor **ValueMap** en **CDS** > **Destino** para **pricelevelid.name [nombre de la lista de precios]** en la **lista de precios** que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="11f25-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="11f25-183">Puede usar la **lista de precios** predeterminada de una sola divisa o usar el valor **ValueMap** si tiene **listas de precios** en varias divisas.</span><span class="sxs-lookup"><span data-stu-id="11f25-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="11f25-184">El valor de la plantilla predeterminada de **pricelevelid.name [nombre de la lista de precios]** es CRM Service USA (ejemplo).</span><span class="sxs-lookup"><span data-stu-id="11f25-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="11f25-185">Tarea de SalesLine</span><span class="sxs-lookup"><span data-stu-id="11f25-185">SalesLine task</span></span>

- <span data-ttu-id="11f25-186">Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="11f25-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="11f25-187">El valor de plantilla predeterminado de **SalesOrder_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="11f25-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="11f25-188">El valor de plantilla predeterminado de **Product_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="11f25-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="11f25-189">Asegúrese de que la asignación necesaria existe en **Origen** > **CDS** de **DeliveryCountryRegionId** a **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="11f25-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="11f25-190">El valor de la plantilla es **ValueMap** con varios países asignados.</span><span class="sxs-lookup"><span data-stu-id="11f25-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="11f25-191">Asegúrese de que el valor necesario **ValueMap** de **SalesUnitSymbol** en Finance and Operations está en **Origen** > **Asignación de CDS**.</span><span class="sxs-lookup"><span data-stu-id="11f25-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="11f25-192">El valor de la plantilla con **ValueMap** se define de **SalesUnitSymbol a Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="11f25-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="11f25-193">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="11f25-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="11f25-194">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="11f25-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="11f25-195">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="11f25-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="11f25-196">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="11f25-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="11f25-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="11f25-197">OrderHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="11f25-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="11f25-200">OrderLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="11f25-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="11f25-203">Related topics</span></span>

[<span data-ttu-id="11f25-204">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="11f25-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="11f25-205">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11f25-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="11f25-206">Sincronizar contactos de Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11f25-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="11f25-207">Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="11f25-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="11f25-208">Sincronizar encabezados y líneas de factura de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="11f25-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


