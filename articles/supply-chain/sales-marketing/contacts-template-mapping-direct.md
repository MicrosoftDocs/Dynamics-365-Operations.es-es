---
title: Sincronizar directamente contactos de Sales con contactos o clientes de Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las entidades Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations.
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d0da8d3f854fe05db2f73d080ec699d0bedfcdb5
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="ff5dd-103">Sincronizar contactos directamente desde Sales con contactos o clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ff5dd-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ff5dd-104">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ff5dd-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="ff5dd-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente las entidades Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="ff5dd-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="ff5dd-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="ff5dd-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="ff5dd-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos sobre cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="ff5dd-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Finance and Operations y Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="ff5dd-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="ff5dd-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ff5dd-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="ff5dd-111">Templates and tasks</span></span>

<span data-ttu-id="ff5dd-112">Para obtener acceso a las plantillas disponibles, abra [Centro de gestión de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="ff5dd-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="ff5dd-113">Seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="ff5dd-114">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar entidades Contacto (contactos) de Sales con entidades Contacto (clientes) de Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="ff5dd-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="ff5dd-115">**Nombres de las plantillas en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="ff5dd-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="ff5dd-116">Contactos (de Sales a Fin and Ops) - Directos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="ff5dd-117">Contactos a Cliente (de Sales a Fin and Ops) - Directos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="ff5dd-118">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="ff5dd-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="ff5dd-119">Contactos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-119">Contacts</span></span>
    - <span data-ttu-id="ff5dd-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="ff5dd-120">ContactToCustomer</span></span>

<span data-ttu-id="ff5dd-121">La tarea siguiente de sincronización es obligatoria antes de la sincronización de contacto: Cuentas (de Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ff5dd-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="ff5dd-122">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="ff5dd-122">Entity sets</span></span>

| <span data-ttu-id="ff5dd-123">Ventas</span><span class="sxs-lookup"><span data-stu-id="ff5dd-123">Sales</span></span>    | <span data-ttu-id="ff5dd-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ff5dd-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="ff5dd-125">Contactos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-125">Contacts</span></span> | <span data-ttu-id="ff5dd-126">Contactos de CDS</span><span class="sxs-lookup"><span data-stu-id="ff5dd-126">CDS Contacts</span></span>           |
| <span data-ttu-id="ff5dd-127">Contactos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-127">Contacts</span></span> | <span data-ttu-id="ff5dd-128">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="ff5dd-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="ff5dd-129">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="ff5dd-129">Entity flow</span></span>

<span data-ttu-id="ff5dd-130">Los contactos se administran en Sales y se sincronizan en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="ff5dd-131">Un contacto de Sales se puede convertir en un contacto o un cliente de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="ff5dd-132">Para determinar si un contacto de Sales se debe sincronizar con Finance and Operations como contacto o cliente, el sistema buscará las siguientes propiedades en el contacto en Sales:</span><span class="sxs-lookup"><span data-stu-id="ff5dd-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="ff5dd-133">**Sincronizar con un cliente en Finance and Operations:** Contactos donde **Es el cliente activo** está establecido en **Sí**</span><span class="sxs-lookup"><span data-stu-id="ff5dd-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="ff5dd-134">**Sincronizar con contacto en Finance and Operations:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)</span><span class="sxs-lookup"><span data-stu-id="ff5dd-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ff5dd-135">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="ff5dd-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ff5dd-136">Un nuevo campo **Es cliente activo** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="ff5dd-137">Este campo se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="ff5dd-138">**Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="ff5dd-139">Solo estos contactos se sincronizan con Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="ff5dd-140">Un nuevo campo **IsCompanyAnAccount** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="ff5dd-141">Este campo indica si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="ff5dd-142">Esta información se usa para identificar los contactos que se deben sincronizar con Finance and Operations como contactos.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="ff5dd-143">Un nuevo campo **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="ff5dd-144">Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="ff5dd-145">El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="ff5dd-146">He aquí un ejemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="ff5dd-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="ff5dd-147">Cuando la solución de integración para Sales se aplica, una secuencia de comandos de actualización establece el campo **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos mencionado antes.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="ff5dd-148">La secuencia de comandos de actualización también define el campo **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="ff5dd-149">En Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ff5dd-149">In Finance and Operations</span></span>

<span data-ttu-id="ff5dd-150">Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="ff5dd-151">Esta propiedad indica que un contacto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="ff5dd-152">En este caso, los contactos mantenidos externamente se mantienen en Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ff5dd-153">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="ff5dd-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="ff5dd-154">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="ff5dd-154">Contact to customer</span></span>

- <span data-ttu-id="ff5dd-155">**CustomerGroup** se requiere en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="ff5dd-156">Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado en la asignación.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="ff5dd-157">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="ff5dd-158">El valor de plantilla predeterminado es **10**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-158">The default template value is **10**.</span></span>

- <span data-ttu-id="ff5dd-159">Si agrega las asignaciones siguientes, puede ayudar a reducir el número de actualizaciones manuales necesarias en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="ff5dd-160">Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="ff5dd-161">**SiteId**: un sitio predeterminado también se puede definir en productos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ff5dd-162">Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="ff5dd-163">No hay definido un valor de plantilla para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="ff5dd-164">**WarehouseId**: un almacén predeterminado también se puede definir en productos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ff5dd-165">Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="ff5dd-166">No hay definido un valor de plantilla para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="ff5dd-167">**LanguageId** – Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="ff5dd-168">El valor de plantilla predeterminado es **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ff5dd-169">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="ff5dd-169">Template mapping in Data integration</span></span>

<span data-ttu-id="ff5dd-170">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff5dd-171">La asignación muestra qué información de campos se sincronizará de Sales a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff5dd-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="ff5dd-172">Contacto con contacto</span><span class="sxs-lookup"><span data-stu-id="ff5dd-172">Contact to contact</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="ff5dd-174">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="ff5dd-174">Contact to customer</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="ff5dd-176">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ff5dd-176">Related topics</span></span>

[<span data-ttu-id="ff5dd-177">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="ff5dd-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="ff5dd-178">Sincronizar directamente cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ff5dd-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="ff5dd-179">Sincronizar directamente productos de Finance and Operations con productos de Sales</span><span class="sxs-lookup"><span data-stu-id="ff5dd-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="ff5dd-180">Sincronizar encabezados y líneas de pedido de ventas directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="ff5dd-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="ff5dd-181">Sincronizar encabezados y líneas de factura directamente de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="ff5dd-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



