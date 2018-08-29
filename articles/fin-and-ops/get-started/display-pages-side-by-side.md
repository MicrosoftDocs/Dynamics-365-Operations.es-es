---
title: "Mostrar páginas en paralelo mediante la característica Abrir en una ventana nueva"
description: "Este artículo explica cómo mostrar páginas en paralelo en Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 8e3ef29618f11b0f247999e3a24e54bff44bf51a
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="show-pages-side-by-side-by-using-the-open-in-new-window-feature"></a><span data-ttu-id="3f1ae-103">Mostrar páginas en paralelo mediante la característica Abrir en una ventana nueva</span><span class="sxs-lookup"><span data-stu-id="3f1ae-103">Show pages side by side by using the Open in new window feature</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f1ae-104">Este artículo explica cómo mostrar páginas en paralelo en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-104">This article explains how to display pages side-by-side in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="3f1ae-105">Microsoft Dynamics 365 for Finance and Operations le ayuda a realizar las tareas de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-105">Microsoft Dynamics 365 for Finance and Operations helps you perform tasks efficiently.</span></span> <span data-ttu-id="3f1ae-106">En algunos casos, puede que desee ver varias páginas en paralelo para completar las tareas con rapidez.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-106">In some cases, you may want to view multiple pages side-by-side to complete tasks quickly.</span></span> <span data-ttu-id="3f1ae-107">Como ejemplo, puede que desee validar o especificar líneas en más de un diario.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-107">As an example, you might want to validate or enter lines in more than one journal.</span></span> <span data-ttu-id="3f1ae-108">Normalmente, para ello tendría que avanzar y retroceder entre la página que muestra una lista de diarios y la página que muestra líneas para un diario dado.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-108">Typically, to do this you would have to go back and forth between the page that displays a list of journals, and the page that displays lines for a given journal.</span></span> <span data-ttu-id="3f1ae-109">Sin embargo, la característica **Abrir en una ventana nueva** le permite mostrar estas páginas en paralelo para que pueda llevar a cabo sus tareas con rapidez.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-109">However, the **Open in new window** feature enables you to display these pages side-by-side so that you can perform your tasks quickly.</span></span> 

<span data-ttu-id="3f1ae-110">Siguiendo con el ejemplo mencionado anteriormente, al ver las líneas, puede hacer clic en el icono **Abrir en ventana nueva**.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-110">Continuing with the example mentioned above, when viewing the lines, you can click the **Open in new window** icon.</span></span> 

<span data-ttu-id="3f1ae-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span><span class="sxs-lookup"><span data-stu-id="3f1ae-111">[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)</span></span> 

<span data-ttu-id="3f1ae-112">Al hacer clic en el icono de **Abrir en una ventana nueva** se abre la página de líneas en un nuevo explorador emergente y, a continuación, navega por el explorador original en el historial hasta la página que mostraba la lista de diarios.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-112">Clicking the **Open in new window** icon opens the lines page in a new, pop-up browser, and then navigates the original browser back in history to the page that displayed the list of journals.</span></span> <span data-ttu-id="3f1ae-113">Se podrán mostrar ambas páginas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-113">You can then display both pages side-by-side.</span></span> <span data-ttu-id="3f1ae-114">Cuando termine de ver un diario, puede cambiar el diario seleccionado en la página de lista de diarios y la página de líneas en la ventana emergente mostrará automáticamente las líneas del diario recién seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-114">When you are done viewing a journal, you can change the selected journal on the journal list page, and the lines page in the pop-up window will automatically display the lines of the newly selected journal.</span></span> 

<span data-ttu-id="3f1ae-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span><span class="sxs-lookup"><span data-stu-id="3f1ae-115">[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)</span></span> 

<span data-ttu-id="3f1ae-116">La actualización y la vinculación dinámica se produce debido a las relaciones que hay entre los datos que apoyan estas páginas.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-116">The dynamic linking and refreshing happens due to the relations that exist between the data that is backing these pages.</span></span> <span data-ttu-id="3f1ae-117">Si el sistema no reconoce la relación entre los datos, la ventana emergente no se actualizará automáticamente en respuesta a un cambio en la ventana de la que se originó.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-117">If the system is not aware of the relation between the data, the pop-up window will not refresh automatically in response to a change in the window it originated from.</span></span> 

