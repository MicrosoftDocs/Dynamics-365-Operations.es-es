---
title: Administrar usuarios y roles de comercio electrónico
description: Este tema explica cómo conceder acceso a los usuarios para el entorno de creación del sitio de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a1f9abae20d0f2e71790a3b27337338dc042b52
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415423"
---
# <a name="manage-e-commerce-users-and-roles"></a><span data-ttu-id="998d7-103">Administrar usuarios y roles de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="998d7-103">Manage e-Commerce users and roles</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="998d7-104">Este tema explica cómo conceder acceso a los usuarios para el entorno de creación del sitio de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="998d7-104">This topic explains how to grant users access to the authoring environment for your Microsoft Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="998d7-105">Para ayudar a controlar el acceso de los usuarios y conceder permiso a los usuarios para realizar tareas específicas, el entorno de creación de sitios usa grupos de seguridad que crea en Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="998d7-105">To help control user access and grant users permission to perform specific tasks, the site authoring environment uses security groups that you create in Microsoft Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="998d7-106">Primero asigna un grupo de seguridad nuevo o existente desde Azure AD a cada rol en el entorno de creación.</span><span class="sxs-lookup"><span data-stu-id="998d7-106">You first assign a new or existing security group from Azure AD to each role in the authoring environment.</span></span> <span data-ttu-id="998d7-107">A continuación, concede o revoca permisos para usuarios individuales agregando esos usuarios a un grupo de seguridad adecuado o quitándolos de un grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="998d7-107">You then grant or revoke permissions for individual users by either adding those users to an appropriate security group or removing them from a security group.</span></span>

## <a name="overview-of-roles-in-the-authoring-environment"></a><span data-ttu-id="998d7-108">Visión general de roles en el entorno de creación</span><span class="sxs-lookup"><span data-stu-id="998d7-108">Overview of roles in the authoring environment</span></span>

<span data-ttu-id="998d7-109">El entorno de creación de Dynamics 365 for Commerce admite los roles siguientes.</span><span class="sxs-lookup"><span data-stu-id="998d7-109">The Dynamics 365 for Commerce authoring environment supports the following roles.</span></span>

| <span data-ttu-id="998d7-110">Función</span><span class="sxs-lookup"><span data-stu-id="998d7-110">Role</span></span>                 | <span data-ttu-id="998d7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="998d7-111">Description</span></span> |
|----------------------|-------------|
| <span data-ttu-id="998d7-112">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="998d7-112">System Administrator</span></span> | <span data-ttu-id="998d7-113">Los usuarios con este rol tienen todos los privilegios para todas las herramientas, y para todas las calificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="998d7-113">Users who have this role have all privileges for all tools, and for all ratings and reviews.</span></span> <span data-ttu-id="998d7-114">También pueden crear sitios.</span><span class="sxs-lookup"><span data-stu-id="998d7-114">They can also create sites.</span></span> |
| <span data-ttu-id="998d7-115">Administrador</span><span class="sxs-lookup"><span data-stu-id="998d7-115">Administrator</span></span>   | <span data-ttu-id="998d7-116">Usuarios que tienen este rol cuentan con todos los privilegios para todas las herramientas y RnR en una estructura de sitio dada.</span><span class="sxs-lookup"><span data-stu-id="998d7-116">Users who have this role have all privileges for all tools and RnR in a given site structure.</span></span> |
| <span data-ttu-id="998d7-117">Productor web</span><span class="sxs-lookup"><span data-stu-id="998d7-117">Web Producer</span></span>         | <span data-ttu-id="998d7-118">Los usuarios con este rol pueden crear páginas, fragmentos y plantillas, cargar y administrar activos, y enriquecer productos y categorías.</span><span class="sxs-lookup"><span data-stu-id="998d7-118">Users who have this role can create pages, fragments and templates, upload and manage assets, and enrich products and categories.</span></span> |
| <span data-ttu-id="998d7-119">Lector</span><span class="sxs-lookup"><span data-stu-id="998d7-119">Reader</span></span>               | <span data-ttu-id="998d7-120">Los usuarios que tengan este rol pueden ver páginas, plantillas, activos, fragmentos, diseños y valores, pero no pueden realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="998d7-120">Users who have this role can view pages, templates, assets, fragments, layouts and settings, but may not make changes.</span></span> |
| <span data-ttu-id="998d7-121">Moderador RnR</span><span class="sxs-lookup"><span data-stu-id="998d7-121">RnR Moderator</span></span>        | <span data-ttu-id="998d7-122">Los usuarios que tienen este rol pueden moderar revisiones de productos.</span><span class="sxs-lookup"><span data-stu-id="998d7-122">Users who have this role can moderate product reviews.</span></span> |

