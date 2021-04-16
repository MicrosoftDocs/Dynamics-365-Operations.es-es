---
title: Aprovisionar Microsoft Teams desde Dynamics 365 Commerce
description: Este tema describe cómo aprovisionar Microsoft Teams mediante el uso de datos organizativos de Dynamics 365 Commerce.
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
ms.openlocfilehash: 96382c072e03506294d72899072a358091bda8ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842743"
---
# <a name="provision-microsoft-teams-from-dynamics-365-commerce"></a><span data-ttu-id="35542-103">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="35542-103">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="35542-104">Este tema describe cómo aprovisionar Microsoft Teams mediante el uso de datos organizativos de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="35542-104">This topic describes how to provision Microsoft Teams by using organizational data from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="35542-105">Dynamics 365 Commerce ofrece una manera fácil de aprovisionar Teams si aún no ha configurado equipos para sus tiendas minoristas allí.</span><span class="sxs-lookup"><span data-stu-id="35542-105">Dynamics 365 Commerce offers an easy way to provision Teams if you haven't yet set up teams for your retail stores there.</span></span> <span data-ttu-id="35542-106">Al aprovechar la información bien definida de Commerce que desea usar en Teams, puede ayudar a los empleados de su tienda a comenzar en Teams.</span><span class="sxs-lookup"><span data-stu-id="35542-106">By taking advantage of well-defined information from Commerce that you want to use in Teams, you can help your store employees get started in Teams.</span></span> <span data-ttu-id="35542-107">Esta información incluye la jerarquía organizativa, los nombres de las tiendas, la información de los empleados y cuentas Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="35542-107">This information includes the organizational hierarchy, store names, employee information, and Azure Active Directory (Azure AD) accounts.</span></span> 

<span data-ttu-id="35542-108">El proceso de aprovisionamiento de Teams tiene dos pasos principales:</span><span class="sxs-lookup"><span data-stu-id="35542-108">The process of provisioning Teams has two main steps:</span></span>

1. <span data-ttu-id="35542-109">En Teams, cree un equipo para cada tienda minorista y agregue trabajadores de la tienda como miembros del equipo apropiado.</span><span class="sxs-lookup"><span data-stu-id="35542-109">In Teams, create a team for each retail store, and add store workers as members of the appropriate team.</span></span> <span data-ttu-id="35542-110">Si un empleado está asociado con más de una tienda minorista, la pertenencia del equipo reflejará ese hecho.</span><span class="sxs-lookup"><span data-stu-id="35542-110">If an employee is associated with more than one retail store, team membership will reflect that fact.</span></span> <span data-ttu-id="35542-111">Se creará un equipo de comunicaciones que incluye administradores regionales como miembros para ayudar a publicar tareas de Teams.</span><span class="sxs-lookup"><span data-stu-id="35542-111">A communications team that includes regional managers as members will be created to help publish tasks from Teams.</span></span>
1. <span data-ttu-id="35542-112">Suba su jerarquía organizativa de Commerce a Teams.</span><span class="sxs-lookup"><span data-stu-id="35542-112">Upload your organizational hierarchy from Commerce to Teams.</span></span>

## <a name="provision-teams-in-commerce-headquarters"></a><span data-ttu-id="35542-113">Equipos de aprovisionamiento en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="35542-113">Provision Teams in Commerce headquarters</span></span>

<span data-ttu-id="35542-114">Antes de aprovisionar Microsoft Teams, complete estas tareas:</span><span class="sxs-lookup"><span data-stu-id="35542-114">Before you provision Microsoft Teams, complete these tasks:</span></span>

- <span data-ttu-id="35542-115">Confirme que todos los gerentes regionales se hayan convertido en gerentes de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="35542-115">Confirm that all regional managers have been made communications managers.</span></span>
- <span data-ttu-id="35542-116">Confirme que la cuenta de Azure de cada gerente y trabajador de la tienda se haya asociado con el registro de trabajador de ese gerente o trabajador en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="35542-116">Confirm that the Azure account of every store manager and worker has been associated with that manager's or worker's worker record in Commerce headquarters.</span></span>

