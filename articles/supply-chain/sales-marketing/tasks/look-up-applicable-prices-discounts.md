---
title: Búsqueda de precios y descuentos aplicables
description: Este procedimiento muestra cómo encontrar el precio y/o el descuento para un producto actualmente válido para un cliente concreto, sin crear un pedido de ventas.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ded87dcd553c0aa9c19ca273460f9adf0a4b542
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148639"
---
# <a name="look-up-applicable-prices-and-discounts"></a><span data-ttu-id="9759e-103">Búsqueda de precios y descuentos aplicables</span><span class="sxs-lookup"><span data-stu-id="9759e-103">Look up applicable prices and discounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9759e-104">Este procedimiento muestra cómo encontrar el precio y/o el descuento para un producto actualmente válido para un cliente concreto, sin crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9759e-104">This procedure shows how to find the price and/or discount for a product which is currently valid for a specific customer, without creating a sales order.</span></span> <span data-ttu-id="9759e-105">El procedimiento le guía por un ejemplo específico y, para poder seleccionar los valores necesarios, necesita seguir el ejemplo con la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9759e-105">The procedure walks through a specific example, and you need follow the example using the USMF demo company in order to select the necessary values.</span></span>


## <a name="find-the-applicable-price"></a><span data-ttu-id="9759e-106">Búsqueda del precio aplicable</span><span class="sxs-lookup"><span data-stu-id="9759e-106">Find the applicable price</span></span>
1. <span data-ttu-id="9759e-107">Vaya Ventas y marketing > Precios y descuentos > Buscar precios.</span><span class="sxs-lookup"><span data-stu-id="9759e-107">Go to Sales and marketing > Prices and discounts > Find prices.</span></span>
2. <span data-ttu-id="9759e-108">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9759e-108">In the Customer account field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="9759e-109">En la lista, busque y seleccione el cliente US-001.</span><span class="sxs-lookup"><span data-stu-id="9759e-109">In the list, find and select customer US-001.</span></span>
4. <span data-ttu-id="9759e-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9759e-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9759e-111">En el campo Código de artículo, escriba 'T0004'.</span><span class="sxs-lookup"><span data-stu-id="9759e-111">In the Item number field, type 'T0004'.</span></span>
    * <span data-ttu-id="9759e-112">Por defecto, el campo Cantidad se haya definido en 1.</span><span class="sxs-lookup"><span data-stu-id="9759e-112">By default, the Quantity field is set to 1.</span></span> <span data-ttu-id="9759e-113">No obstante, si conoce el tamaño del pedido que el cliente pretende realizar para el producto en cuestión, especifique en su lugar este valor.</span><span class="sxs-lookup"><span data-stu-id="9759e-113">However, if you know the size of the order that the customer intends to place for the product in question, then enter this value instead.</span></span> <span data-ttu-id="9759e-114">Esta información es relevante si los acuerdos comerciales con el cliente se dividen en cantidades por niveles, es decir, el precio del producto depende de la cantidad mínima comprada.</span><span class="sxs-lookup"><span data-stu-id="9759e-114">This information is relevant if the trade agreements with the customer have quantity breaks, that is, the product's price depends on the minimum quantity purchased.</span></span>  
6. <span data-ttu-id="9759e-115">En el campo Fecha, especifique una fecha en la que se prevé que el cliente realice un pedido.</span><span class="sxs-lookup"><span data-stu-id="9759e-115">In the Date field, enter a date for when the customer expects to place an order.</span></span> 
    * <span data-ttu-id="9759e-116">La fecha debe ser la fecha en curso o en cualquier fecha futura.</span><span class="sxs-lookup"><span data-stu-id="9759e-116">The date can be today's date or any date in the future.</span></span>  
    * <span data-ttu-id="9759e-117">El sistema devuelve ahora el precio válido para el producto seleccionado cuando lo compra el cliente seleccionado en la fecha seleccionada y de acuerdo con una cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="9759e-117">The system now returns the price that is valid for the selected product when bought by the selected customer on the selected date with a specified quantity.</span></span> <span data-ttu-id="9759e-118">En este ejemplo, si el cliente US-001 compró 1 unidad de producto T0004 hoy, se le cobrarían 350 CAD por cada unidad.</span><span class="sxs-lookup"><span data-stu-id="9759e-118">In this example, if the customer US-001 bought 1 unit of product T0004 today, they would be charged 350 CAD a unit.</span></span> <span data-ttu-id="9759e-119">Este precio proviene de un acuerdo comercial existente y activo con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9759e-119">This price comes from an existing and active trade agreement with the customer.</span></span>      <span data-ttu-id="9759e-120">Los demás campos de la página proporcionan más información acerca del precio del producto y su coste (si se ha configurado en el producto maestro), así como la rentabilidad calculada.</span><span class="sxs-lookup"><span data-stu-id="9759e-120">Other fields on the page provide more details about the product price and product cost (if set up on the product master), and calculated profitability.</span></span>  
    * <span data-ttu-id="9759e-121">Si está seleccionada la opción Mostrar variantes del producto relacionadas, significa que hay acuerdos comerciales adicionales para las variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="9759e-121">If the Show related product variants option is selected, it means that there are additional trade agreements for product's variants.</span></span>  
