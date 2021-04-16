---
title: Preguntas más frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema proporciona respuestas a las preguntas frecuentes sobre la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 26e1dc53126c0615332457aa785415c4c7112bbd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842742"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-faq"></a><span data-ttu-id="9855f-103">Preguntas más frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9855f-103">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="9855f-104">Este tema proporciona respuestas a las preguntas frecuentes sobre la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9855f-104">This topic provides answers to frequently asked questions regarding Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

### <a name="who-in-the-store-becomes-an-owner-of-a-team-while-provisioning-teams-from-commerce"></a><span data-ttu-id="9855f-105">¿Quién en la tienda se convierte en propietario de un equipo mientras aprovisiona Teams de Commerce?</span><span class="sxs-lookup"><span data-stu-id="9855f-105">Who in the store becomes an owner of a team while provisioning Teams from Commerce?</span></span> 

<span data-ttu-id="9855f-106">Todos los gerentes de tienda se agregan automáticamente como propietarios al grupo de equipo correspondiente para que puedan realizar operaciones como agregar un canal privado y agregar o eliminar miembros.</span><span class="sxs-lookup"><span data-stu-id="9855f-106">All store managers are automatically added as owners to the corresponding team group so that they can perform operations such as adding a private channel and adding or deleting members.</span></span> 

### <a name="how-do-i-assign-the-communications-manager-role-to-an-employee-in-commerce-headquarters"></a><span data-ttu-id="9855f-107">¿Cómo asigno el rol de "gerente de comunicaciones" a un empleado en la sede de Commerce?</span><span class="sxs-lookup"><span data-stu-id="9855f-107">How do I assign the "communications manager" role to an employee in Commerce headquarters?</span></span> 

<span data-ttu-id="9855f-108">Responsables de comunicación en Microsoft Teams tienen la capacidad de crear y publicar listas de tareas.</span><span class="sxs-lookup"><span data-stu-id="9855f-108">Communication managers in Microsoft Teams have the ability to create and publish task lists.</span></span> <span data-ttu-id="9855f-109">Los empleados de la organización que necesitan convertirse en gerentes de comunicación deben tener asignado el rol de "gerente de tareas minoristas" en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="9855f-109">Organization employees who need to become communication managers must have the "retail task manager" role assigned to them in Commerce headquarters.</span></span>

<span data-ttu-id="9855f-110">Para asignar el rol de administrador de tareas minoristas a un empleado en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9855f-110">To assign the retail task manager role to an employee in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9855f-111">Vaya a **Retail y Commerce \> Empleados \> Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9855f-111">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="9855f-112">Seleccione un empleado.</span><span class="sxs-lookup"><span data-stu-id="9855f-112">Select an employee.</span></span>
1. <span data-ttu-id="9855f-113">En la ficha desplegable **Roles de usuarios** seleccione **Asignar roles**.</span><span class="sxs-lookup"><span data-stu-id="9855f-113">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="9855f-114">En el cuadro de diálogo **Asignar roles al usuario**, seleccione el rol **Gerente de tareas de Retail**, y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9855f-114">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

### <a name="how-do-i-make-a-specific-organization-hierarchy-available-to-upload-into-microsoft-teams"></a><span data-ttu-id="9855f-115">¿Cómo puedo hacer que una jerarquía organizativa específica esté disponible para cargar en Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="9855f-115">How do I make a specific organization hierarchy available to upload into Microsoft Teams?</span></span>

<span data-ttu-id="9855f-116">En la sede de Commerce, la jerarquía de cada organización está asociada con uno o más propósitos.</span><span class="sxs-lookup"><span data-stu-id="9855f-116">In Commerce headquarters, every organization's hierarchy is associated with one or more purposes.</span></span> <span data-ttu-id="9855f-117">Asegúrese de que la jerarquía en la que desea aprovisionar Microsoft Teams tiene el propósito **Informes minoristas** asociado con él, como se muestra en la siguiente imagen de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9855f-117">Make sure the hierarchy that you want to provision into Microsoft Teams has the **Retail reporting** purpose associated with it, as shown in the following example image.</span></span> 

![Ejemplo de un propósito de jerarquía organizativa en la sede de Commerce](media/d365-commerce-organization-hierarchies-purpose.png)

### <a name="how-do-i-enable-retail-store-workers-to-sign-in-to-commerce-point-of-sale-pos-using-azure-active-directory-azure-ad"></a><span data-ttu-id="9855f-119">¿Cómo puedo permitir que los trabajadores de la tienda minorista inicien sesión en el punto de venta (PDV) de Commerce usando Azure Active Directory (Azure AD)?</span><span class="sxs-lookup"><span data-stu-id="9855f-119">How do I enable retail store workers to sign in to Commerce point of sale (POS) using Azure Active Directory (Azure AD)?</span></span>

