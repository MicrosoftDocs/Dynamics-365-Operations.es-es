---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180953"
---
# <a name="create-new-users"></a><span data-ttu-id="9d3bf-103">Crear nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="9d3bf-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9d3bf-104">Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="9d3bf-105">Asociar un usuario con una licencia (nuevos tipos de licencia solamente)</span><span class="sxs-lookup"><span data-stu-id="9d3bf-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="9d3bf-106">Para los clientes que tienen los nuevos tipos de licencia que se agregaron en octubre de 2019, los usuarios deben estar asociados a una licencia.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="9d3bf-107">Los usuarios que están asociados a una licencia automáticamente se añaden como usuarios del sistema que no tienen ningún rol la primera vez que inician sesión.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="9d3bf-108">Los usuarios que no estén asociadas a una licencia reciben un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="9d3bf-109">Las administraciones del sistema pueden [asignar licencias a los usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) en el [Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9d3bf-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="9d3bf-110">Agregar un usuario nuevo</span><span class="sxs-lookup"><span data-stu-id="9d3bf-110">Add a new user</span></span>
1. <span data-ttu-id="9d3bf-111">Vaya a **Administración del sistema \> Usuarios \> Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="9d3bf-112">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="9d3bf-113">En el campo **Id. de usuario**, especifique un identificador único para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="9d3bf-114">El identificador de usuario es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-114">A user ID is required.</span></span>  
4. <span data-ttu-id="9d3bf-115">En el campo **Nombre de usuario**, escriba el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="9d3bf-116">En el campo **Dominio**, especifique el dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="9d3bf-117">En el campo **Alias** , escriba el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="9d3bf-118">En el campo **Empresa**, seleccione la empresa deseada.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="9d3bf-119">En la ficha desplegable **Roles de usuario** , seleccione **Asignar roles** a [asignar usuarios a roles de seguridad](assign-users-security-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9d3bf-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="9d3bf-120">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-120">Select **OK**.</span></span>
10. <span data-ttu-id="9d3bf-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="9d3bf-122">Importar usuarios</span><span class="sxs-lookup"><span data-stu-id="9d3bf-122">Import users</span></span>
1. <span data-ttu-id="9d3bf-123">En el panel de acciones, seleccione **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="9d3bf-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9d3bf-125">Seleccionar **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-125">Select **Import users**.</span></span>
4. <span data-ttu-id="9d3bf-126">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9d3bf-126">Select **Close**.</span></span>

