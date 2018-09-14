--- 
title: "Creación de grupos de permisos de PDV"
description: "Este procedimiento mostrará cómo crear un grupo de permisos de PDV."
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1b30c9a1d7fe4598695423ba700ebc88a794a49c
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="518f7-103">Creación de grupos de permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="518f7-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="518f7-104">Este procedimiento mostrará cómo crear un grupo de permisos de PDV.</span><span class="sxs-lookup"><span data-stu-id="518f7-104">This procedure will show how to create a POS permission group.</span></span> <span data-ttu-id="518f7-105">La empresa de datos de prueba utilizada para crear esta tarea es USRT.</span><span class="sxs-lookup"><span data-stu-id="518f7-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="518f7-106">Esta tarea está pensada para el rol de encargado de operaciones comerciales.</span><span class="sxs-lookup"><span data-stu-id="518f7-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="518f7-107">Vaya a Grupos de permisos.</span><span class="sxs-lookup"><span data-stu-id="518f7-107">Go to Permission groups.</span></span>
2. <span data-ttu-id="518f7-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="518f7-108">Click New.</span></span>
3. <span data-ttu-id="518f7-109">En el campo Id. de grupo de permisos de PDV, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="518f7-109">In the POS permission group ID field, type a value.</span></span>
4. <span data-ttu-id="518f7-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="518f7-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="518f7-111">Seleccione Sí en el campo Ver entradas de reloj de tiempo.</span><span class="sxs-lookup"><span data-stu-id="518f7-111">Select Yes in the View time clock entries field.</span></span>
    * <span data-ttu-id="518f7-112">Ahora puede habilitar o deshabilitar varios permisos para el grupo de permisos de PDV.</span><span class="sxs-lookup"><span data-stu-id="518f7-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="518f7-113">Para algún permiso puede establecer un valor que se usará para evaluar si el usuario del PDV puede realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="518f7-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span>  <span data-ttu-id="518f7-114">Esta guía de tareas permite algunos permisos que se pueden dar a un cajero.</span><span class="sxs-lookup"><span data-stu-id="518f7-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="518f7-115">Seleccione Sí en el campo Permitir creación de pedidos.</span><span class="sxs-lookup"><span data-stu-id="518f7-115">Select Yes in the Allow create order field.</span></span>
7. <span data-ttu-id="518f7-116">Seleccione Sí en el campo Permitir edición de pedidos.</span><span class="sxs-lookup"><span data-stu-id="518f7-116">Select Yes in the Allow edit order field.</span></span>
8. <span data-ttu-id="518f7-117">Seleccione Sí en el campo Permitir recuperación de pedidos.</span><span class="sxs-lookup"><span data-stu-id="518f7-117">Select Yes in the Allow retrieve order field.</span></span>
9. <span data-ttu-id="518f7-118">Seleccione Sí en el campo Permitir cambio de contraseña.</span><span class="sxs-lookup"><span data-stu-id="518f7-118">Select Yes in the Allow password change field.</span></span>
10. <span data-ttu-id="518f7-119">Seleccione Sí en el campo Permitir cierre en ciego.</span><span class="sxs-lookup"><span data-stu-id="518f7-119">Select Yes in the Allow blind close field.</span></span>
11. <span data-ttu-id="518f7-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="518f7-120">Click Save.</span></span>
    * <span data-ttu-id="518f7-121">Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="518f7-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  
12. <span data-ttu-id="518f7-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="518f7-122">Close the page.</span></span>
13. <span data-ttu-id="518f7-123">Vaya a Trabajos.</span><span class="sxs-lookup"><span data-stu-id="518f7-123">Go to Jobs.</span></span>
    * <span data-ttu-id="518f7-124">A continuación asignaremos el grupo de permisos de PDV a un trabajo.</span><span class="sxs-lookup"><span data-stu-id="518f7-124">Next we will assign the POS permission group to a Job.</span></span>  
14. <span data-ttu-id="518f7-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="518f7-125">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="518f7-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="518f7-126">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="518f7-127">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="518f7-127">Click Edit.</span></span>
17. <span data-ttu-id="518f7-128">Expanda la sección Clasificación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="518f7-128">Expand the Job classification section.</span></span>
18. <span data-ttu-id="518f7-129">En el campo Grupo de permisos de PDV, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="518f7-129">In the POS permission group field, enter or select a value.</span></span>
    * <span data-ttu-id="518f7-130">Todos los trabajadores de puestos para este trabajo usarán los parámetros de este grupo de permisos de PDV a menos que los permisos de PDV de los trabajadores se hayan anulada en su nivel del puesto.</span><span class="sxs-lookup"><span data-stu-id="518f7-130">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
19. <span data-ttu-id="518f7-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="518f7-131">Click Save.</span></span>
    * <span data-ttu-id="518f7-132">Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="518f7-132">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  


