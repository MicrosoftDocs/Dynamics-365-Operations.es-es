---
title: Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de factura de ventas directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 6cbc4d86ac41d90480428ec5439d1360c4d67137
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215985"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="3145e-103">Sincronizar encabezados y líneas de factura de ventas directamente desde Finance and Operations con Sales</span><span class="sxs-lookup"><span data-stu-id="3145e-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3145e-104">En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas de factura de ventas directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="3145e-105">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="3145e-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="3145e-106">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="3145e-107">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="3145e-108">La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="3145e-109">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="3145e-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3145e-110">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="3145e-110">Templates and tasks</span></span>

<span data-ttu-id="3145e-111">Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="3145e-111">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="3145e-112">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="3145e-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="3145e-113">La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas de la factura de ventas de Supply Chain Management a Sales:</span><span class="sxs-lookup"><span data-stu-id="3145e-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="3145e-114">**Nombre de la plantilla en la integración de datos:** Facturas de ventas (Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="3145e-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="3145e-115">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="3145e-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="3145e-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="3145e-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="3145e-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="3145e-117">SalesInvoiceLine</span></span>

<span data-ttu-id="3145e-118">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas de factura:</span><span class="sxs-lookup"><span data-stu-id="3145e-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="3145e-119">Productos (Supply Chain Management a Sales) - Directo</span><span class="sxs-lookup"><span data-stu-id="3145e-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="3145e-120">Cuentas (Sales a Supply Chain Management) - Directo (si se usa)</span><span class="sxs-lookup"><span data-stu-id="3145e-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="3145e-121">Contactos (Sales a Supply Chain Management) - Directo (si se usa)</span><span class="sxs-lookup"><span data-stu-id="3145e-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="3145e-122">Encabezado y líneas de pedido de ventas (Supply Chain Management a Sales) - Directo</span><span class="sxs-lookup"><span data-stu-id="3145e-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="3145e-123">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="3145e-123">Entity set</span></span>

| <span data-ttu-id="3145e-124">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="3145e-124">Supply Chain Management</span></span>                              | <span data-ttu-id="3145e-125">Ventas</span><span class="sxs-lookup"><span data-stu-id="3145e-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="3145e-126">Encabezados de factura de ventas de clientes mantenidos externamente</span><span class="sxs-lookup"><span data-stu-id="3145e-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="3145e-127">Facturas</span><span class="sxs-lookup"><span data-stu-id="3145e-127">Invoices</span></span>       |
| <span data-ttu-id="3145e-128">Líneas de factura de ventas de clientes mantenidas externamente</span><span class="sxs-lookup"><span data-stu-id="3145e-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="3145e-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="3145e-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="3145e-130">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="3145e-130">Entity flow</span></span>

<span data-ttu-id="3145e-131">Las facturas de ventas se crean en Supply Chain Management y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="3145e-132">Actualmente, los impuestos relacionados con los gastos en cabecera de las facturas de ventas no se incluyen en la sincronización de Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="3145e-133">Sales no admite información fiscal en el nivel de la cabecera.</span><span class="sxs-lookup"><span data-stu-id="3145e-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="3145e-134">Sin embargo, los impuestos relacionados con cargos en el nivel de línea se incluyen en la sincronización.</span><span class="sxs-lookup"><span data-stu-id="3145e-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3145e-135">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="3145e-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="3145e-136">El campo **Número de factura** se ha agregado a la entidad **Factura** y se muestra en la página.</span><span class="sxs-lookup"><span data-stu-id="3145e-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="3145e-137">El botón **Crear factura** de la página **Pedido de ventas** se oculta, ya que las facturas se crearán en Supply Chain Management y se sincronizarán en Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="3145e-138">No se puede editar la página **Factura** porque las facturas se sincronizarán desde Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3145e-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="3145e-139">El valor de **Estado del pedido de ventas** cambia automáticamente a **Facturado** si la factura relacionada de Supply Chain Management se ha sincronizado con Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="3145e-140">Además, el propietario del pedido de ventas desde el cual se creó la factura, se asigna como propietario de la factura.</span><span class="sxs-lookup"><span data-stu-id="3145e-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="3145e-141">Por tanto, el propietario del pedido de ventas puede ver la factura.</span><span class="sxs-lookup"><span data-stu-id="3145e-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3145e-142">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="3145e-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="3145e-143">Antes de sincronizar facturas de ventas, es importante actualizar la configuración siguiente en los sistemas.</span><span class="sxs-lookup"><span data-stu-id="3145e-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="3145e-144">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="3145e-144">Setup in Sales</span></span>

<span data-ttu-id="3145e-145">Vaya a **Configuración** > **Administración** > **Configuración del sistema** > **Sales**, y asegúrese de que se utilicen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3145e-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="3145e-146">La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3145e-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="3145e-147">El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="3145e-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="3145e-148">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="3145e-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="3145e-149">Tarea SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="3145e-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="3145e-150">Asegúrese de que la asignación requerida existe para **InvoiceCountryRegionId** como **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="3145e-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="3145e-151">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones.</span><span class="sxs-lookup"><span data-stu-id="3145e-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="3145e-152">Una lista de precios es necesaria para poder crear facturas en Sales.</span><span class="sxs-lookup"><span data-stu-id="3145e-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="3145e-153">Actualice la asignación de valores para **pricelevelid.name \[Nombre de la lista de precios\]** con la lista de precios que se usa en Sales según la divisa.</span><span class="sxs-lookup"><span data-stu-id="3145e-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="3145e-154">Puede usar la lista de precios predeterminada para una sola divisa.</span><span class="sxs-lookup"><span data-stu-id="3145e-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="3145e-155">Como alternativa, si tiene listas de precios en varias divisas, puede usar una asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="3145e-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="3145e-156">El valor de la plantilla para **pricelevelid.name \[Nombre de lista de precios\]** es una asignación de valores que se basa en la divisa con USD = CRM Service USA (ejemplo).</span><span class="sxs-lookup"><span data-stu-id="3145e-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="3145e-157">Tarea de SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="3145e-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="3145e-158">Asegúrese de que la asignación requerida existe para **Unidad de medida**.</span><span class="sxs-lookup"><span data-stu-id="3145e-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="3145e-159">Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3145e-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="3145e-160">Un valor de plantilla que tiene una asignación de valores se define para **SalesUnitSymbol** como **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="3145e-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3145e-161">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="3145e-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="3145e-162">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3145e-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="3145e-163">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="3145e-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="3145e-164">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="3145e-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="3145e-165">La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3145e-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="3145e-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="3145e-166">SalesInvoiceHeader</span></span>

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="3145e-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="3145e-168">SalesInvoiceLine</span></span>

![Asignación de la plantilla en la integración de datos](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="3145e-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3145e-170">Related topics</span></span>

[<span data-ttu-id="3145e-171">Cliente potencial a cliente</span><span class="sxs-lookup"><span data-stu-id="3145e-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="3145e-172">Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3145e-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="3145e-173">Sincronizar productos directamente de Supply Chain Management con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="3145e-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="3145e-174">Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3145e-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="3145e-175">Sincronización de pedidos de ventas entre Sales y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3145e-175">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
