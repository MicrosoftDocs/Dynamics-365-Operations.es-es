---
title: Sincronizar encabezados y líneas de presupuesto de ventas directamente desde Sales a Supply Chain Management
description: En el tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuestos de ventas directamente de Dynamics 365 Sales en Dynamics 365 Supply Chain Management.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: a1cf4072cb873ebbf4e0e46f16771458e436bcac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243114"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a><span data-ttu-id="d2d98-103">Sincronizar encabezados y líneas de presupuesto de ventas directamente desde Sales a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d2d98-103">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d2d98-104">En el tema se abordan las plantillas y las tareas subyacentes que se usan para sincronizar encabezados y líneas del presupuestos de ventas directamente de Dynamics 365 Sales en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d98-105">Para poder usar la solución Prospect to cash, deberá familiarizarse con [Integración de datos en Microsoft Dataverse para aplicaciones](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="d2d98-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="d2d98-106">Flujo de datos en Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="d2d98-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="d2d98-107">La solución Prospect to cash usa la característica de integración de datos para sincronizar datos a través de las instancias de Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="d2d98-108">Las plantillas de Prospect to cash disponibles con la característica de integración de datos permiten el flujo de datos de cuentas, contactos, productos, presupuestos de ventas, pedidos de ventas y facturas de ventas entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="d2d98-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Supply Chain Management y Sales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="d2d98-110">[![Flujo de datos en Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="d2d98-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="d2d98-111">Plantilla y tareas</span><span class="sxs-lookup"><span data-stu-id="d2d98-111">Template and tasks</span></span>

<span data-ttu-id="d2d98-112">La plantilla y las tareas subyacentes siguientes se usan para sincronizar encabezados y líneas del presupuestos de ventas directamente de Sales a Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="d2d98-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="d2d98-113">**Nombre de la plantilla en la integración de datos:** Presupuestos de ventas (Sales a Supply Chain Management) - Directos</span><span class="sxs-lookup"><span data-stu-id="d2d98-113">**Name of the template in Data integration:** Sales Quotes (Sales to Supply Chain Management) - Direct</span></span>
- <span data-ttu-id="d2d98-114">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="d2d98-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="d2d98-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d2d98-115">QuoteHeader</span></span>
    - <span data-ttu-id="d2d98-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d2d98-116">QuoteLine</span></span>

<span data-ttu-id="d2d98-117">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del presupuesto de ventas:</span><span class="sxs-lookup"><span data-stu-id="d2d98-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="d2d98-118">Productos (Supply Chain Management a Sales) - Directo</span><span class="sxs-lookup"><span data-stu-id="d2d98-118">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="d2d98-119">Cuentas (Sales a Supply Chain Management) - Directo (si se usa)</span><span class="sxs-lookup"><span data-stu-id="d2d98-119">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="d2d98-120">Contactos a clientes (de Sales a Supply Chain Management) - Directo (si se usa)</span><span class="sxs-lookup"><span data-stu-id="d2d98-120">Contacts to Customers (Sales to Supply Chain Management) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="d2d98-121">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="d2d98-121">Entity set</span></span>

| <span data-ttu-id="d2d98-122">Sales</span><span class="sxs-lookup"><span data-stu-id="d2d98-122">Sales</span></span>        | <span data-ttu-id="d2d98-123">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="d2d98-123">Supply Chain Management</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="d2d98-124">Ofertas</span><span class="sxs-lookup"><span data-stu-id="d2d98-124">Quotes</span></span>       | <span data-ttu-id="d2d98-125">Encabezado de presupuesto de ventas de Dataverse</span><span class="sxs-lookup"><span data-stu-id="d2d98-125">Dataverse sales quotation header</span></span> |
| <span data-ttu-id="d2d98-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="d2d98-126">QuoteDetails</span></span> | <span data-ttu-id="d2d98-127">Líneas de presupuesto de ventas de Dataverse</span><span class="sxs-lookup"><span data-stu-id="d2d98-127">Dataverse sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="d2d98-128">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="d2d98-128">Entity flow</span></span>

<span data-ttu-id="d2d98-129">Los presupuestos de ventas se crean en Sales y se sincronizan en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-129">Sales quotations are created in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="d2d98-130">Los presupuestos de ventas de Sales se sincronizan solo si se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="d2d98-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="d2d98-131">Todos los productos de presupuestos en las líneas de ventas se mantienen externamente.</span><span class="sxs-lookup"><span data-stu-id="d2d98-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="d2d98-132">Tras hacer clic en **Activar presupuesto**, el presupuesto de ventas se activa.</span><span class="sxs-lookup"><span data-stu-id="d2d98-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d2d98-133">Cliente potencial para cobrar la solución por Sales</span><span class="sxs-lookup"><span data-stu-id="d2d98-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="d2d98-134">El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad **Presupuesto** para realizar un seguimiento constante si el presupuesto de ventas se compone por completo de productos mantenidos externamente.</span><span class="sxs-lookup"><span data-stu-id="d2d98-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="d2d98-135">Si un presupuesto de ventas solo tiene productos mantenidos externamente, los productos se mantienen en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-135">If a sales quotation has only externally maintained products, the products are maintained in Supply Chain Management.</span></span> <span data-ttu-id="d2d98-136">Este comportamiento ayuda a garantizar que no intenta sincronizar las líneas de presupuesto de ventas que tienen productos desconocidos para Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Supply Chain Management.</span></span>

<span data-ttu-id="d2d98-137">Todos los productos de presupuestos en el presupuesto de ventas se actualizan con información de **Solo tiene productos mantenidos externamente** de la cabecera de presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="d2d98-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="d2d98-138">Esta información se encuentra en el campo **Solo tiene productos mantenidos externamente** en la entidad **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="d2d98-139">Un descuento se puede agregar al producto de presupuesto y será sincronizado con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-139">A discount can be added to the quote product and will be synchronized to Supply Chain Management.</span></span> <span data-ttu-id="d2d98-140">Los campos **Descuento**, **Cargos** e **Impuestos** en el encabezado se controlan mediante una configuración compleja en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Supply Chain Management.</span></span> <span data-ttu-id="d2d98-141">Actualmente esta configuración no admite la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="d2d98-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="d2d98-142">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son mantenidos y gestionados en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in FSupply Chain Management.</span></span>

<span data-ttu-id="d2d98-143">En Sales, la solución crea los siguientes campos de solo lectura, ya que los valores no se sincronizan con Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="d2d98-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Supply Chain Management:</span></span>

- <span data-ttu-id="d2d98-144">Campos de solo lectura en el encabezado del presupuesto de ventas: **% de descuento**, **Descuento** e **Importe del flete**</span><span class="sxs-lookup"><span data-stu-id="d2d98-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="d2d98-145">Campos de sólo lectura de productos de presupuesto: **Impuestos**</span><span class="sxs-lookup"><span data-stu-id="d2d98-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d2d98-146">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="d2d98-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="d2d98-147">Antes de sincronizar presupuestos de ventas, es importante actualizar la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2d98-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="d2d98-148">Configuración en Sales</span><span class="sxs-lookup"><span data-stu-id="d2d98-148">Setup in Sales</span></span>

- <span data-ttu-id="d2d98-149">Asegúrese de que los permisos se configuran para el equipo al que está asignado el usuario desde la conexión establecida en Sales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="d2d98-150">Si utiliza datos de prueba, el usuario normalmente tiene acceso de administrador, pero no el equipo.</span><span class="sxs-lookup"><span data-stu-id="d2d98-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="d2d98-151">Si el equipo no tiene derechos de administrador cuando usted ejecuta el proyecto desde la integración de datos, recibirá un mensaje de error que dice que falta el equipo principal.</span><span class="sxs-lookup"><span data-stu-id="d2d98-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="d2d98-152">Para configurar permisos para el equipo, vaya a **Configuración** &gt; **Seguridad** &gt; **Equipos**, y seleccione el equipo relevante.</span><span class="sxs-lookup"><span data-stu-id="d2d98-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="d2d98-153">Seleccione **Gestionar roles**, y seleccione un rol que tenga los permisos necesarios, como **Administrador del sistema**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="d2d98-154">Vaya a **Configuración** &gt; **Administración** &gt; **Configuración del sistema** &gt; **Sales**, y asegúrese de que se utilicen los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d2d98-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="d2d98-155">La opción **Usar el sistema de cálculo del sistema de precios** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="d2d98-156">El campo **Método de cálculo de descuentos** se establece en **Artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="d2d98-157">Configuración del proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="d2d98-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="d2d98-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d2d98-158">QuoteHeader</span></span>

- <span data-ttu-id="d2d98-159">Asegúrese de que la asignación requerida existe para **Shipto\_country** como **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="d2d98-160">En la asignación de valor, puede definir un valor predeterminado que se usa si el valor se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="d2d98-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="d2d98-161">Simplemente deje en blanco el lado izquierdo, y establezca el lado derecho como el país o la región deseada.</span><span class="sxs-lookup"><span data-stu-id="d2d98-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="d2d98-162">De esta manera, no es necesario escribir el país o la región para pedidos nacionales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="d2d98-163">El valor de plantilla es una asignación de valores en la que se asignan varios países o regiones, y donde un valor en blanco es igual a un valor **US**</span><span class="sxs-lookup"><span data-stu-id="d2d98-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="d2d98-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d2d98-164">QuoteLine</span></span>

- <span data-ttu-id="d2d98-165">Asegúrese de que existe la asignación de valores requerida para **SalesUnitSymbol** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-165">Make sure that the required value map exists for **SalesUnitSymbol** in Supply Chain Management.</span></span>
- <span data-ttu-id="d2d98-166">Asegúrese de que las unidades necesarias están definidas en Sales.</span><span class="sxs-lookup"><span data-stu-id="d2d98-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="d2d98-167">Un valor de plantilla que tiene una asignación de valores se define para **oumid.name** como **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="d2d98-168">Opcional: Puede agregar las siguientes asignaciones para ayudar a garantizar que las líneas de presupuesto de ventas se importan en Supply Chain Management si no hay información predeterminada del cliente o del producto:</span><span class="sxs-lookup"><span data-stu-id="d2d98-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Supply Chain Management if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="d2d98-169">**SiteId** – Se requiere un sitio para generar presupuestos y las líneas de pedido de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="d2d98-170">No hay valor de plantilla predeterminado para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="d2d98-171">**WarehouseId** – Se requiere un almacén para procesar presupuestos y las líneas de pedido de ventas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="d2d98-172">No hay valor de plantilla predeterminado para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="d2d98-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="d2d98-173">Asignación de la plantilla en el integrador de datos</span><span class="sxs-lookup"><span data-stu-id="d2d98-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="d2d98-174">Los campos **Descuento**, **Cargos** e **Impuestos** se controlan mediante una configuración compleja en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Supply Chain Management.</span></span> <span data-ttu-id="d2d98-175">Actualmente esta configuración no admite la asignación de la integración.</span><span class="sxs-lookup"><span data-stu-id="d2d98-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="d2d98-176">En el diseño actual, los campos **Precio**, **Descuento**, **Cargo** e **Impuestos** son gestionados por Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d98-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Supply Chain Management.</span></span>
> - <span data-ttu-id="d2d98-177">Los campos **Condiciones de pago**, **Condiciones de carga**, **Condiciones de entrega**, **Método de envío**, y **Modo de entrega** no forman parte de las asignaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d2d98-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="d2d98-178">Para asignar estos campos, debe configurar una asignación de valores que sea específica de los datos en las organizaciones entre las que se sincroniza la entidad.</span><span class="sxs-lookup"><span data-stu-id="d2d98-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="d2d98-179">Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.</span><span class="sxs-lookup"><span data-stu-id="d2d98-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="d2d98-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d2d98-180">QuoteHeader</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="d2d98-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d2d98-182">QuoteLine</span></span>

![Asignación de la plantilla en el integrador de datos](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="d2d98-184">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d2d98-184">Related topics</span></span>

[<span data-ttu-id="d2d98-185">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="d2d98-185">Prospect to cash</span></span>](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]