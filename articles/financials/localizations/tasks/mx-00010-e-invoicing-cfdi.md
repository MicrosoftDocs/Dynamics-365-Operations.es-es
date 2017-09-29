--- 
title: "E- Facturación CFDI (México)"
description: "Esta tarea le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI."
author: sndray
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5944746c73def13d609d84d58b52fe76b4ca1abb
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="e-invoicing-cfdi-mexico"></a><span data-ttu-id="39749-103">E- Facturación CFDI (México)</span><span class="sxs-lookup"><span data-stu-id="39749-103">E-invoicing CFDI (Mexico)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39749-104">Esta tarea le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI.</span><span class="sxs-lookup"><span data-stu-id="39749-104">This task walks you through creating and posting a customer invoice as an electronic invoice by using the CFDI method.</span></span> <span data-ttu-id="39749-105">Puede crear y registrar varios pedidos de ventas como facturas electrónicas y enviar los archivos .pdf y .xml como archivos adjuntos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="39749-105">You can create and post multiple sales orders as electronic invoices and send the .pdf and .xml files as email attachments to customers.</span></span> <span data-ttu-id="39749-106">Esta tarea solo se puede completar si está registrado en una entidad jurídica con dirección principal en México.</span><span class="sxs-lookup"><span data-stu-id="39749-106">This task can only be completed if you are logged into a legal entity with a primary address in Mexico.</span></span> <span data-ttu-id="39749-107">Esta tarea usa la empresa de demostración MXMF.</span><span class="sxs-lookup"><span data-stu-id="39749-107">This task uses the MXMF demo company data.</span></span>

1. <span data-ttu-id="39749-108">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="39749-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="39749-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="39749-109">Click New.</span></span>
3. <span data-ttu-id="39749-110">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39749-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="39749-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39749-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="39749-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="39749-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-113">Click OK.</span></span>
7. <span data-ttu-id="39749-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="39749-115">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39749-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="39749-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="39749-117">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="39749-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="39749-118">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="39749-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="39749-119">Haga clic en la ficha Configurar.</span><span class="sxs-lookup"><span data-stu-id="39749-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="39749-120">En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39749-120">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="39749-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="39749-122">En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39749-122">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="39749-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39749-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="39749-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="39749-125">Haga clic en la ficha Producto.</span><span class="sxs-lookup"><span data-stu-id="39749-125">Click the Product tab.</span></span>
19. <span data-ttu-id="39749-126">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39749-126">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="39749-127">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39749-127">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="39749-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39749-128">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="39749-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-129">Click OK.</span></span>
23. <span data-ttu-id="39749-130">En el campo Aduana, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39749-130">In the Custom number field, type a value.</span></span>
    * <span data-ttu-id="39749-131">Introduzca el número del documento de aduanas que se generó cuando se importó el artículo.</span><span class="sxs-lookup"><span data-stu-id="39749-131">Enter the number of the customs document that was generated when the item was imported.</span></span>  
24. <span data-ttu-id="39749-132">En el campo Fecha de aduana, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="39749-132">In the Custom date field, enter a date.</span></span>
    * <span data-ttu-id="39749-133">Seleccione la fecha en la que se importó el artículo.</span><span class="sxs-lookup"><span data-stu-id="39749-133">Select the date when the item was imported.</span></span>  
25. <span data-ttu-id="39749-134">En el campo Nombre de aduana, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39749-134">In the Custom name field, type a value.</span></span>
    * <span data-ttu-id="39749-135">Escriba el nombre de la autoridad de aduanas del país o región de donde se importó el artículo.</span><span class="sxs-lookup"><span data-stu-id="39749-135">Enter the name of the customs authority in the country/region that the item was imported from.</span></span>  <span data-ttu-id="39749-136">Si escribe valores en los campos Número de aduana, Fecha de aduana y Nombre de aduana, no podrá escribir un valor en el campo Número de propiedad.</span><span class="sxs-lookup"><span data-stu-id="39749-136">If you enter values in the Custom number, Custom date, and Custom name fields, you cannot enter a value in the Property number field.</span></span>  
