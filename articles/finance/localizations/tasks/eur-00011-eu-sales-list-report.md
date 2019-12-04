---
title: EUR-00011 Generar el informe de lista de ventas de la UE
description: Este procedimiento le guía por la generación del informe de la lista de ventas de la UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  EUSalesList, EUSalesListSelection, SysQueryForm, SysLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7038af3977797a0be2523f2414800400757b7007
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183571"
---
# <a name="eur-00011-generate-the-eu-sales-list-report"></a><span data-ttu-id="798f0-103">EUR-00011 Generar el informe de lista de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="798f0-103">EUR-00011 Generate the EU sales list report</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="798f0-104">Este procedimiento le guía por la generación del informe de la lista de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="798f0-104">This procedure walks you through generating the EU sales list report.</span></span> <span data-ttu-id="798f0-105">Esto incluye la transferencia de las transacciones comerciales intracomunitarias a la lista de ventas de la UE y la ejecución del informe.</span><span class="sxs-lookup"><span data-stu-id="798f0-105">This includes transferring intra-community trade transactions to the EU sales list and running the report.</span></span> <span data-ttu-id="798f0-106">Este procedimiento también incluye la creación de una transacción comercial intracomunitaria para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="798f0-106">This procedure also includes creating an intra-community trade transaction for demo purposes.</span></span> <span data-ttu-id="798f0-107">Para obtener más información acerca de los informes de la lista de ventas de la UE, incluidos requisitos previos necesarios, remítase a la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="798f0-107">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="798f0-108">Este procedimiento se aplica a todos los países o regiones europeos.</span><span class="sxs-lookup"><span data-stu-id="798f0-108">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="798f0-109">El procedimiento se creó con la empresa de datos de demostración DEMF y, por tanto, Alemania como país o región nacional de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="798f0-109">The procedure was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="798f0-110">El procedimiento también utiliza Portugal como país o región de la UE de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="798f0-110">The procedure also uses Portugal as an exemplar EU country/region.</span></span> <span data-ttu-id="798f0-111">Para poder completar este procedimiento, debe configurar los informes de listas de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="798f0-111">Before you can complete this procedure, you must configure EU sales list reporting.</span></span>

<span data-ttu-id="798f0-112">Este procedimiento está pensado para contables.</span><span class="sxs-lookup"><span data-stu-id="798f0-112">This procedure is intended for accountants.</span></span>


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a><span data-ttu-id="798f0-113">Crear una transacción de ventas intracomunitaria para fines de demostración</span><span class="sxs-lookup"><span data-stu-id="798f0-113">Create an intra-community sales transaction for demo purposes</span></span>
1. <span data-ttu-id="798f0-114">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="798f0-114">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="798f0-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="798f0-115">Click New.</span></span>
3. <span data-ttu-id="798f0-116">En el campo Cuenta de cliente, escriba "PRT-001".</span><span class="sxs-lookup"><span data-stu-id="798f0-116">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="798f0-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-117">Click OK.</span></span>
5. <span data-ttu-id="798f0-118">En el campo Código de artículo, escriba 'D0001'.</span><span class="sxs-lookup"><span data-stu-id="798f0-118">In the Item number field, type 'D0001'.</span></span>
6. <span data-ttu-id="798f0-119">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="798f0-119">Expand the Line details section.</span></span>
7. <span data-ttu-id="798f0-120">Haga clic en la ficha Configurar.</span><span class="sxs-lookup"><span data-stu-id="798f0-120">Click the Setup tab.</span></span>
8. <span data-ttu-id="798f0-121">En el campo Grupo de impuestos de artículos, escriba "FULL".</span><span class="sxs-lookup"><span data-stu-id="798f0-121">In the Item sales tax group field, type 'FULL'.</span></span>
9. <span data-ttu-id="798f0-122">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="798f0-122">Click Add line.</span></span>
10. <span data-ttu-id="798f0-123">En el campo Código de artículo, escriba 'D0003'.</span><span class="sxs-lookup"><span data-stu-id="798f0-123">In the Item number field, type 'D0003'.</span></span>
11. <span data-ttu-id="798f0-124">En el campo Grupo de impuestos de artículos, escriba "RED".</span><span class="sxs-lookup"><span data-stu-id="798f0-124">In the Item sales tax group field, type 'RED'.</span></span>
12. <span data-ttu-id="798f0-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="798f0-125">Click Save.</span></span>
13. <span data-ttu-id="798f0-126">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="798f0-126">On the Action Pane, click Invoice.</span></span>
14. <span data-ttu-id="798f0-127">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="798f0-127">Click Invoice.</span></span>
15. <span data-ttu-id="798f0-128">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="798f0-128">Expand the Parameters section.</span></span>
16. <span data-ttu-id="798f0-129">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="798f0-129">In the Quantity field, select 'All'.</span></span>
17. <span data-ttu-id="798f0-130">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="798f0-130">Expand the Setup section.</span></span>
18. <span data-ttu-id="798f0-131">En el campo Fecha de factura, establezca la fecha en "11/01/2016".</span><span class="sxs-lookup"><span data-stu-id="798f0-131">In the Invoice date field, set the date to '01/11/2016'.</span></span>
19. <span data-ttu-id="798f0-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-132">Click OK.</span></span>
20. <span data-ttu-id="798f0-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-133">Click OK.</span></span>

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a><span data-ttu-id="798f0-134">Transferir transacciones intracomunitarias a la lista de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="798f0-134">Transfer intra-community trade transactions to the EU sales list</span></span>
1. <span data-ttu-id="798f0-135">Vaya a Impuestos > Declaraciones > Comercio exterior > Lista de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="798f0-135">Go to Tax > Declarations > Foreign trade > EU sales list.</span></span>
2. <span data-ttu-id="798f0-136">Haga clic en Transferir.</span><span class="sxs-lookup"><span data-stu-id="798f0-136">Click Transfer.</span></span>
3. <span data-ttu-id="798f0-137">Seleccione Sí en el campo Artículo para transferir transacciones de artículos.</span><span class="sxs-lookup"><span data-stu-id="798f0-137">Select Yes in the Item field to transfer item transactions.</span></span>
4. <span data-ttu-id="798f0-138">Seleccione Sí en el campo Servicio para transferir transacciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="798f0-138">Select Yes in the Service field to transfer service transactions.</span></span>
    * <span data-ttu-id="798f0-139">También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para transferencia.</span><span class="sxs-lookup"><span data-stu-id="798f0-139">You can also specify additional filters on intra-community trade transactions to transfer.</span></span>  
