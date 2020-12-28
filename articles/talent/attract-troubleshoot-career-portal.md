---
title: Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales
description: En este tema se explica cómo solucionar un problema en el que los usuarios de Attract no pueden solicitar trabajos desde el portal de proyectos profesionales.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462437"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="47e9f-103">Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales</span><span class="sxs-lookup"><span data-stu-id="47e9f-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="47e9f-104">Emitir</span><span class="sxs-lookup"><span data-stu-id="47e9f-104">Issue</span></span>

<span data-ttu-id="47e9f-105">Los usuarios de Attract no pueden solicitar puestos de trabajo desde el portal de proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="47e9f-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="47e9f-106">Cuando intentan solicitar un trabajo creado en Dynamics 365 Talent: Attract, el navegador carga la página continuamente y no completa la acción.</span><span class="sxs-lookup"><span data-stu-id="47e9f-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="47e9f-107">Causa</span><span class="sxs-lookup"><span data-stu-id="47e9f-107">Cause</span></span>

<span data-ttu-id="47e9f-108">Este problema se produce cuando el equipo de relación con talentos no tiene el rol de usuario Talento.</span><span class="sxs-lookup"><span data-stu-id="47e9f-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="47e9f-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="47e9f-109">Resolution</span></span>

<span data-ttu-id="47e9f-110">Asigne el rol de usuario Talento al equipo de relaciones con talentos.</span><span class="sxs-lookup"><span data-stu-id="47e9f-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="47e9f-111">Inicie sesión en el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com) con cualquiera de las siguientes credenciales de administrador:</span><span class="sxs-lookup"><span data-stu-id="47e9f-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="47e9f-112">Administrador de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="47e9f-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="47e9f-113">Administrador global</span><span class="sxs-lookup"><span data-stu-id="47e9f-113">Global admin</span></span>
   - <span data-ttu-id="47e9f-114">Administrador de Power Platform</span><span class="sxs-lookup"><span data-stu-id="47e9f-114">Power Platform admin</span></span>

2. <span data-ttu-id="47e9f-115">En el panel de navegación, seleccione **Entornos** y, a continuación, el entorno en el que asignará el rol de usuario Talento al equipo de relaciones con talentos.</span><span class="sxs-lookup"><span data-stu-id="47e9f-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Seleccionar entorno](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="47e9f-117">En el panel **Entornos**, seleccione la **URL del entorno** e inicie sesión en el portal de administración del entorno (por ejemplo, https:<orgname>.crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="47e9f-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="47e9f-118">Seleccione **Configuración**, **Sistema** y, a continuación, **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="47e9f-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Navegue hasta Seguridad](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="47e9f-120">Seleccione **Equipos**.</span><span class="sxs-lookup"><span data-stu-id="47e9f-120">Select **Teams**.</span></span>

   ![Seleccione Equipos.](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="47e9f-122">Busque **Equipo de relaciones con talentos** en el cuadro de búsqueda y luego seleccione el equipo entre los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="47e9f-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="47e9f-123">Seleccione **ADMINISTRAR ROLES** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="47e9f-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="47e9f-124">En el cuadro de diálogo **Administrar roles de equipo**, seleccione **Usuario de Talent** en la lista de roles disponibles y, a continuación, **Aceptar** para aplicar el rol.</span><span class="sxs-lookup"><span data-stu-id="47e9f-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Aplicar rol](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="47e9f-126">Pruebe sus cambios:</span><span class="sxs-lookup"><span data-stu-id="47e9f-126">Test your changes:</span></span>

   1. <span data-ttu-id="47e9f-127">Inicie sesión en el portal de portal de proyectos profesionales desde una nueva ventana de navegador.</span><span class="sxs-lookup"><span data-stu-id="47e9f-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="47e9f-128">Solicite el trabajo en el portal de proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="47e9f-128">Apply for the job from the career portal.</span></span> 