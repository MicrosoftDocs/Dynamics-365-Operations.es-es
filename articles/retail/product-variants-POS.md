---
title: "Búsqueda de inventario en el punto de venta"
description: "En este tema se describen las opciones disponibles para ver la información de inventario en el punto de venta (PDV)."
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 933875f56b0f47990cb1cb767f84b23b9c9710d4
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="inventory-lookup-in-the-point-of-sale"></a><span data-ttu-id="bf5be-103">Búsqueda de inventario en el punto de venta</span><span class="sxs-lookup"><span data-stu-id="bf5be-103">Inventory lookup in the Point of Sale</span></span> 

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="bf5be-104">La búsqueda de inventario en el punto de venta (PDV) ayuda a los minoristas a lograr la excelencia operativa en tiempo real y obtener información conectando tiendas, el PDV y el back-office.</span><span class="sxs-lookup"><span data-stu-id="bf5be-104">Inventory lookup in the point of sale (POS) helps retailers achieve real-time operational excellence and gain insights by connecting stores, the POS, and the back office.</span></span> <span data-ttu-id="bf5be-105">Esta funcionalidad proporciona una vista precisa en tiempo real del inventario del producto en tiendas y centros de distribución.</span><span class="sxs-lookup"><span data-stu-id="bf5be-105">This functionality provides an accurate real-time view of product inventory across stores and distribution centers.</span></span> <span data-ttu-id="bf5be-106">También ayuda a los minoristas a impulsar eficacias adicionales y ahorro de costes al mejorar la planificación del inventario en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bf5be-106">It also helps retailers drive additional efficiencies and cost savings by improving inventory planning in real time.</span></span>

<span data-ttu-id="bf5be-107">Una vista precisa en tiempo real del inventario en una organización ayuda a los socios del almacén a proporcionar un servicio al cliente oportuno y superior.</span><span class="sxs-lookup"><span data-stu-id="bf5be-107">An accurate real-time view of inventory across an organization helps store associates provide timely, superior customer service.</span></span> <span data-ttu-id="bf5be-108">El momento que más importa es el momento en que el cliente está listo para tomar una decisión de compra.</span><span class="sxs-lookup"><span data-stu-id="bf5be-108">The moment that matters most is the moment when the customer is ready to make a purchase decision.</span></span> <span data-ttu-id="bf5be-109">Es importante que los cajeros de la tienda tenga información en tiempo real sobre el inventario a su alcance, de modo que puedan comprometer con precisión la entrega y la recogida del producto.</span><span class="sxs-lookup"><span data-stu-id="bf5be-109">It's important that cashiers in the store have real-time inventory information at their fingertips, so that they can accurately promise product delivery and pickup.</span></span>

<span data-ttu-id="bf5be-110">Puede abrir la página **Búsqueda de inventario** del espacio de trabajo **Retail Modern POS** o del espacio de trabajo **Retail Cloud POS**.</span><span class="sxs-lookup"><span data-stu-id="bf5be-110">You can open the **Inventory lookup** page from the **Retail Modern POS** workspace or the **Retail Cloud POS** workspace.</span></span>

![Icono de búsqueda de inventario en la página de inicio de PDV](media/POSHomepage.png)

<span data-ttu-id="bf5be-112">En la página **Búsqueda de inventario**, puede utilizar el teclado numérico para introducir un número de producto.</span><span class="sxs-lookup"><span data-stu-id="bf5be-112">On the **Inventory lookup** page, you can use the numeric keyboard to enter a product number.</span></span> <span data-ttu-id="bf5be-113">Puede ver la cantidad disponible para múltiples tiendas y almacenes.</span><span class="sxs-lookup"><span data-stu-id="bf5be-113">You can then view the on-hand quantity for multiple stores and warehouses.</span></span>

![Página de búsqueda de inventario estándar](media/InventoryLookUp.png)

<span data-ttu-id="bf5be-115">Las cantidades **Reservado** y **Pedido** también se muestran para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf5be-115">**Reserved** and **Ordered** quantities are also shown for each location.</span></span>

