---
title: "Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas directamente de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 77b15a51073bf923f09a4a0e83ee5b2642eec4af
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="e9b65-103">Sincronizar directamente encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e9b65-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e9b65-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuesto de ventas directamente de Microsoft Dynamics 365 for Sales (ventas) con Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="e9b65-105">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="e9b65-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="e9b65-106">Plantilla y tareas</span><span class="sxs-lookup"><span data-stu-id="e9b65-106">Template and tasks</span></span>

<span data-ttu-id="e9b65-107">La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del presupuestos de ventas directamente de Sales a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e9b65-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="e9b65-108">**Nombre de la plantilla en la integración de datos:** Presupuestos de ventas (Sales y Fin and Ops) - Directos</span><span class="sxs-lookup"><span data-stu-id="e9b65-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="e9b65-109">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="e9b65-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="e9b65-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e9b65-110">QuoteHeader</span></span>
    - <span data-ttu-id="e9b65-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e9b65-111">QuoteLine</span></span>

<span data-ttu-id="e9b65-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del presupuesto de ventas:</span><span class="sxs-lookup"><span data-stu-id="e9b65-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="e9b65-113">Productos (de Fin and Ops a Sales) - Directos</span><span class="sxs-lookup"><span data-stu-id="e9b65-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="e9b65-114">Cuentas (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="e9b65-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="e9b65-115">Contactos a Clientes (de Sales a Fin and Ops) - Directos (si es que se usan)</span><span class="sxs-lookup"><span data-stu-id="e9b65-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="e9b65-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="e9b65-116">Entity set</span></span>

| <span data-ttu-id="e9b65-117">Ventas</span><span class="sxs-lookup"><span data-stu-id="e9b65-117">Sales</span></span>        | <span data-ttu-id="e9b65-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e9b65-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="e9b65-119">Ofertas</span><span class="sxs-lookup"><span data-stu-id="e9b65-119">Quotes</span></span>       | <span data-ttu-id="e9b65-120">Encabezado de presupuesto de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="e9b65-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="e9b65-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="e9b65-121">QuoteDetails</span></span> | <span data-ttu-id="e9b65-122">Líneas de presupuesto de ventas de CDS</span><span class="sxs-lookup"><span data-stu-id="e9b65-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="e9b65-123">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="e9b65-123">Entity flow</span></span>

<span data-ttu-id="e9b65-124">Los presupuestos de ventas se crean en Sales y se sincronizan en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="e9b65-125">Los presupuestos de ventas de Sales se sincronizan solo si se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e9b65-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="e9b65-126">Todos los productos de presupuestos en las líneas de ventas se mantienen externamente.</span><span class="sxs-lookup"><span data-stu-id="e9b65-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="e9b65-127">Tras hacer clic en **Activar presupuesto**, el presupuesto de ventas se activa.</span><span class="sxs-lookup"><span data-stu-id="e9b65-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e9b65-128">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="e9b65-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="e9b65-129">El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad **Presupuesto** para realizar un seguimiento constante si el presupuesto de ventas se compone por completo de productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="e9b65-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="e9b65-130">Si un presupuesto de ventas solo tiene productos mantenidos externamente, los productos se mantienen en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="e9b65-131">Este comportamiento ayuda a garantizar que no intenta sincronizar las líneas de presupuesto de ventas que tienen productos desconocidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="e9b65-132">Todos los productos de presupuestos en el presupuesto de ventas se actualizan con información de **Solo tiene productos mantenidos externamente** de la cabecera de presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="e9b65-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="e9b65-133">Esta información se encuentra en el campo **Solo tiene productos mantenidos externamente** en la entidad **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="e9b65-134">Un descuento se puede agregar al producto de presupuesto y será sincronizado con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="e9b65-135">Los campos **Descuento**, **Cargos** e **Impuestos** en el encabezado se controlan mediante una configuración compleja en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="e9b65-136">Actualmente esta configuración no admite la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="e9b65-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="e9b65-137">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son mantenidos y gestionados en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="e9b65-138">En Sales, la solución crea los siguientes campos de solo lectura, ya que los valores no se sincronizan con Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e9b65-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="e9b65-139">Campos de solo lectura en el encabezado del presupuesto de ventas: **% de descuento**, **Descuento** e **Importe del fleje**</span><span class="sxs-lookup"><span data-stu-id="e9b65-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="e9b65-140">Campos de sólo lectura de productos de presupuesto: **Impuestos**</span><span class="sxs-lookup"><span data-stu-id="e9b65-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="e9b65-141">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="e9b65-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="e9b65-142">Antes de sincronizar presupuestos de ventas, es importante actualizar la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9b65-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="e9b65-143">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="e9b65-143">Setup in Sales</span></span>

