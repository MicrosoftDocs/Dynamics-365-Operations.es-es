---
title: Sincronice los productos de Finance and Operations con productos en Sales
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="1166f-103">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="1166f-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="1166f-104">Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="1166f-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="1166f-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="1166f-106">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="1166f-106">Template and task</span></span>

<span data-ttu-id="1166f-107">Las siguientes plantillas y tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones) a Microsoft Dynamics 365 for Sales (ventas).</span><span class="sxs-lookup"><span data-stu-id="1166f-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="1166f-108">Nombre de la plantilla: Productos (Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="1166f-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="1166f-109">Nombre de la tarea en el proyecto: Productos</span><span class="sxs-lookup"><span data-stu-id="1166f-109">Name of task in project: Products</span></span>

<span data-ttu-id="1166f-110">Tareas de sincronización requeridas antes de la sincronización del producto: Ninguna</span><span class="sxs-lookup"><span data-stu-id="1166f-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="1166f-111">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="1166f-111">Entity set</span></span>

| <span data-ttu-id="1166f-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="1166f-112">**Finance and Operations**</span></span> | <span data-ttu-id="1166f-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="1166f-113">**CDS**</span></span> | <span data-ttu-id="1166f-114">**Ventas**</span><span class="sxs-lookup"><span data-stu-id="1166f-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="1166f-115">Productos liberados para ventas</span><span class="sxs-lookup"><span data-stu-id="1166f-115">Sellable released products</span></span> | <span data-ttu-id="1166f-116">Producto</span><span class="sxs-lookup"><span data-stu-id="1166f-116">Product</span></span> | <span data-ttu-id="1166f-117">Productos</span><span class="sxs-lookup"><span data-stu-id="1166f-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="1166f-118">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="1166f-118">Entity flow</span></span>

<span data-ttu-id="1166f-119">Los productos se administran en Finance and Operations y se sincronizan en Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="1166f-120">La entidad de datos **Productos liberados para ventas** en Finance and Operations exporta solo los productos que son para ventas, lo que significa que los productos tienen la información necesaria para usarse en un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1166f-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="1166f-121">Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="1166f-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="1166f-122">El **Número de producto** se usa como clave, lo que significa que las variantes del producto se sincronizan con CDS y Sales con **Identificadores de producto** individuales por **Variante del producto**.</span><span class="sxs-lookup"><span data-stu-id="1166f-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="1166f-123">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="1166f-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="1166f-124">En Sales, se agrega un campo nuevo en los productos **Mantenidos externamente** para indicar que un producto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="1166f-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="1166f-125">El valor se establece en **Sí** de forma predeterminada durante la importación a Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="1166f-126">**Mantenido externamente = Sí**: el producto se origina en Finance and Operatios y no se puede editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="1166f-127">**Mantenido externamente = No**: el producto se introduce directamente en Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="1166f-128">**Mantenido externamente = En blanco**: el producto existe en Sales antes de habilitar solución Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="1166f-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="1166f-129">La información **Mantenido externamente** se usa para asegurarse que solo se sincronizarán **Presupuestos** y **Pedidos de ventas** con **Productos mantenidos externamente** con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1166f-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="1166f-130">Los **Productos mantenidos externamente** se agregan automáticamente a la primera **Lista de precios** válida con la misma divisa.</span><span class="sxs-lookup"><span data-stu-id="1166f-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="1166f-131">Tenga en cuenta que la lista se organiza alfabéticamente por **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="1166f-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="1166f-132">El precio de venta del producto de Finance and Operations se usa como precio en la **Lista de precios**.</span><span class="sxs-lookup"><span data-stu-id="1166f-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="1166f-133">Esto significa que es necesario tener una **Lista de precios** en Sales para cada **Divisa de ventas del producto** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1166f-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="1166f-134">La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica, desde la que se exporta el producto.</span><span class="sxs-lookup"><span data-stu-id="1166f-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="1166f-135">La sincronización de productos no se realizará correctamente sin una **Lista de precios** con la divisa correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1166f-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="1166f-136">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="1166f-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="1166f-137">Antes de ejecutar la primera sincronización, debe rellenar la **tabla de producto único** para los productos existentes en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1166f-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="1166f-138">Los productos existentes no se sincronizarán hasta que este trabajo esté completado.</span><span class="sxs-lookup"><span data-stu-id="1166f-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="1166f-139">En Finance and Operations, utilice Buscar para buscar **Rellenar tabla de producto único**.</span><span class="sxs-lookup"><span data-stu-id="1166f-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="1166f-140">Haga clic en **Rellenar tabla de producto único** para ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1166f-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="1166f-141">Este trabajo solo necesita ejecutarse una vez.</span><span class="sxs-lookup"><span data-stu-id="1166f-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="1166f-142">Asegúrese de que el **ValueMap** necesario para vender la **Unidad de medida** (U. de M.) en Finance and Operations existe en la asignación **Origen -\> CDS SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="1166f-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="1166f-143">Asegúrese de que **Decimales admitidos** para la U. de M. coincide con sus requisitos en **CDS -\> Destino**.</span><span class="sxs-lookup"><span data-stu-id="1166f-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="1166f-144">Si necesita valores diferentes por U. de M., esto se puede hacer con **ValueMap** desde la unidad, por ejemplo, [Cada: 0] y [Libra: 2].</span><span class="sxs-lookup"><span data-stu-id="1166f-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="1166f-145">El valor de plantilla se establece de forma predeterminada como 0.</span><span class="sxs-lookup"><span data-stu-id="1166f-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="1166f-146">Actualice el **identificador de la organización de CDS Organization_OrganizationId** en **Origen -\> CDS** .</span><span class="sxs-lookup"><span data-stu-id="1166f-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="1166f-147">El valor de plantilla se establece de forma predeterminada como ORG001.</span><span class="sxs-lookup"><span data-stu-id="1166f-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="1166f-148">Actualice **ValueMap** para el **Grupo de unidad** (**defaultuomscheduleid.name**) en **CDS -\> Destino** para que coincida con los **Grupos de unidad** en Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="1166f-149">El valor de la plantilla se establece de forma predeterminada como **Unidad predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="1166f-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="1166f-150">Asegúrese de que todos los productos que venden U. de M. desde Finance and Operations existen en Sales con el valor **Listas de selección de CDS** .</span><span class="sxs-lookup"><span data-stu-id="1166f-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="1166f-151">Asegúrese de que las **Listas de precios** existen en Sales para cada divisa de ventas del producto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1166f-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="1166f-152">Los productos se pueden crear en Sales con el estado **Borrador** o **Activo**.</span><span class="sxs-lookup"><span data-stu-id="1166f-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="1166f-153">Esto se controla en **Configuración del sistema** en **Ventas** en Sales.</span><span class="sxs-lookup"><span data-stu-id="1166f-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="1166f-154">Los productos creados con estado de borrador tiene que activarse antes de que se puedan añadir a **Presupuesto** o **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1166f-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="1166f-155">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="1166f-155">Template mapping in data integrator</span></span>

<span data-ttu-id="1166f-156">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="1166f-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![asignación de la plantilla en el integrador de datos](./media/products-template-mapping-data-integrator-1.png)

![asignación de la plantilla para productos en el integrador de datos](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="1166f-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1166f-159">Related topics</span></span>

[<span data-ttu-id="1166f-160">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1166f-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="1166f-161">Sincronice contactos de Sales con contactos o clientes en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1166f-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="1166f-162">Sincronice los encabezados y las líneas del presupuesto de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1166f-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