<span data-ttu-id="3f1ae-118">Algunas páginas tienen varias vistas, como la vista de cuadrícula, la vista de encabezado y la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-118">Some pages have multiple views such as the Grid view, Header view, and Details view.</span></span> <span data-ttu-id="3f1ae-119">El icono **Abrir en ventana nueva** hace que la página completa se abra en la nueva ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-119">The **Open in new window** icon causes the entire page to be opened in the new browser window.</span></span> <span data-ttu-id="3f1ae-120">Por lo tanto, no puede mantener dos vistas de la misma página en paralelo con la característica **Abrir en ventana nueva**.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-120">Therefore, you cannot keep two views of the same page side-by-side using the **Open in new window** feature.</span></span> <span data-ttu-id="3f1ae-121">Sin embargo, casi todas esas páginas tienen una lista de navegación que puede usar para pasar de un registro a otro y lograr una experiencia similar.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-121">However, almost all such pages have a navigation list that you can use to switch between records and achieve a similar experience.</span></span> 

<span data-ttu-id="3f1ae-122">Antes de usar la característica **Abrir en una ventana nueva**, debe configurar el bloqueador de elementos emergentes del explorador para permitir mensajes emergentes desde la dirección URL del sitio de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-122">Before using the **Open in new window** feature, you should configure your browser's pop-up blocker to allow pop-ups from the URL of the Finance and Operations site.</span></span> <span data-ttu-id="3f1ae-123">Como ejemplo, podría permitir mensajes emergentes de "\*.dynamics.com".</span><span class="sxs-lookup"><span data-stu-id="3f1ae-123">As an example, you could allow pop-ups from "\*.dynamics.com".</span></span> 

<span data-ttu-id="3f1ae-124">La característica **Abrir en ventana nueva** solo está disponible cuando hay más de una página abierta en la ventana.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-124">The **Open in new window** feature is only available when there is more than one page open in the window.</span></span> <span data-ttu-id="3f1ae-125">Además, la ventana emergente se cierra automáticamente cuando no hay más páginas abiertas (es decir, cuando se cierra la última página de esa ventana).</span><span class="sxs-lookup"><span data-stu-id="3f1ae-125">Also, the pop-up window automatically closes when there are no more pages open (that is, when the last page in that window is closed).</span></span> <span data-ttu-id="3f1ae-126">Finance and Operations también cierra las páginas abiertas cuando navega a otra área de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-126">Finance and Operations also closes open pages when you navigate to a different area in the application.</span></span> <span data-ttu-id="3f1ae-127">Por lo tanto, si tiene ventanas emergentes abiertas y navega a otra área de la aplicación, las ventanas emergentes se cierran automáticamente porque el sistema cerró las páginas de esas ventanas.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-127">Therefore, if you have pop-up windows open and navigate to a different area in the application, the pop-up windows are automatically closed because the pages in those windows were closed by the system.</span></span> 

<span data-ttu-id="3f1ae-128">La barra superior de las ventanas emergentes muestra información acerca de la empresa en la que se abrió la página y es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-128">The top bar in the pop-up windows displays information about the company the page was opened in and is read-only.</span></span> <span data-ttu-id="3f1ae-129">Las ventanas emergentes también dependen de la ventana del explorador principal de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-129">The pop-up windows also rely on the main Finance and Operations browser window.</span></span> <span data-ttu-id="3f1ae-130">Si se cierra o se actualiza la ventana principal, todas las ventanas emergentes serán de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-130">If the main window is closed or refreshed, all open pop-up windows will become read only.</span></span> <span data-ttu-id="3f1ae-131">Esto significa que podrá seguir viendo la información en estas ventanas, pero no podrá interactuar con ella.</span><span class="sxs-lookup"><span data-stu-id="3f1ae-131">This means that you can still view the information in these windows, but you will not be able to interact with it.</span></span>




