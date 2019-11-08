---
title: Integrar aplicaciones de PowerApps en Dynamics 365 - Core HR
description: Este tema explica cómo resolver el problema en el que el elemento de menú de PowerApps ha desaparecido del módulo Gestión del sistema.
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
ms.openlocfilehash: b510c10ebfcf4939eb2e1297972d27aa1812ae5a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551012"
---
# <a name="embed-powerapps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="ba15e-103">Integrar aplicaciones de PowerApps en Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="ba15e-103">Embed PowerApps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ba15e-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="ba15e-104">**Issue**</span></span>

<span data-ttu-id="ba15e-105">El elemento de menú **PowerApps** ha desaparecido del módulo **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="ba15e-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="ba15e-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="ba15e-106">**Cause**</span></span>

<span data-ttu-id="ba15e-107">Se ha cambiado el diseño (IU) de la interfaz de usuario, y Microsoft PowerApps ahora se incluye en el modelo estándar de personalización.</span><span class="sxs-lookup"><span data-stu-id="ba15e-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="ba15e-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="ba15e-108">**Resolution**</span></span>

<span data-ttu-id="ba15e-109">Se ha cambiado el modo en que las aplicaciones de PowerApps se insertan.</span><span class="sxs-lookup"><span data-stu-id="ba15e-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="ba15e-110">Las aplicaciones de PowerApps ahora se agregan a través del modelo de personalización.</span><span class="sxs-lookup"><span data-stu-id="ba15e-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="ba15e-111">Puede agregar las aplicaciones de PowerApps a casi todas las páginas de Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="ba15e-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="ba15e-112">Para obtener información detallada acerca de cómo insertar aplicaciones de PowerApps en Talent, consulte [Integrar aplicaciones de PowerApps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="ba15e-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="ba15e-113">Cualquier cliente de PowerApps que incrustara aplicaciones antes del cambio se debe haber actualizado al modelo nuevo.</span><span class="sxs-lookup"><span data-stu-id="ba15e-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="ba15e-114">El botón **PowerApps** se encuentra en la esquina superior derecha de casi cada página de Talent.</span><span class="sxs-lookup"><span data-stu-id="ba15e-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="ba15e-115">Puede usar este botón para insertar una aplicación de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="ba15e-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="ba15e-116">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ba15e-116">Here is an example.</span></span>

1. <span data-ttu-id="ba15e-117">Vaya a **Administración de personal \> Vínculos \> Trabajadores \> Empleados**.</span><span class="sxs-lookup"><span data-stu-id="ba15e-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="ba15e-118">Seleccione el botón **PowerApps** y, a continuación, seleccione **Insertar una PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="ba15e-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Botón PowerApps](media/png.png)

3. <span data-ttu-id="ba15e-120">Complete los campos en el cuadro de diálogo **Insertar un PowerApp** .</span><span class="sxs-lookup"><span data-stu-id="ba15e-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Insertar un cuadro de diálogo de PowerApp](media/insert-powerapp.png)

<span data-ttu-id="ba15e-122">O bien debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ba15e-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="ba15e-123">En el panel de acciones de la página, en la pestaña **Opciones**, en el grupo **Personalizar**, seleccione **Personalizar este formulario**.</span><span class="sxs-lookup"><span data-stu-id="ba15e-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizar el grupo en la ficha de las opciones](media/options.png)

    <span data-ttu-id="ba15e-125">La barra de herramientas de personalización aparece.</span><span class="sxs-lookup"><span data-stu-id="ba15e-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="ba15e-126">En la barra de herramientas, seleccione **Insertar \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="ba15e-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserte una aplicación de PowerApps mediante la barra de herramientas de personalización](media/powerapp-bar.png)
