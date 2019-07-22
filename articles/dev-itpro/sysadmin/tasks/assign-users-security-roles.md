---
title: Asignar usuarios a roles de seguridad
description: Para obtener acceso a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, se debe asignar a los usuarios a roles de seguridad.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab9f2f5ea07ae1d616c48dffa8810b966f7dbb2f
ms.sourcegitcommit: 33e98f89294086334fe9c0a350abb6a52ef9dacb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "1711140"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="12f02-103">Asignar usuarios a roles de seguridad</span><span class="sxs-lookup"><span data-stu-id="12f02-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12f02-104">Para obtener acceso a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, se debe asignar a los usuarios a roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="12f02-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="12f02-105">Este procedimiento explica cómo los administradores del sistema pueden asignar usuarios a roles automáticamente, en función de los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="12f02-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="12f02-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="12f02-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="12f02-107">Asignar usuarios automáticamente a roles</span><span class="sxs-lookup"><span data-stu-id="12f02-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="12f02-108">Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="12f02-108">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="12f02-109">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="12f02-109">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="12f02-110">Seleccione el rol para el que desea configurar la regla.</span><span class="sxs-lookup"><span data-stu-id="12f02-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="12f02-111">En este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="12f02-111">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="12f02-112">Haga clic en **Agregar regla** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="12f02-112">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="12f02-113">En la lista **Seleccionar una consulta**, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="12f02-113">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="12f02-114">Seleccione la consulta que se usará para esta regla.</span><span class="sxs-lookup"><span data-stu-id="12f02-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="12f02-115">En la lista **Nombre de la regla de pertenencia**, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="12f02-115">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="12f02-116">Haga clic en **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="12f02-116">Click **Edit query**.</span></span> <span data-ttu-id="12f02-117">Edite la consulta según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="12f02-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="12f02-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="12f02-118">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="12f02-119">Excluir usuarios de la asignación automática de roles</span><span class="sxs-lookup"><span data-stu-id="12f02-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="12f02-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="12f02-120">Close the page.</span></span>
2. <span data-ttu-id="12f02-121">Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="12f02-121">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="12f02-122">En el árbol, seleccione "Supervisor contable".</span><span class="sxs-lookup"><span data-stu-id="12f02-122">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="12f02-123">Seleccione una función.</span><span class="sxs-lookup"><span data-stu-id="12f02-123">Select a role.</span></span> <span data-ttu-id="12f02-124">Para este ejemplo, seleccione Supervisor contable.</span><span class="sxs-lookup"><span data-stu-id="12f02-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="12f02-125">En el menú **Usuarios asignados al rol**, seleccione **Asignar o excluir usuarios de forma manual**.</span><span class="sxs-lookup"><span data-stu-id="12f02-125">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="12f02-126">En el lista **Asignar usuarios al rol o excluir usuarios del rol**, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="12f02-126">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="12f02-127">Seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="12f02-127">Select a user.</span></span>  
6. <span data-ttu-id="12f02-128">En el **Panel de acciones**, seleccione **Excluir de rol**.</span><span class="sxs-lookup"><span data-stu-id="12f02-128">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="12f02-129">Haga clic en **Excluir de rol** para excluir los usuarios seleccionados del rol.</span><span class="sxs-lookup"><span data-stu-id="12f02-129">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="12f02-130">Para quitar exclusiones, seleccione los usuarios para los que desea quitar las exclusiones y, a continuación, haga clic en **Restablecer estado**.</span><span class="sxs-lookup"><span data-stu-id="12f02-130">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="12f02-131">Al eliminar una exclusión restableciendo el estado del usuario, el rol del usuario se asigna de nuevo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="12f02-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="12f02-132">Sin embargo, el usuario no se asigna inmediatamente al rol o se excluye del rol al restablecer el estado.</span><span class="sxs-lookup"><span data-stu-id="12f02-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="12f02-133">En su lugar, el usuario se asigna al rol o se elimina del rol la próxima vez que se ejecutan las reglas para la asignación automática de roles.</span><span class="sxs-lookup"><span data-stu-id="12f02-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
