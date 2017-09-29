--- 
title: Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos
description: "Este procedimiento le muestra cómo especificar respuestas a una solicitud de presupuesto, puntuar y comparar ofertas y, a continuación, conceder la oferta a uno de los proveedores."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5dea9d7bfb1bf7b11f6c49cccaab1b73d4e58d16
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="a2fec-103">Especificar y comparar ofertas de la solicitud de presupuesto y conceder contratos</span><span class="sxs-lookup"><span data-stu-id="a2fec-103">Enter and compare RFQ bids and award contracts</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a2fec-104">Este procedimiento le muestra cómo especificar respuestas a una solicitud de presupuesto, puntuar y comparar ofertas y, a continuación, conceder la oferta a uno de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="a2fec-104">This procedure shows you how to enter replies to an RFQ, score and compare bids, and then award the bid to one of the vendors.</span></span> <span data-ttu-id="a2fec-105">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a2fec-105">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="a2fec-106">Antes de empezar, debe tener una solicitud de presupuesto con dos líneas que se ha enviado al menos a dos proveedores.</span><span class="sxs-lookup"><span data-stu-id="a2fec-106">Before you start, you must have an RFQ with two lines that has been sent to at least two vendors.</span></span> <span data-ttu-id="a2fec-107">Puede ejecutar el procedimiento "Crear una solicitud de presupuesto" como requisito previo para crear esto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-107">You can run the "Create a request for quotation" procedure as a prerequisite to create this.</span></span> <span data-ttu-id="a2fec-108">Es necesario haber configurado criterios de puntuación para poder ejecutar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a2fec-108">You need to have set up scoring criteria before you can run this procedure.</span></span>


## <a name="enter-a-reply-from-a-vendor"></a><span data-ttu-id="a2fec-109">Introduzca una respuesta de un proveedor</span><span class="sxs-lookup"><span data-stu-id="a2fec-109">Enter a reply from a vendor</span></span>
1. <span data-ttu-id="a2fec-110">Vaya a Adquisición y abastecimiento > Solicitudes de presupuestos > Todas las solicitudes de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="a2fec-111">Seleccione una solicitud de presupuesto que tenga un estado de Enviado y haga clic en el vínculo del Caso de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-111">Select an RFQ that has a status of Sent and click the link on the Request for quotation case number.</span></span>
    * <span data-ttu-id="a2fec-112">La solicitud de presupuesto se debe haber enviado al menos a 2 proveedores.</span><span class="sxs-lookup"><span data-stu-id="a2fec-112">The RFQ should have been sent to at least 2 vendors.</span></span>  
3. <span data-ttu-id="a2fec-113">Haga clic en Encabezado para ir a la lista de proveedores.</span><span class="sxs-lookup"><span data-stu-id="a2fec-113">Click Header to go to the list of vendors.</span></span>
4. <span data-ttu-id="a2fec-114">Seleccione el proveedor para el que desea escribir una respuesta en la solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-114">Select the vendor for whom you want to enter a response on the RFQ.</span></span>
5. <span data-ttu-id="a2fec-115">Haga clic en Especificar respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-115">Click Enter reply.</span></span>
6. <span data-ttu-id="a2fec-116">En el panel de acciones, haga clic en Contestación.</span><span class="sxs-lookup"><span data-stu-id="a2fec-116">On the Action Pane, click Reply.</span></span>
7. <span data-ttu-id="a2fec-117">Haga clic en Copiar datos en respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-117">Click Copy data to reply.</span></span>
    * <span data-ttu-id="a2fec-118">Esta acción copiará los datos seleccionados, por ejemplo, la cantidad del caso de solicitud de presupuesto a la respuesta de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-118">This action will copy selected data, for example, the quantity from the RFQ case to the RFQ reply.</span></span> <span data-ttu-id="a2fec-119">También puede omitir esta acción y rellenar todos los campos de respuesta manualmente al editar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-119">Alternatively you can skip this action and fill in all the response fields manually when you edit the reply.</span></span>  
8. <span data-ttu-id="a2fec-120">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-120">Click Edit.</span></span>
9. <span data-ttu-id="a2fec-121">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-121">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="a2fec-122">Elija la otra línea de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-122">Choose the other quotation line.</span></span>
11. <span data-ttu-id="a2fec-123">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-123">In the Unit price field, enter a number.</span></span>

