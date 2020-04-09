---
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a aplicaciones de Finance and Operations, se debe asignar a los usuarios a roles de seguridad.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143572"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="f8c7b-103">Asignar usuarios a roles de seguridad</span><span class="sxs-lookup"><span data-stu-id="f8c7b-103">Assign users to security roles</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f8c7b-104">Para usar algo distinto a capacidades comunes, los usuarios deben asignarse a roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="f8c7b-105">Este procedimiento explica cómo los administradores del sistema pueden asignar automáticamente usuarios a roles, en función de los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="f8c7b-106">Asignar usuarios automáticamente a roles</span><span class="sxs-lookup"><span data-stu-id="f8c7b-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="f8c7b-107">Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="f8c7b-108">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="f8c7b-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="f8c7b-109">Seleccione el rol para el que desea configurar la regla.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="f8c7b-110">En este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="f8c7b-111">Haga clic en **Agregar regla** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="f8c7b-112">En la lista **Seleccionar una consulta**, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="f8c7b-113">Seleccione la consulta que se usará para esta regla.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="f8c7b-114">En la lista **Nombre de la regla de pertenencia**, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f8c7b-115">Haga clic en **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-115">Click **Edit query**.</span></span> <span data-ttu-id="f8c7b-116">Edite la consulta según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="f8c7b-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-117">Click **OK**.</span></span>
8. <span data-ttu-id="f8c7b-118">Haga clic en **Ejecutar asignación automática de roles**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="f8c7b-119">Vaya al **Panel de exploración > módulos > Administración del sistema > usuarios > usuarios** (idealmente en una ficha independiente de explorador).</span><span class="sxs-lookup"><span data-stu-id="f8c7b-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="f8c7b-120">Revise los roles asignados a varios usuarios para confirmar que la consulta de la asignación de roles fue correcta.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="f8c7b-121">Ajuste y vuelva a ejecutar si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="f8c7b-122">Excluir usuarios de la asignación automática de roles</span><span class="sxs-lookup"><span data-stu-id="f8c7b-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="f8c7b-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-123">Close the page.</span></span>
2. <span data-ttu-id="f8c7b-124">Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="f8c7b-125">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="f8c7b-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="f8c7b-126">Seleccione una función.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-126">Select a role.</span></span> <span data-ttu-id="f8c7b-127">Para este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="f8c7b-128">En el menú **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="f8c7b-129">En el lista **Asignar usuarios al rol o excluir usuarios del rol**, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="f8c7b-130">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-130">Select a user.</span></span>  
6. <span data-ttu-id="f8c7b-131">En el **Panel de acciones**, seleccione **Excluir de rol**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="f8c7b-132">Haga clic en **Excluir de rol** para excluir los usuarios seleccionados del rol.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="f8c7b-133">Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en **Restablecer estado**.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="f8c7b-134">Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna de nuevo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-134">When you remove an exclusion by resetting the user's status, the user's role is again assigned automatically.</span></span> <span data-ttu-id="f8c7b-135">Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="f8c7b-136">En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.</span><span class="sxs-lookup"><span data-stu-id="f8c7b-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
