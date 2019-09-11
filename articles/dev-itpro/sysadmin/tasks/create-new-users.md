---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916493"
---
# <a name="create-new-users"></a><span data-ttu-id="b54f9-103">Crear nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="b54f9-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b54f9-104">Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.</span><span class="sxs-lookup"><span data-stu-id="b54f9-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="b54f9-105">Los administradores del sistema pueden completar este procedimiento para agregar usuarios al sistema.</span><span class="sxs-lookup"><span data-stu-id="b54f9-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="b54f9-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="b54f9-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="b54f9-107">Agregar un usuario nuevo</span><span class="sxs-lookup"><span data-stu-id="b54f9-107">Add a new user</span></span>
1. <span data-ttu-id="b54f9-108">Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="b54f9-109">En el **panel de acciones**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="b54f9-110">En el campo **Id. de usuario**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b54f9-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="b54f9-111">Escriba un identificador único para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b54f9-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="b54f9-112">El identificador de usuario es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b54f9-112">A user ID is required.</span></span>  
4. <span data-ttu-id="b54f9-113">En el campo **Nombre de usuario**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b54f9-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="b54f9-114">Especifique el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="b54f9-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="b54f9-115">En el campo **Dominio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b54f9-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="b54f9-116">Especifique el dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b54f9-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="b54f9-117">En el campo **Alias**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b54f9-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="b54f9-118">Especifique el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="b54f9-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="b54f9-119">En el campo **Empresa**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b54f9-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b54f9-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b54f9-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="b54f9-121">En la sección **Roles de usuario**, haga clic en **Roles de asignación**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="b54f9-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b54f9-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="b54f9-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-123">Click **OK**.</span></span>
12. <span data-ttu-id="b54f9-124">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="b54f9-125">Importar usuarios</span><span class="sxs-lookup"><span data-stu-id="b54f9-125">Import users</span></span>
1. <span data-ttu-id="b54f9-126">En el **panel de acciones**, haga clic en **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="b54f9-127">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b54f9-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="b54f9-128">Haga clic en **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-128">Click **Import users**.</span></span>
4. <span data-ttu-id="b54f9-129">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b54f9-129">Click **Close**.</span></span>

