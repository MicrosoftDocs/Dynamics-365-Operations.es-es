---
title: Intervalos de servicio
description: "El intervalo de servicio indica la frecuencia con la que se crean líneas de pedido de servicio para líneas de contrato de servicio cuando crea pedidos de servicio."
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4ea10e4c0fbfd21538bba16d2b01deb3e4b3a10d
ms.openlocfilehash: 4a51a3c3483e81cefdaf3d8e62a4f1f47fcd706b
ms.contentlocale: es-es
ms.lasthandoff: 02/20/2018

---

# <a name="service-intervals"></a><span data-ttu-id="6c2cf-103">Intervalos de servicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-103">Service intervals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6c2cf-104">El intervalo de contrato de servicio indica la frecuencia con la que se crean líneas de pedido de servicio para líneas de contrato de servicio cuando se crean pedidos de servicio automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="6c2cf-105">Al crear pedidos de servicio automáticamente, se crean líneas de pedido de servicio en función del intervalo especificado para la línea de contrato de servicio, a partir de la fecha inicial de la línea de contrato.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="6c2cf-106">Si el campo **Intervalo** de una línea de contrato de servicio del formulario **Contratos de servicio** se deja en blanco, la línea es un evento único y no se utiliza para crear pedidos de servicio repetidamente.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="6c2cf-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c2cf-107">Example</span></span>

<span data-ttu-id="6c2cf-108">Este ejemplo muestra cómo un intervalo de servicio afectará a las líneas de contrato de servicio y las líneas de pedido de servicio en un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="6c2cf-109">Cree un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-109">Create a service agreement</span></span>

<span data-ttu-id="6c2cf-110">En primer lugar, cree un contrato de servicio y establezca la opción **Combinar pedidos de servicio** en **Por contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="6c2cf-111">Haga clic en **Contratos de servicio**</span><span class="sxs-lookup"><span data-stu-id="6c2cf-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="6c2cf-112">En el **Panel de acciones**, en la pestaña **Contrato de servicio**, en el grupo **Nuevo**, haga clic en **Contrato de servicio** para crear un nuevo contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="6c2cf-113">Introduzca una descripción, seleccione un proyecto en el campo **Id. de proyecto** y especifique una fecha en el campo **Fecha de inicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="6c2cf-114">En el campo **Combinar pedidos de servicio**, seleccione **Por contrato de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="6c2cf-115">Acaba de crear el siguiente acuerdo de servicio:</span><span class="sxs-lookup"><span data-stu-id="6c2cf-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="6c2cf-116">Project</span><span class="sxs-lookup"><span data-stu-id="6c2cf-116">Project</span></span>      | <span data-ttu-id="6c2cf-117">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="6c2cf-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="6c2cf-118">Su proyecto</span><span class="sxs-lookup"><span data-stu-id="6c2cf-118">Your project</span></span> | <span data-ttu-id="6c2cf-119">La fecha especificada para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-119">The date you specified for the project.</span></span> <span data-ttu-id="6c2cf-120">En este ejemplo, se utiliza la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="6c2cf-121">Crear una línea de contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-121">Create a service agreement line</span></span>

<span data-ttu-id="6c2cf-122">A continuación, cree una línea de contrato de servicio con el tipo de transacción **Hora**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="6c2cf-123">Para realizar esta parte del ejemplo, debe crear un intervalo de servicio de 10 días en la página **Intervalos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="6c2cf-124">Seleccione el acuerdo de servicio que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="6c2cf-125">En la ficha desplegable **Líneas**, haga clic en el botón **Añadir** para crear una nueva línea en el panel inferior de la página **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="6c2cf-126">Seleccione **Hora** en el campo **Tipo de transacción**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="6c2cf-127">En el campo **Trabajador**, seleccione el trabajador que prestará el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="6c2cf-128">En el campo **Intervalo de servicio**, seleccione el intervalo de 10 días.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="6c2cf-129">Ya ha creado una línea de contrato de servicio con el siguiente tipo de transacción:</span><span class="sxs-lookup"><span data-stu-id="6c2cf-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="6c2cf-130">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="6c2cf-130">Transaction type</span></span> | <span data-ttu-id="6c2cf-131">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-131">Start date</span></span>                               | <span data-ttu-id="6c2cf-132">Intervalo de servicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="6c2cf-133">Hora</span><span class="sxs-lookup"><span data-stu-id="6c2cf-133">Hour</span></span>             | <span data-ttu-id="6c2cf-134">La fecha actual.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-134">The current date.</span></span>                        | <span data-ttu-id="6c2cf-135">Cada 10 días</span><span class="sxs-lookup"><span data-stu-id="6c2cf-135">Every 10 days</span></span>    |
| <span data-ttu-id="6c2cf-136">Trabajador</span><span class="sxs-lookup"><span data-stu-id="6c2cf-136">Worker</span></span>           | <span data-ttu-id="6c2cf-137">El trabajador que llevará a cabo el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="6c2cf-138">No hay ninguna ventana de tiempo especificada para la línea.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="6c2cf-139">Crear pedidos de servicio planificados</span><span class="sxs-lookup"><span data-stu-id="6c2cf-139">Create planned service orders</span></span>

<span data-ttu-id="6c2cf-140">Ahora puede crear pedidos de servicio planificados y líneas de pedido de servicio para el mes siguiente.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="6c2cf-141">En la página **Contratos de servicio**, en el **Panel de acciones**, en la pestaña **Entregar**, haga clicc en **Pedidos de servicio planificados**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="6c2cf-142">En la página **Crear pedidos de servicio**, especifique la fecha actual en el campo **Fecha inicial** y una fecha que sea un mes a partir de la fecha actual en el campo **Fecha final**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="6c2cf-143">Establezca el control deslizante **Hora** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="6c2cf-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-144">Click **OK**.</span></span>

<span data-ttu-id="6c2cf-145">Puesto que no existe ninguna agrupación en el pedido de servicio (definida mediante la opción **Por contrato de servicio** en el campo **Combinar pedidos de servicio**), se crea una línea de pedido de servicio por cada pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="6c2cf-146">Pedidos de servicio creados</span><span class="sxs-lookup"><span data-stu-id="6c2cf-146">Service orders created</span></span>

<span data-ttu-id="6c2cf-147">Las tres líneas de pedido de servicio creadas en esta instancia se encuentran en la franja temporal especificada en el cuadro de diálogo **Crear pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="6c2cf-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="6c2cf-148">Puede ver las líneas de pedido de servicio en el formulario **Contratos de servicio** (**Panel de acciones**\> pestaña **Entregar** \> botón **Ver**).</span><span class="sxs-lookup"><span data-stu-id="6c2cf-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c2cf-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6c2cf-149">Related topics</span></span>

[<span data-ttu-id="6c2cf-150">Configurar intervalos de servicio</span><span class="sxs-lookup"><span data-stu-id="6c2cf-150">Set up service intervals</span></span>](set-up-service-intervals.md)  


