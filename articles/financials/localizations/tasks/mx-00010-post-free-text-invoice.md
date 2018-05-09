--- 
title: "Registrar una factura de texto libre (México)"
description: "Use el formulario Factura de texto libre para crear y registrar una factura de cliente como factura electrónica mediante el método CFDI."
author: sndray
manager: AnnBe
ms.date: 05/09/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5b5df06c9eb8eff6c3ca8310366d15bd71318eec
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="post-a-free-text-invoice-mexico"></a><span data-ttu-id="30385-103">Registrar una factura de texto libre (México)</span><span class="sxs-lookup"><span data-stu-id="30385-103">Post a free text invoice (Mexico)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="30385-104">Use el formulario Factura de texto libre para crear y registrar una factura de cliente como factura electrónica mediante el método CFDI.</span><span class="sxs-lookup"><span data-stu-id="30385-104">Use the Free text invoice form to create and post a customer invoice as an electronic invoice by using CFDI method.</span></span> <span data-ttu-id="30385-105">Debe haber iniciado sesión en una entidad jurídica mexicana.</span><span class="sxs-lookup"><span data-stu-id="30385-105">You must to be logged in a Mexican legal entity.</span></span> <span data-ttu-id="30385-106">Esta tarea se creó con los datos de la empresa de demostración MXMF.</span><span class="sxs-lookup"><span data-stu-id="30385-106">This task guide was created using the MXMF demo data company.</span></span>


## <a name="post-and-issue-a-cfdi-electronic-invoice"></a><span data-ttu-id="30385-107">Registro y emisión de una factura electrónica CFDI</span><span class="sxs-lookup"><span data-stu-id="30385-107">Post and issue a CFDI electronic invoice</span></span>
1. <span data-ttu-id="30385-108">Vaya a Clientes > Facturas > Todas las facturas de servicios.</span><span class="sxs-lookup"><span data-stu-id="30385-108">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="30385-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="30385-109">Click New.</span></span>
3. <span data-ttu-id="30385-110">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="30385-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="30385-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="30385-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="30385-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="30385-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="30385-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="30385-113">In the Description field, type a value.</span></span>
7. <span data-ttu-id="30385-114">En el campo Cuenta principal, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="30385-114">In the Main account field, specify the desired values.</span></span>
8. <span data-ttu-id="30385-115">En el campo de grupo de impuestos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="30385-115">In the Sales tax group field, type a value.</span></span>
9. <span data-ttu-id="30385-116">En el campo Grupos de impuestos de artículos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="30385-116">In the Item sales tax group field, type a value.</span></span>
10. <span data-ttu-id="30385-117">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="30385-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="30385-118">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="30385-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="30385-119">Haga clic en la ficha Facturas electrónicas.</span><span class="sxs-lookup"><span data-stu-id="30385-119">Click the Electronic invoices tab.</span></span>
13. <span data-ttu-id="30385-120">En el campo Número de propiedad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="30385-120">In the Property number field, type a value.</span></span>
    * <span data-ttu-id="30385-121">Debe especificar el número de registro de propiedad proporcionado por el gobierno mexicano cuando creó la factura de servicios del servicio de leasing.</span><span class="sxs-lookup"><span data-stu-id="30385-121">You must specify the property registration number provided by the Mexican government when you create the free text invoice for a leasing service.</span></span>  
14. <span data-ttu-id="30385-122">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="30385-122">Click Post.</span></span>
15. <span data-ttu-id="30385-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="30385-123">Click OK.</span></span>
    * <span data-ttu-id="30385-124">Tras presionar Aceptar, la factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).</span><span class="sxs-lookup"><span data-stu-id="30385-124">After you press OK, the customer invoice is posted and scheduled in a specific batch processing for issuing electronic invoices (CFDI).</span></span>  
16. <span data-ttu-id="30385-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="30385-125">Close the page.</span></span>
17. <span data-ttu-id="30385-126">Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="30385-126">Go to Accounts receivable > Invoices > E-Invoices > Export/import electronic invoice process.</span></span>
18. <span data-ttu-id="30385-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="30385-127">Click OK.</span></span>
    * <span data-ttu-id="30385-128">Este trabajo por lotes ejecuta la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica CFDI.</span><span class="sxs-lookup"><span data-stu-id="30385-128">This batch job executes the connection with the PAC web services to get the approval or cancellation of a CFDI electronic invoice.</span></span> <span data-ttu-id="30385-129">La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.</span><span class="sxs-lookup"><span data-stu-id="30385-129">The task in the batch can run manually or scheduled by specific period of time.</span></span>    <span data-ttu-id="30385-130">Tras presionar Aceptar, se establece la conexión web para obtener la validación y la firma digital.</span><span class="sxs-lookup"><span data-stu-id="30385-130">After you press OK, a web connection with the  is established in order to get the validation and digital signature.</span></span> <span data-ttu-id="30385-131">Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualiza para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="30385-131">If the electronic invoice is approved,  the PAC sends the response XML message and the status of the electronic invoice is set to Approved.</span></span> <span data-ttu-id="30385-132">Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto.</span><span class="sxs-lookup"><span data-stu-id="30385-132">An email is automatically sent out to the customer with the XML and PDF file attached.</span></span> <span data-ttu-id="30385-133">Las casillas Enviar correo y Enviar archivo de informe: PDF deben estar activadas en los parámetros de factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="30385-133">Send mail and Send report file - PDF checkboxes must be enable in the electronic invoice parameters.</span></span> <span data-ttu-id="30385-134">Si no, puede enviar por correo electrónico o imprimir un informe PDF basándose en la solicitud del cliente mediante el menú Consultar e informar > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="30385-134">Otherwise, you can email or print a PDF report based on customer's request by using Inquire and Reports > CFDI (electronic invoices) menu.</span></span>    
19. <span data-ttu-id="30385-135">Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="30385-135">Go to Accounts receivable > Inquiries and reports > CFDI (electronic invoices).</span></span>
20. <span data-ttu-id="30385-136">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="30385-136">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="30385-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="30385-137">In the list, click the link in the selected row.</span></span>


