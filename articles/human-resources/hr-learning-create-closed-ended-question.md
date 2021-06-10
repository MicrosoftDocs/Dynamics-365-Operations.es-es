---
title: Crear una pregunta cerrada
description: Las preguntas cerradas le permiten proporcionar opciones entre las que el encuestado puede elegir.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0316661d8be04cc5912e88bc50b3a1c7a73bbcb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056693"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="cf379-103">Crear una pregunta cerrada</span><span class="sxs-lookup"><span data-stu-id="cf379-103">Create a closed ended question</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="cf379-104">Las preguntas cerradas le permiten proporcionar opciones entre las que el encuestado puede elegir.</span><span class="sxs-lookup"><span data-stu-id="cf379-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="cf379-105">Primero, necesita crear el grupo de respuestas con las respuestas y luego crear la pregunta que usará el grupo de respuestas.</span><span class="sxs-lookup"><span data-stu-id="cf379-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="cf379-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="cf379-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="cf379-107">Creación de un grupo de respuestas</span><span class="sxs-lookup"><span data-stu-id="cf379-107">Create an answer group</span></span>
1. <span data-ttu-id="cf379-108">Vaya a Cuestionario > Diseño > Grupos de respuestas.</span><span class="sxs-lookup"><span data-stu-id="cf379-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="cf379-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-109">Click New.</span></span>
3. <span data-ttu-id="cf379-110">En el campo Grupo de respuestas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="cf379-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="cf379-112">Use la función Aleatorizar para colocar aleatoriamente las respuestas en un orden diferente cada vez que se use el grupo de respuestas para una pregunta.</span><span class="sxs-lookup"><span data-stu-id="cf379-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="cf379-113">Haga clic en Respuesta.</span><span class="sxs-lookup"><span data-stu-id="cf379-113">Click Answer.</span></span>
6. <span data-ttu-id="cf379-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-114">Click New.</span></span>
    * <span data-ttu-id="cf379-115">El número de secuencia controla el orden en que se muestran las respuestas, a menos que Aleatorizar esté seleccionado en el grupo de respuestas.</span><span class="sxs-lookup"><span data-stu-id="cf379-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="cf379-116">Se pueden otorgar puntos a las respuestas y usarlas para puntuar el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="cf379-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="cf379-117">En el campo Puntos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cf379-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="cf379-118">La respuesta correcta se puede marcar para indicar que la respuesta seleccionada es la correcta.</span><span class="sxs-lookup"><span data-stu-id="cf379-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="cf379-119">Esto se puede usar para puntuar el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="cf379-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="cf379-120">En el campo Respuesta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="cf379-121">Continúe creando las opciones de selección de respuestas para el grupo de respuestas.</span><span class="sxs-lookup"><span data-stu-id="cf379-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="cf379-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-122">Click New.</span></span>
10. <span data-ttu-id="cf379-123">En el campo Puntos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cf379-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="cf379-124">En el campo Respuesta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="cf379-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-125">Click New.</span></span>
13. <span data-ttu-id="cf379-126">En el campo Puntos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cf379-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="cf379-127">En el campo Respuesta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="cf379-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-128">Click New.</span></span>
16. <span data-ttu-id="cf379-129">En el campo Puntos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cf379-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="cf379-130">En el campo Respuesta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="cf379-131">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-131">Click New.</span></span>
19. <span data-ttu-id="cf379-132">En el campo Puntos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cf379-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="cf379-133">En el campo Respuesta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="cf379-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf379-134">Close the page.</span></span>
22. <span data-ttu-id="cf379-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf379-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="cf379-136">Creación de la pregunta</span><span class="sxs-lookup"><span data-stu-id="cf379-136">Create the question</span></span>
1. <span data-ttu-id="cf379-137">Vaya a Cuestionario > Diseño > Preguntas.</span><span class="sxs-lookup"><span data-stu-id="cf379-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="cf379-138">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cf379-138">Click New.</span></span>
3. <span data-ttu-id="cf379-139">Use el campo Tipo para agrupar las preguntas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="cf379-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="cf379-140">Puede usar tipos de entrada de casilla, botón alternativo o cuadro combinado para las preguntas cerradas.</span><span class="sxs-lookup"><span data-stu-id="cf379-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="cf379-141">En el campo Tipo de entrada, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cf379-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="cf379-142">En el campo Grupos de respuestas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="cf379-143">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cf379-143">In the Text field, type a value.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]