---
title: Agregar a su diario de rendimiento y enviar elogio a alguien
description: El diario de rendimiento contiene información relacionada con cómo alcanzó sus objetivos o cuál fue su rendimiento durante un período.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EssWorkspace, HcmPerfJournal, HcmPerfJournalAddLink, HcmPerfPraise, HcmWorkerLookUpByPerson, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 574925f0e278ad7bd3c654432fd0f862fd3c3259
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115881"
---
# <a name="add-to-your-performance-journal-and-send-praise-to-someone"></a><span data-ttu-id="af9b3-103">Agregar a su diario de rendimiento y enviar elogio a alguien</span><span class="sxs-lookup"><span data-stu-id="af9b3-103">Add to your performance journal and send praise to someone</span></span>

<span data-ttu-id="af9b3-104">El diario de rendimiento contiene información relacionada con cómo alcanzó sus objetivos o cuál fue su rendimiento durante un período.</span><span class="sxs-lookup"><span data-stu-id="af9b3-104">The performance journal holds information that relates to how you met your goals or how you performed during a period.</span></span> <span data-ttu-id="af9b3-105">También puede elogiar las acciones de un compañero de trabajo del diario.</span><span class="sxs-lookup"><span data-stu-id="af9b3-105">You can also praise the actions of a co-worker from the journal.</span></span> <span data-ttu-id="af9b3-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="af9b3-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="af9b3-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="af9b3-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="af9b3-108">Vaya a Todos los espacios de trabajo > Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="af9b3-108">Go to All workspaces > Employee self service.</span></span>
2. <span data-ttu-id="af9b3-109">Haga clic en Diario de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="af9b3-109">Click Performance journal.</span></span>
3. <span data-ttu-id="af9b3-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="af9b3-110">Click New.</span></span>
4. <span data-ttu-id="af9b3-111">En el campo Título, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="af9b3-111">In the Title field, type a value.</span></span>
5. <span data-ttu-id="af9b3-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="af9b3-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="af9b3-113">La fecha del diario de rendimiento es la fecha de creación del diario.</span><span class="sxs-lookup"><span data-stu-id="af9b3-113">The performance journal date is the date that the journal was created.</span></span>  
    * <span data-ttu-id="af9b3-114">El origen representa el lugar de donde procede el diario de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="af9b3-114">The source represents where the performance journal came from.</span></span> <span data-ttu-id="af9b3-115">Cuando usted crea uno, procede de Mi diario.</span><span class="sxs-lookup"><span data-stu-id="af9b3-115">When you create one, it comes from My journal.</span></span> <span data-ttu-id="af9b3-116">Si su responsable crea uno, procede del Diario del responsable.</span><span class="sxs-lookup"><span data-stu-id="af9b3-116">If your manager creates one, it comes from the Manager journal.</span></span>  
    * <span data-ttu-id="af9b3-117">Puede compartir este diario con su responsable o que sea visible únicamente para usted.</span><span class="sxs-lookup"><span data-stu-id="af9b3-117">You can share this journal with your manager or make it only visible to you.</span></span>  
6. <span data-ttu-id="af9b3-118">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="af9b3-118">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="af9b3-119">En el campo Fecha de finalización, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="af9b3-119">In the Date completed field, enter a date.</span></span>
8. <span data-ttu-id="af9b3-120">Seleccione Sí en el campo Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="af9b3-120">Select Yes in the Development plan field.</span></span>
9. <span data-ttu-id="af9b3-121">En el campo Palabras clave, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="af9b3-121">In the Keywords field, type a value.</span></span>
10. <span data-ttu-id="af9b3-122">Haga clic en Agregar vínculo externo.</span><span class="sxs-lookup"><span data-stu-id="af9b3-122">Click Add external link.</span></span>
11. <span data-ttu-id="af9b3-123">En el campo Descripción, escriba "Envision".</span><span class="sxs-lookup"><span data-stu-id="af9b3-123">In the Description field, type 'Envision'.</span></span>
12. <span data-ttu-id="af9b3-124">En el campo Dirección de Internet, escriba "https://www.microsoft.com/en/envision/default".</span><span class="sxs-lookup"><span data-stu-id="af9b3-124">In the Internet address field, type 'https://www.microsoft.com/en/envision/default'.</span></span>
13. <span data-ttu-id="af9b3-125">Haga clic en la leyenda debajo del botón Guardar denominado "Diario de rendimiento" para volver a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="af9b3-125">Click on the caption below the Save button called "Performance journal" to return to the grid.</span></span>
    * <span data-ttu-id="af9b3-126">Puede agregar el diario o diarios seleccionados a un objetivo de modo que aparezca al abrir el objetivo.</span><span class="sxs-lookup"><span data-stu-id="af9b3-126">You can add the selected journal or journals to a goal so that it appears when you open the goal.</span></span> <span data-ttu-id="af9b3-127">Se agregará un vínculo en la pestaña rápida Vínculos. Si agrega un diario a un objetivo y luego el objetivo a una revisión, el diario aparecerá en la revisión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="af9b3-127">A link will be added in the Links fast tab.    If you add a journal to a goal and then add the goal to a review, the journal will appear on the review automatically.</span></span>  
    * <span data-ttu-id="af9b3-128">Puede agregar el diario o diarios seleccionados a una revisión de modo que aparezca al abrir la revisión.</span><span class="sxs-lookup"><span data-stu-id="af9b3-128">You can add the selected journal or journals to a review so that it appears when you open the review.</span></span>    <span data-ttu-id="af9b3-129">Se agregará un vínculo en la ficha Vínculos rápidos.</span><span class="sxs-lookup"><span data-stu-id="af9b3-129">A link will be added in the Links fast tab.</span></span>  
14. <span data-ttu-id="af9b3-130">Haga clic en Agregar rápido.</span><span class="sxs-lookup"><span data-stu-id="af9b3-130">Click Quick add.</span></span>
15. <span data-ttu-id="af9b3-131">En el campo Título, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="af9b3-131">In the Title field, type a value.</span></span>
16. <span data-ttu-id="af9b3-132">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="af9b3-132">In the Description field, type a value.</span></span>
17. <span data-ttu-id="af9b3-133">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="af9b3-133">Click Save.</span></span>
18. <span data-ttu-id="af9b3-134">Haga clic en Enviar elogio.</span><span class="sxs-lookup"><span data-stu-id="af9b3-134">Click Send praise.</span></span>
19. <span data-ttu-id="af9b3-135">Seleccione una persona de la lista de empleados de la empresa.</span><span class="sxs-lookup"><span data-stu-id="af9b3-135">Select a person from the list of employees in the company.</span></span>
20. <span data-ttu-id="af9b3-136">En el campo Descripción, especifique "¡Gracias por toda la ayuda recibida en la conferencia!".</span><span class="sxs-lookup"><span data-stu-id="af9b3-136">In the Description field, enter 'Thanks for all the help at the conference!'.</span></span>
21. <span data-ttu-id="af9b3-137">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="af9b3-137">Click Send.</span></span>