<span data-ttu-id="35542-117">Para aprovisionar Teams en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="35542-117">To provision Teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="35542-118">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="35542-118">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="35542-119">En el panel Acciones, seleccione **Aprovisionar equipos**.</span><span class="sxs-lookup"><span data-stu-id="35542-119">On the Action Pane, select **Provision teams**.</span></span> <span data-ttu-id="35542-120">Un trabajo por lotes que se denomina **Provisión de equipos** es creado.</span><span class="sxs-lookup"><span data-stu-id="35542-120">A batch job that is named **Teams provision** is created.</span></span>
1. <span data-ttu-id="35542-121">Vaya a **Administración del sistema \> Consultas \> Trabajos por lotes** y busque el trabajo más reciente que tenga la descripción **Provisión de equipos**.</span><span class="sxs-lookup"><span data-stu-id="35542-121">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="35542-122">Espere hasta que este trabajo termine de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="35542-122">Wait until this job has finished running.</span></span>

> [!TIP]
> <span data-ttu-id="35542-123">Si ninguno de sus gerentes regionales, gerentes de tienda y trabajadores de la tienda se ha asociado con una licencia de Teams, es posible que reciba el siguiente mensaje de error: "No se pudieron recuperar las categorías de Sku aplicables para el usuario".</span><span class="sxs-lookup"><span data-stu-id="35542-123">If none of your regional managers, store managers, and store workers have been associated with a Teams license, you might receive the following error message: "Failed to retrieve appliable Sku categories for the user."</span></span> <span data-ttu-id="35542-124">Para corregir el problema, seleccione **Sincronizar equipos y miembros** en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="35542-124">To correct the issue, select **Sync teams and members** on the Action Pane.</span></span>

<!-- ![Dynamics 365 Commerce - Teams integration configuration](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)-->

## <a name="validate-teams-provisioning-in-the-teams-admin-center"></a><span data-ttu-id="35542-125">Valide el aprovisionamiento de Teams en el centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="35542-125">Validate Teams provisioning in the Teams admin center</span></span>

<span data-ttu-id="35542-126">Para validar el aprovisionamiento de Microsoft Teams en el centro de administración de Microsoft Teams, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="35542-126">To validate Microsoft Teams provisioning in the Microsoft Teams admin center, follow these steps.</span></span>
    