<span data-ttu-id="9855f-120">Para obtener información sobre cómo configurar la experiencia de inicio de sesión de Commerce PDV para usar autenticación de Azure AD, vea [Habilitar autenticación Azure Active Directory para el inicio de sesión de PDV](aad-pos-logon.md).</span><span class="sxs-lookup"><span data-stu-id="9855f-120">For information about how to configure the Commerce POS sign-in experience to use Azure AD authentication, see [Enable Azure Active Directory authentication for POS sign-in](aad-pos-logon.md).</span></span>

### <a name="how-do-i-map-stores-and-corresponding-teams-in-commerce-headquarters-if-my-organization-has-already-created-teams-in-microsoft-teams"></a><span data-ttu-id="9855f-121">¿Cómo asigno las tiendas y los equipos correspondientes en la sede de Commerce si mi organización ya ha creado equipos en Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="9855f-121">How do I map stores and corresponding teams in Commerce headquarters if my organization has already created teams in Microsoft Teams?</span></span>

<span data-ttu-id="9855f-122">Para obtener información sobre cómo asignar tiendas y equipos si hay equipos preexistentes, consulte [Asignar tiendas y equipos correspondientes si su organización tiene equipos preexistentes en Microsoft Teams](map-stores-existing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9855f-122">For information on how to map stores and teams if there are pre-existing teams, see [Map stores and corresponding teams if your organization has pre-existing teams in Microsoft Teams](map-stores-existing-teams.md).</span></span>

### <a name="how-do-i-clear-the-microsoft-graph-api-token-stored-in-the-session-storage"></a><span data-ttu-id="9855f-123">¿Cómo borro el token de la API de Microsoft Graph almacenado en el almacenamiento de la sesión?</span><span class="sxs-lookup"><span data-stu-id="9855f-123">How do I clear the Microsoft Graph API token stored in the session storage?</span></span>

<span data-ttu-id="9855f-124">Un usuario que ha iniciado sesión en el punto de venta (PDV) con una cuenta Azure Active Directory (Azure AD) debe cerrar sesión en el PDV o cerrar la aplicación para borrar el almacenamiento de la sesión.</span><span class="sxs-lookup"><span data-stu-id="9855f-124">A user who has signed in to the point of sale (POS) with an Azure Active Directory (Azure AD) account should sign out from the POS or close the application to clear the session storage.</span></span> 

> [!TIP]
> <span data-ttu-id="9855f-125">Una mejor práctica recomendada es hacer que los trabajadores de la tienda bloqueen siempre el terminal PDV o cierren la sesión cuando no estén usando el terminal.</span><span class="sxs-lookup"><span data-stu-id="9855f-125">A recommended best practice is to always have store workers lock the POS terminal or sign out from a session when not using the terminal.</span></span> 

### <a name="what-happens-if-a-store-doesnt-have-store-managers"></a><span data-ttu-id="9855f-126">¿Qué sucede si una tienda no tiene gerentes de tienda?</span><span class="sxs-lookup"><span data-stu-id="9855f-126">What happens if a store doesn't have store managers?</span></span>

<span data-ttu-id="9855f-127">Si una tienda no tiene gerentes, no se creará un grupo de equipo para la tienda o en Teams.</span><span class="sxs-lookup"><span data-stu-id="9855f-127">If a store doesn't have managers, a team group will not be created for the store or in Teams.</span></span> 

### <a name="what-happens-if-a-store-manager-leaves-the-company"></a><span data-ttu-id="9855f-128">¿Qué sucede si el gerente de una tienda deja la empresa?</span><span class="sxs-lookup"><span data-stu-id="9855f-128">What happens if a store manager leaves the company?</span></span>

<span data-ttu-id="9855f-129">Cualquiera con el rol de propietario puede agregar un nuevo gerente de tienda en la sede de Commerce y reaprovisionar Teams para que el nuevo gerente tenga los privilegios necesarios en Teams para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9855f-129">Anyone with the owner role can add a new store manager in Commerce headquarters and reprovision Teams so that the new manager will have the necessary privileges in Teams for the group.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="9855f-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9855f-130">Additional resources</span></span>

[<span data-ttu-id="9855f-131">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9855f-131">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="9855f-132">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9855f-132">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="9855f-133">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9855f-133">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="9855f-134">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="9855f-134">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="9855f-135">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9855f-135">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="9855f-136">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9855f-136">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)