5. <span data-ttu-id="798f0-140">Haga clic en Transferir.</span><span class="sxs-lookup"><span data-stu-id="798f0-140">Click Transfer.</span></span>
    * <span data-ttu-id="798f0-141">Compruebe que la transacción de ventas intracomunitaria se transfiere correctamente a la lista de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="798f0-141">Verify that the intra-community sales transaction is successfully transferred to the EU sales list.</span></span>  

## <a name="generate-the-eu-sales-list-report"></a><span data-ttu-id="798f0-142"> Generar el informe de lista de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="798f0-142">Generate the EU sales list report</span></span>
1. <span data-ttu-id="798f0-143">Haga clic en Informes.</span><span class="sxs-lookup"><span data-stu-id="798f0-143">Click Reporting.</span></span>
2. <span data-ttu-id="798f0-144">En el campo Período de notificación, seleccione "Mensual".</span><span class="sxs-lookup"><span data-stu-id="798f0-144">In the Reporting period field, select 'Monthly'.</span></span>
3. <span data-ttu-id="798f0-145">En el campo Fecha inicial, defina la fecha en "01/01/2016".</span><span class="sxs-lookup"><span data-stu-id="798f0-145">In the From date field, set the date to '01/01/2016'.</span></span>
4. <span data-ttu-id="798f0-146">Seleccione Sí en el campo Generar archivo.</span><span class="sxs-lookup"><span data-stu-id="798f0-146">Select Yes in the Generate file field.</span></span>
5. <span data-ttu-id="798f0-147">Seleccione Sí en el campo Generar informe.</span><span class="sxs-lookup"><span data-stu-id="798f0-147">Select Yes in the Generate report field.</span></span>
6. <span data-ttu-id="798f0-148">En el campo Nombre de archivo, escriba "EUSalesList".</span><span class="sxs-lookup"><span data-stu-id="798f0-148">In the File name field, type 'EUSalesList'.</span></span>
7. <span data-ttu-id="798f0-149">En el campo Nombre de archivo de informe, escriba "EUSalesList".</span><span class="sxs-lookup"><span data-stu-id="798f0-149">In the Report file name field, type 'EUSalesList'.</span></span>
8. <span data-ttu-id="798f0-150">En el campo Id. de registro de lista de ventas de la UE, escriba "123".</span><span class="sxs-lookup"><span data-stu-id="798f0-150">In the EU Sales List Registration ID field, type '123'.</span></span>
    * <span data-ttu-id="798f0-151">Este campo solo está disponible para Alemania.</span><span class="sxs-lookup"><span data-stu-id="798f0-151">This field is only available for Germany.</span></span>  
    * <span data-ttu-id="798f0-152">También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para incluirlas en el informe.</span><span class="sxs-lookup"><span data-stu-id="798f0-152">You can also specify additional filters on intra-community trade transactions to include in the report.</span></span>  