1. <span data-ttu-id="35542-127">Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com/) e inicie sesión como administrador de su inquilino de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="35542-127">Go to the [Teams admin center](https://admin.teams.microsoft.com/), and sign in as the administrator of your e-commerce tenant.</span></span>
1. <span data-ttu-id="35542-128">En el panel de navegación izquierdo, seleccione **Teams** para expandirlo y luego seleccione **Administrar equipos**.</span><span class="sxs-lookup"><span data-stu-id="35542-128">In the left navigation pane, select **Teams** to expand it, and then select **Manage teams**.</span></span>
1. <span data-ttu-id="35542-129">Confirme que se haya creado un equipo para cada tienda minorista Commerce.</span><span class="sxs-lookup"><span data-stu-id="35542-129">Confirm that one team has been created for each Commerce retail store.</span></span>
1. <span data-ttu-id="35542-130">Seleccione un equipo y confirme que los trabajadores de la tienda se hayan agregado como miembros.</span><span class="sxs-lookup"><span data-stu-id="35542-130">Select a team, and confirm that store workers have been added to it as members.</span></span>
1. <span data-ttu-id="35542-131">En el panel de navegación izquierdo, seleccione **Usuarios** y confirme que todos los empleados de la tienda en todas las tiendas se hayan agregado como usuarios.</span><span class="sxs-lookup"><span data-stu-id="35542-131">In the left navigation pane, select **Users**, and confirm that all store employees in all stores have been added as users.</span></span>

<span data-ttu-id="35542-132">La siguiente ilustración muestra un ejemplo de la página **Administrar equipos** en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="35542-132">The following illustration shows an example of the **Manage teams** page in the Teams admin center.</span></span>

![Ejemplo de la página Administrar equipos en el centro de administración de Teams](media/Teams-FLW-Admin-Teams.png)

## <a name="upload-a-commerce-organizational-hierarchy-to-teams"></a><span data-ttu-id="35542-134">Suba una jerarquía organizativa de Commerce a Teams</span><span class="sxs-lookup"><span data-stu-id="35542-134">Upload a Commerce organizational hierarchy to Teams</span></span>
    
<span data-ttu-id="35542-135">La jerarquía organizativa de Commerce se puede utilizar en Microsoft Teams para publicar tareas en todas las tiendas o en tiendas seleccionadas que utilizan la misma estructura jerárquica.</span><span class="sxs-lookup"><span data-stu-id="35542-135">The Commerce organizational hierarchy can be used in Microsoft Teams to publish tasks to all or selected stores that use the same hierarchy structure.</span></span>

<span data-ttu-id="35542-136">Para subir un jerarquía organizativa de Commerce a Teams, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="35542-136">To upload a Commerce organizational hierarchy to Teams, follow these steps.</span></span>
    
1. <span data-ttu-id="35542-137">En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Configuración de integración de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="35542-137">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="35542-138">Seleccione **Descargar la jerarquía de destino** y luego seleccione **Tiendas minoristas por región** para descargar un archivo de valores separados por comas (CSV) de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="35542-138">Select **Download targeting hierarchy**, and then select **Retail Stores by Region** to download a comma-separated values (CSV) file of the organizational hierarchy.</span></span>
1. <span data-ttu-id="35542-139">Instale el módulo Microsoft Teams PowerShell siguiendo los pasos en [Instalar Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="35542-139">Install the Microsoft Teams PowerShell module by following the steps in [Install Microsoft Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
1. <span data-ttu-id="35542-140">Cuando se le solicite en la ventana de Teams PowerShell, inicie sesión con la cuenta de administrador para su inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="35542-140">When you're prompted in the Teams PowerShell window, sign in by using the administrator account for your Azure AD tenant.</span></span>
1. <span data-ttu-id="35542-141">Siga los pasos en [Configurar la jerarquía de orientación de su equipo](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) para cargar el archivo CSV para la jerarquía de orientación.</span><span class="sxs-lookup"><span data-stu-id="35542-141">Follow the steps in [Set up your team targeting hierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy) to upload the CSV file for the targeting hierarchy.</span></span>

## <a name="verify-that-the-organizational-hierarchy-was-uploaded-to-teams"></a><span data-ttu-id="35542-142">Verifique que la jerarquía organizativa se cargó en Teams</span><span class="sxs-lookup"><span data-stu-id="35542-142">Verify that the organizational hierarchy was uploaded to Teams</span></span>

<span data-ttu-id="35542-143">Para verificar que la jerarquía organizativa se cargó en Microsoft Teams, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="35542-143">To verify that the organizational hierarchy was uploaded to Microsoft Teams, follow these steps.</span></span>

1. <span data-ttu-id="35542-144">Inicie sesión en el Teams como director de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="35542-144">Sign in to Teams as a communications manager.</span></span>
1. <span data-ttu-id="35542-145">En el panel de navegación izquierdo, seleccione **Tareas por planificador**.</span><span class="sxs-lookup"><span data-stu-id="35542-145">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="35542-146">En la pestaña **Listas publicadas**, cree una nueva lista que tenga una tarea ficticia.</span><span class="sxs-lookup"><span data-stu-id="35542-146">On the **Published lists** tab, create a new list that has a dummy task.</span></span>
1. <span data-ttu-id="35542-147">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="35542-147">Select **Publish**.</span></span> <span data-ttu-id="35542-148">La jerarquía organizativa debe aparecer en el cuadro de diálogo **Seleccione a quién publicar**, como se muestra en el ejemplo de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="35542-148">The organizational hierarchy should appear in the **Select who to publish to** dialog box, as shown in the example in the following illustration.</span></span>

![Ejemplo de una jerarquía organizativa en el cuadro de diálogo Seleccionar a quién publicar](media/Microsoft-teams-verify-org-hierarchy.png)

## <a name="additional-resources"></a><span data-ttu-id="35542-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="35542-150">Additional resources</span></span>

[<span data-ttu-id="35542-151">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35542-151">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="35542-152">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35542-152">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="35542-153">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="35542-153">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="35542-154">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35542-154">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="35542-155">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35542-155">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="35542-156">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35542-156">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
