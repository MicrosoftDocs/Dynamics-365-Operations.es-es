---
title: "Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales"
description: "Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales."
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 0d409b3b7f19ca31d9c720bca191f1ddba81caa3
ms.openlocfilehash: 347509a9556f15e7d880508e36516f04bc6964b7
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2018

---

# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="e8160-103">Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="e8160-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e8160-104">Este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de facturación de ventas directamente de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, con Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="e8160-105">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="e8160-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="e8160-106">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="e8160-107">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="e8160-108">La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="e8160-109">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="e8160-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="e8160-110">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="e8160-110">Templates and tasks</span></span>

<span data-ttu-id="e8160-111">Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="e8160-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="e8160-112">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="e8160-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="e8160-113">La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas de facturación de ventas de Finance and Operations a Sales:</span><span class="sxs-lookup"><span data-stu-id="e8160-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="e8160-114">**Nombre de la plantilla en la integración de datos:** Facturas de ventas (Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="e8160-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="e8160-115">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="e8160-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="e8160-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="e8160-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="e8160-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="e8160-117">SalesInvoiceLine</span></span>

<span data-ttu-id="e8160-118">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:</span><span class="sxs-lookup"><span data-stu-id="e8160-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="e8160-119">Productos (de Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="e8160-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="e8160-120">Cuentas (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="e8160-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="e8160-121">Contactos (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="e8160-121">Contacts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="e8160-122">Cabecera y líneas del pedido de ventas (de Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="e8160-122">Sales order header and lines (Fin and Ops to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="e8160-123">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="e8160-123">Entity set</span></span>

| <span data-ttu-id="e8160-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e8160-124">Finance and Operations</span></span>                               | <span data-ttu-id="e8160-125">Ventas</span><span class="sxs-lookup"><span data-stu-id="e8160-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="e8160-126">Encabezados de factura de ventas de clientes mantenidos externamente</span><span class="sxs-lookup"><span data-stu-id="e8160-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="e8160-127">Facturas</span><span class="sxs-lookup"><span data-stu-id="e8160-127">Invoices</span></span>       |
| <span data-ttu-id="e8160-128">Líneas de factura de ventas de clientes mantenidas externamente</span><span class="sxs-lookup"><span data-stu-id="e8160-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="e8160-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="e8160-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="e8160-130">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="e8160-130">Entity flow</span></span>

<span data-ttu-id="e8160-131">Las facturas de ventas se crean en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-131">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="e8160-132">Actualmente, los impuestos relacionados con los gastos en cabecera de las facturas de ventas no se incluyen en la sincronización de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="e8160-133">Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="e8160-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="e8160-134">Sin embargo, los impuestos relacionados con cargos en el nivel de línea se incluyen en la sincronización.</span><span class="sxs-lookup"><span data-stu-id="e8160-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e8160-135">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="e8160-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="e8160-136">El campo **Número de factura** se ha agregado a la entidad **Factura** y se muestra en la página.</span><span class="sxs-lookup"><span data-stu-id="e8160-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="e8160-137">El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Finance and Operations y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="e8160-138">No se puede editar la página **Factura** porque las facturas se sincronizarán desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e8160-138">The **Invoice** page can't be edited, because invoices will be synchronized from Finance and Operations.</span></span>
- <span data-ttu-id="e8160-139">El valor de **Estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Finance and Operations se ha sincronizado con Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Finance and Operations has been synchronized to Sales.</span></span> <span data-ttu-id="e8160-140">Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura.</span><span class="sxs-lookup"><span data-stu-id="e8160-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="e8160-141">Por tanto, el propietario del pedido de ventas puede ver la factura.</span><span class="sxs-lookup"><span data-stu-id="e8160-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="e8160-142">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="e8160-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="e8160-143">Antes de sincronizar facturas de ventas, es importante actualizar la configuración siguiente en los sistemas.</span><span class="sxs-lookup"><span data-stu-id="e8160-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="e8160-144">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="e8160-144">Setup in Sales</span></span>

<span data-ttu-id="e8160-145">Vaya a **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, y asegúrese de que se utilicen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8160-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="e8160-146">La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e8160-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="e8160-147">El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="e8160-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="e8160-148">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="e8160-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="e8160-149">Tarea SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="e8160-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="e8160-150">Asegúrese de que la asignación requerida existe para **InvoiceCountryRegionId** como **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="e8160-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="e8160-151">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.</span><span class="sxs-lookup"><span data-stu-id="e8160-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="e8160-152">Una lista de precios es necesaria para poder crear facturas en Sales.</span><span class="sxs-lookup"><span data-stu-id="e8160-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="e8160-153">Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="e8160-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="e8160-154">Puede usar la lista de precios predeterminada para una sola divisa.</span><span class="sxs-lookup"><span data-stu-id="e8160-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="e8160-155">Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="e8160-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="e8160-156">El valor de la plantilla para **pricelevelid.name \[Nombre de lista de precios\]** es una asignación de valores que se basa en la divisa con USD = CRM Service USA (ejemplo).</span><span class="sxs-lookup"><span data-stu-id="e8160-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="e8160-157">Tarea de SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="e8160-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="e8160-158">Asegúrese de que la asignación requerida existe para **Unidad de medida**.</span><span class="sxs-lookup"><span data-stu-id="e8160-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="e8160-159">Asegúrese de que la asignación de valores requerida para **SalesUnitSymbol** existe en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e8160-159">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="e8160-160">Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="e8160-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e8160-161">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="e8160-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="e8160-162">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="e8160-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="e8160-163">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="e8160-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="e8160-164">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="e8160-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="e8160-165">La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e8160-165">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="e8160-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="e8160-166">SalesInvoiceHeader</span></span>

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="e8160-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="e8160-168">SalesInvoiceLine</span></span>

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="e8160-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e8160-170">Related topics</span></span>

[<span data-ttu-id="e8160-171">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="e8160-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="e8160-172">Sincronizar directamente cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e8160-172">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="e8160-173">Sincronizar productos directamente desde Finance and Operations con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="e8160-173">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="e8160-174">Sincronizar contactos directamente desde Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e8160-174">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="e8160-175">Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="e8160-175">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)







