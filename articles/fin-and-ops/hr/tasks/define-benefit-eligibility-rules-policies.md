--- 
title: Definir reglas y directivas de idoneidad para prestaciones
description: "Este registro mostrará cómo puede crear reglas y directivas de opción a prestaciones y después asignar reglas a las prestaciones."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a9d0d9a3f278a09e89311ee75b6f95fb4f3b04cb
ms.openlocfilehash: 329598430edf07e3a743b0d7061a51825f12a066
ms.contentlocale: es-es
ms.lasthandoff: 02/02/2018

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="8facf-103">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="8facf-103">Define benefit eligibility rules and policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8facf-104">Este registro mostrará cómo puede crear reglas y directivas de opción a prestaciones y después asignar reglas a las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8facf-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="8facf-105">La empresa de datos de prueba utilizada para crear este registro es USMF.</span><span class="sxs-lookup"><span data-stu-id="8facf-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="8facf-106">Creación de tipos de reglas de directivas de opción de prestaciones</span><span class="sxs-lookup"><span data-stu-id="8facf-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="8facf-107">Vaya a Recursos humanos > Prestaciones > Idoneidad > Tipos de reglas de idoneidad de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8facf-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="8facf-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8facf-108">Click New.</span></span>
3. <span data-ttu-id="8facf-109">En el campo Nombre de regla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8facf-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="8facf-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8facf-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8facf-111">En el campo Nombre de consulta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8facf-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8facf-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8facf-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="8facf-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8facf-113">Click Save.</span></span>
8. <span data-ttu-id="8facf-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8facf-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="8facf-115">Directiva de idoneidad de beneficio</span><span class="sxs-lookup"><span data-stu-id="8facf-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="8facf-116">Vaya a Recursos humanos > Prestaciones > Idoneidad > Políticas de opción a prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8facf-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="8facf-117">Seleccione una directiva de prestación existente.</span><span class="sxs-lookup"><span data-stu-id="8facf-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="8facf-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8facf-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8facf-119">Expanda las secciones Organizaciones de directivas.</span><span class="sxs-lookup"><span data-stu-id="8facf-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="8facf-120">Aquí puede agregar o quitar cualquier organización que desee incluir en la directiva.</span><span class="sxs-lookup"><span data-stu-id="8facf-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="8facf-121">Expanda o contraiga la sección Reglas de directivas.</span><span class="sxs-lookup"><span data-stu-id="8facf-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="8facf-122">En la lista, busque la regla de directiva que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8facf-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="8facf-123">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="8facf-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="8facf-124">En el campo Fecha de vigencia, especifique la fecha en la que desea que la directiva entrara en vigor.</span><span class="sxs-lookup"><span data-stu-id="8facf-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="8facf-125">Al definir las fechas de vigencia y finales, podrá realizar cambios futuros en las reglas de las directivas, así como ya no tendrá que volver a la directiva cuando desee que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="8facf-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="8facf-126">Por ejemplo, si quisiera que la regla solo se aplicase a los directores de ventas, podría crear la cláusula Where para decir: Where descripción del puesto equals director de ventas.</span><span class="sxs-lookup"><span data-stu-id="8facf-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="8facf-127">Puede incluir operadores "And" u "Or" en las instrucciones Where de las reglas.</span><span class="sxs-lookup"><span data-stu-id="8facf-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="8facf-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8facf-128">Click OK.</span></span>
11. <span data-ttu-id="8facf-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8facf-129">Close the page.</span></span>
12. <span data-ttu-id="8facf-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8facf-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="8facf-131">Asignación de reglas a prestaciones</span><span class="sxs-lookup"><span data-stu-id="8facf-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="8facf-132">Vaya a Recursos humanos > Prestaciones > Prestaciones.</span><span class="sxs-lookup"><span data-stu-id="8facf-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="8facf-133">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="8facf-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8facf-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8facf-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8facf-135">Expanda o contraiga la sección Regla de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="8facf-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="8facf-136">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="8facf-136">Click Edit.</span></span>
6. <span data-ttu-id="8facf-137">En el campo Idoneidad, seleccione Basada en reglas en la lista.</span><span class="sxs-lookup"><span data-stu-id="8facf-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="8facf-138">En el campo Tipo de regla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8facf-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="8facf-139">En la lista, busque y seleccione la regla que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8facf-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="8facf-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8facf-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="8facf-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8facf-141">Click Save.</span></span>
11. <span data-ttu-id="8facf-142">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="8facf-142">Close the form.</span></span>