## <a name="score-the-bid"></a><span data-ttu-id="a2fec-124">Puntuar la oferta</span><span class="sxs-lookup"><span data-stu-id="a2fec-124">Score the bid</span></span>
1. <span data-ttu-id="a2fec-125">Haga clic en Encabezado para ir a la puntuación de la oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-125">Click Header to go to the scoring of the bid.</span></span>
2. <span data-ttu-id="a2fec-126">Expanda la sección Puntuación de oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-126">Expand the Bid scoring section.</span></span>
3. <span data-ttu-id="a2fec-127">En el campo Resultado, escriba un número para uno de los criterios de puntuación.</span><span class="sxs-lookup"><span data-stu-id="a2fec-127">In the Score field, enter a number for one of the scoring criteria.</span></span>
    * <span data-ttu-id="a2fec-128">Si mantiene el puntero por encima de los criterios de puntuación, una información sobre herramientas muestra el intervalo que tiene que puntuar dentro.</span><span class="sxs-lookup"><span data-stu-id="a2fec-128">If you hover over one of the scoring criteria a tooltip shows the range that you have to score within.</span></span> <span data-ttu-id="a2fec-129">En esta demostración puede agregar un número entre 1 y 5 a cualquiera de los criterios.</span><span class="sxs-lookup"><span data-stu-id="a2fec-129">In this demo you can add a number between 1 and 5 to any of the criteria.</span></span>  
4. <span data-ttu-id="a2fec-130">Seleccione otro criterio de puntuación.</span><span class="sxs-lookup"><span data-stu-id="a2fec-130">Select another scoring criterion.</span></span>
5. <span data-ttu-id="a2fec-131">En el campo Puntuación, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-131">In the Score field, enter a number.</span></span>
6. <span data-ttu-id="a2fec-132">Expanda la sección Cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="a2fec-132">Expand the Questionnaires section.</span></span>
    * <span data-ttu-id="a2fec-133">Si el caso de la solicitud de presupuesto tiene un cuestionario que se envió a los proveedores, puede especificar sus respuestas en la sección del cuestionario.</span><span class="sxs-lookup"><span data-stu-id="a2fec-133">If the RFQ case has a questionnaire that was sent to the vendors, you can enter their responses in the questionnaire section.</span></span>  
7. <span data-ttu-id="a2fec-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-134">Close the page.</span></span>

## <a name="enter-a-reply-for-another-vendor"></a><span data-ttu-id="a2fec-135">Escribir una respuesta para otro proveedor</span><span class="sxs-lookup"><span data-stu-id="a2fec-135">Enter a reply for another vendor</span></span>
1. <span data-ttu-id="a2fec-136">Seleccione el siguiente proveedor desactivando el proveedor para el que acaba de escribir la respuesta y seleccionando a continuación la fila del siguiente proveedor.</span><span class="sxs-lookup"><span data-stu-id="a2fec-136">Select the next vendor by clearing the vendor you have just entered the reply for and then selecting the row for the next vendor.</span></span>
2. <span data-ttu-id="a2fec-137">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2fec-137">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a2fec-138">Haga clic en Especificar respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-138">Click Enter reply.</span></span>
4. <span data-ttu-id="a2fec-139">Haga clic en Copiar datos en respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-139">Click Copy data to reply.</span></span>
5. <span data-ttu-id="a2fec-140">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-140">Click Edit.</span></span>
6. <span data-ttu-id="a2fec-141">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-141">In the Unit price field, enter a number.</span></span>
7. <span data-ttu-id="a2fec-142">Elija la otra línea de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-142">Choose the other quotation line.</span></span>
8. <span data-ttu-id="a2fec-143">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-143">In the Unit price field, enter a number.</span></span>

