---
title: Delegación de elementos de trabajo de un flujo de trabajo
description: Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509463"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="ba99c-103">Delegar elementos de trabajo de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ba99c-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="ba99c-104">Delegación manual de un elemento de trabajo</span><span class="sxs-lookup"><span data-stu-id="ba99c-104">Manually delegate a work item</span></span>

<span data-ttu-id="ba99c-105">Para delegar un elemento de trabajo individual, seleccione la opción **Delegar** en el menú **Flujo de trabajo** y especifique el usuario al que se delegará junto con un comentario.</span><span class="sxs-lookup"><span data-stu-id="ba99c-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="ba99c-106">Esto reasignará el elemento de trabajo a dicho usuario para que puedan completarlo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="ba99c-107">Delegación automática de elementos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ba99c-107">Automatically delegate work items</span></span>

<span data-ttu-id="ba99c-108">Si tiene planeado ausentarse de la oficina o de otro modo no va a poder dedicar tiempo a los elementos de trabajo durante un tiempo, puede delegar elementos nuevos de trabajo automáticamente a otros usuarios mediante la página **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="ba99c-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="ba99c-109">Configuración de la delegación automática</span><span class="sxs-lookup"><span data-stu-id="ba99c-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="ba99c-110">Vaya a las opciones Común > Configuración > Opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="ba99c-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="ba99c-111">Haga clic en la pestaña Flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="ba99c-112">Asegúrese de que la sección Delegación está expandida.</span><span class="sxs-lookup"><span data-stu-id="ba99c-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="ba99c-113">Para configurar el sistema para que sus elementos de trabajo se deleguen de manera automática a otros usuarios, debe crear reglas de delegación, que especifican cuándo se delegan determinados tipos de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="ba99c-114">Siga estos pasos para crear una regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="ba99c-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="ba99c-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ba99c-115">Click Add.</span></span>
4. <span data-ttu-id="ba99c-116">En el campo Ámbito, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ba99c-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="ba99c-117">Todo: permite delegar todos los elementos de trabajo que tiene asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="ba99c-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="ba99c-118">Módulo: delegar solo los elementos de trabajo relacionados con un tipo específico de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="ba99c-119">Si selecciona esta opción, también debe seleccionar el tipo de flujo de trabajo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="ba99c-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="ba99c-120">Flujo de trabajo: delegue solo los elementos de trabajo relacionados con un flujo de trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="ba99c-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="ba99c-121">Si selecciona esta opción, también debe seleccionar el flujo de trabajo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="ba99c-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="ba99c-122">En el campo Delegado, seleccione el usuario al que desea delegar los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="ba99c-123">Use los campos Fecha/hora inicial y Fecha/hora final para especificar cuándo quiere delegar automáticamente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="ba99c-124">En el campo Fecha/hora inicial, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="ba99c-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="ba99c-125">En el campo Fecha/hora final, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="ba99c-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="ba99c-126">Active la casilla de verificación Habilitado para activar la regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="ba99c-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="ba99c-127">Si ha seleccionado Módulo como el Ámbito, deberá seleccionar el módulo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="ba99c-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="ba99c-128">Si ha seleccionado Flujo de trabajo como el Ámbito, deberá seleccionar el flujo de trabajo específico para delegar el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="ba99c-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="ba99c-129">En el campo Comentario, introduzca un comentario en el que se explique el motivo por el que delega los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba99c-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

