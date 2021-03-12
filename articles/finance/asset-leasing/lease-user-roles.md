---
title: Asignar roles de usuario de arrendamiento
description: Este tema describe los roles de seguridad que se utilizan en el arrendamiento de activos. También explica cómo asignar usuarios a esos roles.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: df23e219f5bd859b0072785dfd5f7a0ec63f540e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995402"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="a842b-104">Asignar roles de usuario de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a842b-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a842b-105">Este tema describe los roles de seguridad que se utilizan en el arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a842b-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="a842b-106">También explica cómo asignar usuarios a esos roles.</span><span class="sxs-lookup"><span data-stu-id="a842b-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="a842b-107">Tres roles de usuario diferencian el acceso en el arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a842b-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="a842b-108">Un rol es apropiado para mantener arrendamientos, otro es apropiado para ver arrendamientos y otro es apropiado para realizar las tareas de un empleado de la sección de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="a842b-109">Cada rol tiene permisos específicos para todas las páginas de arrendamiento y cada uno permite a los usuarios ver, crear, editar o eliminar arrendamientos, de acuerdo con sus deberes laborales.</span><span class="sxs-lookup"><span data-stu-id="a842b-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="a842b-110">Función</span><span class="sxs-lookup"><span data-stu-id="a842b-110">Role</span></span>           | <span data-ttu-id="a842b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a842b-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="a842b-112">Mantener arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a842b-112">Maintain Lease</span></span> | <span data-ttu-id="a842b-113">Los usuarios en este rol pueden agregar, editar, eliminar y ver arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="a842b-114">Esta función está diseñada para usuarios diarios cuyas tareas incluyen la creación y registro de movimientos de diario mensuales y la adición de nuevos arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="a842b-115">Este rol da acceso a todas las funciones de arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a842b-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="a842b-116">Ver arrendamiento</span><span class="sxs-lookup"><span data-stu-id="a842b-116">View Lease</span></span>     | <span data-ttu-id="a842b-117">Los usuarios con este rol solo pueden ver registros de arrendamiento, programas y ejecutar informes.</span><span class="sxs-lookup"><span data-stu-id="a842b-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="a842b-118">No pueden crear nuevos arrendamientos, editar arrendamientos existentes ni crear movimientos de diario contra arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="a842b-119">El rol está diseñado para usuarios que solo tienen que ver los arrendamientos, las programaciones de arrendamientos y las transacciones que ocurren con esos arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="a842b-120">Empleado administrativo de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="a842b-120">Lease Clerk</span></span>    | <span data-ttu-id="a842b-121">Los usuarios con este rol solo pueden crear nuevos arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="a842b-122">No pueden editar ni eliminar arrendamientos existentes, ver programaciones de arrendamientos ni registrar entradas de diario de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="a842b-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="a842b-123">Este rol está diseñado para usuarios que trabajan en una capacidad de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="a842b-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="a842b-124">Siga estos pasos para asignar usuarios a los roles que se utilizan en el arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="a842b-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="a842b-125">Vaya a **Administración del sistema \> Seguridad \> Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="a842b-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="a842b-126">Seleccione el rol **Mantener arrendamiento**, **Empleado de sección de arrendamientos** o **Ver arrendamiento** y luego seleccione **Asignar/excluir usuarios manualmente**.</span><span class="sxs-lookup"><span data-stu-id="a842b-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="a842b-127">Seleccione el usuario para asignar al rol y luego seleccione **Asignar a rol**.</span><span class="sxs-lookup"><span data-stu-id="a842b-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>
