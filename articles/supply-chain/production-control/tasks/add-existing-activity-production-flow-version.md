---
title: Agregar una actividad existente a una versión del flujo de producción
description: Al crear nuevas versiones de flujos de producción, puede decidir si agregar actividades creadas para versiones anteriores a la nueva versión.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c01d988469ead4ab09d69b1cb6e2f9b417080c69
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149421"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="a04f1-103">Agregar una actividad existente a una versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="a04f1-103">Add an existing activity to a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a04f1-104">Al crear nuevas versiones de flujos de producción, puede decidir si agregar actividades creadas para versiones anteriores a la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="a04f1-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="a04f1-105">Este procedimiento muestra cómo se crea una nueva versión para un flujo de producción existente, sin copiar las actividades.</span><span class="sxs-lookup"><span data-stu-id="a04f1-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="a04f1-106">En el paso siguiente, una actividad existente se agrega a la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="a04f1-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="a04f1-107">Esta tarea necesita que haya un flujo de producción con versión y actividades ya creadas.</span><span class="sxs-lookup"><span data-stu-id="a04f1-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="a04f1-108">Crear una nueva versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="a04f1-108">Create a new production flow version</span></span>
1. <span data-ttu-id="a04f1-109">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="a04f1-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="a04f1-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a04f1-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a04f1-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a04f1-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a04f1-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a04f1-112">Click Edit.</span></span>
5. <span data-ttu-id="a04f1-113">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a04f1-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="a04f1-114">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="a04f1-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="a04f1-115">Tenga en cuenta que antes de crear una nueva versión del flujo de producción, debe asegurarse de comprobar la fecha y hora de vencimiento de la versión activa.</span><span class="sxs-lookup"><span data-stu-id="a04f1-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="a04f1-116">La nueva versión se creará con una fecha de vigencia inicial, que se vincula a la fecha de caducidad de la versión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a04f1-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="a04f1-117">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a04f1-117">Click Add.</span></span>
8. <span data-ttu-id="a04f1-118">Seleccione No en la Copia del campo de la versión.</span><span class="sxs-lookup"><span data-stu-id="a04f1-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="a04f1-119">Seleccione No para empezar con una versión vacía si la mayoría de las actividades de la versión copiada van a ser sustituidas por nuevas actividades.</span><span class="sxs-lookup"><span data-stu-id="a04f1-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="a04f1-120">Agregue las actividades sin cambios a la función Agregar existente en el formulario de actividades manualmente.</span><span class="sxs-lookup"><span data-stu-id="a04f1-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="a04f1-121">Seleccione No en el campo Duplicado de las reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="a04f1-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="a04f1-122">Cuando las actividades no se copian en la nueva versión, no se podrá copiar reglas kanban en el momento de la creación de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="a04f1-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="a04f1-123">En su lugar, deberá usar la función para crear una sustitución kanban más adelante en el formulario de la regla kanban, para reemplazar las reglas kanban de la antigua versión del flujo de producción, con reglas kanban que utilicen las actividades de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="a04f1-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="a04f1-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a04f1-124">Click OK.</span></span>
11. <span data-ttu-id="a04f1-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a04f1-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="a04f1-126">Agregue una actividad existente</span><span class="sxs-lookup"><span data-stu-id="a04f1-126">Add an existing activity</span></span>
1. <span data-ttu-id="a04f1-127">Haga clic en Actividades.</span><span class="sxs-lookup"><span data-stu-id="a04f1-127">Click Activities.</span></span>
2. <span data-ttu-id="a04f1-128">Haga clic en Agregar existentes para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a04f1-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="a04f1-129">Busque y seleccione una actividad existente para agregarla a la nueva versión del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="a04f1-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="a04f1-130">Tenga en cuenta que la lista muestra todas las actividades creadas para este flujo de producción para todas las versiones anteriores del flujo.</span><span class="sxs-lookup"><span data-stu-id="a04f1-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="a04f1-131">En el campo Actividad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a04f1-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="a04f1-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a04f1-132">Click OK.</span></span>

