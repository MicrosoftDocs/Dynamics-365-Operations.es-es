---
title: "Sincronizar encabezados y líneas de factura de Finance and Operations en Sales"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="a211e-103">Sincronizar encabezados y líneas de factura de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="a211e-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a211e-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="a211e-105">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="a211e-105">Templates and tasks</span></span>

<span data-ttu-id="a211e-106">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas de facturación de ventas de Finance and Operations a Sales:</span><span class="sxs-lookup"><span data-stu-id="a211e-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="a211e-107">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="a211e-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="a211e-108">Facturación de ventas (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="a211e-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="a211e-109">**Nombres de las tareas en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="a211e-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="a211e-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="a211e-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="a211e-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="a211e-111">SalesInvoiceLine</span></span>

<span data-ttu-id="a211e-112">Tareas de sincronización necesarias antes de sincronizar el encabezado y las líneas de factura en Sales:</span><span class="sxs-lookup"><span data-stu-id="a211e-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="a211e-113">Productos (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="a211e-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="a211e-114">Cuentas (de Sales a Fin and Ops), si es que se usan</span><span class="sxs-lookup"><span data-stu-id="a211e-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="a211e-115">Contactos (de Sales a Fin and Ops), si es que se usan</span><span class="sxs-lookup"><span data-stu-id="a211e-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="a211e-116">Cabecera y líneas del pedido de ventas (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="a211e-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="a211e-117">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="a211e-117">Entity set</span></span>

| <span data-ttu-id="a211e-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a211e-118">Finance and Operations</span></span>                               | <span data-ttu-id="a211e-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="a211e-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="a211e-120">Ventas</span><span class="sxs-lookup"><span data-stu-id="a211e-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="a211e-121">Encabezados de factura de ventas de clientes mantenidos externamente</span><span class="sxs-lookup"><span data-stu-id="a211e-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="a211e-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="a211e-122">SalesInvoice</span></span>     | <span data-ttu-id="a211e-123">Facturas</span><span class="sxs-lookup"><span data-stu-id="a211e-123">Invoices</span></span>       |
| <span data-ttu-id="a211e-124">Líneas de factura de ventas de clientes mantenidas externamente</span><span class="sxs-lookup"><span data-stu-id="a211e-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="a211e-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="a211e-125">SalesInvoiceLine</span></span> | <span data-ttu-id="a211e-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="a211e-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="a211e-127">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="a211e-127">Entity flow</span></span>

<span data-ttu-id="a211e-128">Las facturas de ventas se crean en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="a211e-129">Los impuestos relacionados con los gastos en **Cabecera de las facturas de ventas** no se incluyen actualmente en la sincronización de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="a211e-130">Esto se debe a que Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="a211e-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="a211e-131">Se incluyen los cargos relacionados con los impuestos a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="a211e-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="a211e-132">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="a211e-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="a211e-133">Se agrega el **Campo de número de factura** a la entidad **Factura** y se muestra en la página.</span><span class="sxs-lookup"><span data-stu-id="a211e-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="a211e-134">El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="a211e-135">No se puede editar la página **Factura** porque las facturas se sincronizarán desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a211e-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="a211e-136">El **estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Finance and Operations se ha sincronizado con Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="a211e-137">Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura.</span><span class="sxs-lookup"><span data-stu-id="a211e-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="a211e-138">Esto ofrece al propietario del pedido de ventas la capacidad de ver la factura.</span><span class="sxs-lookup"><span data-stu-id="a211e-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="a211e-139">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="a211e-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="a211e-140">Antes de sincronizar las facturas de ventas, es importante actualizar los sistemas mediante la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="a211e-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="a211e-141">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="a211e-141">Setup in Sales</span></span>

- <span data-ttu-id="a211e-142">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Usar el sistema de cálculo del sistema de precios** está establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a211e-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="a211e-143">En **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, asegúrese de que la opción **Método de cálculo de descuentos** está establecida en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="a211e-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="a211e-144">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="a211e-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="a211e-145">Tarea SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="a211e-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="a211e-146">Actualice la asignación del **id. de la organización de CDS** en **Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="a211e-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="a211e-147">El valor de plantilla predeterminado de **SalesOrder_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="a211e-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="a211e-148">El valor de plantilla predeterminado de **Account_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="a211e-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="a211e-149">El valor de plantilla predeterminado de **Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="a211e-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="a211e-150">Asegúrese de que la asignación necesaria existe en **Origen** > **CDS de InvoiceCountryRegionId** a **BillingAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="a211e-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="a211e-151">El valor de la plantilla es **ValueMap** con varios países asignados.</span><span class="sxs-lookup"><span data-stu-id="a211e-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="a211e-152">La **Lista de precios** es necesaria para poder crear facturas en Sales.</span><span class="sxs-lookup"><span data-stu-id="a211e-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="a211e-153">Actualice el valor **ValueMap** en **CDS** > **Destino para pricelevelid.name [nombre de la lista de precios]** en la **lista de precios** que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="a211e-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="a211e-154">Puede usar la **lista de precios** predeterminada de una sola divisa o usar el valor **ValueMap** si tiene **listas de precios** en varias divisas.</span><span class="sxs-lookup"><span data-stu-id="a211e-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="a211e-155">El valor de la plantilla de **pricelevelid.name [nombre de la lista de precios]** es **ValueMap** basado en la **Divisa**.</span><span class="sxs-lookup"><span data-stu-id="a211e-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="a211e-156">usd: CRM Service USA (ejemplo).</span><span class="sxs-lookup"><span data-stu-id="a211e-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="a211e-157">Tarea de SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="a211e-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="a211e-158">Asegúrese de que la asignación necesaria está en **Origen** > **CDS de la unidad de medida**.</span><span class="sxs-lookup"><span data-stu-id="a211e-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="a211e-159">Asegúrese de que el valor necesario **ValueMap** de **SalesUnitSymbol** en Finance and Operations está en **Origen** > **Asignación de CDS**.</span><span class="sxs-lookup"><span data-stu-id="a211e-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="a211e-160">El valor de la plantilla con **ValueMap** se define de **SalesUnitSymbol a Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="a211e-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="a211e-161">Actualice la asignación del **id. de la organización de CDS en Origen** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="a211e-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="a211e-162">El valor de plantilla predeterminado de **SalesInvoicer_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="a211e-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="a211e-163">El valor de plantilla predeterminado de **Product_Organization_OrganizationId** es ORG001.</span><span class="sxs-lookup"><span data-stu-id="a211e-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="a211e-164">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="a211e-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="a211e-165">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío** y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="a211e-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="a211e-166">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="a211e-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="a211e-167">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="a211e-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="a211e-172">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a211e-172">Related topics</span></span>

[<span data-ttu-id="a211e-173">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="a211e-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="a211e-174">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a211e-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="a211e-175">Sincronizar contactos de Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a211e-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="a211e-176">Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a211e-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="a211e-177">Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="a211e-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


