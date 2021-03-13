---
title: Definir reglas y directivas de idoneidad para prestaciones
description: Este artículo muestra cómo puede crear reglas y directivas de opción a prestaciones y después asignar reglas a las prestaciones.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: cc80549eaffa72a22dec51829c86d04a763de96a
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114117"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="26df1-103">Definir reglas y directivas de idoneidad para prestaciones</span><span class="sxs-lookup"><span data-stu-id="26df1-103">Define benefit eligibility rules and policies</span></span>

<span data-ttu-id="26df1-104">Este tema muestra cómo puede crear reglas y directivas de idoneidad para prestaciones y después asignar reglas a las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="26df1-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="26df1-105">Creación de tipos de reglas de directivas de opción de prestaciones</span><span class="sxs-lookup"><span data-stu-id="26df1-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="26df1-106">Vaya a **Recursos humanos > Prestaciones > Idoneidad > Tipos de reglas de idoneidad de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="26df1-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="26df1-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="26df1-107">Select **New**.</span></span>
3. <span data-ttu-id="26df1-108">En el campo **Nombre de regla**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="26df1-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="26df1-109">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="26df1-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="26df1-110">En el campo **Nombre de la consulta**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="26df1-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="26df1-111">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26df1-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="26df1-112">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="26df1-112">Select **Save**.</span></span>
8. <span data-ttu-id="26df1-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="26df1-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="26df1-114">Directiva de idoneidad de beneficio</span><span class="sxs-lookup"><span data-stu-id="26df1-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="26df1-115">Vaya a **Recursos humanos > Prestaciones > Idoneidad > Directivas de idoneidad para prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="26df1-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="26df1-116">Seleccione una directiva de prestación existente.</span><span class="sxs-lookup"><span data-stu-id="26df1-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="26df1-117">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26df1-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="26df1-118">Expanda las secciones **Organizaciones de directivas**.</span><span class="sxs-lookup"><span data-stu-id="26df1-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="26df1-119">Puede agregar o quitar cualquier organización que desee incluir en la directiva.</span><span class="sxs-lookup"><span data-stu-id="26df1-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="26df1-120">Expanda o contraiga la sección **Reglas de directivas**.</span><span class="sxs-lookup"><span data-stu-id="26df1-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="26df1-121">En la lista, busque la regla de directiva que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="26df1-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="26df1-122">Seleccione **Crear regla de directivas**.</span><span class="sxs-lookup"><span data-stu-id="26df1-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="26df1-123">En el campo **Fecha de vigencia**, especifique la fecha en la que desea que la directiva entre en vigor.</span><span class="sxs-lookup"><span data-stu-id="26df1-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="26df1-124">Establecer las fechas finales vigentes permite realizar cambios futuros en las reglas de las directivas para no tener que volver a la directiva cuando se desee que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="26df1-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="26df1-125">Si es necesario, agregue una cláusula Donde al campo **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="26df1-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="26df1-126">Por ejemplo, si quisiera que la regla solo se aplicase a los directores de ventas, podría crear la cláusula Donde para decir: Donde la descripción del puesto es igual a director de ventas.</span><span class="sxs-lookup"><span data-stu-id="26df1-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="26df1-127">Puede agregar varias cláusulas Donde a la regla.</span><span class="sxs-lookup"><span data-stu-id="26df1-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="26df1-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26df1-128">Select **OK**.</span></span>
11. <span data-ttu-id="26df1-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="26df1-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="26df1-130">Asignación de reglas a prestaciones</span><span class="sxs-lookup"><span data-stu-id="26df1-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="26df1-131">Vaya a **Recursos humanos > Prestaciones > Prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="26df1-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="26df1-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="26df1-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="26df1-133">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26df1-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="26df1-134">Expanda o contraiga la sección **Reglas de idoneidad**.</span><span class="sxs-lookup"><span data-stu-id="26df1-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="26df1-135">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="26df1-135">Select **Edit**.</span></span>
6. <span data-ttu-id="26df1-136">En el campo **Idoneidad**, seleccione la regla.</span><span class="sxs-lookup"><span data-stu-id="26df1-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="26df1-137">En el campo **Tipo de regla**, seleccione la regla que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="26df1-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="26df1-138">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26df1-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="26df1-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="26df1-139">Select **Save**.</span></span>
11. <span data-ttu-id="26df1-140">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="26df1-140">Close the form.</span></span>