- <span data-ttu-id="bf5be-116">**Reservado**: la cantidad hace referencia al valor **Física reservada** del back-office para el número de producto especificado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf5be-116">**Reserved** – This quantity refers to the **Physical reserved** value from the back office for the specified product number at the location.</span></span>
- <span data-ttu-id="bf5be-117">**Pedido**: esta cantidad hace referencia al valor **Pedido en total** del back-office para el número de producto especificado en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf5be-117">**Ordered** – This quantity refers to the **Ordered in total** value from the back office for the specified product number at the location.</span></span>

## <a name="locations-that-inventory-availability-information-is-shown-for"></a><span data-ttu-id="bf5be-118">Ubicaciones para las que se muestra información de disponibilidad del inventario</span><span class="sxs-lookup"><span data-stu-id="bf5be-118">Locations that inventory availability information is shown for</span></span>

<span data-ttu-id="bf5be-119">La lista de ubicaciones incluye dos tipos de entidades:</span><span class="sxs-lookup"><span data-stu-id="bf5be-119">The list of locations includes two types of entities:</span></span>

- <span data-ttu-id="bf5be-120">**Tiendas minoristas**: la lista muestra las tiendas que se configuran usando el grupo de localizadores de tiendas para la tienda actual en Central Retail.</span><span class="sxs-lookup"><span data-stu-id="bf5be-120">**Retail stores** – The list shows stores that are configured by using the store locator group for the current store in the Retail headquarters.</span></span> 
- <span data-ttu-id="bf5be-121">**Centros de distribución**: los distintos tipos de centros de distribución (como almacenes) pueden configurarse en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="bf5be-121">**Distribution centers** – Various types of distribution centers (such as warehouses) can be configured in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="bf5be-122">Sin embargo, la lista muestra información de disponibilidad del inventario solo para centros de distribución del tipo predeterminado **Estándar** .</span><span class="sxs-lookup"><span data-stu-id="bf5be-122">However, the list shows inventory availability information only for distribution centers of the **Standard** default type.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="bf5be-123">La información de disponibilidad del inventario no se muestra para almacenes de los tipos **Tránsito**, **Cuarentena** y **Mercancías en ruta** para el PDV.</span><span class="sxs-lookup"><span data-stu-id="bf5be-123">Inventory availability information isn't shown for warehouses of the **Transit**, **Quarantine**, and **Goods in Route** types for the POS.</span></span>

<span data-ttu-id="bf5be-124">En la página **Búsqueda de inventario**, puede ver las cantidades de neto no comprometido (NNC) para cada tienda, además de las cantidades disponibles actuales, las cantidades reservadas y las cantidades pedidas.</span><span class="sxs-lookup"><span data-stu-id="bf5be-124">On the **Inventory lookup** page, you can view available to promise (ATP) quantities for each store, in addition to the current on-hand quantities, reserved quantities, and ordered quantities.</span></span> <span data-ttu-id="bf5be-125">Seleccione la tienda para ver la información de NNC y, a continuación, seleccione **Mostrar disponibilidad en tienda**.</span><span class="sxs-lookup"><span data-stu-id="bf5be-125">Select the store to view the ATP information for, and then select **Show store availability**.</span></span>