26. <span data-ttu-id="39749-137">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="39749-137">In the Unit price field, enter a number.</span></span>
27. <span data-ttu-id="39749-138">Expanda o contraiga la sección Encabezado de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="39749-138">Expand or collapse the Sales order header section.</span></span>
28. <span data-ttu-id="39749-139">En el panel de acciones, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="39749-139">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="39749-140">Haga clic en Confirmar pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="39749-140">Click Confirm sales order.</span></span>
30. <span data-ttu-id="39749-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-141">Click OK.</span></span>
31. <span data-ttu-id="39749-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-142">Click OK.</span></span>
32. <span data-ttu-id="39749-143">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="39749-143">On the Action Pane, click Invoice.</span></span>
33. <span data-ttu-id="39749-144">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="39749-144">Click Invoice.</span></span>
34. <span data-ttu-id="39749-145">Expanda la sección Parámetros para revisar los parámetros antes del registro.</span><span class="sxs-lookup"><span data-stu-id="39749-145">Expand the Parameters section to review the parameters before posting.</span></span>
35. <span data-ttu-id="39749-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-146">Click OK.</span></span>
    * <span data-ttu-id="39749-147">Tras presionar Aceptar, la factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).</span><span class="sxs-lookup"><span data-stu-id="39749-147">After you press OK, the customer invoice is posted and scheduled in a specific batch processing for issuing electronic invoices (CFDI).</span></span>  
36. <span data-ttu-id="39749-148">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-148">Click OK.</span></span>
37. <span data-ttu-id="39749-149">Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="39749-149">Go to Accounts receivable > Invoices > E-Invoices > Export/import electronic invoice process.</span></span>
38. <span data-ttu-id="39749-150">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39749-150">Click OK.</span></span>
    * <span data-ttu-id="39749-151">Este trabajo por lotes inicia la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica (CFDI).</span><span class="sxs-lookup"><span data-stu-id="39749-151">This batch job initiates the connection with the PAC web services to get the approval or cancellation of an electronic invoice (CFDI).</span></span> <span data-ttu-id="39749-152">La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="39749-152">The task in the batch can run manually or it can be scheduled by specific period of time.</span></span>      <span data-ttu-id="39749-153">Tras presionar Aceptar, la validación y la firma digital se recuperarán de PAC.</span><span class="sxs-lookup"><span data-stu-id="39749-153">After you press OK, the validation and the digital signature will be retrieved from the PAC.</span></span> <span data-ttu-id="39749-154">Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualizará para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="39749-154">If the electronic invoice is approved,  the PAC send the response XML message and the status of the electronic invoice will update to be Approved.</span></span> <span data-ttu-id="39749-155">Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto.</span><span class="sxs-lookup"><span data-stu-id="39749-155">An email is automatically sent out to the customer with the XML and PDF file attached.</span></span> <span data-ttu-id="39749-156">Los controles deslizantes Enviar correo y Enviar archivo de informe: PDF se deben establecer en "Sí" en la página de parámetros de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="39749-156">The Send mail and Send report file - PDF sliders must be set to "Yes" on the electronic invoice parameters page.</span></span> <span data-ttu-id="39749-157">Si no, puede enviar por correo electrónico o imprimir el informe PDF basándose en la solicitud del cliente mediante el menú Consultar e informar > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="39749-157">Otherwise, you can email or print PDF report based on the customer's request by using the Inquire and Reports > CFDI (electronic invoices) menu.</span></span>  
39. <span data-ttu-id="39749-158">Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="39749-158">Go to Accounts receivable > Inquiries and reports > CFDI (electronic invoices).</span></span>
40. <span data-ttu-id="39749-159">En la lista, haga clic en la factura electrónica que revisar.</span><span class="sxs-lookup"><span data-stu-id="39749-159">In the list, click the electronic invoice to review.</span></span>