7. <span data-ttu-id="9759e-122">Haga clic en la casilla Mostrar variantes del producto relacionadas.</span><span class="sxs-lookup"><span data-stu-id="9759e-122">Click the Show related product variants checkbox.</span></span>
    * <span data-ttu-id="9759e-123">Se muestra una lista de variantes del producto con información sobre sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="9759e-123">A list of the product variants is shown, with information about their dimensions.</span></span>  
8. <span data-ttu-id="9759e-124">En la lista, marque la línea que representa el color blanco.</span><span class="sxs-lookup"><span data-stu-id="9759e-124">In the list, mark the line representing color White.</span></span>
    * <span data-ttu-id="9759e-125">Observe cómo el precio del producto es diferente ahora del mostrado anteriormente cuando no se había especificado por dimensión.</span><span class="sxs-lookup"><span data-stu-id="9759e-125">Notice, that the product price is now different from the one displayed previously when it was not specified per dimension.</span></span>  
9. <span data-ttu-id="9759e-126">Haga clic en Ver precios de venta.</span><span class="sxs-lookup"><span data-stu-id="9759e-126">Click View sales prices.</span></span>
    * <span data-ttu-id="9759e-127">La página Precios (ventas) muestra todos los acuerdos comerciales aplicables al producto, incluidas sus variantes.</span><span class="sxs-lookup"><span data-stu-id="9759e-127">The Price (sales) page displays all the trade agreements applicable to the product, including its variants.</span></span>  
10. <span data-ttu-id="9759e-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9759e-128">Close the page.</span></span>

## <a name="find-the-applicable-discount"></a><span data-ttu-id="9759e-129">Búsqueda del descuento aplicable</span><span class="sxs-lookup"><span data-stu-id="9759e-129">Find the applicable discount</span></span>
<span data-ttu-id="9759e-130">Asegúrese de que el campo Cuenta de cliente contiene el número de cliente US-001. </span><span class="sxs-lookup"><span data-stu-id="9759e-130">Make sure the Customer account field contains customer number US-001</span></span>   
1. <span data-ttu-id="9759e-131">En el campo Código de artículo, escriba 'T0012'.</span><span class="sxs-lookup"><span data-stu-id="9759e-131">In the Item number field, type 'T0012'.</span></span>
    * <span data-ttu-id="9759e-132">Asegúrese de que el campo Cantidad se haya definido en 1.</span><span class="sxs-lookup"><span data-stu-id="9759e-132">Make sure the Quantity field is set to 1.</span></span>  
    * <span data-ttu-id="9759e-133">Los siguientes detalles de precios mostrados para el producto T0012 proceden de uno o varios acuerdos comerciales: el precio unitario es de 1.000 CAD, y el porcentaje de descuento es 5.</span><span class="sxs-lookup"><span data-stu-id="9759e-133">The following pricing details shown for product T0012 come from one or more trade agreements: The unit price is 1,000 CAD and the discount percentage is 5.</span></span>  
2. <span data-ttu-id="9759e-134">Establezca el valor de cantidad en '20'.</span><span class="sxs-lookup"><span data-stu-id="9759e-134">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="9759e-135">El aumento de la cantidad del pedido hace que el descuento de línea que se ofrecerá al cliente cambie del 5 al 7 por ciento.</span><span class="sxs-lookup"><span data-stu-id="9759e-135">The increased order quantity causes the line discount that will be offered to the customer to change from 5 to 7 percent.</span></span>  
    * <span data-ttu-id="9759e-136">El importe neto se calcula según el precio unitario, el descuento y la cantidad total.</span><span class="sxs-lookup"><span data-stu-id="9759e-136">The Net amount is calculated based on the unit price, discount and the total quantity.</span></span>  
3. <span data-ttu-id="9759e-137">Haga clic en Ver descuento de línea.</span><span class="sxs-lookup"><span data-stu-id="9759e-137">Click View line discount.</span></span>
    * <span data-ttu-id="9759e-138">Existen dos acuerdos de descuento de línea para el producto T0012: un 5 por ciento de descuento para pedidos de 1 a 10 y un 7 por ciento de descuento para pedidos de más de 10.</span><span class="sxs-lookup"><span data-stu-id="9759e-138">There are two line discount agreements for product T0012, specifying a 5 percent discount for an order line quantity from 1 to 10, and 7 percent discount for order quantities above 10.</span></span> <span data-ttu-id="9759e-139">Observe cómo se aplican los descuentos a un grupo de productos, en este ejemplo, el código de grupo 01, al cual pertenece el producto T0012.</span><span class="sxs-lookup"><span data-stu-id="9759e-139">Note that the discounts are applied to a group of products, in this example, Group code 01, of which product T0012 is a member.</span></span>  
4. <span data-ttu-id="9759e-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9759e-140">Close the page.</span></span>

