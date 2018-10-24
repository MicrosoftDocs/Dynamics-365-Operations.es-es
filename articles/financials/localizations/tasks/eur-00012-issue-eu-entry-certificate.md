--- 
title: "EUR-00012 Emisión de un certificado de entrada de la UE"
description: "Este procedimiento le muestra cómo habilitar un certificado de entrada de la UE, cómo configurar una cuenta de cliente para usar certificados de entrada y emitir un certificado."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5a566b1d25064e3fccc8953dc883aa63bd16a301
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="21f04-103">EUR-00012 Emisión de un certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="21f04-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="21f04-104">Este procedimiento le muestra cómo habilitar un certificado de entrada de la UE, cómo configurar una cuenta de cliente para usar certificados de entrada y emitir un certificado.</span><span class="sxs-lookup"><span data-stu-id="21f04-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="21f04-105">Este procedimiento se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="21f04-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="21f04-106">Habilitar administración de certificados de entrada</span><span class="sxs-lookup"><span data-stu-id="21f04-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="21f04-107">Vaya a Clientes > Configuración > Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="21f04-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="21f04-108">Haga clic en la ficha Envíos.</span><span class="sxs-lookup"><span data-stu-id="21f04-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="21f04-109">Expanda la sección Certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="21f04-110">Seleccione Sí en el campo Habilitar administración de certificados de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="21f04-111">Seleccione Sí en el campo Habilitar emisión de certificados de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="21f04-112">Haga clic en la ficha Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="21f04-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="21f04-113">En la lista, busque y seleccione Fila de certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="21f04-114">En el campo Código de secuencia numérica, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="21f04-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="21f04-115">Configuración de un cliente</span><span class="sxs-lookup"><span data-stu-id="21f04-115">Set up a customer</span></span>
1. <span data-ttu-id="21f04-116">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="21f04-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="21f04-117">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="21f04-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="21f04-118">Por ejemplo, filtre por el campo Cuenta, por el valor "DE-015".</span><span class="sxs-lookup"><span data-stu-id="21f04-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="21f04-119">Abra los detalles de la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="21f04-119">Open customer account details.</span></span>
4. <span data-ttu-id="21f04-120">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="21f04-120">Click Edit.</span></span>
5. <span data-ttu-id="21f04-121">Expanda la sección Factura y entrega.</span><span class="sxs-lookup"><span data-stu-id="21f04-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="21f04-122">Seleccione Sí en el campo Se necesita certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="21f04-123">Seleccione Sí en el campo Emitir certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="21f04-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="21f04-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="21f04-125">Creación automática de un certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="21f04-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="21f04-126">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="21f04-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="21f04-127">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="21f04-127">Click New.</span></span>
3. <span data-ttu-id="21f04-128">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="21f04-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="21f04-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-129">Click OK.</span></span>
5. <span data-ttu-id="21f04-130">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="21f04-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="21f04-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="21f04-131">Click Save.</span></span>
7. <span data-ttu-id="21f04-132">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="21f04-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="21f04-133">Haga clic en Registrar albarán.</span><span class="sxs-lookup"><span data-stu-id="21f04-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="21f04-134">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="21f04-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="21f04-135">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="21f04-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="21f04-136">Quite la marca de la casilla Emitir certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="21f04-137">Un certificado de entrada se puede emitir al registrar un albarán o al facturar un pedido.</span><span class="sxs-lookup"><span data-stu-id="21f04-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="21f04-138">Deje la casilla Emitir certificado de entrada sin marcar para emitirlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="21f04-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="21f04-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-139">Click OK.</span></span>
13. <span data-ttu-id="21f04-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-140">Click OK.</span></span>
14. <span data-ttu-id="21f04-141">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="21f04-142">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-142">Click Invoice.</span></span>
    * <span data-ttu-id="21f04-143">Compruebe que las casillas Se necesita certificado de entrada y Emitir certificado de entrada en la sección Visión general estén marcadas.</span><span class="sxs-lookup"><span data-stu-id="21f04-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="21f04-144">También puede seleccionar la casilla Imprimir certificado de entrada para permitir imprimir el certificado.</span><span class="sxs-lookup"><span data-stu-id="21f04-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="21f04-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-145">Click OK.</span></span>
17. <span data-ttu-id="21f04-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-146">Click OK.</span></span>
18. <span data-ttu-id="21f04-147">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="21f04-148">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-148">Click Invoice.</span></span>
20. <span data-ttu-id="21f04-149">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="21f04-150">Haga clic en Ver certificados de entrada emitidos.</span><span class="sxs-lookup"><span data-stu-id="21f04-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="21f04-151">Haga clic en Imprimir.</span><span class="sxs-lookup"><span data-stu-id="21f04-151">Click Print.</span></span>
23. <span data-ttu-id="21f04-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="21f04-152">Close the page.</span></span>
24. <span data-ttu-id="21f04-153">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="21f04-153">Click Change status.</span></span>
25. <span data-ttu-id="21f04-154">En el campo Nuevo estado, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="21f04-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="21f04-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-155">Click OK.</span></span>
27. <span data-ttu-id="21f04-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="21f04-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="21f04-157">Creación manual de un certificado de entrada de la UE</span><span class="sxs-lookup"><span data-stu-id="21f04-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="21f04-158">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="21f04-159">Haga clic en Crear certificado de entrada.</span><span class="sxs-lookup"><span data-stu-id="21f04-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="21f04-160">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="21f04-160">Click OK.</span></span>
4. <span data-ttu-id="21f04-161">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="21f04-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="21f04-162">Haga clic en Ver certificados de entrada emitidos.</span><span class="sxs-lookup"><span data-stu-id="21f04-162">Click View issued entry certificates.</span></span>


