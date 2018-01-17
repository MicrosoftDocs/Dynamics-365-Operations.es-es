---
title: "Sincronice los encabezados y las líneas del presupuesto de Sales con Finance and Operations"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d34c808bce5b61b528f50224e3a72590476d8e55
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="1daa5-103">Sincronice los encabezados y las líneas del presupuesto de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1daa5-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="1daa5-104">Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="1daa5-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="1daa5-105">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones).</span><span class="sxs-lookup"><span data-stu-id="1daa5-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="1daa5-106">Plantilla y tareas</span><span class="sxs-lookup"><span data-stu-id="1daa5-106">Template and tasks</span></span>

<span data-ttu-id="1daa5-107">Las plantillas y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del presupuestos de ventas de Sales a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="1daa5-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="1daa5-108">**Nombre de la plantilla:** Presupuestos de ventas (Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="1daa5-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="1daa5-109">**Nombres de las tareas en el proyecto:**</span><span class="sxs-lookup"><span data-stu-id="1daa5-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="1daa5-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1daa5-110">QuoteHeader</span></span>
    - <span data-ttu-id="1daa5-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1daa5-111">QuoteLine</span></span>

<span data-ttu-id="1daa5-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del presupuesto de ventas:</span><span class="sxs-lookup"><span data-stu-id="1daa5-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="1daa5-113">Productos (de Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="1daa5-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="1daa5-114">Cuentas (de Sales a Fin and Ops), si es que se usan</span><span class="sxs-lookup"><span data-stu-id="1daa5-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="1daa5-115">Contactos a Clientes (de Sales a Fin and Ops) si es que se usan</span><span class="sxs-lookup"><span data-stu-id="1daa5-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="1daa5-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="1daa5-116">Entity set</span></span>

| <span data-ttu-id="1daa5-117">Ventas</span><span class="sxs-lookup"><span data-stu-id="1daa5-117">Sales</span></span>        | <span data-ttu-id="1daa5-118">CDS</span><span class="sxs-lookup"><span data-stu-id="1daa5-118">CDS</span></span>           | <span data-ttu-id="1daa5-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1daa5-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="1daa5-120">Ofertas</span><span class="sxs-lookup"><span data-stu-id="1daa5-120">Quotes</span></span>       | <span data-ttu-id="1daa5-121">Presupuesto</span><span class="sxs-lookup"><span data-stu-id="1daa5-121">Quotation</span></span>     | <span data-ttu-id="1daa5-122">Encabezados de presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="1daa5-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="1daa5-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="1daa5-123">QuoteDetails</span></span> | <span data-ttu-id="1daa5-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="1daa5-124">QuotationLine</span></span> | <span data-ttu-id="1daa5-125">Líneas de presupuesto de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="1daa5-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="1daa5-126">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="1daa5-126">Entity flow</span></span>

<span data-ttu-id="1daa5-127">Los presupuestos de ventas se crean en Sales y se sincronizan en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="1daa5-128">Los presupuestos de ventas de Sales se sincronizan solo si se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="1daa5-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="1daa5-129">Todos los productos en las líneas de presupuesto de ventas se mantienen externamente.</span><span class="sxs-lookup"><span data-stu-id="1daa5-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="1daa5-130">El presupuesto de ventas está activo o activado.</span><span class="sxs-lookup"><span data-stu-id="1daa5-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="1daa5-131">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="1daa5-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="1daa5-132">El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad Presupuesto para realizar un seguimiento constante si el presupuesto de ventas se compone por completo de productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="1daa5-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="1daa5-133">Si un presupuesto de ventas solo tiene productos mantenidos externamente, los productos se mantienen en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="1daa5-134">Este comportamiento ayuda a garantizar que no intenta sincronizar las líneas de presupuesto de ventas con productos desconocidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="1daa5-135">Todos los productos y líneas del presupuesto se actualizan con la información **Solo tiene productos mantenidos externamente** de la cabecera de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="1daa5-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="1daa5-136">Esta información se puede encontrar en el campo **Solo tiene productos mantenidos externamente** en la entidad Línea de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="1daa5-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="1daa5-137">Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="1daa5-138">Esta configuración no admite actualmente la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="1daa5-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="1daa5-139">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son dominados y gestionados por Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="1daa5-140">En Sales, la solución crea los siguientes campos de solo lectura, ya que los valores no se sincronizan con Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="1daa5-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="1daa5-141">**Campos de solo lectura en el encabezado del presupuesto de ventas:** % de descuento, Descuento, Importe del fleje</span><span class="sxs-lookup"><span data-stu-id="1daa5-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="1daa5-142">**Campos de solo lectura en líneas de presupuesto de ventas:** Impuestos</span><span class="sxs-lookup"><span data-stu-id="1daa5-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="1daa5-143">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="1daa5-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="1daa5-144">Antes de sincronizar los pedidos de ventas, es importante actualizar los sistemas mediante la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="1daa5-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="1daa5-145">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="1daa5-145">Setup in Sales</span></span>

- <span data-ttu-id="1daa5-146">Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Ventas** y asegúrese de que el campo **Método de cálculo del descuento** está establecido en **Por unidad**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="1daa5-147">Este valor ayuda a garantizar que el descuento del artículo de la línea de Sales coincide con la configuración en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="1daa5-148">De lo contrario, el descuento no será correcto en Finance and Operations, ya que Finance and Operations leerá el descuento como un descuento por unidad incluso si era un descuento por línea en Sales.</span><span class="sxs-lookup"><span data-stu-id="1daa5-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="1daa5-149">Configuración en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1daa5-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="1daa5-150">Vaya a **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="1daa5-151">En la pestaña **Secuencia numérica**, seleccione la secuencia numérica para presupuestos de ventas y luego haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="1daa5-152">A continuación, en **Configuración general**, establezca el campo **Manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="1daa5-153">Vaya a **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="1daa5-154">A continuación, en la pestaña **Envíos**, establezca el campo **Control de fecha de entrega** en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="1daa5-155">Este valor ayuda a evitar que la sincronización falle para presupuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="1daa5-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="1daa5-156">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="1daa5-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="1daa5-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1daa5-157">QuoteHeader</span></span>

- <span data-ttu-id="1daa5-158">El campo **Fecha de entrega solicitada** es obligatorio en Finance and Operations, y la sincronización fallará si el campo se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="1daa5-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="1daa5-159">Para evitar este problema, si el campo está en blanco, la fecha predeterminada se toma de **Origen &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="1daa5-160">La fecha debe actualizarse a un valor preferido.</span><span class="sxs-lookup"><span data-stu-id="1daa5-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="1daa5-161">Actualmente, no puede introducir un valor como **Hoy** para representar la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="1daa5-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="1daa5-162">Debe introducir una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="1daa5-162">You must enter a specific date.</span></span> <span data-ttu-id="1daa5-163">El valor de plantilla predeterminado para **Fecha de entrega solicitada** es **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="1daa5-164">El campo **Código de país/región de la dirección** es obligatorio en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="1daa5-165">Para ayudar a evitar errores de sincronización, puede especificar un valor predeterminado que se usa si el campo se deja en blanco en Sales.</span><span class="sxs-lookup"><span data-stu-id="1daa5-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="1daa5-166">Este valor predeterminado también resulta útil, ya que no tiene que introducir manualmente un valor en el campo **País/región** para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="1daa5-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="1daa5-167">No hay valor de plantilla predeterminado para **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="1daa5-168">Actualice la asignación para **Identificador de la organización de CDS** en **Origen &gt; CDS** para que coincida con la **Organización de CDS** en la entidad de organización:</span><span class="sxs-lookup"><span data-stu-id="1daa5-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="1daa5-169">El valor de plantilla predeterminado para **Organization_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="1daa5-170">El valor de plantilla predeterminado para **Account_Organization_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="1daa5-171">El valor de plantilla predeterminado para **InvoiceAccount_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="1daa5-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1daa5-172">QuoteLine</span></span>

- <span data-ttu-id="1daa5-173">Actualice la asignación para **Identificador de la organización de CDS** en **Origen &gt; CDS** para que coincida con la **Organización de CDS** en la entidad de organización:</span><span class="sxs-lookup"><span data-stu-id="1daa5-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="1daa5-174">El valor de plantilla predeterminado para **Organization_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="1daa5-175">El valor de plantilla predeterminado para **Product_Organization_Organization_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="1daa5-176">El valor de plantilla predeterminado para **Quotation_Organization_Organization_OrganizationId** es **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="1daa5-177">El campo **Fecha de entrega solicitada** es obligatorio en Finance and Operations, y la sincronización fallará si el campo se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="1daa5-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="1daa5-178">Para evitar este problema, si el campo está en blanco, la fecha predeterminada se toma de **Origen &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="1daa5-179">La fecha debe actualizarse a un valor preferido.</span><span class="sxs-lookup"><span data-stu-id="1daa5-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="1daa5-180">Actualmente, no puede introducir un valor como **Hoy** para representar la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="1daa5-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="1daa5-181">Debe introducir una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="1daa5-181">You must enter a specific date.</span></span> <span data-ttu-id="1daa5-182">El valor de plantilla predeterminado para **Fecha de entrega solicitada** es **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="1daa5-183">Puede agregar las siguientes asignaciones desde **CDS &gt; Destino** para ayudar a garantizar que las líneas de presupuesto se importan en Finance and Operations si no hay información predeterminada del cliente o del producto:</span><span class="sxs-lookup"><span data-stu-id="1daa5-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="1daa5-184">**SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="1daa5-185">No hay valor de plantilla predeterminado para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="1daa5-186">**WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="1daa5-187">No hay valor de plantilla predeterminado para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="1daa5-188">Asegúrese de que la asignación del valor requerido para la unidad de medida (U. de M.) vendedora en Finance and Operations existe en la asignación **CDS &gt; Destino** para **Quantity_UOM.** a **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="1daa5-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="1daa5-189">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="1daa5-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="1daa5-190">Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="1daa5-191">Esta configuración no admite actualmente la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="1daa5-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="1daa5-192">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados por Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1daa5-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="1daa5-193">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="1daa5-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="1daa5-194">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="1daa5-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="1daa5-195">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="1daa5-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="1daa5-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1daa5-196">QuoteHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="1daa5-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1daa5-199">QuoteLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="1daa5-202">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1daa5-202">Related topics</span></span>

[<span data-ttu-id="1daa5-203">Sincronice los productos de Finance and Operations con productos en Sales</span><span class="sxs-lookup"><span data-stu-id="1daa5-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="1daa5-204">Sincronizar cuentas de Sales con clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1daa5-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="1daa5-205">Sincronice contactos de Sales con contactos o clientes en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1daa5-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



