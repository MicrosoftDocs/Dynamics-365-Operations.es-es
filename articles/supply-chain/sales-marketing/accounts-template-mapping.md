---
title: Sincronice las cuentas de Sales con clientes de Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
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
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="76d38-103">Sincronice las cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76d38-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="76d38-104">Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="76d38-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="76d38-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones).</span><span class="sxs-lookup"><span data-stu-id="76d38-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="76d38-106">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="76d38-106">Template and task</span></span>

<span data-ttu-id="76d38-107">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar cuentas de Sales en Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="76d38-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="76d38-108">**Nombre de la plantilla:** Cuentas (Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="76d38-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="76d38-109">**Nombre de la tarea en el proyecto:** Cuentas - Cuenta - Clientes</span><span class="sxs-lookup"><span data-stu-id="76d38-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="76d38-110">Tareas de sincronización requeridas antes de la sincronización de la cuenta/cliente: Ninguna</span><span class="sxs-lookup"><span data-stu-id="76d38-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="76d38-111">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="76d38-111">Entity set</span></span>

| <span data-ttu-id="76d38-112">Ventas</span><span class="sxs-lookup"><span data-stu-id="76d38-112">Sales</span></span>    | <span data-ttu-id="76d38-113">CDS</span><span class="sxs-lookup"><span data-stu-id="76d38-113">CDS</span></span>     | <span data-ttu-id="76d38-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76d38-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="76d38-115">Cuentas</span><span class="sxs-lookup"><span data-stu-id="76d38-115">Accounts</span></span> | <span data-ttu-id="76d38-116">Cuenta</span><span class="sxs-lookup"><span data-stu-id="76d38-116">Account</span></span> | <span data-ttu-id="76d38-117">Empresas cliente</span><span class="sxs-lookup"><span data-stu-id="76d38-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="76d38-118">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="76d38-118">Entity flow</span></span>

<span data-ttu-id="76d38-119">Las cuentas se administran en Sales y se sincronizan en Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="76d38-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="76d38-120">La propiedad **Mantenida externamente** de estos clientes se establece en **Sí** para realizar un seguimiento de los clientes que proceden de Sales.</span><span class="sxs-lookup"><span data-stu-id="76d38-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="76d38-121">Durante la facturación, esta información se usa para filtrar las facturas que se sincronizan con Sales.</span><span class="sxs-lookup"><span data-stu-id="76d38-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="76d38-122">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="76d38-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="76d38-123">El campo **Número de cuenta** está disponible en la página **Cuenta** .</span><span class="sxs-lookup"><span data-stu-id="76d38-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="76d38-124">Se ha convertido en una clave natural y única para admitir la integración.</span><span class="sxs-lookup"><span data-stu-id="76d38-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="76d38-125">La característica de clave natural de la solución de la gestión de relaciones con el cliente (CRM) puede afectar a los clientes que utilicen ya el campo **Número de cuenta** , pero que no usen los valores **Número de cuenta** únicos por cuenta.</span><span class="sxs-lookup"><span data-stu-id="76d38-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="76d38-126">Actualmente, la solución de integración no admite este caso.</span><span class="sxs-lookup"><span data-stu-id="76d38-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="76d38-127">Cuando se crea una nueva cuenta, si todavía no existe un valor **Número de cuenta** , se genera automáticamente mediante una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="76d38-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="76d38-128">El valor consiste en **ACC**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="76d38-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="76d38-129">He aquí un ejemplo: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="76d38-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="76d38-130">Cuando se aplique la solución de integración para Sales, una secuencia de comandos de actualización establece el campo **Número de cuenta** de las cuentas existentes en Sales.</span><span class="sxs-lookup"><span data-stu-id="76d38-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="76d38-131">Si no hay valores para **Número de cuenta** , se usa la secuencia numérica que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="76d38-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="76d38-132">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="76d38-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="76d38-133">La asignación **CustomerGroupId** de **CDS &gt; Destino** debe actualizarse a un valor válido en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-133">**CustomerGroupId** mapping from **CDS &gt; Destination** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="76d38-134">Puede especificar un valor predeterminado, o se puede definir el valor mediante una asignación del valor.</span><span class="sxs-lookup"><span data-stu-id="76d38-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="76d38-135">El valor de plantilla predeterminado es **10**.</span><span class="sxs-lookup"><span data-stu-id="76d38-135">The default template value is **10**.</span></span>
- <span data-ttu-id="76d38-136">**Código de país/región de la dirección** se requiere en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="76d38-137">Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**.</span><span class="sxs-lookup"><span data-stu-id="76d38-137">To avoid synchronization errors, you can specify a default value in the mapping from **CDS &gt; Destination**.</span></span> <span data-ttu-id="76d38-138">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="76d38-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="76d38-139">El valor de plantilla predeterminado para **AddressCountryRegionISOCode** es **USA**.</span><span class="sxs-lookup"><span data-stu-id="76d38-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="76d38-140">El valor de plantilla predeterminado para **DeliveryAddressCountryRegionISOCode** es **USA**.</span><span class="sxs-lookup"><span data-stu-id="76d38-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="76d38-141">Si agrega las asignaciones siguientes desde **CDS &gt; Destino**, puede ayudar a reducir el número de actualizaciones manuales necesarias en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="76d38-142">Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.</span><span class="sxs-lookup"><span data-stu-id="76d38-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="76d38-143">**SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="76d38-144">Un sitio predeterminado se puede obtener del producto, o el cliente del encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="76d38-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="76d38-145">El valor de plantilla predeterminado para **SiteId** es **1**.</span><span class="sxs-lookup"><span data-stu-id="76d38-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="76d38-146">**WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="76d38-147">Un almacén predeterminado se puede obtener del producto, o el cliente del encabezado del pedido en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="76d38-148">El valor de plantilla predeterminado para **WarehouseId** es **13**.</span><span class="sxs-lookup"><span data-stu-id="76d38-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="76d38-149">**LanguageId** – Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="76d38-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="76d38-150">De forma predeterminada, se usa el idioma del encabezado del pedido del cliente.</span><span class="sxs-lookup"><span data-stu-id="76d38-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="76d38-151">El valor de plantilla predeterminado para **LanguageId** es **en-us**.</span><span class="sxs-lookup"><span data-stu-id="76d38-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="76d38-152">Actualice el identificador de la organización de CDS (**Organization_OrganizationId**) en la asignación **Origen &gt; CDS** .</span><span class="sxs-lookup"><span data-stu-id="76d38-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="76d38-153">El valor de plantilla predeterminado es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="76d38-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="76d38-154">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="76d38-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="76d38-155">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="76d38-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="76d38-156">Para asignar estos campos, debe configurar una asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="76d38-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="76d38-157">Las asignaciones de valores son específicas de los datos de las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="76d38-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="76d38-158">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="76d38-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Asignación de la plantilla en el integrador de datos](./media/accounts-template-mapping-data-integrator-1.png)

![Asignación de la plantilla para cuentas en el integrador de datos](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="76d38-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76d38-161">Related topics</span></span>

[<span data-ttu-id="76d38-162">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="76d38-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="76d38-163">Sincronice contactos de Sales con contactos o clientes en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76d38-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="76d38-164">Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="76d38-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="76d38-165">Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="76d38-165">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="76d38-166">Sincronizar encabezados y líneas de factura de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="76d38-166">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)




