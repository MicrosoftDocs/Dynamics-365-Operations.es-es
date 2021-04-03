---
title: Disponibilidad de inventario en doble escritura
description: Este tema proporciona información sobre cómo comprobar la disponibilidad de inventarios en doble escritura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 48e54c043967ea5db15938857bd8f020dd4dfc64
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566748"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="b4659-103">Disponibilidad de inventario en doble escritura</span><span class="sxs-lookup"><span data-stu-id="b4659-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4659-104">Al utilizar la disponibilidad de inventario, puede verificar su inventario antes de agregar un producto a las páginas **Presupuestos**, **Pedidos** o **Facturas** en aplicaciones en Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b4659-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="b4659-105">Por ejemplo, comprueba el inventario y determina una fecha de cumplimiento como una tarea clave en el proceso [cliente potencial a efectivo](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="b4659-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="b4659-106">Si no tiene suficiente inventario, puede estimar una fecha de entrega basada en los recibos y problemas de inventario proyectados.</span><span class="sxs-lookup"><span data-stu-id="b4659-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="b4659-107">También puede verificar la información de neto no comprometido (ATP), donde puede encontrar la cantidad de ATP en el intervalo de tiempo predefinido.</span><span class="sxs-lookup"><span data-stu-id="b4659-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="b4659-108">Inventario disponible</span><span class="sxs-lookup"><span data-stu-id="b4659-108">On-hand inventory</span></span>

<span data-ttu-id="b4659-109">En Dynamics 365 Sales, se ha agregado un nuevo botón **Inventario disponible** al encabezado de las páginas **Presupuestos**, **Pedidos** y **Facturas**.</span><span class="sxs-lookup"><span data-stu-id="b4659-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="b4659-110">Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa y el producto para el que desea comprobar el inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="b4659-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="b4659-111">Este cuadro de diálogo muestra la misma información que [Inventario disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="b4659-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="b4659-112">El cuadro de diálogo devuelve la información de inventario desde Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b4659-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b4659-113">Esta información incluye las siguientes cantidades:</span><span class="sxs-lookup"><span data-stu-id="b4659-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="b4659-114">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="b4659-114">On-hand quantity</span></span>
- <span data-ttu-id="b4659-115">Cantidad disponible reservada</span><span class="sxs-lookup"><span data-stu-id="b4659-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="b4659-116">Cantidad disponible lista</span><span class="sxs-lookup"><span data-stu-id="b4659-116">Available on-hand quantity</span></span>
- <span data-ttu-id="b4659-117">Cantidad pedida</span><span class="sxs-lookup"><span data-stu-id="b4659-117">Ordered quantity</span></span>
- <span data-ttu-id="b4659-118">Cantidad en pedido</span><span class="sxs-lookup"><span data-stu-id="b4659-118">On-order quantity</span></span>
- <span data-ttu-id="b4659-119">Cantidad solicitada reservada</span><span class="sxs-lookup"><span data-stu-id="b4659-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="b4659-120">Cantidad total disponible</span><span class="sxs-lookup"><span data-stu-id="b4659-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="b4659-121">Información de NNC</span><span class="sxs-lookup"><span data-stu-id="b4659-121">ATP information</span></span>

<span data-ttu-id="b4659-122">En Sales, se ha agregado un nuevo botón **Información de NNC** a los artículos de línea en las páginas **Presupuestos**, **Pedidos** y **Facturas**.</span><span class="sxs-lookup"><span data-stu-id="b4659-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="b4659-123">Cuando selecciona este botón, aparece un cuadro de diálogo, donde puede especificar la empresa, el producto, el sitio del inventario, el almacén de inventario y la cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="b4659-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="b4659-124">Este cuadro de diálogo tiene la misma configuración que se describe en [Compromisos de pedido](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="b4659-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="b4659-125">El cuadro de diálogo devuelve la información de NNC de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b4659-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="b4659-126">Esta información incluye las siguientes cantidades:</span><span class="sxs-lookup"><span data-stu-id="b4659-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="b4659-127">Cantidad de NNC</span><span class="sxs-lookup"><span data-stu-id="b4659-127">ATP quantity</span></span>
- <span data-ttu-id="b4659-128">Cantidad de recepción</span><span class="sxs-lookup"><span data-stu-id="b4659-128">Receipt quantity</span></span>
- <span data-ttu-id="b4659-129">Cantidad de emisión</span><span class="sxs-lookup"><span data-stu-id="b4659-129">Issue quantity</span></span>
- <span data-ttu-id="b4659-130">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="b4659-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b4659-131">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="b4659-131">How it works</span></span>

<span data-ttu-id="b4659-132">Cuando selecciona el botón **Inventario disponible** en la página **Ofertas**, **Pedidos** o **Facturas**, se realiza una llamada de escritura dual en vivo a la API **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="b4659-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="b4659-133">La API calcula el inventario disponible para el producto dado.</span><span class="sxs-lookup"><span data-stu-id="b4659-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="b4659-134">El resultado se almacena en **InventCDSInventoryOnHandRequestEntity** y en las tablas **InventCDSInventoryOnHandEntryEntity**, y luego se escribe en Dataverse mediante escritura dual.</span><span class="sxs-lookup"><span data-stu-id="b4659-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="b4659-135">Para utilizar esta funcionalidad, debe ejecutar los siguientes mapas de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="b4659-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="b4659-136">Omita la sincronización inicial cuando ejecute los mapas.</span><span class="sxs-lookup"><span data-stu-id="b4659-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="b4659-137">Entradas de inventario de CDS disponibles (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="b4659-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="b4659-138">Solicitudes de inventario de CDS disponibles (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="b4659-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="b4659-139">Plantillas</span><span class="sxs-lookup"><span data-stu-id="b4659-139">Templates</span></span>
<span data-ttu-id="b4659-140">Las siguientes plantillas están disponibles para exponer los datos de inventario disponibles.</span><span class="sxs-lookup"><span data-stu-id="b4659-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="b4659-141">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b4659-141">Finance and Operations apps</span></span> | <span data-ttu-id="b4659-142">Aplicación Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="b4659-142">Customer engagement app</span></span> | <span data-ttu-id="b4659-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4659-143">Description</span></span> 
---|---|---
[<span data-ttu-id="b4659-144">Entradas disponibles del inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="b4659-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="b4659-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="b4659-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="b4659-146">Solicitudes disponibles del inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="b4659-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="b4659-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="b4659-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="b4659-148">Entradas de inventario de CDS disponibles (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="b4659-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="b4659-149">Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b4659-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="b4659-150">Campo de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b4659-150">Finance and Operations field</span></span> | <span data-ttu-id="b4659-151">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="b4659-151">Map type</span></span> | <span data-ttu-id="b4659-152">Campo Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="b4659-152">Customer engagement field</span></span> | <span data-ttu-id="b4659-153">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b4659-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="b4659-154">Solicitudes de inventario de CDS disponibles (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="b4659-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="b4659-155">Esta plantilla sincroniza datos entre aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b4659-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="b4659-156">Campo de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b4659-156">Finance and Operations field</span></span> | <span data-ttu-id="b4659-157">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="b4659-157">Map type</span></span> | <span data-ttu-id="b4659-158">Campo Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="b4659-158">Customer engagement field</span></span> | <span data-ttu-id="b4659-159">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b4659-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]