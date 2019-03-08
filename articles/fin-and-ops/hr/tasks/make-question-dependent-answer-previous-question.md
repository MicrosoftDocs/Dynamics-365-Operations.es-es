---
title: Realizar una pregunta según la respuesta a la pregunta anterior
description: Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb79398f5a0ebdbdb774c106c90ca50a69c275e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "341290"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="e8eb9-103">Realizar una pregunta según la respuesta a la pregunta anterior</span><span class="sxs-lookup"><span data-stu-id="e8eb9-103">Make a question dependent on the answer of the previous question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e8eb9-104">Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="e8eb9-105">Por ejemplo, si pregunta "¿Prefiere café o té?", se podrá determinar una pregunta de seguimiento lógica en función de si el encuestado selecciona café o té como respuesta.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="e8eb9-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="e8eb9-107">Localización del cuestionario existente</span><span class="sxs-lookup"><span data-stu-id="e8eb9-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="e8eb9-108">Vaya a Cuestionario > Diseño > Cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="e8eb9-109">En la lista, seleccione el cuestionario de WorkFH.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="e8eb9-110">Adición de todas las preguntas y subpreguntas al cuestionario</span><span class="sxs-lookup"><span data-stu-id="e8eb9-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="e8eb9-111">Haga clic en Preguntas.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-111">Click Questions.</span></span>
2. <span data-ttu-id="e8eb9-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-112">Click New.</span></span>
3. <span data-ttu-id="e8eb9-113">En el campo Pregunta, seleccione el número de pregunta 00016.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="e8eb9-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e8eb9-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e8eb9-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-116">Click Save.</span></span>
7. <span data-ttu-id="e8eb9-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="e8eb9-118">Definición de la secuencia del cuestionario en Condicional y determinación de la pregunta según la respuesta adecuada</span><span class="sxs-lookup"><span data-stu-id="e8eb9-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="e8eb9-119">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-119">Click Edit.</span></span>
2. <span data-ttu-id="e8eb9-120">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="e8eb9-121">En el campo Orden de preguntas, seleccione Condicional.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="e8eb9-122">Haga clic en Pregunta condicional.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-122">Click Conditional question.</span></span>
5. <span data-ttu-id="e8eb9-123">En el árbol, seleccione "Preguntas\Explique por qué respondió así a la pregunta anterior".</span><span class="sxs-lookup"><span data-stu-id="e8eb9-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="e8eb9-124">En el campo Pregunta principal, seleccione el número de pregunta 00009.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="e8eb9-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e8eb9-126">En el campo Respuesta, especifique el identificador de secuencia de respuesta de la opción de respuesta de la que quiera que dependa la pregunta.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="e8eb9-127">Por ejemplo, escriba 1 para la primera opción de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="e8eb9-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-128">Click Save.</span></span>
10. <span data-ttu-id="e8eb9-129">En el árbol, seleccione "Preguntas\Me pagan justamente por el trabajo que hago".</span><span class="sxs-lookup"><span data-stu-id="e8eb9-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="e8eb9-130">Observe cómo el árbol de preguntas se ha actualizado para mostrar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-130">Note that the question tree updated to show the dependency.</span></span>  

