---
title: Crear grupos de permisos de PDV
description: Este tema explica cómo crear un grupo de permisos de PDV.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ffc64fd39a390af3ca7110178ef0999527106dc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141393"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="cc26c-103">Crear grupos de permisos de PDV</span><span class="sxs-lookup"><span data-stu-id="cc26c-103">Create POS permission groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc26c-104">Este tema explica cómo crear un grupo de permisos de PDV.</span><span class="sxs-lookup"><span data-stu-id="cc26c-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="cc26c-105">La empresa de datos de prueba utilizada para crear esta tarea es USRT.</span><span class="sxs-lookup"><span data-stu-id="cc26c-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="cc26c-106">Esta tarea está pensada para el rol de encargado de operaciones de Commerce.</span><span class="sxs-lookup"><span data-stu-id="cc26c-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="cc26c-107">En el panel de navegación, vaya a **Módulos > Retail y Commerce> Empleados > Grupos de permisos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="cc26c-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-108">Select **New**.</span></span>
3. <span data-ttu-id="cc26c-109">En el campo **Id. de grupo de permisos de PDV**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cc26c-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="cc26c-110">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cc26c-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="cc26c-111">Seleccione **Sí** en el campo **Ver entradas de reloj de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="cc26c-112">Ahora puede habilitar o deshabilitar varios permisos para el grupo de permisos de PDV.</span><span class="sxs-lookup"><span data-stu-id="cc26c-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="cc26c-113">Para algún permiso puede establecer un valor que se usará para evaluar si el usuario del PDV puede realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="cc26c-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="cc26c-114">Esta guía de tareas permite algunos permisos que se pueden dar a un cajero.</span><span class="sxs-lookup"><span data-stu-id="cc26c-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="cc26c-115">Seleccione **Sí** en el campo **Permitir creación de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="cc26c-116">Seleccione **Sí** en el campo **Permitir edición de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="cc26c-117">Seleccione **Sí** en el campo **Permitir recuperación de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="cc26c-118">Seleccione **Sí** en el campo **Permitir cambio de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="cc26c-119">Seleccione **Sí** en el campo **Permitir cierre en ciego**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="cc26c-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-120">Select **Save**.</span></span> <span data-ttu-id="cc26c-121">Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales de Commerce.</span><span class="sxs-lookup"><span data-stu-id="cc26c-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="cc26c-122">En el Panel de exploración, vaya a **Módulos > Recursos humanos > Trabajos > Trabajos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="cc26c-123">A continuación asignaremos el grupo de permisos de PDV a un trabajo.</span><span class="sxs-lookup"><span data-stu-id="cc26c-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="cc26c-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cc26c-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="cc26c-125">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-125">Select **Edit**.</span></span>
15. <span data-ttu-id="cc26c-126">Expanda la sección **Clasificación de trabajos**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="cc26c-127">En el campo Grupo de permisos de PDV, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cc26c-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="cc26c-128">Todos los trabajadores de puestos para este trabajo usarán los parámetros de este grupo de permisos de PDV a menos que los permisos de PDV de los trabajadores se hayan anulada en su nivel del puesto.</span><span class="sxs-lookup"><span data-stu-id="cc26c-128">All Workers in Positions for this Job will use this POS permission group's settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="cc26c-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="cc26c-129">Select **Save**.</span></span> <span data-ttu-id="cc26c-130">Una vez se guarden los cambios necesita ejecutar la programación de distribución del personal para aplicar los cambios en canales.</span><span class="sxs-lookup"><span data-stu-id="cc26c-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  