## <a name="system-administrator-role"></a><span data-ttu-id="998d7-123">Rol Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="998d7-123">System Administrator role</span></span>

<span data-ttu-id="998d7-124">Al aprovisionar Dynamics 365 Commerce en el entorno de Lifecycle Services (LCS) de Microsoft Dynamics, se te pedirá que proporciones un grupo de seguridad para el rol **Administrador del sistema**.</span><span class="sxs-lookup"><span data-stu-id="998d7-124">When you provision Dynamics 365 Commerce in the Microsoft Dynamics Lifecycle Services (LCS) environment, you're asked to provide a security group for the **System Administrator** role.</span></span> <span data-ttu-id="998d7-125">A continuación, este rol se aplicará automáticamente a todos los sitios que cree en el entorno que está configurando.</span><span class="sxs-lookup"><span data-stu-id="998d7-125">This role is then automatically applied to all sites that you create in the environment that you're configuring.</span></span> <span data-ttu-id="998d7-126">El grupo de seguridad para este rol solo se puede actualizar en LCS.</span><span class="sxs-lookup"><span data-stu-id="998d7-126">The security group for this role can be updated only in LCS.</span></span> <span data-ttu-id="998d7-127">En la página **Administración del sitio** para todos los sitios, aparece como de solo lectura y es meramente informativo.</span><span class="sxs-lookup"><span data-stu-id="998d7-127">On the **Site Administration** page for all sites, it appears as read-only and is for informational purposes only.</span></span>

## <a name="administrator-role"></a><span data-ttu-id="998d7-128">Rol Administrador</span><span class="sxs-lookup"><span data-stu-id="998d7-128">Administrator role</span></span>

<span data-ttu-id="998d7-129">Al crear un nuevo sitio en comercio, se le pide proporcionar un grupo de seguridad para el rol **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="998d7-129">When you create a new site in Commerce, you're asked to provide a security group for the **Administrator** role.</span></span> <span data-ttu-id="998d7-130">Consulte la tabla anterior de este tema para obtener una visión general de los permisos que este rol concede.</span><span class="sxs-lookup"><span data-stu-id="998d7-130">See the table earlier in this topic for an overview of the permissions that this role grants.</span></span>

## <a name="add-or-update-security-groups"></a><span data-ttu-id="998d7-131">Agregar o actualizar grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="998d7-131">Add or update security groups</span></span>

<span data-ttu-id="998d7-132">Una vez creado el sitio, solo los usuarios que se encuentren en los grupos de seguridad que están asociados a los roles **Administrador del sistema** y **Administrador** pueden tener acceso al entorno de creación para ese sitio.</span><span class="sxs-lookup"><span data-stu-id="998d7-132">After your site is created, only users who are in the security groups that are associated with the **System Administrator** and **Administrator** roles can access the authoring environment for that site.</span></span> <span data-ttu-id="998d7-133">Para asignar usuarios a los roles **Productor web**, **Moderador RnR** y Lector **Reader**, debe asignar grupos de seguridad a esos roles.</span><span class="sxs-lookup"><span data-stu-id="998d7-133">To assign users to the **Web Producer**, **RnR Moderator**, and **Reader** roles, you must assign security groups to those roles.</span></span> <span data-ttu-id="998d7-134">Para agregar un grupo de seguridad a un rol, o actualizar un grupo de seguridad que está asignado actualmente a un rol, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="998d7-134">To add a security group to a role, or to update a security group that is currently assigned to a role, follow these steps.</span></span>

1. <span data-ttu-id="998d7-135">Vaya al sitio que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="998d7-135">Go to the site that you want to update.</span></span>
1. <span data-ttu-id="998d7-136">En el **Administración del sitio**, abra la página **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="998d7-136">In **Site management**, open the **Security** page.</span></span>
1. <span data-ttu-id="998d7-137">Seleccione el rol que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="998d7-137">Select the role to modify.</span></span>
1. <span data-ttu-id="998d7-138">Agregue grupos de seguridad a roles, o quite grupos de seguridad de roles.</span><span class="sxs-lookup"><span data-stu-id="998d7-138">Add security groups to roles, or remove security groups from roles.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="998d7-139">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="998d7-139">Additional resources</span></span>

[<span data-ttu-id="998d7-140">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="998d7-140">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="998d7-141">Consideraciones de optimización de motor de búsqueda (SEO) para su sitio</span><span class="sxs-lookup"><span data-stu-id="998d7-141">Search engine optimization (SEO) considerations for your site</span></span>](search-engine-optimization-considerations.md)

[<span data-ttu-id="998d7-142">Gestionar la directiva de seguridad de contenido (CSP)</span><span class="sxs-lookup"><span data-stu-id="998d7-142">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
