---
title: Talent no figura entre las aplicaciones de Microsoft Dynamics 365 (Common Data Service 1.0)
description: Este tema explica qué hacer si el cliente no ve la aplicación Microsoft Dynamics 365 Talent entre las aplicaciones de Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7f0cc1c7ec1234b7eedaade0ffadb66965ed2121
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772997"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a><span data-ttu-id="38d3a-103">Talent no figura entre las aplicaciones de Microsoft Dynamics 365 (Common Data Service 1.0)</span><span class="sxs-lookup"><span data-stu-id="38d3a-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (Common Data Service 1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="38d3a-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="38d3a-104">**Issue**</span></span>

<span data-ttu-id="38d3a-105">El cliente no consulta la aplicación Microsoft Dynamics 365 Talent entre las aplicaciones de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="38d3a-105">The customer doesn't see the Microsoft Dynamics 365 Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="38d3a-106">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="38d3a-106">**Resolution**</span></span>

<span data-ttu-id="38d3a-107">Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="38d3a-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="38d3a-108">El usuario de gestión que dispone de una licencia de Power Apps Plan 2 debe abrir [Portal de gestión de Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="38d3a-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="38d3a-109">Seleccione **Entornos**, y seleccione el entorno correcto para Talent.</span><span class="sxs-lookup"><span data-stu-id="38d3a-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="38d3a-110">En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="38d3a-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Ficha Roles de entorno](media/environment-roles.png)

4. <span data-ttu-id="38d3a-112">En la pestaña **Usuarios** , agregue el usuario o su organización.</span><span class="sxs-lookup"><span data-stu-id="38d3a-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Pestaña usuarios](media/environment-maker.png)

5. <span data-ttu-id="38d3a-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="38d3a-114">Select **Save**.</span></span>
6. <span data-ttu-id="38d3a-115">Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="38d3a-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="38d3a-116">Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="38d3a-116">Select **Sync** to update the user apps.</span></span>

    ![Botón de sincronización](media/get-more.png)

    <span data-ttu-id="38d3a-118">Una vez que esté completada la sincronización, Talent aparecerá en la página principal.</span><span class="sxs-lookup"><span data-stu-id="38d3a-118">After synchronization is completed, Talent will appear on the home page.</span></span>