## <a name="score-the-second-bid"></a><span data-ttu-id="a2fec-144">Puntuar la segunda oferta</span><span class="sxs-lookup"><span data-stu-id="a2fec-144">Score the second bid</span></span>
1. <span data-ttu-id="a2fec-145">Haga clic en Encabezado para ir a la puntuación de la oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-145">Click Header to go to scoring of the bid.</span></span>
2. <span data-ttu-id="a2fec-146">En el campo Puntuación, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-146">In the Score field, enter a number.</span></span>
3. <span data-ttu-id="a2fec-147">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2fec-147">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a2fec-148">En el campo Puntuación, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-148">In the Score field, enter a number.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="a2fec-149">Comparar las respuestas</span><span class="sxs-lookup"><span data-stu-id="a2fec-149">Compare the replies</span></span>
1. <span data-ttu-id="a2fec-150">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="a2fec-150">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="a2fec-151">Haga clic en Comparar respuestas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-151">Click Compare replies.</span></span>
3. <span data-ttu-id="a2fec-152">En el campo Categoría, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-152">In the Rank field, enter a number.</span></span>
    * <span data-ttu-id="a2fec-153">Esta página muestra las ofertas con el encabezado y las líneas, y la puntuación total en el nivel de encabezado.</span><span class="sxs-lookup"><span data-stu-id="a2fec-153">This page shows the bids with the header and lines, and the total score on the header level.</span></span> <span data-ttu-id="a2fec-154">Puede comparar las líneas ordenando en la cuadrícula de modo que las líneas comparables estén una junto a la otra.</span><span class="sxs-lookup"><span data-stu-id="a2fec-154">You can compare the lines by sorting in the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="a2fec-155">La información también incluye: Cantidad: La cantidad presupuestada por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="a2fec-155">The information also includes:   Quantity: The quantity quoted by the vendor.</span></span> <span data-ttu-id="a2fec-156">Esta cantidad puede no ser igual a la cantidad especificada en la solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-156">This might not equal the quantity specified in the RFQ.</span></span>   <span data-ttu-id="a2fec-157">Importe neto: el precio presupuestado por un proveedor, después de restar los descuentos, para los artículos de la línea.</span><span class="sxs-lookup"><span data-stu-id="a2fec-157">Net amount: The price quoted by a vendor, after subtracting any discounts, for the items on the line.</span></span>   <span data-ttu-id="a2fec-158">Desviación: el número de días que se desplaza la fecha de entrega en la cabecera de la oferta o la línea de la fecha de entrega solicitada en la cabecera o línea de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-158">Deviation: The number of days that the delivery date in the bid header or line deviates from the requested delivery date in the RFQ header or RFQ line.</span></span>   <span data-ttu-id="a2fec-159">Puede especificar una categoría para cada oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-159">You can enter a rank for each bid.</span></span>  
4. <span data-ttu-id="a2fec-160">Seleccione la línea de encabezado para la otra oferta que desea clasificar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-160">Select the header line for the other bid that you want to rank.</span></span>
5. <span data-ttu-id="a2fec-161">En el campo Categoría, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2fec-161">In the Rank field, enter a number.</span></span>
6. <span data-ttu-id="a2fec-162">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-162">Click Save.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="a2fec-163">Rechazar una oferta</span><span class="sxs-lookup"><span data-stu-id="a2fec-163">Reject a bid</span></span>
1. <span data-ttu-id="a2fec-164">Seleccione la línea de encabezado para la oferta que desea rechazar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-164">Select the header line for the bid that you want to reject.</span></span>
    * <span data-ttu-id="a2fec-165">Solo puede aceptar, rechazar o devolver una oferta o líneas dentro de una oferta cada vez.</span><span class="sxs-lookup"><span data-stu-id="a2fec-165">You can only accept, reject, or return one bid or lines within one bid at a time.</span></span>  
2. <span data-ttu-id="a2fec-166">Active la casilla Marcar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-166">Select the Mark check box.</span></span>
    * <span data-ttu-id="a2fec-167">Si activa la casilla Marcar en el encabezado de la oferta, se marcarán también todas las líneas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-167">If you select the Mark check box on the Header of the bid then all the lines will be marked as well.</span></span> <span data-ttu-id="a2fec-168">También podría elegir marcar un subconjunto de las líneas dentro de la oferta para rechazarlas o aceptarlas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-168">You could also choose to mark a subset of the lines within the bid to reject or accept those.</span></span> <span data-ttu-id="a2fec-169">Es posible aceptar la propuesta de un proveedor para algunas líneas de la solicitud de presupuesto y después conceder otras líneas de la solicitud de presupuesto a otro proveedor. No obstante necesita hacer esto en 2 pasos, una oferta cada vez.</span><span class="sxs-lookup"><span data-stu-id="a2fec-169">It’s possible to accept one vendor’s bid for some lines of an RFQ, and then award other RFQ lines to a different vendor, however you need to do this in 2 steps, one bid at a time.</span></span> <span data-ttu-id="a2fec-170">Si las líneas alternativas están presentes, solo puede aceptar la línea de oferta original o su alternativa, pero no ambas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-170">If alternate lines are present, you can only accept either the original bid line or its alternate, but not both.</span></span>  
