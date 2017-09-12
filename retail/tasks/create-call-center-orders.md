--- 
title: Crear pedidos de centro de llamadas
description: "Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 62f88cc2e28405a9d2eb43819fb09d83a64658b6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="create-call-center-orders"></a><span data-ttu-id="61e3b-103">Crear pedidos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="61e3b-103">Create call center orders</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="61e3b-104">Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente.</span><span class="sxs-lookup"><span data-stu-id="61e3b-104">This procedure walks through looking up a customer, creating a new order, searching for a product, and collecting payment from the customer.</span></span> <span data-ttu-id="61e3b-105">Este procedimiento usa la empresa de datos de demostración USRT y está pensado para el funcionario de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e3b-105">This procedure uses demo data company USRT and is intended for the Sales Order Clerk.</span></span> <span data-ttu-id="61e3b-106">Requisitos previos: el usuario que complete el procedimiento se configura como usuario del centro de llamadas y el catálogo semestral de Fabrikam se publica con al menos un código fuente en él.</span><span class="sxs-lookup"><span data-stu-id="61e3b-106">Pre-requisites:  The user who completes the procedure is set up as a Call center user and the Fabrikam Semi-Annual Catalog is published with at least one Source code on it.</span></span>

1. <span data-ttu-id="61e3b-107">Vaya a Venta minorista y comercio > Clientes > Servicio atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="61e3b-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="61e3b-108">En el campo SearchText, especifique los criterios de búsqueda para buscar el cliente.</span><span class="sxs-lookup"><span data-stu-id="61e3b-108">In the SearchText field, enter the search criteria to look up the customer.</span></span>
    * <span data-ttu-id="61e3b-109">Para este procedimiento de ejemplo, escriba “karen” y presione el tabulador.</span><span class="sxs-lookup"><span data-stu-id="61e3b-109">For this example procedure type in 'karen' and press tab.</span></span>  
3. <span data-ttu-id="61e3b-110">Haga clic en Buscar</span><span class="sxs-lookup"><span data-stu-id="61e3b-110">Click Search.</span></span>
    * <span data-ttu-id="61e3b-111">Dado que solo hay un cliente llamado Karen en los datos de demostración, se seleccionarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="61e3b-111">Since there is only one customer named Karen in demo data they will be automatically selected.</span></span>  
4. <span data-ttu-id="61e3b-112">Haga clic en Nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e3b-112">Click New sales order.</span></span>
5. <span data-ttu-id="61e3b-113">Expanda o contraiga la sección Encabezado de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e3b-113">Expand or collapse the Sales order header section.</span></span>
6. <span data-ttu-id="61e3b-114">Seleccione el código fuente para el catálogo.</span><span class="sxs-lookup"><span data-stu-id="61e3b-114">Select the source code for the catalog.</span></span>
    * <span data-ttu-id="61e3b-115">Si no hay códigos de origen activos, puede cerrar el campo Origen y omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="61e3b-115">If there are no active Source codes you can close the Source field and skip this step.</span></span>  
7. <span data-ttu-id="61e3b-116">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="61e3b-116">Click Add line.</span></span>
8. <span data-ttu-id="61e3b-117">En el campo Código de artículo, especifique el término de búsqueda del artículo.</span><span class="sxs-lookup"><span data-stu-id="61e3b-117">In the Item number field, enter the item search term.</span></span>
    * <span data-ttu-id="61e3b-118">Para este procedimiento de ejemplo especifique un número de artículo parcial de “8111" y presione el tabulador.</span><span class="sxs-lookup"><span data-stu-id="61e3b-118">For this sample procedure enter a partial item number of '8111' and press tab.</span></span> <span data-ttu-id="61e3b-119">De esta manera surgirá la ventana de búsqueda de artículos.</span><span class="sxs-lookup"><span data-stu-id="61e3b-119">This will pop up the item search window.</span></span>  
9. <span data-ttu-id="61e3b-120">Seleccionar el producto que se agregará al pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="61e3b-120">Select the product to add to the sales order</span></span>
10. <span data-ttu-id="61e3b-121">Especifique la cantidad de ventas.</span><span class="sxs-lookup"><span data-stu-id="61e3b-121">Enter the sales quantity.</span></span>
11. <span data-ttu-id="61e3b-122">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="61e3b-122">Click Create.</span></span>
12. <span data-ttu-id="61e3b-123">Haga clic en Completar para capturar el pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="61e3b-123">Click Complete to capture the customer payment.</span></span>
13. <span data-ttu-id="61e3b-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="61e3b-124">Click Add.</span></span>
    * <span data-ttu-id="61e3b-125">El vínculo Agregar se encuentra en la pestaña Pagos.</span><span class="sxs-lookup"><span data-stu-id="61e3b-125">The Add link is in the Payments tab.</span></span> <span data-ttu-id="61e3b-126">Expanda la pestaña Pagos si está contraída.</span><span class="sxs-lookup"><span data-stu-id="61e3b-126">Expand the Payments tab if it is collapsed.</span></span>  
14. <span data-ttu-id="61e3b-127">Seleccione el método de pago.</span><span class="sxs-lookup"><span data-stu-id="61e3b-127">Select the payment method.</span></span>
    * <span data-ttu-id="61e3b-128">Para este procedimiento, seleccione el método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="61e3b-128">For this procedure, select the cash payment method.</span></span>  
15. <span data-ttu-id="61e3b-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="61e3b-129">Close the page.</span></span>
16. <span data-ttu-id="61e3b-130">Especifique el importe.</span><span class="sxs-lookup"><span data-stu-id="61e3b-130">Enter the amount.</span></span>
    * <span data-ttu-id="61e3b-131">Para este procedimiento, especifique un importe igual al saldo del pedido que se puede ver en la página Resumen de pedido de ventas a la izquierda del campo de importe.</span><span class="sxs-lookup"><span data-stu-id="61e3b-131">For this procedure enter an amount equal to the order balance which can be seen in the Sales order summary page to the left of the amount field.</span></span> <span data-ttu-id="61e3b-132">Esto le permitirá que completar el pedido como totalmente pagado.</span><span class="sxs-lookup"><span data-stu-id="61e3b-132">This will allow you to complete the order as fully paid.</span></span>  
17. <span data-ttu-id="61e3b-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61e3b-133">Click OK.</span></span>
18. <span data-ttu-id="61e3b-134">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="61e3b-134">Click Submit.</span></span>


