---
title: Crear nuevos usuarios
description: Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 89e492ef5030dd28020094152259b615010aa676
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851320"
---
# <a name="create-new-users"></a><span data-ttu-id="46a8f-103">Crear nuevos usuarios</span><span class="sxs-lookup"><span data-stu-id="46a8f-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46a8f-104">Los usuarios son empleados internos de la organización o clientes y proveedores externos que requieren acceso al sistema para llevar a cabo sus trabajos.</span><span class="sxs-lookup"><span data-stu-id="46a8f-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="46a8f-105">Los administradores del sistema pueden completar este procedimiento para agregar usuarios al sistema.</span><span class="sxs-lookup"><span data-stu-id="46a8f-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="46a8f-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="46a8f-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="46a8f-107">Agregar un usuario nuevo</span><span class="sxs-lookup"><span data-stu-id="46a8f-107">Add a new user</span></span>
1. <span data-ttu-id="46a8f-108">Vaya a Administración del sistema > Usuarios > Usuarios.</span><span class="sxs-lookup"><span data-stu-id="46a8f-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="46a8f-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="46a8f-109">Click New.</span></span>
3. <span data-ttu-id="46a8f-110">En el campo Id. de usuario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="46a8f-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="46a8f-111">Escriba un identificador único para el usuario.</span><span class="sxs-lookup"><span data-stu-id="46a8f-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="46a8f-112">El identificador de usuario es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="46a8f-112">A user ID is required.</span></span>  
4. <span data-ttu-id="46a8f-113">En el campo Nombre de usuario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="46a8f-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="46a8f-114">Especifique el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="46a8f-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="46a8f-115">En el campo Dominio, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="46a8f-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="46a8f-116">Especifique el dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="46a8f-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="46a8f-117">En el campo Alias, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="46a8f-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="46a8f-118">Especifique el alias del usuario.</span><span class="sxs-lookup"><span data-stu-id="46a8f-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="46a8f-119">En el campo Empresa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="46a8f-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="46a8f-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="46a8f-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="46a8f-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="46a8f-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="46a8f-122">Seleccione la empresa del usuario.</span><span class="sxs-lookup"><span data-stu-id="46a8f-122">Select the user's company</span></span>  
10. <span data-ttu-id="46a8f-123">Haga clic en Asignar roles.</span><span class="sxs-lookup"><span data-stu-id="46a8f-123">Click Assign roles.</span></span>
11. <span data-ttu-id="46a8f-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="46a8f-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="46a8f-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="46a8f-125">Click OK.</span></span>
13. <span data-ttu-id="46a8f-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="46a8f-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="46a8f-127">Importar usuarios</span><span class="sxs-lookup"><span data-stu-id="46a8f-127">Import users</span></span>
1. <span data-ttu-id="46a8f-128">Haga clic en Importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="46a8f-128">Click Import users.</span></span>
2. <span data-ttu-id="46a8f-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="46a8f-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="46a8f-130">Haga clic en Importar usuarios.</span><span class="sxs-lookup"><span data-stu-id="46a8f-130">Click Import users.</span></span>
4. <span data-ttu-id="46a8f-131">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="46a8f-131">Click Close.</span></span>

