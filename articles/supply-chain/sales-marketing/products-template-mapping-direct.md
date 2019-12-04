---
title: Sincronizar productos directamente de Supply Chain Management con productos de Sales
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1a96fda4e7f7b6407c51ee4056088d05027462cf
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813256"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="ca9d6-103">Sincronizar productos directamente de Supply Chain Management con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="ca9d6-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ca9d6-104">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="ca9d6-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="ca9d6-105">En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar productos de directamente de Dynamics 365 Supply Chain Management a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="ca9d6-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="ca9d6-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="ca9d6-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="ca9d6-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="ca9d6-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="ca9d6-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="ca9d6-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ca9d6-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="ca9d6-111">Templates and tasks</span></span>

<span data-ttu-id="ca9d6-112">Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="ca9d6-112">To access the available templates, open [Power Apps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="ca9d6-113">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="ca9d6-114">La plantilla y las tareas subyacente siguientes se usan para sincronizar productos de Sales en Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="ca9d6-115">**Nombre de la plantilla en la integración de datos:** Productos (Supply Chain Management a Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="ca9d6-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="ca9d6-116">**Nombre de la tarea en el proyecto de integración de datos**: Productos</span><span class="sxs-lookup"><span data-stu-id="ca9d6-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="ca9d6-117">No se requieren tareas de sincronización para que pueda producirse la sincronización de productos.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="ca9d6-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="ca9d6-118">Entity set</span></span>

| <span data-ttu-id="ca9d6-119">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="ca9d6-119">Supply Chain Management</span></span>    | <span data-ttu-id="ca9d6-120">Ventas</span><span class="sxs-lookup"><span data-stu-id="ca9d6-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="ca9d6-121">Productos liberados para ventas</span><span class="sxs-lookup"><span data-stu-id="ca9d6-121">Sellable released products</span></span> | <span data-ttu-id="ca9d6-122">Productos</span><span class="sxs-lookup"><span data-stu-id="ca9d6-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="ca9d6-123">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="ca9d6-123">Entity flow</span></span>

<span data-ttu-id="ca9d6-124">Los productos se administran en Supply Chain Management y se sincronizan con Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="ca9d6-125">La entidad de datos **Productos liberados para ventas** en Supply Chain Management exporta solo los productos que son *para ventas*.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="ca9d6-126">Los productos para ventas son productos que tienen la información que requieren para usarse en un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="ca9d6-127">Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="ca9d6-128">El número de producto se usa como clave.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-128">The product number is used as a key.</span></span> <span data-ttu-id="ca9d6-129">Por tanto, cuando las variantes del producto se sincronizan con Sales, cada variante del producto tiene un Id. de producto individual.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ca9d6-130">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="ca9d6-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ca9d6-131">En Sales, un nuevo campo **Mantenidos externamente** se ha agregado en productos para indicar que un producto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="ca9d6-132">De forma predeterminada, el valor se establece en **Sí** de forma predeterminada durante la importación a Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="ca9d6-133">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ca9d6-133">The following values are available:</span></span>

- <span data-ttu-id="ca9d6-134">**Sí**: el producto se ha originado en Supply Chain Management y no se podrá editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="ca9d6-135">**No** - El producto se ha especificado directamente en Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="ca9d6-136">**(En blanco)** - El producto existía en Sales antes de que se habilitara la solución Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="ca9d6-137">El campo **Mantenido externamente** ayuda a garantizar que solo se sincronizarán con Supply Chain Management presupuestos y pedidos de ventas con productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="ca9d6-138">Los Productos mantenidos externamente se agregan automáticamente a la primera lista de precios válida con la misma divisa.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="ca9d6-139">Las listas de precios se organizan alfabéticamente por nombre.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="ca9d6-140">El precio de venta del producto de Supply Chain Management se usa como precio en la lista de precios.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="ca9d6-141">Por tanto, debe haber una lista de precios existen en Sales para todas las divisas de ventas del producto en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="ca9d6-142">La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica desde la que se exporta el producto.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="ca9d6-143">La sincronización de productos no se realizará correctamente a menos que haya una lista de precios que tenga una divisa correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="ca9d6-144">Puede controlar la lista de precios utilizada con la integración mediante la asignación de pricelevelid.name [Lista de precios predeterminada (Nombre)] en el proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="ca9d6-145">La entrada tiene que estar en letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="ca9d6-146">Por ejemplo, el valor predeterminado para una lista de precios en las Ventas denominada ‘Estándar’ sería: Campo de destino: pricelevelid.name [Lista de precios predeterminada (Nombre)] y tipo de asignación: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="ca9d6-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ca9d6-147">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="ca9d6-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="ca9d6-148">Antes de ejecutar la sincronización por primera vez, debe rellenar la tabla de producto único para los productos existentes en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="ca9d6-149">Los productos existentes no se sincronizarán hasta que este trabajo esté completado.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="ca9d6-150">En Supply Chain Management, utilice Buscar para buscar **Rellenar tabla de producto único**.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="ca9d6-151">Seleccione **Rellenar tabla de producto único** para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="ca9d6-152">Este trabajo se debe ejecutar una vez.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-152">This job must be run only one time.</span></span>

- <span data-ttu-id="ca9d6-153">Asegúrese de que la asignación de valores requeridas para la unidad de medida (U. de M.) vendedora entre Supply Chain Management y Sales existe en la asignación de **SalesUnitSymbol** a **DefaultUnit (Nombre)**.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="ca9d6-154">Actualice la asignación de valores para el **Grupo de unidad** (**defaultuomscheduleid.name**) para que coincida con los **Grupos de unidad** en Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="ca9d6-155">El valor de la plantilla predeterminada es **Unidad predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="ca9d6-156">Asegúrese de que las U. de M. de venta para todos los productos de Supply Chain Management existen en Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="ca9d6-157">Asegúrese de que las listas de precios existen en Sales para todas las divisas de ventas del producto en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="ca9d6-158">Cuando los productos se crean en Sales, pueden tener un estado de **Borrador** o **Activo**.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="ca9d6-159">El comportamiento se controla en **Configuración** > **Administración** > **Configuración del sistema** > **Sales** en Sales.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="ca9d6-160">Los productos que tienen estado **Borrador** cuando se crean deben activarse antes de que puedan agregarse a presupuestos o pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ca9d6-161">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="ca9d6-161">Template mapping in Data integration</span></span>

<span data-ttu-id="ca9d6-162">La siguiente ilustración muestra un ejemplo de una asignación de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="ca9d6-163">La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca9d6-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Asignación de la plantilla en el integrador de datos](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="ca9d6-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ca9d6-165">Related topics</span></span>

[<span data-ttu-id="ca9d6-166">Cliente potencial a cliente</span><span class="sxs-lookup"><span data-stu-id="ca9d6-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="ca9d6-167">Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ca9d6-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="ca9d6-168">Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ca9d6-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="ca9d6-169">Sincronización de pedidos de ventas entre Sales y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ca9d6-169">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="ca9d6-170">Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales</span><span class="sxs-lookup"><span data-stu-id="ca9d6-170">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



