---
title: Uso del programa de continuidad
description: Este procedimiento muestra el proceso de venta de un programa de continuidad y el procesamiento de pedidos de ventas relacionados.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd0bfcd99a23e4c639a6317adefb41a947a487a5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023910"
---
# <a name="using-continuity-program"></a><span data-ttu-id="de81c-103">Uso del programa de continuidad</span><span class="sxs-lookup"><span data-stu-id="de81c-103">Using continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="de81c-104">Este procedimiento muestra el proceso de venta de un programa de continuidad y el procesamiento de pedidos de ventas relacionados.</span><span class="sxs-lookup"><span data-stu-id="de81c-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="de81c-105">Para completar este procedimiento, el usuario tiene que configurarse como un usuario del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="de81c-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="de81c-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="de81c-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="de81c-107">Vaya a Retail y Commerce > Clientes > Servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="de81c-107">Go to Retail and Commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="de81c-108">En el campo SearchText, escriba "Karen" y luego presione la tecla de tabulador.</span><span class="sxs-lookup"><span data-stu-id="de81c-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="de81c-109">Debería surgir el diálogo de búsqueda avanzada.</span><span class="sxs-lookup"><span data-stu-id="de81c-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="de81c-110">Si no es así, haga clic en Búsqueda a la derecha de este campo.</span><span class="sxs-lookup"><span data-stu-id="de81c-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="de81c-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de81c-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="de81c-112">Debe haber una sola fila con la demostración de Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="de81c-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="de81c-113">Seleccione la fila haciendo clic en la columna de la marca de verificación en el extremo izquierdo de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="de81c-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="de81c-114">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="de81c-114">Click Select.</span></span>
5. <span data-ttu-id="de81c-115">Haga clic en Nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="de81c-115">Click New sales order.</span></span>
    * <span data-ttu-id="de81c-116">Conviene anotar el número de pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="de81c-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="de81c-117">Lo necesitará más adelante en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="de81c-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="de81c-118">En el campo Número de artículo, escriba "88000" y luego presione la tecla de tabulador.</span><span class="sxs-lookup"><span data-stu-id="de81c-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="de81c-119">Esto es un elemento de continuidad en los datos de demostración de USRT.</span><span class="sxs-lookup"><span data-stu-id="de81c-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="de81c-120">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="de81c-120">Click Complete.</span></span>
8. <span data-ttu-id="de81c-121">En el campo Método de pago, seleccione "Visa".</span><span class="sxs-lookup"><span data-stu-id="de81c-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="de81c-122">Haga clic en Agregar tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="de81c-122">Click Add credit card.</span></span>
    * <span data-ttu-id="de81c-123">Especifique la información de la tarjeta de crédito requerida en esta página.</span><span class="sxs-lookup"><span data-stu-id="de81c-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="de81c-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="de81c-124">Click OK.</span></span>
11. <span data-ttu-id="de81c-125">Expanda la sección Pago.</span><span class="sxs-lookup"><span data-stu-id="de81c-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="de81c-126">Para enviar un pedido del centro de llamadas, es necesario especificar los pagos para el pedido.</span><span class="sxs-lookup"><span data-stu-id="de81c-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="de81c-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="de81c-127">Click OK.</span></span>
13. <span data-ttu-id="de81c-128">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="de81c-128">Click Submit.</span></span>
    * <span data-ttu-id="de81c-129">Ha finalizado con la creación de un nuevo pedido de continuidad.</span><span class="sxs-lookup"><span data-stu-id="de81c-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="de81c-130">A continuación, deberá ejecutar dos procesos de lotes que se usan para procesar los pedidos de continuidad.</span><span class="sxs-lookup"><span data-stu-id="de81c-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="de81c-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="de81c-131">Close the page.</span></span>
15. <span data-ttu-id="de81c-132">Vaya a Retail y Commerce > Continuidad > Procesar pagos de continuidad.</span><span class="sxs-lookup"><span data-stu-id="de81c-132">Go to Retail and Commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="de81c-133">En el campo Artículo de continuidad, escriba “88000 " y luego presione la tecla de tabulador.</span><span class="sxs-lookup"><span data-stu-id="de81c-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="de81c-134">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="de81c-134">Click OK.</span></span>
18. <span data-ttu-id="de81c-135">Vaya a Retail y Commerce > Continuidad > Crear pedidos secundarios de continuidad.</span><span class="sxs-lookup"><span data-stu-id="de81c-135">Go to Retail and Commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="de81c-136">Este proceso creará nuevos pedidos de ventas en función de los valores de sus programas de continuidad.</span><span class="sxs-lookup"><span data-stu-id="de81c-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="de81c-137">En el campo Artículo de continuidad, escriba “88000 " y luego presione la tecla de tabulador.</span><span class="sxs-lookup"><span data-stu-id="de81c-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="de81c-138">El artículo "88000" es un artículo de continuidad en los datos de demostración de USRT.</span><span class="sxs-lookup"><span data-stu-id="de81c-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="de81c-139">En el campo Pedido de ventas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="de81c-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="de81c-140">Especifique el número de pedido de ventas que ha anotado antes en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="de81c-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="de81c-141">Esto mantendrá el tiempo de procesamiento al mínimo para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="de81c-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="de81c-142">El campo Pedido de ventas es opcional. Podría procesar todos los pedidos para cualquier programa.</span><span class="sxs-lookup"><span data-stu-id="de81c-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="de81c-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="de81c-143">Click OK.</span></span>