3. <span data-ttu-id="a2fec-171">Haga clic en Rechazar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-171">Click Reject.</span></span>
4. <span data-ttu-id="a2fec-172">Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2fec-172">Click Parameters to open the drop dialog.</span></span>
5. <span data-ttu-id="a2fec-173">En el campo Motivo de rechazo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2fec-173">In the Reason reject field, enter or select a value.</span></span>
    * <span data-ttu-id="a2fec-174">El motivo del rechazo se almacenará en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-174">The reason for rejection will be stored on the reply.</span></span>  
6. <span data-ttu-id="a2fec-175">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2fec-175">Click OK.</span></span>
7. <span data-ttu-id="a2fec-176">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2fec-176">Click OK.</span></span>
8. <span data-ttu-id="a2fec-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-177">Close the page.</span></span>
9. <span data-ttu-id="a2fec-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-178">Close the page.</span></span>
10. <span data-ttu-id="a2fec-179">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-179">Refresh the page.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="a2fec-180">Aceptar una oferta</span><span class="sxs-lookup"><span data-stu-id="a2fec-180">Accept a bid</span></span>
1. <span data-ttu-id="a2fec-181">Seleccione la oferta que desea aceptar y haga clic en el vínculo del campo Solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-181">Select the bid that you want to accept and then click the link in the Request for quotation field.</span></span>
2. <span data-ttu-id="a2fec-182">En el panel de acciones, haga clic en Contestación.</span><span class="sxs-lookup"><span data-stu-id="a2fec-182">On the Action Pane, click Reply.</span></span>
3. <span data-ttu-id="a2fec-183">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="a2fec-183">Click Accept.</span></span>
    * <span data-ttu-id="a2fec-184">Si ha marcado líneas específicas y no otras, la acción de aceptación solo incluirá las líneas marcadas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-184">If you have marked specific lines and not others then the accept action will only include the marked lines.</span></span> <span data-ttu-id="a2fec-185">Si desea aceptar todas las líneas de la oferta, no es necesario marcar las líneas.</span><span class="sxs-lookup"><span data-stu-id="a2fec-185">If you want to accept all lines on the bid then you do not have to mark the lines.</span></span>  
4. <span data-ttu-id="a2fec-186">Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2fec-186">Click Parameters to open the drop dialog.</span></span>
    * <span data-ttu-id="a2fec-187">Esto le permite registrar un motivo para aceptar la oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-187">This allows you to record a reason for accepting the bid.</span></span> <span data-ttu-id="a2fec-188">El motivo se almacenará en la oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-188">The reason will be stored on the bid.</span></span>  
5. <span data-ttu-id="a2fec-189">En el campo Motivo de aceptación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2fec-189">In the Reason accept field, enter or select a value.</span></span>
6. <span data-ttu-id="a2fec-190">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2fec-190">Click OK.</span></span>
7. <span data-ttu-id="a2fec-191">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2fec-191">Click OK.</span></span>
    * <span data-ttu-id="a2fec-192">Al hacer clic en Aceptar esto genera un pedido de compra basado en las líneas que se incluyen en la aceptación de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a2fec-192">When you click OK this generates a purchase order based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="a2fec-193">Si hay otras ofertas que no se han procesado (aceptado, rechazado o devuelto), el sistema le pedirá rechazar las ofertas restantes.</span><span class="sxs-lookup"><span data-stu-id="a2fec-193">If there are other bids that have not been processed (accepted, rejected, or returned) then the system will prompt you to reject the remaining bids.</span></span>  

## <a name="view-the-purchase-order-thats-been-generated"></a><span data-ttu-id="a2fec-194">Ver el pedido de compra que se ha generado</span><span class="sxs-lookup"><span data-stu-id="a2fec-194">View the purchase order that's been generated</span></span>
1. <span data-ttu-id="a2fec-195">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="a2fec-195">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="a2fec-196">Haga clic en Pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="a2fec-196">Click Purchase order.</span></span>
    * <span data-ttu-id="a2fec-197">Aquí puede ver el pedido de compra que se generó al aceptar la oferta.</span><span class="sxs-lookup"><span data-stu-id="a2fec-197">Here you can see the purchase order that was generated when you accepted the bid.</span></span>  
3. <span data-ttu-id="a2fec-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-198">Close the page.</span></span>
4. <span data-ttu-id="a2fec-199">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-199">Close the page.</span></span>
5. <span data-ttu-id="a2fec-200">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-200">Close the page.</span></span>
6. <span data-ttu-id="a2fec-201">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2fec-201">Close the page.</span></span>


