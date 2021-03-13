---
title: Recursos humanos no aparece en aplicaciones de Microsoft Dynamics 365
description: Este artículo explica lo que hacer si el cliente no ve la aplicación Dynamics 365 Human Resources de Microsoft entre las aplicaciones de Microsoft Dynamics 365.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d78199cf0e76ffd0676a26961a8e646938dc7333
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114193"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="dc09c-103">Recursos humanos no aparece en aplicaciones de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dc09c-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="dc09c-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="dc09c-104">**Issue**</span></span>

<span data-ttu-id="dc09c-105">El cliente no ve Dynamics 365 Human Resources entre las aplicaciones de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="dc09c-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="dc09c-106">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="dc09c-106">**Resolution**</span></span>

<span data-ttu-id="dc09c-107">Se debe agregar el usuario al rol del fabricante del entorno para el entorno de Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dc09c-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="dc09c-108">El usuario de gestión que dispone de una licencia de Power Apps Plan 2 debe abrir [Portal de gestión de Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="dc09c-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="dc09c-109">Seleccione **Entornos**, seleccione el entorno correcto para Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="dc09c-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="dc09c-110">En la pestaña **Seguridad** , en la pestaña **Roles de entorno** , seleccione **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Ficha Roles de entorno](media/environment-roles.png)

4. <span data-ttu-id="dc09c-112">En la pestaña **Usuarios** , agregue el usuario o su organización.</span><span class="sxs-lookup"><span data-stu-id="dc09c-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Pestaña usuarios](media/environment-maker.png)

5. <span data-ttu-id="dc09c-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dc09c-114">Select **Save**.</span></span>

6. <span data-ttu-id="dc09c-115">Ahora el usuario debe iniciar sesión en [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="dc09c-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="dc09c-116">Seleccione **Sincronizar** para actualizar las aplicaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc09c-116">Select **Sync** to update the user apps.</span></span>

    ![Botón de sincronización](media/get-more.png)

    <span data-ttu-id="dc09c-118">Después de terminar la sincronización, los Recursos humanos aparecerán en la página principal.</span><span class="sxs-lookup"><span data-stu-id="dc09c-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