- <span data-ttu-id="e9b65-144">Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión establecida en Sales.</span><span class="sxs-lookup"><span data-stu-id="e9b65-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="e9b65-145">Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo.</span><span class="sxs-lookup"><span data-stu-id="e9b65-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="e9b65-146">Si el equipo no tiene derechos de administrador cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.</span><span class="sxs-lookup"><span data-stu-id="e9b65-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="e9b65-147">Para configurar permisos para el equipo, vaya a **Configuración** &gt; **Seguridad** &gt; **Equipos**, y seleccione el equipo relevante.</span><span class="sxs-lookup"><span data-stu-id="e9b65-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="e9b65-148">Seleccione **Gestionar roles**, y seleccione un rol que tenga los permisos necesarios, como **Administrador del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="e9b65-149">Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Sales**, y asegúrese de que se utilicen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9b65-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="e9b65-150">La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="e9b65-151">El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="e9b65-152">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="e9b65-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="e9b65-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e9b65-153">QuoteHeader</span></span>

- <span data-ttu-id="e9b65-154">Asegúrese de que la asignación requerida existe para **Shipto\_country** como **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="e9b65-155">En la asignación de valor, puede definir un valor predeterminado que se usa si el valor se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="e9b65-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="e9b65-156">Simplemente deje en blanco el lado izquierdo, y establezca el lado derecho como el país o la región deseada.</span><span class="sxs-lookup"><span data-stu-id="e9b65-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="e9b65-157">De esta manera, no es necesario escribir el país o la región para pedidos nacionales.</span><span class="sxs-lookup"><span data-stu-id="e9b65-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="e9b65-158">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones, y donde un valor en blanco es igual a un valor **US**</span><span class="sxs-lookup"><span data-stu-id="e9b65-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="e9b65-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e9b65-159">QuoteLine</span></span>

- <span data-ttu-id="e9b65-160">Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="e9b65-161">Asegúrese de que las unidades necesarias están definidas en Sales.</span><span class="sxs-lookup"><span data-stu-id="e9b65-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="e9b65-162">Un valor de plantilla que tiene una asignación de valores se define para **oumid.name** como **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="e9b65-163">Opcional: Puede agregar las siguientes asignaciones para ayudar a garantizar que las líneas de presupuesto de ventas se importan en Finance and Operations si no hay información predeterminada del cliente o del producto:</span><span class="sxs-lookup"><span data-stu-id="e9b65-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="e9b65-164">**SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e9b65-165">No hay valor de plantilla predeterminado para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="e9b65-166">**WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e9b65-167">No hay valor de plantilla predeterminado para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="e9b65-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="e9b65-168">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="e9b65-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="e9b65-169">Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="e9b65-170">Actualmente esta configuración no admite la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="e9b65-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="e9b65-171">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados por Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e9b65-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="e9b65-172">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="e9b65-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="e9b65-173">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="e9b65-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="e9b65-174">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="e9b65-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="e9b65-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e9b65-175">QuoteHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="e9b65-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e9b65-177">QuoteLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="e9b65-179">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e9b65-179">Related topics</span></span>

[<span data-ttu-id="e9b65-180">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="e9b65-180">Prospect to cash</span></span>](prospect-to-cash.md)


