---
title: Crear un proyecto de contratación maestra
description: Este procedimiento le muestra el proceso para configurar un proyecto de contratación masiva.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject,  HRMMassHireLineCreate, HcmJobLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19d2f41f92aef7739e8e36012e207b96af155190
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010502"
---
# <a name="create-a-mass-hire-project"></a><span data-ttu-id="9b181-103">Crear un proyecto de contratación maestra</span><span class="sxs-lookup"><span data-stu-id="9b181-103">Create a mass hire project</span></span>



<span data-ttu-id="9b181-104">Este procedimiento le muestra el proceso para configurar un proyecto de contratación masiva.</span><span class="sxs-lookup"><span data-stu-id="9b181-104">This procedure walks through the process of setting up a mass hire project.</span></span> <span data-ttu-id="9b181-105">La persona a cargo de la contratación puede usar proyectos de contratación masiva para crear fácilmente varios puestos y contratar a varios trabajadores para ellos.</span><span class="sxs-lookup"><span data-stu-id="9b181-105">A recruiter can use mass hire projects to easily create multiple positions and hire a number of workers into those positions.</span></span> <span data-ttu-id="9b181-106">Para iniciar este procedimiento, vaya a Recursos humanos > Contratación > Proyectos de contratación masiva.</span><span class="sxs-lookup"><span data-stu-id="9b181-106">To begin this procedure, go to Human resources > Recruitment > Mass hire projects.</span></span> <span data-ttu-id="9b181-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="9b181-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="9b181-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9b181-108">Click New.</span></span>
2. <span data-ttu-id="9b181-109">En el campo Contratación masiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9b181-109">In the Mass hire project field, type a value.</span></span>
3. <span data-ttu-id="9b181-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9b181-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="9b181-111">En el campo Inicio del proyecto, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="9b181-111">In the Project start field, enter a date.</span></span>
5. <span data-ttu-id="9b181-112">En el campo Final de proyecto, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="9b181-112">In the Project end field, enter a date.</span></span>
6. <span data-ttu-id="9b181-113">Haga clic en Abrir proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b181-113">Click Open project.</span></span>
7. <span data-ttu-id="9b181-114">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="9b181-114">Click Yes.</span></span>
8. <span data-ttu-id="9b181-115">Haga clic en Crear puestos.</span><span class="sxs-lookup"><span data-stu-id="9b181-115">Click Create positions.</span></span>
9. <span data-ttu-id="9b181-116">En el campo Cantidad, especifique el número de puestos que desee crear.</span><span class="sxs-lookup"><span data-stu-id="9b181-116">In the Quantity field, enter the number of positions that you want to create</span></span>
    * <span data-ttu-id="9b181-117">La fecha de inicio se convertirá en la fecha de contratación para los trabajadores nuevos.</span><span class="sxs-lookup"><span data-stu-id="9b181-117">The Start date will become the Hire date for the new workers.</span></span>  
    * <span data-ttu-id="9b181-118">La fecha de fin será la fecha de cese para los trabajadores nuevos.</span><span class="sxs-lookup"><span data-stu-id="9b181-118">The End date will be the Termination date for the new workers.</span></span>  
    * <span data-ttu-id="9b181-119">Especifique si los trabajadores nuevos serán empleados o contratistas.</span><span class="sxs-lookup"><span data-stu-id="9b181-119">Specify whether the new workers will be Employees or Contractors.</span></span>  
10. <span data-ttu-id="9b181-120">En el campo Trabajo, haga clic en el botón desplegable para seleccionar el trabajo para el cual crear los puestos.</span><span class="sxs-lookup"><span data-stu-id="9b181-120">In the Job field, click the drop-down button to select the job to create the positions for.</span></span>
11. <span data-ttu-id="9b181-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9b181-121">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="9b181-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b181-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9b181-123">El valor de jornada completa equivalente predeterminado provendrá del trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9b181-123">The default full-time equivalent value will come from the selected job.</span></span> <span data-ttu-id="9b181-124">Si es necesario, se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="9b181-124">You can change this if needed.</span></span>  
    * <span data-ttu-id="9b181-125">También puede seleccionar el departamento para los nuevos puestos.</span><span class="sxs-lookup"><span data-stu-id="9b181-125">Optionally, select the Department for the new positions.</span></span>  
13. <span data-ttu-id="9b181-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9b181-126">Click OK.</span></span>

