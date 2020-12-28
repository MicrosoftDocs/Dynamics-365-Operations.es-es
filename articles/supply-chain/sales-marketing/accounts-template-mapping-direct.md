---
title: Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management
description: En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar cuentas de Dynamics 365 Sales en Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
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
ms.openlocfilehash: 8aa03f94e0fb89a6d34ce014dbb6004a1a666327
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529219"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="aeacd-103">Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="aeacd-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="aeacd-104">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="aeacd-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="aeacd-105">En este tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar cuentas directamente de Dynamics 365 Sales en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="aeacd-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="aeacd-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="aeacd-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="aeacd-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="aeacd-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="aeacd-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="aeacd-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="aeacd-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="aeacd-111">Templates and tasks</span></span>

<span data-ttu-id="aeacd-112">Para obtener acceso a las plantillas disponibles, abra [Centro de administración de Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="aeacd-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="aeacd-113">Seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="aeacd-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="aeacd-114">La plantilla y la tarea subyacente siguientes se usan para sincronizar cuentas de Sales en Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="aeacd-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="aeacd-115">**Nombre de la plantilla en la integración de datos:** Cuentas (de Sales a Fin and Ops) - Directos</span><span class="sxs-lookup"><span data-stu-id="aeacd-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="aeacd-116">**Nombre de la tarea en el proyecto:** Cuentas - Clientes</span><span class="sxs-lookup"><span data-stu-id="aeacd-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="aeacd-117">No se requieren tareas de sincronización para que pueda producirse la sincronización de cuentas/clientes.</span><span class="sxs-lookup"><span data-stu-id="aeacd-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="aeacd-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="aeacd-118">Entity set</span></span>

| <span data-ttu-id="aeacd-119">Ventas</span><span class="sxs-lookup"><span data-stu-id="aeacd-119">Sales</span></span>    | <span data-ttu-id="aeacd-120">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="aeacd-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="aeacd-121">Cuentas</span><span class="sxs-lookup"><span data-stu-id="aeacd-121">Accounts</span></span> | <span data-ttu-id="aeacd-122">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="aeacd-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="aeacd-123">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="aeacd-123">Entity flow</span></span>

<span data-ttu-id="aeacd-124">Las cuentas se administran en Sales y se sincronizan con Supply Chain Management como clientes.</span><span class="sxs-lookup"><span data-stu-id="aeacd-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="aeacd-125">La propiedad **Mantenida externamente** de estos clientes se establece en **Sí** para realizar un seguimiento de los clientes que proceden de Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="aeacd-126">Durante la facturación, esta información se usa para filtrar las facturas que se sincronizan con Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="aeacd-127">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="aeacd-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="aeacd-128">El campo **Número de cuenta** está disponible en la página **Cuenta** .</span><span class="sxs-lookup"><span data-stu-id="aeacd-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="aeacd-129">Se ha convertido en una clave natural y única para admitir la integración.</span><span class="sxs-lookup"><span data-stu-id="aeacd-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="aeacd-130">La característica de clave natural de la solución de la gestión de relaciones con el cliente (CRM) puede afectar a los clientes que utilicen ya el campo **Número de cuenta** , pero que no usen los valores **Número de cuenta** únicos por cuenta.</span><span class="sxs-lookup"><span data-stu-id="aeacd-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="aeacd-131">Actualmente, la solución de integración no admite este caso.</span><span class="sxs-lookup"><span data-stu-id="aeacd-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="aeacd-132">Cuando se crea una nueva cuenta, si todavía no existe un valor **Número de cuenta** , se genera automáticamente mediante una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="aeacd-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="aeacd-133">El valor consiste en **ACC**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="aeacd-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="aeacd-134">He aquí un ejemplo: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="aeacd-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="aeacd-135">Cuando se aplique la solución de integración para Sales, una secuencia de comandos de actualización establece el campo **Número de cuenta** de las cuentas existentes en Sales.</span><span class="sxs-lookup"><span data-stu-id="aeacd-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="aeacd-136">Si no hay valores para **Número de cuenta** , se usa la secuencia numérica que se ha mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="aeacd-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="aeacd-137">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="aeacd-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="aeacd-138">La asignación **CustomerGroupId** se debe actualizar en un valor válido en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="aeacd-139">Puede especificar un valor predeterminado, o se puede definir el valor mediante una asignación del valor.</span><span class="sxs-lookup"><span data-stu-id="aeacd-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="aeacd-140">El valor de plantilla predeterminado es **10**.</span><span class="sxs-lookup"><span data-stu-id="aeacd-140">The default template value is **10**.</span></span>

- <span data-ttu-id="aeacd-141">Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="aeacd-142">Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.</span><span class="sxs-lookup"><span data-stu-id="aeacd-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="aeacd-143">**SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="aeacd-144">Un sitio predeterminado se puede obtener del producto, o el cliente del encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="aeacd-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="aeacd-145">El valor de plantilla predeterminado es **1**.</span><span class="sxs-lookup"><span data-stu-id="aeacd-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="aeacd-146">**WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="aeacd-147">Un almacén predeterminado se puede obtener del producto, o el cliente del encabezado del pedido en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="aeacd-148">El valor de plantilla predeterminado es **13**.</span><span class="sxs-lookup"><span data-stu-id="aeacd-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="aeacd-149">**LanguageId** – Se requiere un sitio para generar presupuestos y pedidos de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="aeacd-150">De forma predeterminada, se usa el idioma del encabezado del pedido del cliente.</span><span class="sxs-lookup"><span data-stu-id="aeacd-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="aeacd-151">El valor de plantilla predeterminado es **en-us**.</span><span class="sxs-lookup"><span data-stu-id="aeacd-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="aeacd-152">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="aeacd-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="aeacd-153">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no se incluyen en las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="aeacd-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="aeacd-154">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="aeacd-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="aeacd-155">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="aeacd-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="aeacd-156">La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aeacd-156">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Asignación de la plantilla en la integración de datos](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="aeacd-158">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aeacd-158">Related topics</span></span>


[<span data-ttu-id="aeacd-159">Cliente potencial a cliente</span><span class="sxs-lookup"><span data-stu-id="aeacd-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="aeacd-160">Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="aeacd-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="aeacd-161">Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="aeacd-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="aeacd-162">Sincronización de pedidos de ventas entre Sales y Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="aeacd-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="aeacd-163">Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales</span><span class="sxs-lookup"><span data-stu-id="aeacd-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)

