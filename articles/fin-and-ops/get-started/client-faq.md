---
title: Preguntas frecuentes para clientes de Finance and Operations
description: "Este artículo proporciona respuestas a preguntas frecuentes acerca del cliente de Microsoft Dynamics 365 for Finance and Operations."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 55d4fa4629d203aa888fe6400126a872d2eee000
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="finance-and-operations-client-faq"></a><span data-ttu-id="0f26c-103">Preguntas frecuentes para clientes de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0f26c-103">Finance and Operations client FAQ</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0f26c-104">Este artículo proporciona respuestas a preguntas frecuentes acerca del cliente de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f26c-104">This article provides answers to frequently asked questions about the Microsoft Dynamics 365 for Finance and Operations client.</span></span>

<a name="why-arent-symbols-loaded-when-i-use-finance-and-operations"></a><span data-ttu-id="0f26c-105">¿Por qué no se cargan los símbolos cuando uso Dynamics 365 for Finance and Operations?</span><span class="sxs-lookup"><span data-stu-id="0f26c-105">Why aren't symbols loaded when I use Finance and Operations?</span></span>
-----------------------------------------------------------------

<span data-ttu-id="0f26c-106">Las opciones de seguridad del explorador pueden impedir que los símbolos se carguen correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f26c-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="0f26c-107">Para resolver este problema, pruebe los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0f26c-107">To resolve this issue, try the following steps:</span></span>

-   <span data-ttu-id="0f26c-108">Si tiene este problema en Internet Explorer, haga clic en **Herramientas** y después haga clic en **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="0f26c-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  <span data-ttu-id="0f26c-109">En el cuadro de diálogo Opciones de Internet, en la pestaña **Privacidad**, haga clic en **Nivel personalizado** y asegúrese de que la opción **Descarga de fuentes** está activada.</span><span class="sxs-lookup"><span data-stu-id="0f26c-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
-   <span data-ttu-id="0f26c-110">De lo contrario, puede que tenga que agregar el sitio de Finance and Operations a la lista de sitios de confianza.</span><span class="sxs-lookup"><span data-stu-id="0f26c-110">Otherwise, you might have to add the Finance and Operations site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="0f26c-111">No veo la cinta de opciones de Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="0f26c-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="0f26c-112">¿Puedo mantener las pestañas del Panel de acciones abiertas todo el tiempo?</span><span class="sxs-lookup"><span data-stu-id="0f26c-112">Can I keep Action Pane tabs open all the time?</span></span>
<span data-ttu-id="0f26c-113">Estamos planeando implementar esta característica pronto.</span><span class="sxs-lookup"><span data-stu-id="0f26c-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="0f26c-114">Los usuarios podrán elegir entonces mantener las pestañas de los paneles de acciones abiertas todo el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0f26c-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="0f26c-115">De lo contrario, las pestañas se contraerán cuando no se usen, para lograr más espacio en la pantalla para la página.</span><span class="sxs-lookup"><span data-stu-id="0f26c-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a><span data-ttu-id="0f26c-116">¿Por qué a veces veo diferentes menús contextuales cuando hago clic con el botón secundario?</span><span class="sxs-lookup"><span data-stu-id="0f26c-116">Why do I sometimes see different shortcut menus when I rightclick?</span></span>
<span data-ttu-id="0f26c-117">Si hace clic con el botón secundario en un campo editable (o si se selecciona texto), se mostrará el menú contextual del explorador.</span><span class="sxs-lookup"><span data-stu-id="0f26c-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="0f26c-118">Este menú le concede acceso a los comandos **Cortar**, **Copiar** y **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="0f26c-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="0f26c-119">No podemos integrar estos comandos en los menús contextuales de Finance and Operations porque, por motivos de seguridad, los exploradores no nos permiten obtener acceso mediante programación al portapapeles del sistema.</span><span class="sxs-lookup"><span data-stu-id="0f26c-119">We can't embed these commands into the Finance and Operations shortcut menus because, for security reasons, browsers don’t allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="0f26c-120">Si hace clic con el botón secundario en una etiqueta de campo o el valor de un control de solo lectura, verá el menú contextual de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f26c-120">If you right-click a field label or the value of a read-only control, you'll see the Finance and Operations shortcut menu.</span></span>

<span data-ttu-id="0f26c-121">Para facilitar el acceso al teclado, planeamos implementar un método abreviado de teclado en el futuro que abra el menú contextual de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f26c-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the Finance and Operations shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality-in-finance-and-operations"></a><span data-ttu-id="0f26c-122">¿Dónde se encuentra la funcionalidad Ver detalles en Finance and Operations?</span><span class="sxs-lookup"><span data-stu-id="0f26c-122">Where is the View details functionality in Finance and Operations?</span></span>
<span data-ttu-id="0f26c-123">La opción **Ver detalles** solo está disponible de dos formas diferentes:</span><span class="sxs-lookup"><span data-stu-id="0f26c-123">The **View details** option is available in a couple of ways:</span></span>

-   <span data-ttu-id="0f26c-124">Si un control tiene capacidades **Ver detalles**, y si el control tiene un valor, ese valor se muestra como hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="0f26c-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="0f26c-125">Puede hacer clic en el hipervínculo para abrir una página que contiene detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="0f26c-125">You can click the hyperlink to open a page that contains additional details.</span></span>
-   <span data-ttu-id="0f26c-126">**Ver detalles** también es una opción en los menús contextuales de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0f26c-126">**View details** is also an option on Finance and Operations shortcut menus.</span></span> <span data-ttu-id="0f26c-127">Para obtener más información acerca de cuándo se muestran los menús contextuales de Finance and Operations al hacer clic con el botón secundario, consulte la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="0f26c-127">For more information about when Finance and Operations shortcut menus are displayed when you right-click, see the previous section.</span></span>





