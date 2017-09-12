--- 
title: "Delegación de elementos de trabajo de un flujo de trabajo"
description: "Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6483307ff89ce79a3ef16bb763e3124ac537a5d8
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="947d2-103">Delegación de elementos de trabajo de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="947d2-103">Delegate work items in a workflow</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="947d2-104">Si tiene planeado ausentarse de la oficina o, por alguna otra razón, no va a poder encargarse de los elementos de trabajo, puede delegar, o volver a asignar, sus elementos de trabajo a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="947d2-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="947d2-105">este procedimiento le ayuda a configurar el sistema para delegar automáticamente los elementos de trabajo a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="947d2-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="947d2-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="947d2-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="947d2-107">Configuración de la delegación automática</span><span class="sxs-lookup"><span data-stu-id="947d2-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="947d2-108">Vaya a las opciones Común > Configuración > Opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="947d2-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="947d2-109">Haga clic en la pestaña Flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="947d2-110">Asegúrese de que la sección Delegación está expandida.</span><span class="sxs-lookup"><span data-stu-id="947d2-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="947d2-111">Para configurar el sistema para que sus elementos de trabajo se deleguen de manera automática a otros usuarios, debe crear reglas de delegación, que especifican cuándo se delegan determinados tipos de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="947d2-112">Siga estos pasos para crear una regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="947d2-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="947d2-113">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="947d2-113">Click Add.</span></span>
4. <span data-ttu-id="947d2-114">En el campo Ámbito, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="947d2-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="947d2-115">Todo: permite delegar todos los elementos de trabajo que tiene asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="947d2-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="947d2-116">Módulo: delegar solo los elementos de trabajo relacionados con un tipo específico de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="947d2-117">Si selecciona esta opción, también debe seleccionar el tipo de flujo de trabajo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="947d2-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="947d2-118">Flujo de trabajo: delegue solo los elementos de trabajo relacionados con un flujo de trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="947d2-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="947d2-119">Si selecciona esta opción, también debe seleccionar el flujo de trabajo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="947d2-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="947d2-120">En el campo Delegado, seleccione el usuario al que desea delegar los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="947d2-121">Use los campos Fecha/hora inicial y Fecha/hora final para especificar cuándo quiere delegar automáticamente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="947d2-122">En el campo Fecha/hora inicial, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="947d2-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="947d2-123">En el campo Fecha/hora final, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="947d2-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="947d2-124">Active la casilla de verificación Habilitado para activar la regla de delegación.</span><span class="sxs-lookup"><span data-stu-id="947d2-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="947d2-125">Si ha seleccionado Módulo como el Ámbito, deberá seleccionar el módulo en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="947d2-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="947d2-126">Si ha seleccionado Flujo de trabajo como el Ámbito, deberá seleccionar el flujo de trabajo específico para delegar el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="947d2-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="947d2-127">En el campo Comentario, introduzca un comentario en el que se explique el motivo por el que delega los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="947d2-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>


