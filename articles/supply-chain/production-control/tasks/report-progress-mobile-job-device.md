---
title: Notificar progreso en un dispositivo móvil de trabajo
description: Este procedimiento le muestra cómo iniciar y notificar el progreso en cuanto a un trabajo de producción en el formulario de registro de dispositivo de trabajo.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a659dbb851dd6beeb59228116095577d2b4cb97a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210534"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="2b4b8-103">Notificar progreso en un dispositivo móvil de trabajo</span><span class="sxs-lookup"><span data-stu-id="2b4b8-103">Report progress on a mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2b4b8-104">Este procedimiento le muestra cómo iniciar y notificar el progreso en cuanto a un trabajo de producción en el formulario de registro de dispositivo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="2b4b8-105">Para poder ejecutar este procedimiento, debe tener el rol del administrador del sistema o del operador de maquinaria asociado a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="2b4b8-106">Vaya a Control de producción > Ejecución de fabricación > Dispositivo de tarjetas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="2b4b8-107">En el campo WorkerTextField, especifique la tarjeta de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="2b4b8-108">En el tipo de datos de demostración, escriba USMF "123" para Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="2b4b8-109">Haga clic en Iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-109">Click Log in.</span></span>
4. <span data-ttu-id="2b4b8-110">Haga clic en el botón Filtrar.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-110">Click the Filter button.</span></span>
5. <span data-ttu-id="2b4b8-111">Active o desactive la casilla Aplicar filtro de configuración.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="2b4b8-112">Si establece un filtro, puede usar la unidad de producción 110 en USMF.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="2b4b8-113">En el campo Unidad de producción, seleccione el grupo de recursos para el que el trabajador puede trabajar en los trabajos de producción.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="2b4b8-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2b4b8-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-115">Click OK.</span></span>
9. <span data-ttu-id="2b4b8-116">Haga clic en el botón Iniciar trabajo.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-116">Click the Start job button.</span></span>
10. <span data-ttu-id="2b4b8-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-117">Click OK.</span></span>
11. <span data-ttu-id="2b4b8-118">Haga clic en el botón Informar progreso.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="2b4b8-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-119">Click OK.</span></span>
13. <span data-ttu-id="2b4b8-120">Haga clic en el botón Trabajo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-120">Click the Next job button.</span></span>
14. <span data-ttu-id="2b4b8-121">Haga clic en Asignado para ver una descripción del botón de todos los trabajos de producción.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="2b4b8-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-122">Close the page.</span></span>
16. <span data-ttu-id="2b4b8-123">Haga clic en el botón Interrupción.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-123">Click the Break button.</span></span>
17. <span data-ttu-id="2b4b8-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="2b4b8-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-125">Click OK.</span></span>
19. <span data-ttu-id="2b4b8-126">Haga clic en el botón Baja laboral.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="2b4b8-127">Seleccione para cerrar sesión.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-127">Select to log out.</span></span>
21. <span data-ttu-id="2b4b8-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-128">Click OK.</span></span>
22. <span data-ttu-id="2b4b8-129">En el campo WorkerTextField, inicie sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="2b4b8-130">Puede seleccionar el trabajador "123" en datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="2b4b8-131">Haga clic en Iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-131">Click Log in.</span></span>
24. <span data-ttu-id="2b4b8-132">Haga clic en Detener descanso.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-132">Click Stop break.</span></span>
25. <span data-ttu-id="2b4b8-133">Haga clic en el botón Actividad.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-133">Click the Activity button.</span></span>
26. <span data-ttu-id="2b4b8-134">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-134">Click Cancel.</span></span>
27. <span data-ttu-id="2b4b8-135">Haga clic en el botón Baja laboral.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="2b4b8-136">Seleccione para la hora de salida.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-136">Select to clock out.</span></span>
29. <span data-ttu-id="2b4b8-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2b4b8-137">Click OK.</span></span>
30. <span data-ttu-id="2b4b8-138">Seleccione un motivo por el que ha estado realizando la hora de salida pronto.</span><span class="sxs-lookup"><span data-stu-id="2b4b8-138">Select a reason why you are clocking out early.</span></span>

