---
title: Delegación de elementos de trabajo de un flujo de trabajo
description: Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 054e183374d2b24f38b0f90ff90acfeeca013861
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560564"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="85798-103">Delegar elementos de trabajo de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="85798-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="85798-104">Delegación manual de un elemento de trabajo</span><span class="sxs-lookup"><span data-stu-id="85798-104">Manually delegate a work item</span></span>

<span data-ttu-id="85798-105">Para delegar un elemento de trabajo individual, seleccione la opción **Delegar** en el menú **Flujo de trabajo** y especifique el usuario al que se delegará junto con un comentario.</span><span class="sxs-lookup"><span data-stu-id="85798-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="85798-106">Esto reasignará el elemento de trabajo a dicho usuario para que puedan completarlo.</span><span class="sxs-lookup"><span data-stu-id="85798-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="85798-107">Delegar manualmente múltiples elementos de trabajo</span><span class="sxs-lookup"><span data-stu-id="85798-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="85798-108">Se pueden delegar varios elementos de trabajo juntos desde la página **Elementos de trabajo asignados a mí**.</span><span class="sxs-lookup"><span data-stu-id="85798-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="85798-109">Los siguientes tipos de flujo de trabajo se pueden elegir para la delegación masiva: flujo de trabajo de aprobación de acuerdo de compra, flujo de trabajo de orden de compra, revisión de solicitud de compra y flujo de trabajo de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="85798-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="85798-110">La característica **Delegar múltiples elementos de trabajo** está deshabilitada de manera predeterminada y se puede habilitar en **Espacios de trabajo> Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="85798-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="85798-111">Póngase en contacto con el administrador del sistema para obtener ayuda para habilitar esta función.</span><span class="sxs-lookup"><span data-stu-id="85798-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="85798-112">Vaya a **Común> Común> Elementos de trabajo> Elementos de trabajo asignados a mí**.</span><span class="sxs-lookup"><span data-stu-id="85798-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="85798-113">Seleccione los elementos de trabajo que se delegarán.</span><span class="sxs-lookup"><span data-stu-id="85798-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="85798-114">Haga clic en el menú **Delegar elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="85798-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="85798-115">En el campo **Usuario**, seleccione el usuario al que desea delegar los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="85798-116">En el campo **Comentario**, escriba un comentario en el que se explique el motivo por el que delega los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="85798-117">Haga clic en el botón **Delegar elementos de trabajo** para completar la delegación del elemento de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="85798-118">Delegación automática de elementos de trabajo</span><span class="sxs-lookup"><span data-stu-id="85798-118">Automatically delegate work items</span></span>

<span data-ttu-id="85798-119">Si tiene planeado ausentarse de la oficina o de otro modo no va a poder dedicar tiempo a los elementos de trabajo durante un tiempo, puede delegar elementos nuevos de trabajo automáticamente a otros usuarios mediante la página **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="85798-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="85798-120">Configuración de la delegación automática</span><span class="sxs-lookup"><span data-stu-id="85798-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="85798-121">Vaya a **Común > Configuración > Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="85798-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="85798-122">Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección de delegación.</span><span class="sxs-lookup"><span data-stu-id="85798-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="85798-123">Para configurar el sistema para que sus elementos de trabajo se deleguen de manera automática a otros usuarios, debe crear reglas de delegación, que especifican cuándo se delegan determinados tipos de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="85798-124">Siga estos pasos para crear una regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="85798-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="85798-125">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="85798-125">Click **Add**.</span></span>
4. <span data-ttu-id="85798-126">En el campo **Ámbito**, seleccione una opción:</span><span class="sxs-lookup"><span data-stu-id="85798-126">In the **Scope** field, select an option:</span></span>
    - <span data-ttu-id="85798-127">Todo: permite delegar todos los elementos de trabajo que tiene asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="85798-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="85798-128">Módulo: delegar solo los elementos de trabajo relacionados con un tipo específico de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="85798-129">Si selecciona esta opción, debe seleccionar el tipo de flujo de trabajo en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="85798-129">If you select this option, you must select the type of workflow in the **Name** field.</span></span>
    - <span data-ttu-id="85798-130">Flujo de trabajo: delegue solo los elementos de trabajo relacionados con un flujo de trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="85798-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="85798-131">Si selecciona esta opción, también debe seleccionar el flujo de trabajo en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="85798-131">If you select this option, you must select the workflow in the **Name** field.</span></span>  
5. <span data-ttu-id="85798-132">En el campo **Nombre**:</span><span class="sxs-lookup"><span data-stu-id="85798-132">In the **Name** field:</span></span>
    - <span data-ttu-id="85798-133">En el ámbito **Módulo**, seleccione el módulo de destino.</span><span class="sxs-lookup"><span data-stu-id="85798-133">For **Module** scope, select the target module.</span></span>
    - <span data-ttu-id="85798-134">En el ámbito **Flujo de trabajo**, seleccione el flujo de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="85798-134">For **Workflow** scope, select the target workflow.</span></span>
6. <span data-ttu-id="85798-135">En el campo **Delegado**, seleccione el usuario al que desea delegar los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-135">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="85798-136">Use los campos **Fecha/hora de inicio** y **Fecha/hora de finalización** para especificar cuándo desea delegar automáticamente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-136">Use the **Start date/time** and **End date/time** fields to specify when you want the work items to be automatically delegated.</span></span>  
7. <span data-ttu-id="85798-137">En el campo **Fecha y hora inicial**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="85798-137">In the **Start date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="85798-138">En el campo **Fecha y hora final**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="85798-138">In the **End date/time** field, enter a date and time.</span></span>
9. <span data-ttu-id="85798-139">Active la casilla de verificación **Habilitado** para activar la regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="85798-139">Select the **Enabled** check box to activate the delegation rule.</span></span> 
10. <span data-ttu-id="85798-140">En el campo **Comentario**, escriba un comentario en el que se explique el motivo por el que delega los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="85798-140">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]