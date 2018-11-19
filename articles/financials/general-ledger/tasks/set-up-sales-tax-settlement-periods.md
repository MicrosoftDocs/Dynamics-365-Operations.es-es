--- 
title: "Configurar períodos de liquidación de impuestos"
description: "Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos."
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 81214cc52b1488bb70ac5fd6ccc817f6f979163d
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.contentlocale: es-es
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="20d1b-103">Configurar períodos de liquidación de impuestos</span><span class="sxs-lookup"><span data-stu-id="20d1b-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20d1b-104">Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos.</span><span class="sxs-lookup"><span data-stu-id="20d1b-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="20d1b-105">Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto.</span><span class="sxs-lookup"><span data-stu-id="20d1b-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="20d1b-106">Todos los códigos de impuestos asociados con el período de liquidación se liquidarán.</span><span class="sxs-lookup"><span data-stu-id="20d1b-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="20d1b-107">Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="20d1b-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="20d1b-108">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="20d1b-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="20d1b-109">Vaya a Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="20d1b-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="20d1b-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="20d1b-110">Click New.</span></span>
3. <span data-ttu-id="20d1b-111">En el campo Período de liquidación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="20d1b-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="20d1b-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="20d1b-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="20d1b-113">En el campo Autoridad, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="20d1b-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="20d1b-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="20d1b-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="20d1b-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20d1b-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="20d1b-116">En el campo Condiciones de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="20d1b-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="20d1b-117">La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="20d1b-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="20d1b-118">Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="20d1b-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="20d1b-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="20d1b-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="20d1b-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20d1b-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="20d1b-121">Seleccione un tipo para los intervalos del período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="20d1b-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="20d1b-122">Especifique el número de unidades del intervalo de períodos por período.</span><span class="sxs-lookup"><span data-stu-id="20d1b-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="20d1b-123">Por ejemplo, un trimestre tiene 3 meses.</span><span class="sxs-lookup"><span data-stu-id="20d1b-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="20d1b-124">Active o desactive la casilla Usar procesamiento por lotes para la liquidación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="20d1b-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="20d1b-125">El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="20d1b-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="20d1b-126">Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="20d1b-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
14. <span data-ttu-id="20d1b-127">Seleccione o borre la casilla Evitar generar transacciones de impuestos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="20d1b-127">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="20d1b-128">De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="20d1b-128">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="20d1b-129">Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="20d1b-129">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="20d1b-130">Expanda la ficha Intervalos de período.</span><span class="sxs-lookup"><span data-stu-id="20d1b-130">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="20d1b-131">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="20d1b-131">Click Add.</span></span>
17. <span data-ttu-id="20d1b-132">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="20d1b-132">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="20d1b-133">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="20d1b-133">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="20d1b-134">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="20d1b-134">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="20d1b-135">Haga clic en Intervalo de período nuevo.</span><span class="sxs-lookup"><span data-stu-id="20d1b-135">Click New period interval.</span></span>
    * <span data-ttu-id="20d1b-136">Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente.</span><span class="sxs-lookup"><span data-stu-id="20d1b-136">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="20d1b-137">Puede volverse y agregar nuevos intervalos de períodos en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="20d1b-137">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="20d1b-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="20d1b-138">Close the page.</span></span>


