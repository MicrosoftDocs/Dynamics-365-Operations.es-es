---
title: Insertar aplicaciones de Power Apps en Dynamics 365 Human Resources
description: Este tema explica cómo resolver el problema en el que el elemento de menú de Microsoft Power Apps ha desaparecido del módulo Gestión del sistema.
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
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462430"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="a1b96-103">Insertar aplicaciones de Power Apps en Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="a1b96-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="a1b96-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="a1b96-104">**Issue**</span></span>

<span data-ttu-id="a1b96-105">El elemento de menú **Power Apps** ha desaparecido del módulo **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="a1b96-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a1b96-106">**Cause**</span></span>

<span data-ttu-id="a1b96-107">Se ha cambiado el diseño (IU) de la interfaz de usuario, y Microsoft Power Apps ahora se incluye en el modelo estándar de personalización.</span><span class="sxs-lookup"><span data-stu-id="a1b96-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="a1b96-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a1b96-108">**Resolution**</span></span>

<span data-ttu-id="a1b96-109">Se ha cambiado el modo en que las Power Apps se insertan.</span><span class="sxs-lookup"><span data-stu-id="a1b96-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="a1b96-110">Ahora las Power Apps se agregan a través del modelo de personalización.</span><span class="sxs-lookup"><span data-stu-id="a1b96-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="a1b96-111">Puede agregar Power Apps a casi todas las páginas de Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="a1b96-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="a1b96-112">Para obtener información detallada acerca de cómo insertar Power Apps en Talent, consulte [Integrar Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="a1b96-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="a1b96-113">Cualquier cliente de Power Apps que incrustara aplicaciones antes del cambio se debe haber actualizado al modelo nuevo.</span><span class="sxs-lookup"><span data-stu-id="a1b96-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="a1b96-114">El botón **Power Apps** se encuentra en la esquina superior derecha de casi cada página de Talent.</span><span class="sxs-lookup"><span data-stu-id="a1b96-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="a1b96-115">Puede usar este botón para insertar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a1b96-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="a1b96-116">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1b96-116">Here is an example.</span></span>

1. <span data-ttu-id="a1b96-117">Vaya a **Administración de personal \> Vínculos \> Trabajadores \> Empleados**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="a1b96-118">Seleccione el botón **Power Apps** y luego seleccione **Agregar una aplicación desde Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Botón Power Apps](media/png.png)

3. <span data-ttu-id="a1b96-120">Complete los campos del cuadro de diálogo **Agregar una aplicación desde Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Cuadro de diálogo Agregar una aplicación desde Power Apps](media/insert-powerapp.png)

<span data-ttu-id="a1b96-122">O bien debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a1b96-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="a1b96-123">En el panel de acciones de la página, en la pestaña **Opciones**, en el grupo **Personalizar**, seleccione **Personalizar esta página**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Personalizar el grupo en la ficha de las opciones](media/options.png)

    <span data-ttu-id="a1b96-125">La barra de herramientas de personalización aparece.</span><span class="sxs-lookup"><span data-stu-id="a1b96-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="a1b96-126">En la barra de herramientas, seleccione **Agregar una aplicación desde Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="a1b96-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Agregar una aplicación desde Power Apps mediante la barra de herramientas de personalización](media/powerapp-bar.png)
