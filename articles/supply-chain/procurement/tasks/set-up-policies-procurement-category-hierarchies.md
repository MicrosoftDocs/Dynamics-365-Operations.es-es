--- 
title: "Configurar directivas para jerarquías de categorías de compras"
description: "Use este procedimiento para configurar las reglas para solicitar productos en una categoría."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a773675b858a196e795ad54cc534ef5eb98ef484
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="9ea1c-103">Configurar directivas para jerarquías de categorías de compras</span><span class="sxs-lookup"><span data-stu-id="9ea1c-103">Set up policies for procurement category hierarchies</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9ea1c-104">Use este procedimiento para configurar las reglas para solicitar productos en una categoría.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="9ea1c-105">Las reglas se definen para una directiva de compras específica.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="9ea1c-106">La regla de acceso de categorías controla a qué categorías de compras tendrán acceso los empleados al crear una solicitud.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="9ea1c-107">Cuando se está creando una solicitud, la directiva de compra y regla de acceso de categoría que se deben aplicar se determinan por la entidad jurídica y la unidad operativa a las que pertenece el empleado.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="9ea1c-108">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="9ea1c-109">Esta tarea la realizará normalmente un director de compras.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="9ea1c-110">Encuentre la directiva de compras</span><span class="sxs-lookup"><span data-stu-id="9ea1c-110">Find the procurement policy</span></span>
1. <span data-ttu-id="9ea1c-111">Vaya a Adquisición y abastecimiento > Configuración > Directivas > Directivas de compra.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="9ea1c-112">Haga clic en el vínculo en la directiva de USMF de la directiva de compras.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="9ea1c-113">Esta es la política a la que agregará una regla.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="9ea1c-114">Debe ser una directiva activa.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="9ea1c-115">Crear una regla de acceso de categorías</span><span class="sxs-lookup"><span data-stu-id="9ea1c-115">Create a category access rule</span></span>
1. <span data-ttu-id="9ea1c-116">Seleccione la Regla de directivas de acceso a categorías.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="9ea1c-117">Si el botón Crear regla de directivas aparece atenuado, se debe a que ya hay una regla de directivas activa para el acceso de categorías.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="9ea1c-118">Compruebe los campos Vigencia y Fecha de vencimiento para determinar cuál es, después selecciónelo y haga clic en Regla de directivas de jubilación.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="9ea1c-119">Si el botón Crear regla de directivas está disponible, no necesita hacer nada.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="9ea1c-120">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="9ea1c-121">En el campo Fecha de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="9ea1c-122">El tiempo no se debe superponer con otra regla que ya esté activa.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="9ea1c-123">Seleccione una categoría a la que se aplicará la regla.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="9ea1c-124">Anote qué categoría es, ya que la necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="9ea1c-125">Al seleccionar una categoría, sus categorías principales también se agregará a la lista Categorías seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="9ea1c-126">Si desea que la regla se aplique a todas las subcategorías de la categoría seleccionada, active la casilla Incluir subcategorías.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="9ea1c-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-127">Click Add.</span></span>
    * <span data-ttu-id="9ea1c-128">Si establece la opción Incluir regla principal en Sí, la regla de directivas que se defina para una categoría principal también se asigna a sus categorías secundarias si no se ha definido ninguna regla de directivas para las categorías secundarias.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="9ea1c-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9ea1c-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="9ea1c-130">Cree una regla de directivas de categoría.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-130">Create a category policy rule</span></span>
1. <span data-ttu-id="9ea1c-131">Seleccione la Regla de directivas de categorías</span><span class="sxs-lookup"><span data-stu-id="9ea1c-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="9ea1c-132">Si el botón Crear regla de directivas aparece atenuado, seleccione la regla de directivas activa y, a continuación, haga clic en Regla de directivas de jubilación.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="9ea1c-133">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="9ea1c-134">En el campo Fecha de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="9ea1c-135">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-135">Click Add.</span></span>
5. <span data-ttu-id="9ea1c-136">Seleccione la misma categoría que utilizó para la regla de acceso de categorías.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="9ea1c-137">En el campo Selección de proveedores, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="9ea1c-138">Seleccione una regla para controlar qué tipo de proveedores se pueden seleccionar para la categoría al crear solicitudes.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="9ea1c-139">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-139">Click Close.</span></span>
    * <span data-ttu-id="9ea1c-140">Las reglas de directivas que ha definido han sido para solicitudes de tipo Consumo.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="9ea1c-141">Si deseara definir directivas para solicitudes del tipo Reabastecimiento, crearía una regla para el tipo Regla de directivas llamada “Regla de directivas de acceso de categorías de reabastecimiento”.</span><span class="sxs-lookup"><span data-stu-id="9ea1c-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  


