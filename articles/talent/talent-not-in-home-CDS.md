---
title: Talent no se ve entre las aplicaciones de Microsoft Dynamics 365 (CDS1.0)
description: "Este tema explica qué hacer si el cliente no ve la aplicación Microsoft Dynamics 365 for Talent entre las aplicaciones de Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a><span data-ttu-id="07769-103">Talent no se ve entre las aplicaciones de Microsoft Dynamics 365 (CDS1.0)</span><span class="sxs-lookup"><span data-stu-id="07769-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (CDS1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="07769-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="07769-104">**Issue**</span></span>

<span data-ttu-id="07769-105">El cliente no ve la aplicación Microsoft Dynamics 365 for Talent entre las aplicaciones de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="07769-105">The customer doesn't see the Microsoft Dynamics 365 for Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="07769-106">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="07769-106">**Resolution**</span></span>

<span data-ttu-id="07769-107">Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="07769-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="07769-108">El usuario de gestión que dispone de una licencia de PowerApps Plan 2 debe abrir [Portal de gestión de PowerApps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="07769-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="07769-109">Seleccione **Entornos**, y seleccione el entorno correcto para Talent.</span><span class="sxs-lookup"><span data-stu-id="07769-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="07769-110">En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="07769-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Ficha Roles de entorno](media/environment-roles.png)

4. <span data-ttu-id="07769-112">En la pestaña **Usuarios** , agregue el usuario o su organización.</span><span class="sxs-lookup"><span data-stu-id="07769-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Pestaña usuarios](media/environment-maker.png)

5. <span data-ttu-id="07769-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="07769-114">Select **Save**.</span></span>
6. <span data-ttu-id="07769-115">Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="07769-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="07769-116">Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="07769-116">Select **Sync** to update the user apps.</span></span>

    ![Botón de sincronización](media/get-more.png)

    <span data-ttu-id="07769-118">Una vez que esté completada la sincronización, Talent aparecerá en la página principal.</span><span class="sxs-lookup"><span data-stu-id="07769-118">After synchronization is completed, Talent will appear on the home page.</span></span>

