---
title: Sincronice contactos de Sales con contactos o clientes en Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
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
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="d4f41-103">Sincronice contactos de Sales con contactos o clientes en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4f41-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d4f41-104">Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="d4f41-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="d4f41-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar entidades de Contacto (contactos) y Contacto (clientes) de Microsoft Dynamics 365 for Sales con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones).</span><span class="sxs-lookup"><span data-stu-id="d4f41-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d4f41-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="d4f41-106">Templates and tasks</span></span>

<span data-ttu-id="d4f41-107">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar Contacto (contactos) de Sales con Contacto (clientes) de Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d4f41-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="d4f41-108">**Nombres de la plantillas:**</span><span class="sxs-lookup"><span data-stu-id="d4f41-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="d4f41-109">Contactos (de Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="d4f41-109">Contacts (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="d4f41-110">Contactos a Cliente (de Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="d4f41-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="d4f41-111">**Nombres de las tareas en el proyecto:**</span><span class="sxs-lookup"><span data-stu-id="d4f41-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="d4f41-112">Contactos</span><span class="sxs-lookup"><span data-stu-id="d4f41-112">Contacts</span></span>
    - <span data-ttu-id="d4f41-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="d4f41-113">ContactToCustomer</span></span>

<span data-ttu-id="d4f41-114">La tarea siguiente de sincronización es obligatoria antes de la sincronización de contacto: Cuentas (de Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="d4f41-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="d4f41-115">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="d4f41-115">Entity sets</span></span>

| <span data-ttu-id="d4f41-116">Ventas</span><span class="sxs-lookup"><span data-stu-id="d4f41-116">Sales</span></span>    | <span data-ttu-id="d4f41-117">CDS</span><span class="sxs-lookup"><span data-stu-id="d4f41-117">CDS</span></span>     | <span data-ttu-id="d4f41-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4f41-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="d4f41-119">Contactos</span><span class="sxs-lookup"><span data-stu-id="d4f41-119">Contacts</span></span> | <span data-ttu-id="d4f41-120">Contacto</span><span class="sxs-lookup"><span data-stu-id="d4f41-120">Contact</span></span> | <span data-ttu-id="d4f41-121">Contactos de CDS</span><span class="sxs-lookup"><span data-stu-id="d4f41-121">CDS Contacts</span></span>           |
| <span data-ttu-id="d4f41-122">Contactos</span><span class="sxs-lookup"><span data-stu-id="d4f41-122">Contacts</span></span> | <span data-ttu-id="d4f41-123">Cuenta</span><span class="sxs-lookup"><span data-stu-id="d4f41-123">Account</span></span> | <span data-ttu-id="d4f41-124">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="d4f41-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="d4f41-125">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="d4f41-125">Entity flow</span></span>

<span data-ttu-id="d4f41-126">Los contactos se administran en Sales y se sincronizan con Common Data Service (CDS) y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="d4f41-127">Un contacto de Sales se puede convertir en un contacto de CDS y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="d4f41-128">Como alternativa, puede convertirse en una cuenta en CDS y un cliente en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="d4f41-129">Para determinar si un contacto debe elegirse en Sales para sincronizarlo con CDS y Finance and Operations (por ejemplo, Contactos en Sales &gt; Contacto en CDS &gt; Contactos en Finance and Operations), el sistema buscará las siguientes propiedades en Contacto en Sales:</span><span class="sxs-lookup"><span data-stu-id="d4f41-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="d4f41-130">**Sincronizar con cuenta en CDS y Cliente en Finance and Operations:** Contactos donde **Es el cliente activo** está establecido en **Sí**</span><span class="sxs-lookup"><span data-stu-id="d4f41-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="d4f41-131">**Sincronizar con Contacto en CDS y Contacto en Finance and Operations:** Contactos donde **Es cliente activo** se establece en **No** y **Empresa** (cuenta o contacto principal) apunta a una cuenta (no a un contacto)</span><span class="sxs-lookup"><span data-stu-id="d4f41-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d4f41-132">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="d4f41-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="d4f41-133">Un nuevo campo **Es cliente activo** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="d4f41-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="d4f41-134">Este campo se utiliza para distinguir los contactos que tienen actividad de ventas y los contactos que no tienen actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="d4f41-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="d4f41-135">**Es cliente activo** se establece en **Sí** únicamente para los contactos que tienen presupuestos, pedidos o facturas relacionados.</span><span class="sxs-lookup"><span data-stu-id="d4f41-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="d4f41-136">Solo estos contactos se sincronizan con Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="d4f41-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="d4f41-137">Un nuevo campo **IsCompanyAnAccount** se ha agregado al contacto.</span><span class="sxs-lookup"><span data-stu-id="d4f41-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="d4f41-138">Este campo se usa para indicar si un contacto está vinculado a una empresa (cuenta o contacto principal) del tipo **Cuenta** .</span><span class="sxs-lookup"><span data-stu-id="d4f41-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="d4f41-139">Esta información se usa para identificar los contactos que se deben sincronizar con Finance and Operations como contactos.</span><span class="sxs-lookup"><span data-stu-id="d4f41-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="d4f41-140">Un nuevo campo **Número de contacto** se ha agregado al contacto para ayudar a garantizar una clave natural y única para la integración.</span><span class="sxs-lookup"><span data-stu-id="d4f41-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="d4f41-141">Cuando se crea un contacto nuevo, un valor **Número de contacto** se genera automáticamente mediante una secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="d4f41-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="d4f41-142">El valor consiste en **CON**, seguido por una secuencia numérica que aumenta y después un sufijo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="d4f41-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="d4f41-143">He aquí un ejemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="d4f41-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="d4f41-144">Cuando la solución de integración para Sales se agrega a Sales, una secuencia de comandos de actualización establece el campo **Número de contacto** para los contactos existentes usando la secuencia numérica que hemos tratado antes.</span><span class="sxs-lookup"><span data-stu-id="d4f41-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="d4f41-145">La secuencia de comandos de actualización también define el campo **Es cliente activo** en **Sí** para todos los contactos con actividad de ventas.</span><span class="sxs-lookup"><span data-stu-id="d4f41-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="d4f41-146">En Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4f41-146">In Finance and Operations</span></span> 

<span data-ttu-id="d4f41-147">Los contactos se etiquetan con la propiedad **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="d4f41-148">Esta propiedad indica que un contacto determinado se mantiene externamente.</span><span class="sxs-lookup"><span data-stu-id="d4f41-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="d4f41-149">En este caso, los contactos mantenidos externamente se mantienen en Sales.</span><span class="sxs-lookup"><span data-stu-id="d4f41-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d4f41-150">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="d4f41-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="d4f41-151">Contacto con contacto</span><span class="sxs-lookup"><span data-stu-id="d4f41-151">Contact to Contact</span></span>

- <span data-ttu-id="d4f41-152">Actualice el **identificador de la organización de CDS** en la asignación **Origen &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="d4f41-153">El valor de plantilla predeterminado para **Organization_OrganizationId [id. de organización]** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="d4f41-154">El valor de plantilla predeterminado para **PrimaryAccount_Organization_OrganizationId [id. de organización]** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="d4f41-155">**Código de país/región de la dirección** se requiere en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="d4f41-156">Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Operaciones**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="d4f41-157">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="d4f41-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="d4f41-158">El valor de plantilla predeterminado para **PrimaryAddressCountryRegionISOCode** es **EE. UU**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="d4f41-159">Asegúrese de que el valor para el campo siguiente existe en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="d4f41-160">Si la información no se requiere en Finance and Operations, puede quitar la asignación de la asignación **CDS &gt; Destino**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="d4f41-161">**Nombre de campo en Finance and Operations:** Decisión</span><span class="sxs-lookup"><span data-stu-id="d4f41-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="d4f41-162">**Asignación:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="d4f41-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="d4f41-163">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="d4f41-163">Contact to Customer</span></span>

- <span data-ttu-id="d4f41-164">Actualice el **identificador de la organización de CDS** en la asignación **Origen &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="d4f41-165">El valor de plantilla predeterminado para **Organization_OrganizationId [id. de organización]** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="d4f41-166">**Código de país/región de la dirección** se requiere en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="d4f41-167">Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="d4f41-168">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="d4f41-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="d4f41-169">El valor de plantilla predeterminado para **PrimaryAddressCountryRegionISOCode** es **EE. UU**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="d4f41-170">**CustomerGroup** se requiere en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="d4f41-171">Para evitar errores de sincronización, puede especificar un valor predeterminado en la asignación **CDS &gt; Destino**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="d4f41-172">El valor predeterminado se utiliza si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="d4f41-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="d4f41-173">El valor de plantilla predeterminado para **CustomerGroupId** es **10**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="d4f41-174">Si agrega las asignaciones siguientes desde **CDS &gt; Destino**, puede ayudar a reducir el número de actualizaciones manuales en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="d4f41-175">Puede usar un valor predeterminado o asignar un valor de, por ejemplo, **País/región** o **Ciudad**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="d4f41-176">**SiteId**: un sitio predeterminado también se puede definir en productos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="d4f41-177">Un sitio es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="d4f41-178">No hay definido un valor de plantilla para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="d4f41-179">**WarehouseId**: un almacén predeterminado también se puede definir en productos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="d4f41-180">Un almacén es obligatorio para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="d4f41-181">No hay definido un valor de plantilla para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="d4f41-182">**LanguageId**: Se requiere un idioma para generar presupuestos y pedidos de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4f41-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="d4f41-183">El valor de plantilla predeterminado para **LanguageId** es **en-us**.</span><span class="sxs-lookup"><span data-stu-id="d4f41-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="d4f41-184">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="d4f41-184">Template mapping in data integrator</span></span>

<span data-ttu-id="d4f41-185">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="d4f41-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="d4f41-186">Contacto con contacto</span><span class="sxs-lookup"><span data-stu-id="d4f41-186">Contact to Contact</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-template-mapping-data-integrator-1.png)

![Asignación de la plantilla para contactos en el integrador de datos](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="d4f41-189">Contacto con cliente</span><span class="sxs-lookup"><span data-stu-id="d4f41-189">Contact to Customer</span></span>

![Asignación de la plantilla en el integrador de datos](./media/contacts-template-mapping-data-integrator-3.png)

![Asignación de la plantilla para contactos en el integrador de datos](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="d4f41-192">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d4f41-192">Related topics</span></span>

[<span data-ttu-id="d4f41-193">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="d4f41-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="d4f41-194">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4f41-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="d4f41-195">Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4f41-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="d4f41-196">Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="d4f41-196">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="d4f41-197">Sincronizar encabezados y líneas de factura de Finance and Operations en Sales</span><span class="sxs-lookup"><span data-stu-id="d4f41-197">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)

