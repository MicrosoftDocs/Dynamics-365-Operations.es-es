---
title: Especificar los acuerdos de ventas
description: Este procedimiento le muestra cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 025c9fe2f769f37b63bd79c6c3afedc31a955310
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "346879"
---
# <a name="enter-sales-agreements"></a><span data-ttu-id="d808e-103">Especificar los acuerdos de ventas</span><span class="sxs-lookup"><span data-stu-id="d808e-103">Enter sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d808e-104">Este procedimiento le muestra cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales.</span><span class="sxs-lookup"><span data-stu-id="d808e-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="d808e-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="d808e-105">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="d808e-106">Configurar el encabezado del acuerdo de venta</span><span class="sxs-lookup"><span data-stu-id="d808e-106">Set up sales agreement header</span></span>
1. <span data-ttu-id="d808e-107">Vaya a Ventas y marketing > Acuerdos de venta > Acuerdos de venta.</span><span class="sxs-lookup"><span data-stu-id="d808e-107">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="d808e-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d808e-108">Click New.</span></span>
3. <span data-ttu-id="d808e-109">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d808e-109">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d808e-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d808e-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d808e-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d808e-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d808e-112">En el campo Clasificación del acuerdo de venta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d808e-112">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d808e-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d808e-113">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d808e-114">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="d808e-114">Expand the General section.</span></span>
9. <span data-ttu-id="d808e-115">En el campo Compromiso predeterminado, seleccione "Compromiso de valor de producto".</span><span class="sxs-lookup"><span data-stu-id="d808e-115">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="d808e-116">Un tipo de compromiso es un criterio obligatorio que debe asignar el acuerdo para definir cómo se cumplirá el contrato del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="d808e-116">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="d808e-117">Los cuatro tipos predefinidos le permiten configurar el destino de compromiso del cliente, expresado como cantidad o valor.</span><span class="sxs-lookup"><span data-stu-id="d808e-117">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="d808e-118">El tipo de compromiso de cantidad solo puede aplicarse a un producto específico, pero los tipos basados en valores son aplicables a la venta tanto de productos específicos como no específicos.</span><span class="sxs-lookup"><span data-stu-id="d808e-118">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="d808e-119">En el campo Fecha de vencimiento, establezca la fecha en una fecha futura en la que desea que expire el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="d808e-119">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="d808e-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d808e-120">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="d808e-121">Configurar líneas de compromiso de valor de producto</span><span class="sxs-lookup"><span data-stu-id="d808e-121">Set up product value commitment lines</span></span>
1. <span data-ttu-id="d808e-122">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="d808e-122">Click Add line.</span></span>
2. <span data-ttu-id="d808e-123">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d808e-123">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d808e-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d808e-124">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d808e-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d808e-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d808e-126">El tipo de compromiso que ha elegido para el acuerdo afecta a la clase de información que puede especificar para las líneas del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="d808e-126">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="d808e-127">Por ejemplo, para un acuerdo basado en valor debe especificar el importe neto total (en la divisa acordada) para el que el cliente se compromete a comprarle mercancías.</span><span class="sxs-lookup"><span data-stu-id="d808e-127">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="d808e-128">En este ejemplo, los campos Cantidad y Unidad de la línea no están disponibles porque está creando un acuerdo para que el cliente compre un valor específico de un producto.</span><span class="sxs-lookup"><span data-stu-id="d808e-128">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="d808e-129">En el campo Importe neto, especifique el importe monetario que el cliente se ha comprometido a comprar.</span><span class="sxs-lookup"><span data-stu-id="d808e-129">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="d808e-130">En el campo Porcentaje de descuento, especifique un valor de porcentaje que se aplicará a las líneas de pedidos de ventas del cliente que están vinculadas al acuerdo.</span><span class="sxs-lookup"><span data-stu-id="d808e-130">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="d808e-131">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="d808e-131">Expand the Line details section.</span></span>
8. <span data-ttu-id="d808e-132">Seleccione Sí en el campo Máximo aplicado.</span><span class="sxs-lookup"><span data-stu-id="d808e-132">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="d808e-133">La selección de la Máximo aplicado es obligatoria implica que el importe total de todas las líneas de pedidos de ventas que usan los precios especiales del compromiso, los descuentos y las condiciones de pago no deben superar el importe especificado en el compromiso.</span><span class="sxs-lookup"><span data-stu-id="d808e-133">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="d808e-134">Los importes mínimo y máximos parciales especifican un intervalo de valores que se deben vender en cada pedido de ventas que usa el acuerdo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d808e-134">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="d808e-135">Expanda la sección Encabezado del acuerdo de venta.</span><span class="sxs-lookup"><span data-stu-id="d808e-135">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="d808e-136">A menos que el estado del acuerdo se establezca en Vigente, los pedidos de ventas no se pueden asociar al acuerdo y por tanto no pueden contribuir a su cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d808e-136">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="d808e-137">No puede modificar el estado de forma manual en esta etapa.</span><span class="sxs-lookup"><span data-stu-id="d808e-137">You can change the status manually at this stage.</span></span> <span data-ttu-id="d808e-138">Sin embargo, el estado se cambiaría normalmente cuando confirma el acuerdo para el cliente.</span><span class="sxs-lookup"><span data-stu-id="d808e-138">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="d808e-139">En el panel de acciones, haga clic en Acuerdo de venta</span><span class="sxs-lookup"><span data-stu-id="d808e-139">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="d808e-140">Haga clic en Confirmación.</span><span class="sxs-lookup"><span data-stu-id="d808e-140">Click Confirmation.</span></span>
    * <span data-ttu-id="d808e-141">Asegúrese de que la opción Marcar acuerdo como vigente se establece en Sí.</span><span class="sxs-lookup"><span data-stu-id="d808e-141">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="d808e-142">Seleccione Sí en el campo Imprimir informe.</span><span class="sxs-lookup"><span data-stu-id="d808e-142">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="d808e-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d808e-143">Click OK.</span></span>
14. <span data-ttu-id="d808e-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d808e-144">Close the page.</span></span>
    * <span data-ttu-id="d808e-145">El acuerdo está ahora vigente y puede empezar a vincular los pedidos del cliente al acuerdo, para compensar contra el objetivo comprometido.</span><span class="sxs-lookup"><span data-stu-id="d808e-145">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  