9. <span data-ttu-id="798f0-153">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-153">Click OK.</span></span>
    * <span data-ttu-id="798f0-154">Compruebe que las ventanas emergentes aparecen para confirmar que se están descargando el archivo y el informe de control.</span><span class="sxs-lookup"><span data-stu-id="798f0-154">Verify that pop-up windows appear to confirm that the file and the control report are being downloaded.</span></span>  

## <a name="mark-eu-sales-list-lines-as-reported"></a><span data-ttu-id="798f0-155">Marcar las líneas de la lista de ventas de la UE como notificadas</span><span class="sxs-lookup"><span data-stu-id="798f0-155">Mark EU sales list lines as Reported</span></span>
1. <span data-ttu-id="798f0-156">Haga clic en Marcar.</span><span class="sxs-lookup"><span data-stu-id="798f0-156">Click Mark.</span></span>
2. <span data-ttu-id="798f0-157">Haga clic en Marcar como notificado.</span><span class="sxs-lookup"><span data-stu-id="798f0-157">Click Mark as reported.</span></span>
3. <span data-ttu-id="798f0-158">En la lista, seleccione la fila para el campo Fecha de factura.</span><span class="sxs-lookup"><span data-stu-id="798f0-158">In the list, select the row for the Invoice date field.</span></span>
4. <span data-ttu-id="798f0-159">En el campo Criterios, escriba "01/01/2016..01/31/2016".</span><span class="sxs-lookup"><span data-stu-id="798f0-159">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="798f0-160">En la lista, seleccione la fila para el campo Estado de notificación.</span><span class="sxs-lookup"><span data-stu-id="798f0-160">In the list, select the row for the Reporting status field.</span></span>
6. <span data-ttu-id="798f0-161">En el campo Criterios, seleccione "Incluido".</span><span class="sxs-lookup"><span data-stu-id="798f0-161">In the Criteria field, select 'Included'.</span></span>
    * <span data-ttu-id="798f0-162">También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para marcarlas como notificadas.</span><span class="sxs-lookup"><span data-stu-id="798f0-162">You can also specify additional filters on intra-community trade transactions to mark as Reported.</span></span>  
7. <span data-ttu-id="798f0-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-163">Click OK.</span></span>
8. <span data-ttu-id="798f0-164">En el campo Selección, seleccione "Notificado".</span><span class="sxs-lookup"><span data-stu-id="798f0-164">In the Selection field, select 'Reported'.</span></span>

## <a name="mark-eu-sales-list-lines-as-closed"></a><span data-ttu-id="798f0-165">Marcar las líneas de la lista de ventas de la UE como cerradas</span><span class="sxs-lookup"><span data-stu-id="798f0-165">Mark EU sales list lines as Closed</span></span>
1. <span data-ttu-id="798f0-166">Haga clic en Marcar.</span><span class="sxs-lookup"><span data-stu-id="798f0-166">Click Mark.</span></span>
2. <span data-ttu-id="798f0-167">Haga clic en Marcar como cerrado.</span><span class="sxs-lookup"><span data-stu-id="798f0-167">Click Mark as closed.</span></span>
3. <span data-ttu-id="798f0-168">En la lista, marque la fila para el campo Fecha de factura.</span><span class="sxs-lookup"><span data-stu-id="798f0-168">In the list, mark the row for the Invoice date field.</span></span>
4. <span data-ttu-id="798f0-169">En el campo Criterios, escriba "01/01/2016..01/31/2016".</span><span class="sxs-lookup"><span data-stu-id="798f0-169">In the Criteria field, type '01/01/2016..01/31/2016'.</span></span>
5. <span data-ttu-id="798f0-170">En la lista, marque la fila para el campo Estado de notificación.</span><span class="sxs-lookup"><span data-stu-id="798f0-170">In the list, mark the row for the Reporting status field.</span></span>
6. <span data-ttu-id="798f0-171">En el campo Criterios, seleccione "Notificado".</span><span class="sxs-lookup"><span data-stu-id="798f0-171">In the Criteria field, select ‘Reported’.</span></span>
    * <span data-ttu-id="798f0-172">También puede especificar filtros adicionales en transacciones comerciales intracomunitarias para marcarlas como cerradas.</span><span class="sxs-lookup"><span data-stu-id="798f0-172">You can also specify additional filters on intra-community trade transactions to mark as Closed.</span></span>  
7. <span data-ttu-id="798f0-173">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="798f0-173">Click OK.</span></span>
8. <span data-ttu-id="798f0-174">En el campo Selección, seleccione "Cerrado".</span><span class="sxs-lookup"><span data-stu-id="798f0-174">In the Selection field, select 'Closed'.</span></span>
