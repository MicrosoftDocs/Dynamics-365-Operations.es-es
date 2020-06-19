---
title: Especificar hojas de horas de proyectos
description: Este procedimiento le permite crear una hoja de horas a partir de un formulario en blanco.
author: andreabichsel
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Operations, Human Resources
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10dbb43cec47a758d11362947f27932a4911911a
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430288"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="2ec27-103">Especificar hojas de horas de proyectos</span><span class="sxs-lookup"><span data-stu-id="2ec27-103">Enter project timesheets</span></span>



<span data-ttu-id="2ec27-104">Este procedimiento le permite crear una hoja de horas a partir de un formulario en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ec27-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="2ec27-105">La nueva hoja de horas se puede basar en la información de una hoja de horas anterior, o en las asignaciones de proyecto y actividad de la página **Mis favoritos**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the **My favorites** page.</span></span> <span data-ttu-id="2ec27-106">De forma predeterminada, la página de lista **Todas las hojas de horas** muestra todas las hojas de horas del período actual.</span><span class="sxs-lookup"><span data-stu-id="2ec27-106">By default, the **All timesheets** list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="2ec27-107">Puede usar la lista desplegable para el campo **Mostrar** campo en la página **Mis hojas de horas** para filtrar la lista de la hoja de horas por período de tiempo o proyecto, o a para ver las hojas de horas que se crearon en nombre de otros trabajadores.</span><span class="sxs-lookup"><span data-stu-id="2ec27-107">You can use the drop-down list for the **Show** field in the **My timesheets** page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="2ec27-108">La empresa de datos de demostración utilizada para crear este procedimiento es USSI.</span><span class="sxs-lookup"><span data-stu-id="2ec27-108">The demo data company used to create this procedure is USSI.</span></span> 

1. <span data-ttu-id="2ec27-109">En el **Panel de exploración**, vaya a **Módulos > Gestión y contabilidad de proyectos > Hojas de horas > Mis hojas de horas**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Timesheets > My timesheets**.</span></span>
2. <span data-ttu-id="2ec27-110">Para especificar una nueva hoja de horas, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-110">To enter a new timesheet, click **New**.</span></span>
    - <span data-ttu-id="2ec27-111">La lista desplegable Recurso muestra el trabajador asignado al usuario actual, de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    - <span data-ttu-id="2ec27-112">Si se designa el usuario como delegado, este mostrará los nombres de modo que un usuario puede especificar una hoja de horas en su nombre.</span><span class="sxs-lookup"><span data-stu-id="2ec27-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
3. <span data-ttu-id="2ec27-113">En el campo **Fecha**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="2ec27-113">In the **Date** field, enter a date.</span></span> <span data-ttu-id="2ec27-114">Si se selecciona esta opción, se crearán las nuevas líneas de hoja de horas con la configuración de la hoja de horas que se configuró como favorita.</span><span class="sxs-lookup"><span data-stu-id="2ec27-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
4. <span data-ttu-id="2ec27-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-115">Click **OK**.</span></span>
5. <span data-ttu-id="2ec27-116">Haga clic en **Nueva línea**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-116">Click **New line**.</span></span>
6. <span data-ttu-id="2ec27-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-117">In the list, mark the selected row.</span></span> <span data-ttu-id="2ec27-118">El campo **Entidad jurídica** muestra la Entidad jurídica actual de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-118">The **Legal Entity** field displays the current Legal entity by default.</span></span>   
7. <span data-ttu-id="2ec27-119">En el campo **Proyecto**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2ec27-119">In the **Project** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2ec27-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2ec27-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="2ec27-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="2ec27-122">En el campo **Número de actividad**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2ec27-122">In the **Activity number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="2ec27-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2ec27-123">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="2ec27-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="2ec27-125">En el campo **Categoría**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2ec27-125">In the **Category** field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="2ec27-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2ec27-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="2ec27-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ec27-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="2ec27-128">Indicar la cantidad de horas trabajadas cada día.</span><span class="sxs-lookup"><span data-stu-id="2ec27-128">Enter the number of hours worked each day.</span></span> <span data-ttu-id="2ec27-129">Escriba las horas en formato decimal.</span><span class="sxs-lookup"><span data-stu-id="2ec27-129">Enter the hours in decimal format.</span></span> <span data-ttu-id="2ec27-130">Por ejemplo, si ha trabajado durante dos horas y quince minutos, escriba 2,25.</span><span class="sxs-lookup"><span data-stu-id="2ec27-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="2ec27-131">En **Detalles de línea**, las siguientes opciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2ec27-131">In **Line details**, the following options are available:</span></span>
    - <span data-ttu-id="2ec27-132">Agregar información acerca de los impuestos y las dimensiones financieras en **General** y la pestaña **Dimensiones financieras** .</span><span class="sxs-lookup"><span data-stu-id="2ec27-132">Add information about taxes and financial dimensions in the **General** and the **Financial Dimensions** tab.</span></span>
    - <span data-ttu-id="2ec27-133">Agregar comentarios acerca de la línea de la hoja de horas en la pestaña **Comentario**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-133">Add comments about the timesheet line in the **Comment** tab.</span></span>
20. <span data-ttu-id="2ec27-134">En el **panel de acciones**, haga clic en **Flujo de trabajo** para abrir el diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="2ec27-134">In the **Action pane**, click **Workflow** to open the drop dialog.</span></span>
21. <span data-ttu-id="2ec27-135">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-135">Click **Submit**.</span></span>
22. <span data-ttu-id="2ec27-136">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2ec27-136">Click **Submit**.</span></span>

