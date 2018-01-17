---
title: Sincronizar directamente productos de Finance and Operations con productos de Sales
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, a Microsoft Dynamics 365 for Sales.
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
ms.openlocfilehash: c34da408ea364d54471c60f45c3322cce0c263fc
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="84cf3-103">Sincronizar directamente productos de Finance and Operations con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="84cf3-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="84cf3-104">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="84cf3-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="84cf3-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, a Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="84cf3-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="84cf3-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="84cf3-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="84cf3-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="84cf3-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="84cf3-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="84cf3-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="84cf3-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="84cf3-111">Templates and tasks</span></span>

<span data-ttu-id="84cf3-112">Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="84cf3-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="84cf3-113">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="84cf3-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="84cf3-114">La plantilla y las tareas subyacentes siguientes se usan para sincronizar productos de Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="84cf3-115">**Nombre de la plantilla en la integración de datos:** Productos (Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="84cf3-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="84cf3-116">**Nombre de la tarea en el proyecto de integración de datos**: Productos</span><span class="sxs-lookup"><span data-stu-id="84cf3-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="84cf3-117">No se requieren tareas de sincronización para que pueda producirse la sincronización de productos.</span><span class="sxs-lookup"><span data-stu-id="84cf3-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="84cf3-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="84cf3-118">Entity set</span></span>

| <span data-ttu-id="84cf3-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="84cf3-119">Finance and Operations</span></span>     | <span data-ttu-id="84cf3-120">Ventas</span><span class="sxs-lookup"><span data-stu-id="84cf3-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="84cf3-121">Productos liberados para ventas</span><span class="sxs-lookup"><span data-stu-id="84cf3-121">Sellable released products</span></span> | <span data-ttu-id="84cf3-122">Productos</span><span class="sxs-lookup"><span data-stu-id="84cf3-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="84cf3-123">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="84cf3-123">Entity flow</span></span>

<span data-ttu-id="84cf3-124">Los productos se administran en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="84cf3-125">La entidad de datos **Productos liberados para ventas** en Finance and Operations exporta solo los productos que son *para ventas*.</span><span class="sxs-lookup"><span data-stu-id="84cf3-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="84cf3-126">Los productos para ventas son productos que tienen la información que requieren para usarse en un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="84cf3-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="84cf3-127">Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="84cf3-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="84cf3-128">El número de producto se usa como clave.</span><span class="sxs-lookup"><span data-stu-id="84cf3-128">The product number is used as a key.</span></span> <span data-ttu-id="84cf3-129">Por tanto, cuando las variantes del producto se sincronizan con Sales, cada variante del producto tiene un Id. de producto individual.</span><span class="sxs-lookup"><span data-stu-id="84cf3-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="84cf3-130">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="84cf3-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="84cf3-131">En Sales, un nuevo campo **Mantenidos externamente** se ha agregado en productos para indicar que un producto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="84cf3-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="84cf3-132">De forma predeterminada, el valor se establece en **Sí** de forma predeterminada durante la importación a Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="84cf3-133">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="84cf3-133">The following values are available:</span></span>

- <span data-ttu-id="84cf3-134">**Sí** - El producto originado de Finance and Operations y no se podrá editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="84cf3-135">**No** - El producto se ha especificado directamente en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="84cf3-136">**(En blanco)** - El producto existía en Sales antes de que se habilitara la solución Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="84cf3-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="84cf3-137">La información **Mantenido externamente** ayuda a asegurarse que solo se sincronizarán con Finance and Operations presupuestos y pedidos de ventas con productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="84cf3-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="84cf3-138">Los Productos mantenidos externamente se agregan automáticamente a la primera lista de precios válida con la misma divisa.</span><span class="sxs-lookup"><span data-stu-id="84cf3-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="84cf3-139">Las listas de precios se organizan alfabéticamente por nombre.</span><span class="sxs-lookup"><span data-stu-id="84cf3-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="84cf3-140">El precio de venta del producto de Finance and Operations se usa como precio en la lista de precios.</span><span class="sxs-lookup"><span data-stu-id="84cf3-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="84cf3-141">Por tanto, debe haber una lista de precios existen en Sales para todas las divisas de ventas del producto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="84cf3-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="84cf3-142">La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica desde la que se exporta el producto.</span><span class="sxs-lookup"><span data-stu-id="84cf3-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> <span data-ttu-id="84cf3-143">La sincronización de productos no se realizará correctamente a menos que haya una lista de precios que tenga una divisa correspondiente.</span><span class="sxs-lookup"><span data-stu-id="84cf3-143">Product synchronization won't succeed unless there is a price list that has a matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="84cf3-144">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="84cf3-144">Preconditions and mapping setup</span></span>

- <span data-ttu-id="84cf3-145">Antes de ejecutar la sincronización por primera vez, debe rellenar la tabla de producto único para los productos existentes en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="84cf3-145">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="84cf3-146">Los productos existentes no se sincronizarán hasta que este trabajo esté completado.</span><span class="sxs-lookup"><span data-stu-id="84cf3-146">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="84cf3-147">En Finance and Operations, utilice Buscar para buscar **Rellenar tabla de producto único**.</span><span class="sxs-lookup"><span data-stu-id="84cf3-147">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="84cf3-148">Seleccione **Rellenar tabla de producto único** para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="84cf3-148">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="84cf3-149">Este trabajo se debe ejecutar una vez.</span><span class="sxs-lookup"><span data-stu-id="84cf3-149">This job must be run only one time.</span></span>

- <span data-ttu-id="84cf3-150">Asegúrese de que la asignación de valores requeridas para la unidad de medida (U. de M.) vendedora entre Finance and Operations y Sales existe en la asignación de **SalesUnitSymbol** a **DefaultUnit (Nombre)**.</span><span class="sxs-lookup"><span data-stu-id="84cf3-150">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="84cf3-151">Actualice la asignación de valores para el **Grupo de unidad** (**defaultuomscheduleid.name**) para que coincida con los **Grupos de unidad** en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-151">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="84cf3-152">El valor de la plantilla predeterminada es **Unidad predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="84cf3-152">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="84cf3-153">Asegúrese de que las U. de M. de venta para todos los productos de Finance and Operations existen en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-153">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="84cf3-154">Asegúrese de que las listas de precios existen en Sales para todas las divisas de ventas del producto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="84cf3-154">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="84cf3-155">Cuando los productos se crean en Sales, pueden tener un estado de **Borrador** o **Activo**.</span><span class="sxs-lookup"><span data-stu-id="84cf3-155">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="84cf3-156">El comportamiento se controla en **Configuración** > **Administración** > **Configuración del sistema** > **Sales** en Sales.</span><span class="sxs-lookup"><span data-stu-id="84cf3-156">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="84cf3-157">Los productos que tienen estado **Borrador** cuando se crean deben activarse antes de que puedan agregarse a presupuestos o pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="84cf3-157">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="84cf3-158">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="84cf3-158">Template mapping in Data integration</span></span>

<span data-ttu-id="84cf3-159">La siguiente ilustración muestra un ejemplo de una asignación de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="84cf3-159">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="84cf3-160">La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="84cf3-160">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Asignación de la plantilla en el integrador de datos](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="84cf3-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="84cf3-162">Related topics</span></span>

[<span data-ttu-id="84cf3-163">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="84cf3-163">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="84cf3-164">Sincronizar directamente cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="84cf3-164">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="84cf3-165">Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="84cf3-165">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="84cf3-166">Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="84cf3-166">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="84cf3-167">Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="84cf3-167">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




