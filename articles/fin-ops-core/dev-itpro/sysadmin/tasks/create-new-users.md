---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e84130ff2b1cf83b7d2b95eefc72175dc57743c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982511"
---
# <a name="create-new-users"></a><span data-ttu-id="ea3ab-103">Crear nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="ea3ab-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ea3ab-104">Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="ea3ab-105">Asociar un usuario con una licencia (nuevos tipos de licencia solamente)</span><span class="sxs-lookup"><span data-stu-id="ea3ab-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="ea3ab-106">Para los clientes que tienen los nuevos tipos de licencia que se agregaron en octubre de 2019, los usuarios deben estar asociados a una licencia.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="ea3ab-107">Los usuarios que están asociados a una licencia automáticamente se añaden como usuarios del sistema que no tienen ningún rol la primera vez que inician sesión.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="ea3ab-108">Las administraciones del sistema pueden [asignar licencias a los usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) en el [Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="ea3ab-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="ea3ab-109">Asociar un usuario externo con una licencia (nuevos tipos de licencia solamente)</span><span class="sxs-lookup"><span data-stu-id="ea3ab-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="ea3ab-110">Los usuarios externos al inquilino en el que se implementó el entorno deben estar representados en el directorio del inquilino host (Azure Active Directory (Azure AD)) para que se les puedan asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="ea3ab-111">Esos usuarios externos deben agregarse al inquilino en Azure AD como usuarios invitados y luego se les deben asignar las licencias correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="ea3ab-112">Para obtener más información, consulte [Agregar usuarios de colaboración B2B de Azure Active Directory en el portal de Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="ea3ab-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="ea3ab-113">Agregar un usuario nuevo</span><span class="sxs-lookup"><span data-stu-id="ea3ab-113">Add a new user</span></span>
1. <span data-ttu-id="ea3ab-114">Vaya a **Administración del sistema \> Usuarios \> Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="ea3ab-115">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="ea3ab-116">En el campo **Id. de usuario**, especifique un identificador único para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="ea3ab-117">El identificador de usuario es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-117">A user ID is required.</span></span>  
4. <span data-ttu-id="ea3ab-118">En el campo **Nombre de usuario**, escriba el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="ea3ab-119">En el campo **Dominio**, especifique el dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="ea3ab-120">En el campo **Alias** , escriba el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="ea3ab-121">En el campo **Empresa**, seleccione la empresa deseada.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="ea3ab-122">En la ficha desplegable **Roles de usuario**, seleccione **Asignar roles** para asignar usuarios a roles de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="ea3ab-123">Para obtener más información, consulte [Asignar usuarios a roles de seguridad](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ea3ab-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="ea3ab-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-124">Select **OK**.</span></span>
10. <span data-ttu-id="ea3ab-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="ea3ab-126">Importar usuarios</span><span class="sxs-lookup"><span data-stu-id="ea3ab-126">Import users</span></span>
1. <span data-ttu-id="ea3ab-127">Vaya a **Administración del sistema \> Usuarios \> Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-127">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="ea3ab-128">En el panel de acciones, seleccione **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-128">On the Action Pane, select **Import users**.</span></span>
3. <span data-ttu-id="ea3ab-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-129">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ea3ab-130">Seleccionar **Importar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-130">Select **Import users**.</span></span>
5. <span data-ttu-id="ea3ab-131">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ea3ab-131">Select **Close**.</span></span>

