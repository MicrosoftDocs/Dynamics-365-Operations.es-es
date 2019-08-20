---
title: Configurar períodos de liquidación de impuestos
description: Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8304d9e8997a5d31740ee1203aa4bf0603014056
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862997"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="7cf75-103">Configurar períodos de liquidación de impuestos</span><span class="sxs-lookup"><span data-stu-id="7cf75-103">Set up sales tax settlement periods</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7cf75-104">Los períodos de liquidación de impuestos contienen información sobre los intervalos de períodos para los que tienen que notificarse y pagarse los impuestos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-104">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="7cf75-105">Un proceso de liquidación se puede ejecutar para un período de liquidación de un intervalo de fechas concreto.</span><span class="sxs-lookup"><span data-stu-id="7cf75-105">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="7cf75-106">Todos los códigos de impuestos asociados con el período de liquidación se liquidarán.</span><span class="sxs-lookup"><span data-stu-id="7cf75-106">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="7cf75-107">Según la configuración de la autoridad fiscal relacionada, la deuda tributaria se registra en un proveedor o en una cuenta de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="7cf75-107">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>



<span data-ttu-id="7cf75-108">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="7cf75-108">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="7cf75-109">Vaya a Impuestos > Impuestos indirectos > Impuestos > Períodos de liquidación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-109">Go to Tax > Indirect taxes > Sales tax > Sales tax settlement periods.</span></span>
2. <span data-ttu-id="7cf75-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7cf75-110">Click New.</span></span>
3. <span data-ttu-id="7cf75-111">En el campo Período de liquidación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7cf75-111">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="7cf75-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7cf75-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7cf75-113">En el campo Autoridad, seleccione la autoridad fiscal que recibe los informes y los pagos creados para el período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="7cf75-113">In the Authority field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="7cf75-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7cf75-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="7cf75-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7cf75-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7cf75-116">En el campo Condiciones de pago, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7cf75-116">In the Terms of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7cf75-117">La autoridad fiscal relacionada se puede establecer como proveedor y la liquidación de impuestos creará una factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="7cf75-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="7cf75-118">Las condiciones de pago definen la fecha de vencimiento de la factura de proveedor abierta.</span><span class="sxs-lookup"><span data-stu-id="7cf75-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
9. <span data-ttu-id="7cf75-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7cf75-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="7cf75-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7cf75-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="7cf75-121">Seleccione un tipo para los intervalos del período de liquidación.</span><span class="sxs-lookup"><span data-stu-id="7cf75-121">Select a type for the settlement period intervals.</span></span>
12. <span data-ttu-id="7cf75-122">Especifique el número de unidades del intervalo de períodos por período.</span><span class="sxs-lookup"><span data-stu-id="7cf75-122">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="7cf75-123">Por ejemplo, un trimestre tiene 3 meses.</span><span class="sxs-lookup"><span data-stu-id="7cf75-123">For example, a quarter has 3 months.</span></span>
13. <span data-ttu-id="7cf75-124">Active o desactive la casilla Usar procesamiento por lotes para la liquidación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-124">Select or clear the Use batch processing for sales tax settlement check box.</span></span>
    * <span data-ttu-id="7cf75-125">El proceso de liquidación para el período de liquidación se puede procesar como un trabajo por lotes en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7cf75-125">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="7cf75-126">Esto se recomienda para un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-126">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="7cf75-127">No se admite actualmente en Austria, Bélgica, España, Italia, Japón y Países Bajos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-127">Currently this is not supported in Austria, Belgium, Spain, Italy, Japan, and the Netherlands.</span></span>
14. <span data-ttu-id="7cf75-128">Seleccione o borre la casilla Evitar generar transacciones de impuestos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="7cf75-128">Select or clear the Prevent generating offset tax transactions check box.</span></span>
    * <span data-ttu-id="7cf75-129">De forma predeterminada, el sistema genera transacciones de impuestos de contrapartida durante el proceso de liquidación, lo que puede crear un problema de rendimiento si existe un gran número de transacciones de impuestos dentro de un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="7cf75-129">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="7cf75-130">Seleccione esta casilla de verificación para evitar generar transacciones de impuestos de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="7cf75-130">Select this check box to prevent generating offset tax transactions.</span></span>
15. <span data-ttu-id="7cf75-131">Expanda la ficha Intervalos de período.</span><span class="sxs-lookup"><span data-stu-id="7cf75-131">Expand the Period intervals tab.</span></span>
16. <span data-ttu-id="7cf75-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7cf75-132">Click Add.</span></span>
17. <span data-ttu-id="7cf75-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7cf75-133">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="7cf75-134">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="7cf75-134">In the From date field, enter a date.</span></span>
19. <span data-ttu-id="7cf75-135">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="7cf75-135">In the To date field, enter a date.</span></span>
20. <span data-ttu-id="7cf75-136">Haga clic en Intervalo de período nuevo.</span><span class="sxs-lookup"><span data-stu-id="7cf75-136">Click New period interval.</span></span>
    * <span data-ttu-id="7cf75-137">Una vez que se ha especificado el primer intervalo de períodos, los nuevos períodos se pueden crear automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7cf75-137">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="7cf75-138">Puede volverse y agregar nuevos intervalos de períodos en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="7cf75-138">You can come back and add new period intervals as required.</span></span>  
21. <span data-ttu-id="7cf75-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7cf75-139">Close the page.</span></span>

