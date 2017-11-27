--- 
title: "Crear el formato de recuento y suma para informes electrónicos (ER)"
description: "Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: 3c4ae958a03d4681a85f5b83d81fe64b9ac99cf5
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="create-format-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="0fca4-103">Crear el formato de recuento y suma para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="0fca4-103">Create format for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fca4-104">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="0fca4-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="0fca4-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="0fca4-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="0fca4-106">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="0fca4-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="0fca4-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="0fca4-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="0fca4-108">Obtenga acceso a la lista de configuraciones proporcionada por Microsoft</span><span class="sxs-lookup"><span data-stu-id="0fca4-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="0fca4-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0fca4-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="0fca4-110">Asegúrese de que el proveedor “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="0fca4-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="0fca4-111">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="0fca4-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="0fca4-112">Seleccione el proveedor "Litware,</span><span class="sxs-lookup"><span data-stu-id="0fca4-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="0fca4-113">Inc.</span><span class="sxs-lookup"><span data-stu-id="0fca4-113">provider.</span></span>
3. <span data-ttu-id="0fca4-114">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="0fca4-114">Click Repositories.</span></span>
    * <span data-ttu-id="0fca4-115">Si ya existe un repositorio del tipo "Recursos de Operations", omita los pasos restantes de la subtarea actual.</span><span class="sxs-lookup"><span data-stu-id="0fca4-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="0fca4-116">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="0fca4-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="0fca4-117">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="0fca4-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="0fca4-118">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="0fca4-118">Click Create repository.</span></span>
7. <span data-ttu-id="0fca4-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0fca4-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="0fca4-120">Obtenga las configuraciones de Intrastat proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="0fca4-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="0fca4-121">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="0fca4-121">Click Open.</span></span>
2. <span data-ttu-id="0fca4-122">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="0fca4-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="0fca4-123">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="0fca4-123">Click Import.</span></span>
    * <span data-ttu-id="0fca4-124">Haga clic en Importar para la versión 1.1 de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0fca4-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="0fca4-125">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="0fca4-125">Click Yes.</span></span>
5. <span data-ttu-id="0fca4-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0fca4-126">Close the page.</span></span>
6. <span data-ttu-id="0fca4-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0fca4-127">Close the page.</span></span>
7. <span data-ttu-id="0fca4-128">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="0fca4-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="0fca4-129">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="0fca4-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="0fca4-130">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="0fca4-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