![Cantidades ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a><span data-ttu-id="bf5be-127">Apertura de la vista Matriz basada en dimensión para mostrar todas las variantes</span><span class="sxs-lookup"><span data-stu-id="bf5be-127">Opening the Dimension based matrix view to show all variants</span></span>

<span data-ttu-id="bf5be-128">En la página **Detalles de producto** de un producto maestro, o en la página **Búsqueda de inventario**, seleccione **Ver todas las variantes** desde la barra de la aplicación en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="bf5be-128">On the **Product details** page of a product master, or on the **Inventory lookup** page, select **View all variants** from the app-bar at bottom of the page.</span></span> <span data-ttu-id="bf5be-129">La vista **Matriz basada en dimensión** para la versión inicial de estas páginas muestra la información de disponibilidad del inventario para todas las variantes de un producto para la tienda actual.</span><span class="sxs-lookup"><span data-stu-id="bf5be-129">The **Dimension based matrix** view for the initial launch from these pages shows the inventory availability information for all variants of a product for the current store.</span></span>

> [!NOTE]
> <span data-ttu-id="bf5be-130">El botón **Ver todas las variantes** solo está disponible para los productos maestros del artículo que tienen variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="bf5be-130">The **View all variants** button is available only for item product masters that have product variants.</span></span> <span data-ttu-id="bf5be-131">No está disponible para productos o kits independientes.</span><span class="sxs-lookup"><span data-stu-id="bf5be-131">It isn't available for standalone products or kits.</span></span>

![Permite ver el botón de todas las variantes en la página Búsqueda de inventario](media/StandardToMatrix.png)

<span data-ttu-id="bf5be-133">Seleccione **Ver todas las variantes** en la página **Detalles de producto** de un producto maestro, o en la página **Búsqueda de inventario**, sin seleccionar una ubicación, para ir a la vista **Matriz basada en dimensión** y ver la información de disponibilidad del inventario para todas las variantes de un producto para la tienda actual.</span><span class="sxs-lookup"><span data-stu-id="bf5be-133">Select **View all variants** on the **Product details** page of a product master, or on the **Inventory lookup** page, without selecting a location, to go to the **Dimension based matrix** view to view the inventory availability information for all variants of a product for the current store.</span></span>

![Vista Matriz basada en dimensión para la página Búsqueda de inventario](media/Matrix.png)

> [!NOTE]
> <span data-ttu-id="bf5be-135">En la ilustración anterior, el orden de visualización de las dimensiones es alfabético, ya que el orden de visualización de dimensiones no se configuró para el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bf5be-135">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="bf5be-136">En la vista **Matriz basada en dimensión**, las celdas para las variantes de producto incluyen un valor disponible en la esquina inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="bf5be-136">In the **Dimension based matrix** view, the cells for the product variants include an on-hand value in the lower-right corner.</span></span> <span data-ttu-id="bf5be-137">La siguiente tabla explica el significado de los distintos valores.</span><span class="sxs-lookup"><span data-stu-id="bf5be-137">The following table explains the meaning of the various values.</span></span>

| <span data-ttu-id="bf5be-138">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="bf5be-138">On-hand value</span></span>                            | <span data-ttu-id="bf5be-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf5be-139">Description</span></span> |
|------------------------------------------|-------------|
| <span data-ttu-id="bf5be-140">Valor numérico que es superior a 0 (cero)</span><span class="sxs-lookup"><span data-stu-id="bf5be-140">Numeric value that is more than 0 (zero)</span></span> | <span data-ttu-id="bf5be-141">Se liberó una variante para la ubicación seleccionada y puede realizar acciones adicionales en la celda.</span><span class="sxs-lookup"><span data-stu-id="bf5be-141">A variant has been released to the selected location, and you can perform additional actions in the cell.</span></span> <span data-ttu-id="bf5be-142">(Estas acciones se describirán con más detalle más adelante en este tema.)</span><span class="sxs-lookup"><span data-stu-id="bf5be-142">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="bf5be-143">**0** (cero)</span><span class="sxs-lookup"><span data-stu-id="bf5be-143">**0** (zero)</span></span>                             | <span data-ttu-id="bf5be-144">Se liberó una variante para la ubicación seleccionada, pero el artículo no está disponible en la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5be-144">A variant has been released to the selected location, but the item isn't available in selected location.</span></span> <span data-ttu-id="bf5be-145">Sin embargo, puede realizar acciones adicionales en la celda.</span><span class="sxs-lookup"><span data-stu-id="bf5be-145">However, you can perform additional actions in the cell.</span></span> <span data-ttu-id="bf5be-146">(Estas acciones se describirán con más detalle más adelante en este tema.)</span><span class="sxs-lookup"><span data-stu-id="bf5be-146">(These actions are described in more detail later in this topic.)</span></span> |
| <span data-ttu-id="bf5be-147">**n/a** o una celda inactiva</span><span class="sxs-lookup"><span data-stu-id="bf5be-147">**n/a** or an inactive cell</span></span>              | <span data-ttu-id="bf5be-148">No se liberó una variante para la ubicación seleccionada y no puede realizar acciones adicionales en la celda.</span><span class="sxs-lookup"><span data-stu-id="bf5be-148">A variant hasn't been released to the selected location, and you can't perform additional actions in the cell.</span></span> |

<span data-ttu-id="bf5be-149">También puede cambiar el pivote para las dimensiones seleccionando la nueva dimensión a utilizar.</span><span class="sxs-lookup"><span data-stu-id="bf5be-149">You can also change the pivot for dimensions by selecting the new dimension to use.</span></span> 

![Cambio de pivote](media/ChangePivot.png)

![Pivote modificado](media/PivotChanged.png)

> [!NOTE]
> <span data-ttu-id="bf5be-152">En las ilustraciones anteriores, el orden de visualización de las dimensiones del producto seleccionado es personalizado (no alfabético).</span><span class="sxs-lookup"><span data-stu-id="bf5be-152">In the preceding illustrations, the display order of the dimensions for the selected product is custom (non-alphabetic).</span></span> <span data-ttu-id="bf5be-153">Se basa en el orden de visualización de la dimensión que se establece en el back-office.</span><span class="sxs-lookup"><span data-stu-id="bf5be-153">It's based on the dimension display order that is set in the back office.</span></span>

<span data-ttu-id="bf5be-154">Además, en el vista **Matriz basada en dimensión** se pueden realizar más acciones para ayudar a aumentar la productividad de un socio de la tienda.</span><span class="sxs-lookup"><span data-stu-id="bf5be-154">Additionally, in the **Dimension based matrix** view, more actions can be performed to help boost a store associate's productivity.</span></span> <span data-ttu-id="bf5be-155">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="bf5be-155">Here are some examples:</span></span>

- <span data-ttu-id="bf5be-156">Cambie la ubicación de la tienda para buscar la disponibilidad del inventario de todas las variantes de producto en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="bf5be-156">Change the store location to look up the inventory availability of all product variants at other locations.</span></span> <span data-ttu-id="bf5be-157">Estas ubicaciones incluyen otras tiendas en el grupo de localizadores de tiendas y los centros de distribución del tipo predeterminado **Estándar** .</span><span class="sxs-lookup"><span data-stu-id="bf5be-157">These locations include other stores in the store locator group and distribution centers of the **Standard** default type.</span></span>
- <span data-ttu-id="bf5be-158">Venda una variante del producto individual a un cliente mediante el uso de pago al contado sin entrega al domicilio, recogida en tienda o envío a una dirección.</span><span class="sxs-lookup"><span data-stu-id="bf5be-158">Sell an individual product variant to a customer by using cash and carry, in-store pickup, or shipment to an address.</span></span>
- <span data-ttu-id="bf5be-159">Proporcione al cliente información de NNC para una variante del producto individual en una ubicación concreta.</span><span class="sxs-lookup"><span data-stu-id="bf5be-159">Provide the customer with ATP information for an individual product variant at a specific location.</span></span>

![Acciones adicionales en los iconos de variantes](media/VariantActions.png)

> [!NOTE]
> <span data-ttu-id="bf5be-161">En la ilustración anterior, el orden de visualización de las dimensiones es alfabético, ya que el orden de visualización de dimensiones no se configuró para el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bf5be-161">In the preceding illustration, the display order of the dimensions is alphabetic, because the display order of dimensions wasn't configured for the selected product.</span></span>

<span data-ttu-id="bf5be-162">La siguiente tabla ofrece más información acerca de las acciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="bf5be-162">The following table provides more information about the additional actions that are available.</span></span>


|        <span data-ttu-id="bf5be-163">Acción</span><span class="sxs-lookup"><span data-stu-id="bf5be-163">Action</span></span>        |                                                                                                                    <span data-ttu-id="bf5be-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf5be-164">Description</span></span>                                                                                                                    |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="bf5be-165">Vender ahora</span><span class="sxs-lookup"><span data-stu-id="bf5be-165">Sell now</span></span>       |                               <span data-ttu-id="bf5be-166">Agregue la variante del artículo seleccionada a la transacción y redirija al usuario a la pantalla de transacción.</span><span class="sxs-lookup"><span data-stu-id="bf5be-166">Add the selected item variant to the transaction, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="bf5be-167">(Esta acción no está disponible cuando la ubicación seleccionada es un centro de distribución.)</span><span class="sxs-lookup"><span data-stu-id="bf5be-167">(This action isn't available when the selected location is a distribution center.)</span></span>                               |
|   <span data-ttu-id="bf5be-168">Recoger en tienda</span><span class="sxs-lookup"><span data-stu-id="bf5be-168">Pick up in store</span></span>   |      <span data-ttu-id="bf5be-169">Cree un pedido de cliente para la variante del producto que se recogerá de la ubicación seleccionada y redirija al usuario a la pantalla de transacción.</span><span class="sxs-lookup"><span data-stu-id="bf5be-169">Create a customer order for the product variant that will be picked up from the selected location, and redirect the user to the transaction screen.</span></span> <span data-ttu-id="bf5be-170">(Esta acción no está disponible cuando la ubicación seleccionada es un centro de distribución.)</span><span class="sxs-lookup"><span data-stu-id="bf5be-170">(This action isn't available when the selected location is a distribution center.)</span></span>       |
|     <span data-ttu-id="bf5be-171">Enviar producto</span><span class="sxs-lookup"><span data-stu-id="bf5be-171">Ship product</span></span>     |                                                 <span data-ttu-id="bf5be-172">Cree un pedido de cliente para la variante del producto que se enviará desde la ubicación seleccionada y redirija al usuario a la pantalla de transacción.</span><span class="sxs-lookup"><span data-stu-id="bf5be-172">Create a customer order for the product variant that will be shipped from the selected location, and redirect the user to the transaction screen.</span></span>                                                 |
|     <span data-ttu-id="bf5be-173">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="bf5be-173">Availability</span></span>     |                                                                             <span data-ttu-id="bf5be-174">Muestre la información de NNC para la combinación de variantes seleccionada para la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5be-174">Show the ATP information for the selected variant combination for the selected location.</span></span>                                                                              |
|  <span data-ttu-id="bf5be-175">Muestre tzodas las ubicaciones</span><span class="sxs-lookup"><span data-stu-id="bf5be-175">Show all locations</span></span>  | <span data-ttu-id="bf5be-176">Cambie a la vista de búsqueda de inventario estándar y resalte la información de disponibilidad del inventario para la variante de artículo en todas las tiendas del grupo de localizadores de tiendas, y también en centros de distribución de tipo <strong>Estándar/Predeterminado</strong>.</span><span class="sxs-lookup"><span data-stu-id="bf5be-176">Switch to the standard inventory lookup view, and highlight inventory availability information for the item variant across all stores in the store locator group, and also in distribution centers of the <strong>Standard/Default</strong> type.</span></span> |
| <span data-ttu-id="bf5be-177">Ver detalles del producto</span><span class="sxs-lookup"><span data-stu-id="bf5be-177">View product details</span></span> |                                                                         <span data-ttu-id="bf5be-178">Redirija al usuario a la página <strong>Detalles de producto</strong> del producto maestro asociado.</span><span class="sxs-lookup"><span data-stu-id="bf5be-178">Redirect the user to the <strong>Product details</strong> page of the associated product master.</span></span>                                                                          |


