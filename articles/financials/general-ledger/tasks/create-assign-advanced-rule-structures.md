---
title: Crear y asignar estructuras de reglas avanzadas
description: Esta guía de tareas describe los pasos de la creación y asignación de una estructura de regla avanzada a una estructura contable.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558915"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="d9e7e-103">Crear y asignar estructuras de reglas avanzadas</span><span class="sxs-lookup"><span data-stu-id="d9e7e-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d9e7e-104">Esta guía de tareas describe los pasos de la creación y asignación de una estructura de regla avanzada a una estructura contable.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="d9e7e-105">Esta guía usa la empresa de demostración de USMF.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="d9e7e-106">Crear una estructura de reglas avanzada</span><span class="sxs-lookup"><span data-stu-id="d9e7e-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="d9e7e-107">Vaya a Contabilidad general > Plan contable > Estructuras > Estructuras de regla avanzadas.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="d9e7e-108">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="d9e7e-109">En el campo de Estructura de reglas avanzada, escriba un nombre para describir la estructura de la regla.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="d9e7e-110">En el campo Descripción, escriba un valor para describir la estructura.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="d9e7e-111">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d9e7e-111">Click OK.</span></span>
6. <span data-ttu-id="d9e7e-112">Haga clic en Agregar segmento.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-112">Click Add segment.</span></span>
7. <span data-ttu-id="d9e7e-113">En la lista de segmentos, seleccione una dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="d9e7e-114">Por ejemplo, Almacén.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-114">For example, Store.</span></span>  
8. <span data-ttu-id="d9e7e-115">Haga clic en Agregar segmento.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-115">Click Add segment.</span></span>
9. <span data-ttu-id="d9e7e-116">En la lista, haga clic en el vínculo de la estructura de regla avanzada para verla.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="d9e7e-117">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-117">Click Activate.</span></span>
11. <span data-ttu-id="d9e7e-118">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="d9e7e-119">Aplicar una estructura de reglas avanzada a una estructura contable</span><span class="sxs-lookup"><span data-stu-id="d9e7e-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="d9e7e-120">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-120">Close the form.</span></span>
2. <span data-ttu-id="d9e7e-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-121">Close the page.</span></span>
3. <span data-ttu-id="d9e7e-122">Vaya a Contabilidad general > Plan contable > Estructuras > Configurar estructuras contables.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="d9e7e-123">En la lista, busque y seleccione la estructura contable a la que desea aplicar la regla avanzada.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="d9e7e-124">Haga clic en el nombre de la estructura contable para abrirla.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="d9e7e-125">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-125">Click Edit.</span></span>
    * <span data-ttu-id="d9e7e-126">También puede hacer clic en Reglas avanzadas y se le pedirá que ponga la estructura contable en el modo de borrador.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="d9e7e-127">Haga clic en Reglas avanzadas.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="d9e7e-128">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="d9e7e-129">En el campo Regla avanzada, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="d9e7e-130">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="d9e7e-131">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-131">Click Create.</span></span>
12. <span data-ttu-id="d9e7e-132">Haga clic en Agregar nuevos criterios.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="d9e7e-133">En el campo Lugar, seleccione la cuenta principal o una dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="d9e7e-134">En el campo Operador, seleccione una opción, como está entre e incluye.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="d9e7e-135">En el campo Valor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="d9e7e-136">En el campo hasta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="d9e7e-137">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="d9e7e-138">En la lista, busque la estructura de regla avanzada que desea usar cuando se cumplen los criterios especificados.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="d9e7e-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-139">Click Add.</span></span>
20. <span data-ttu-id="d9e7e-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-140">Close the page.</span></span>
21. <span data-ttu-id="d9e7e-141">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-141">Click Activate.</span></span>
22. <span data-ttu-id="d9e7e-142">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="d9e7e-142">Click Activate.</span></span>

