---
title: Sincronizar facturas de acuerdos en Field Service con facturas de texto libre en Supply Chain Management
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdo en Dynamics 365 Field Service a facturas de texto libre en Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
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
ms.openlocfilehash: 943bf04378a8202d676cbabb282a0a6208a92ef3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210015"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="2c9d8-103">Sincronizar facturas de acuerdos en Field Service con facturas de texto libre en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2c9d8-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2c9d8-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar facturas de acuerdo en Dynamics 365 Field Service a facturas de texto libre en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2c9d8-105">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="2c9d8-105">Templates and tasks</span></span>

<span data-ttu-id="2c9d8-106">Se utilizan la plantilla siguiente y las tareas subyacentes para ejecutar la sincronización de las facturas de acuerdos de Field Service con las facturas de servicios en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="2c9d8-107">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2c9d8-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="2c9d8-108">Facturas de acuerdo (Field service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="2c9d8-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="2c9d8-109">**Nombres de las tareas en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2c9d8-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="2c9d8-110">Encabezados de factura</span><span class="sxs-lookup"><span data-stu-id="2c9d8-110">Invoice headers</span></span>
- <span data-ttu-id="2c9d8-111">Líneas de factura</span><span class="sxs-lookup"><span data-stu-id="2c9d8-111">Invoice lines</span></span>

<span data-ttu-id="2c9d8-112">Las siguiente sincronización es necesaria antes de que pueda producirse la sincronización de las facturas de acuerdos:</span><span class="sxs-lookup"><span data-stu-id="2c9d8-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="2c9d8-113">Cuentas (Sales a Supply Chain Management) - Direct</span><span class="sxs-lookup"><span data-stu-id="2c9d8-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="2c9d8-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="2c9d8-114">Entity set</span></span>

| <span data-ttu-id="2c9d8-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="2c9d8-115">Field Service</span></span>  | <span data-ttu-id="2c9d8-116">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="2c9d8-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="2c9d8-117">facturas</span><span class="sxs-lookup"><span data-stu-id="2c9d8-117">invoices</span></span>       | <span data-ttu-id="2c9d8-118">Encabezados de factura de servicios de cliente de CDS</span><span class="sxs-lookup"><span data-stu-id="2c9d8-118">CDS customer free text invoice headers</span></span> |
| <span data-ttu-id="2c9d8-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="2c9d8-119">invoicedetails</span></span> | <span data-ttu-id="2c9d8-120">Líneas de factura de servicios de cliente de CDS</span><span class="sxs-lookup"><span data-stu-id="2c9d8-120">CDS customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="2c9d8-121">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="2c9d8-121">Entity flow</span></span>

<span data-ttu-id="2c9d8-122">Las facturas creadas desde un acuerdo en Field Service se pueden sincronizar con Supply Chain Management mediante un proyecto de integración de datos del Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Common Data Service Data integration project.</span></span> <span data-ttu-id="2c9d8-123">Las actualizaciones de estas facturas se sincronizan a las facturas de Supply Chain Management si el estado contable de las facturas de servicios es **En proceso**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="2c9d8-124">Una vez que las facturas de servicios se registren en Supply Chain Management y el estado contable se actualice a **Completado**, ya no se pueden sincronizar las actualizaciones desde Field Service.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="2c9d8-125">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="2c9d8-125">Field Service CRM solution</span></span>

<span data-ttu-id="2c9d8-126">El campo **Tiene líneas con origen del acuerdo** se ha agregado a la entidad **Factura**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-126">The **Has Lines With Agreement Origin** field has been added to the **Invoice** entity.</span></span> <span data-ttu-id="2c9d8-127">Este campo permite garantizar que solo las facturas que se crean a partir de un acuerdo se sincronicen.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-127">This field helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="2c9d8-128">El valor es **verdadero** si la factura contiene al menos una línea de factura que origine desde un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="2c9d8-129">El campo **Tiene origen del acuerdo** se ha agregado a la entidad **Línea de factura**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-129">The **Has Agreement Origin** field has been added to the **Invoice Line** entity.</span></span> <span data-ttu-id="2c9d8-130">Este campo permite garantizar que solo las líneas de facturas que se crean a partir de un acuerdo se sincronicen.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-130">This field helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="2c9d8-131">El valor es **verdadero** si la línea de factura se origina desde un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="2c9d8-132">**Fecha de factura** es un campo obligatorio en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="2c9d8-133">Por lo tanto, el campo debe contener un valor en Field Service antes de que se realice la sincronización.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-133">Therefore, the field must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="2c9d8-134">Para cumplir este requisito, se agrega la lógica siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c9d8-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="2c9d8-135">Si el campo **Fecha de factura** está en blanco en la entidad **Factura** (es decir, si no tiene ningún valor), se establece en la fecha actual en que se agrega una línea de factura que se origina desde un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-135">If the **Invoice Date** field is blank on the **Invoice** entity (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="2c9d8-136">El usuario puede modificar el campo **Fecha de factura**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-136">The user can change the **Invoice Date** field.</span></span> <span data-ttu-id="2c9d8-137">Sin embargo, cuando el usuario intenta guardar una factura que se origina desde un acuerdo, recibe un error de proceso de negocio si el campo **Fecha de factura** está en blanco en la factura.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** field is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="2c9d8-138">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="2c9d8-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="2c9d8-139">En Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2c9d8-139">In Supply Chain Management</span></span>

<span data-ttu-id="2c9d8-140">Un origen de factura se debe configurar para la integración, para distinguir las facturas de servicios en Supply Chain Management que se crean de facturas de acuerdos en Field Service.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="2c9d8-141">Cuando una factura tiene un origen de factura del tipo **Integración de factura de acuerdo**, el campo **Número de factura externo** se muestra en el encabezado **Factura de ventas**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="2c9d8-142">Además de aparecer en el encabezado de factura, la información **Número de factura externo** se pueden usar para ayudar a garantizar que las facturas que se crean desde facturas de acuerdo de Field Service se filtran durante la sincronización de Supply Chain Management con Field Service.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="2c9d8-143">Vaya a **Clientes** \> **Configuración** \> **Códigos de origen de factura**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="2c9d8-144">Seleccione **Nuevo** para crear un nuevo origen de factura.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="2c9d8-145">En el campo **Origen de factura**, especifique un nombre para el origen de la factura, como **FS**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="2c9d8-146">En el campo **Descripción**, especifique una descripción, como **Factura de acuerdo de Field Service**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="2c9d8-147">Seleccione la casilla de verificación **Asignación de tipo de origen**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="2c9d8-148">Establezca el campo **Tipo de origen de la factura** a **Integración de la factura de acuerdo**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="2c9d8-149">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="2c9d8-150">En el proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="2c9d8-150">In the Data Integration project</span></span>

<span data-ttu-id="2c9d8-151">Tarea: **Líneas de factura**</span><span class="sxs-lookup"><span data-stu-id="2c9d8-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="2c9d8-152">Asegúrese de que el valor predeterminado del campo de Supply Chain Management **Mostrar valor de la cuenta principal** se haya actualizado para que coincida con el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="2c9d8-153">El valor de plantilla predeterminado es **401100**.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2c9d8-154">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="2c9d8-154">Template mapping in Data integration</span></span>

<span data-ttu-id="2c9d8-155">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="2c9d8-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="2c9d8-156">Facturas de acuerdo (Field service a Supply Chain Management): encabezados de facturas</span><span class="sxs-lookup"><span data-stu-id="2c9d8-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="2c9d8-157">[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="2c9d8-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="2c9d8-158">Facturas de acuerdo (Field service a Supply Chain Management): líneas de facturas</span><span class="sxs-lookup"><span data-stu-id="2c9d8-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="2c9d8-159">[![Asignación de la plantilla en la integración de datos](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="2c9d8-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>
