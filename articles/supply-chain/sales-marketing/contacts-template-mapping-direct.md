---
title: Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar entidades de Contacto (Contactos) y Contacto (Clientess) directamente de Dynamics 365 Sales a Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: 7d3a4602a3d8462666dfcb26b97a4f652891f7bc
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249989"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="354aa-103">Sincronizar contactos directamente desde Sales con contactos o clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="354aa-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="354aa-104">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Common Data Service para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="354aa-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="354aa-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar entidades de Contacto (Contactos) y Contacto (Clientess) directamente de Dynamics 365 Sales a Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="354aa-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="354aa-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="354aa-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="354aa-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="354aa-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="354aa-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="354aa-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="354aa-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="354aa-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="354aa-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="354aa-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="354aa-111">Templates and tasks</span></span>

<span data-ttu-id="354aa-112">Para obtener acceso a las plantillas disponibles, abra [Centro de administración de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="354aa-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="354aa-113">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="354aa-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="354aa-114">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar entidades de Contacto (contactos) de Sales con entidades de Contacto (clientes) de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Supply Chain Management.</span></span>

- <span data-ttu-id="354aa-115">**Nombres de las plantillas en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="354aa-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="354aa-116">Contactos (de Sales a Supply Chain Management) - Directo</span><span class="sxs-lookup"><span data-stu-id="354aa-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="354aa-117">Contactos a cliente (de Sales a Supply Chain Management) - Directo</span><span class="sxs-lookup"><span data-stu-id="354aa-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="354aa-118">**Nombres de las tareas en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="354aa-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="354aa-119">Contactos</span><span class="sxs-lookup"><span data-stu-id="354aa-119">Contacts</span></span>
    - <span data-ttu-id="354aa-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="354aa-120">ContactToCustomer</span></span>

<span data-ttu-id="354aa-121">La tarea siguiente de sincronización es obligatoria antes de la sincronización de contactos: Cuentas (de Sales a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="354aa-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="354aa-122">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="354aa-122">Entity sets</span></span>

| <span data-ttu-id="354aa-123">Ventas</span><span class="sxs-lookup"><span data-stu-id="354aa-123">Sales</span></span>    | <span data-ttu-id="354aa-124">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="354aa-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="354aa-125">Contactos</span><span class="sxs-lookup"><span data-stu-id="354aa-125">Contacts</span></span> | <span data-ttu-id="354aa-126">Contactos de CDS</span><span class="sxs-lookup"><span data-stu-id="354aa-126">CDS Contacts</span></span>           |
| <span data-ttu-id="354aa-127">Contactos</span><span class="sxs-lookup"><span data-stu-id="354aa-127">Contacts</span></span> | <span data-ttu-id="354aa-128">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="354aa-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="354aa-129">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="354aa-129">Entity flow</span></span>

<span data-ttu-id="354aa-130">Los contactos se administran en Sales y se sincronizan con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="354aa-131">Un contacto de Sales se puede convertir en un contacto o un cliente en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="354aa-132">Para determinar si un contacto de Sales se debe sincronizar con Supply Chain Management como contacto o cliente, el sistema buscará las siguientes propiedades en el contacto en Sales:</span><span class="sxs-lookup"><span data-stu-id="354aa-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="354aa-133">**Sincronizar con un cliente en Supply Chain Management:** Contactos donde **Es el cliente activo** está establecido en **Sí**</span><span class="sxs-lookup"><span data-stu-id="354aa-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="354aa-134">**Sincronizar con contacto en Supply Chain Management:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)</span><span class="sxs-lookup"><span data-stu-id="354aa-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="354aa-135">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="354aa-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="354aa-136">Un nuevo campo **Es cliente activo** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="354aa-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="354aa-137">Este campo se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="354aa-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="354aa-138">**Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados.</span><span class="sxs-lookup"><span data-stu-id="354aa-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="354aa-139">Solo estos contactos se sincronizan con Supply Chain Management como clientes.</span><span class="sxs-lookup"><span data-stu-id="354aa-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="354aa-140">Un nuevo campo **IsCompanyAnAccount** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="354aa-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="354aa-141">Este campo indica si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="354aa-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="354aa-142">Esta información se usa para identificar los contactos que se deben sincronizar con Supply Chain Management como contactos.</span><span class="sxs-lookup"><span data-stu-id="354aa-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="354aa-143">Un nuevo campo **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración.</span><span class="sxs-lookup"><span data-stu-id="354aa-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="354aa-144">Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="354aa-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="354aa-145">El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="354aa-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="354aa-146">He aquí un ejemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="354aa-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="354aa-147">Cuando la solución de integración para Sales se aplica, una secuencia de comandos de actualización establece el campo **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos mencionado antes.</span><span class="sxs-lookup"><span data-stu-id="354aa-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="354aa-148">La secuencia de comandos de actualización también define el campo **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="354aa-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="354aa-149">En Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="354aa-149">In Supply Chain Management</span></span>

<span data-ttu-id="354aa-150">Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="354aa-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="354aa-151">Esta propiedad indica que un contacto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="354aa-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="354aa-152">En este caso, los contactos mantenidos externamente se mantienen en Sales.</span><span class="sxs-lookup"><span data-stu-id="354aa-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="354aa-153">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="354aa-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="354aa-154">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="354aa-154">Contact to customer</span></span>

- <span data-ttu-id="354aa-155">**CustomerGroup** se requiere en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="354aa-156">Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado en la asignación.</span><span class="sxs-lookup"><span data-stu-id="354aa-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="354aa-157">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="354aa-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="354aa-158">El valor de plantilla predeterminado es **10**.</span><span class="sxs-lookup"><span data-stu-id="354aa-158">The default template value is **10**.</span></span>

- <span data-ttu-id="354aa-159">Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="354aa-160">Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.</span><span class="sxs-lookup"><span data-stu-id="354aa-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="354aa-161">**SiteId**: un sitio predeterminado también se puede definir en productos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="354aa-162">Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="354aa-163">No hay definido un valor de plantilla para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="354aa-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="354aa-164">**WarehouseId**: un almacén predeterminado también se puede definir en productos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="354aa-165">Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="354aa-166">No hay definido un valor de plantilla para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="354aa-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="354aa-167">**LanguageId** – Se requiere un sitio para generar presupuestos y pedidos de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="354aa-168">El valor de plantilla predeterminado es **en-us**.</span><span class="sxs-lookup"><span data-stu-id="354aa-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="354aa-169">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="354aa-169">Template mapping in Data integration</span></span>

<span data-ttu-id="354aa-170">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="354aa-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="354aa-171">La asignación muestra qué información de campos se sincronizará de Sales a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="354aa-171">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="354aa-172">Contacto con contacto</span><span class="sxs-lookup"><span data-stu-id="354aa-172">Contact to contact</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="354aa-174">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="354aa-174">Contact to customer</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="354aa-176">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="354aa-176">Related topics</span></span>

[<span data-ttu-id="354aa-177">Cliente potencial a cliente</span><span class="sxs-lookup"><span data-stu-id="354aa-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="354aa-178">Sincronizar cuentas directamente desde Sales con clientes de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="354aa-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="354aa-179">Sincronizar productos directamente de Supply Chain Management con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="354aa-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="354aa-180">Sincronizar encabezados y líneas de pedidos de ventas directamente desde Supply Chain Management a Sales</span><span class="sxs-lookup"><span data-stu-id="354aa-180">Synchronize sales order headers and lines directly from Supply Chain Management to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="354aa-181">Sincronizar encabezados y líneas de factura de ventas directamente desde Supply Chain Management a Sales</span><span class="sxs-lookup"><span data-stu-id="354aa-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)


