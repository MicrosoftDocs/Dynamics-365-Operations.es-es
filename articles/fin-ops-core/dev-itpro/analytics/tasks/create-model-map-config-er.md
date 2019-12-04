---
title: Crear configuraciones de asignación de modelo de informes electrónicos (ER)
description: Use este procedimiento para diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcfc258e7fe364779fd77cc79413e8d5e871e214
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182701"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a><span data-ttu-id="10033-103">Crear configuraciones de asignación de modelo de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="10033-103">Create Electronic reporting (ER) model mapping configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10033-104">Use este procedimiento para diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.</span><span class="sxs-lookup"><span data-stu-id="10033-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="10033-105">En este procedimiento, creará una configuración para la empresa de ejemplo Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="10033-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="10033-106">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="10033-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="10033-107">Estos pasos se pueden completar mediante cualquier conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="10033-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="10033-108">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="10033-108">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="10033-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="10033-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="10033-110">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo.</span><span class="sxs-lookup"><span data-stu-id="10033-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="10033-111">Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="10033-111">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="10033-112">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="10033-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="10033-113">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="10033-113">Click Show filters.</span></span>
4. <span data-ttu-id="10033-114">En el campo "Nombre" escriba el valor de filtro "Intrastat" y use el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="10033-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="10033-115">Aplicar este filtro para buscar la configuración del modelo de datos de "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="10033-115">Apply this filter to find the ‘Intrastat’ data model configuration.</span></span> <span data-ttu-id="10033-116">Este modelo puede existir en el árbol de las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="10033-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="10033-117">Si es así, omita subtarea la siguiente.</span><span class="sxs-lookup"><span data-stu-id="10033-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="10033-118">Obtenga la configuración de modelo de Intrastat proporcionada por Microsoft</span><span class="sxs-lookup"><span data-stu-id="10033-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="10033-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="10033-119">Close the page.</span></span>
2. <span data-ttu-id="10033-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="10033-120">Close the page.</span></span>
3. <span data-ttu-id="10033-121">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="10033-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="10033-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="10033-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="10033-123">Seleccione el mosaico del proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10033-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="10033-124">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="10033-124">Click Repositories.</span></span>
    * <span data-ttu-id="10033-125">Haga clic en Repositorios en el icono de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10033-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="10033-126">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="10033-126">Click Show filters.</span></span>
7. <span data-ttu-id="10033-127">En el campo "Escribir el nombre" escriba el valor de filtro "recursos" y use el operador de filtro "contiene".</span><span class="sxs-lookup"><span data-stu-id="10033-127">In the "Type name" field, enter the filter value, “resources” and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="10033-128">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="10033-128">Click Open.</span></span>
9. <span data-ttu-id="10033-129">En el árbol, seleccione 'Intrastat model'.</span><span class="sxs-lookup"><span data-stu-id="10033-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="10033-130">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="10033-130">Click Import.</span></span>
11. <span data-ttu-id="10033-131">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="10033-131">Click Yes.</span></span>
    * <span data-ttu-id="10033-132">Se ha importado la configuración del modelo de ER que contiene el modelo de datos que usará para explorar cómo la nueva funcionalidad de ER se puede usar.</span><span class="sxs-lookup"><span data-stu-id="10033-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="10033-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="10033-133">Close the page.</span></span>
13. <span data-ttu-id="10033-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="10033-134">Close the page.</span></span>
14. <span data-ttu-id="10033-135">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="10033-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="10033-136">Agregar una nueva configuración de asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="10033-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="10033-137">En el árbol, seleccione 'Intrastat model'.</span><span class="sxs-lookup"><span data-stu-id="10033-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="10033-138">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="10033-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="10033-139">En el campo Nuevo, especifique "Asignación de modelo según el modelo de datos Intrastat".</span><span class="sxs-lookup"><span data-stu-id="10033-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="10033-140">En el campo Nombre, escriba "Asignación de muestra de Intrastat".</span><span class="sxs-lookup"><span data-stu-id="10033-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="10033-141">Asignación de muestra de Intrastat</span><span class="sxs-lookup"><span data-stu-id="10033-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="10033-142">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="10033-142">Click Create configuration.</span></span>
