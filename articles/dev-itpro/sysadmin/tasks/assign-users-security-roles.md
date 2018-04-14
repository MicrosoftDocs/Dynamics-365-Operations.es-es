--- 
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a Microsoft Dynamics 365 or Finance and Operations, los usuarios se deben asignar a roles de seguridad.
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c7f35f57223798e91fc2a81c0821a2dc81512624
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="7978a-103">Asignar usuarios a roles de seguridad</span><span class="sxs-lookup"><span data-stu-id="7978a-103">Assign users to security roles</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7978a-104">Para obtener acceso a Microsoft Dynamics 365 or Finance and Operations, los usuarios se deben asignar a roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7978a-104">To access Microsoft Dynamics 365 for Finance and Operations, users must be assigned to security roles.</span></span> <span data-ttu-id="7978a-105">Este procedimiento explica cómo los administradores del sistema pueden asignar usuarios a roles automáticamente, en función de los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="7978a-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="7978a-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="7978a-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="7978a-107">Asignar usuarios automáticamente a roles</span><span class="sxs-lookup"><span data-stu-id="7978a-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="7978a-108">Vaya a Administración del sistema > Seguridad > Asignar usuarios a roles.</span><span class="sxs-lookup"><span data-stu-id="7978a-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="7978a-109">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="7978a-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="7978a-110">Seleccione el rol para el que desea configurar la regla.</span><span class="sxs-lookup"><span data-stu-id="7978a-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="7978a-111">En este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="7978a-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="7978a-112">Haga clic en Agregar regla para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="7978a-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="7978a-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7978a-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7978a-114">Seleccione la consulta que se usará para esta regla.</span><span class="sxs-lookup"><span data-stu-id="7978a-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="7978a-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7978a-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7978a-116">Haga clic en Editar consulta.</span><span class="sxs-lookup"><span data-stu-id="7978a-116">Click Edit query.</span></span>
    * <span data-ttu-id="7978a-117">Edite la consulta según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7978a-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="7978a-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7978a-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="7978a-119">Excluir usuarios de la asignación automática de roles</span><span class="sxs-lookup"><span data-stu-id="7978a-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="7978a-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7978a-120">Close the page.</span></span>
2. <span data-ttu-id="7978a-121">Vaya a Administración del sistema > Seguridad > Asignar usuarios a roles.</span><span class="sxs-lookup"><span data-stu-id="7978a-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="7978a-122">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="7978a-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="7978a-123">Seleccione una función.</span><span class="sxs-lookup"><span data-stu-id="7978a-123">Select a role.</span></span> <span data-ttu-id="7978a-124">Para este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="7978a-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="7978a-125">Haga clic en Asignar o excluir usuarios de forma manual.</span><span class="sxs-lookup"><span data-stu-id="7978a-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="7978a-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7978a-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7978a-127">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="7978a-127">Select a user.</span></span>  
6. <span data-ttu-id="7978a-128">Haga clic en Excluir de rol.</span><span class="sxs-lookup"><span data-stu-id="7978a-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="7978a-129">Haga clic en Excluir de rol para excluir los usuarios seleccionados del rol.</span><span class="sxs-lookup"><span data-stu-id="7978a-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="7978a-130">Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en Restablecer estado.</span><span class="sxs-lookup"><span data-stu-id="7978a-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="7978a-131">Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna de nuevo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7978a-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="7978a-132">Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado.</span><span class="sxs-lookup"><span data-stu-id="7978a-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="7978a-133">En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.</span><span class="sxs-lookup"><span data-stu-id="7978a-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


