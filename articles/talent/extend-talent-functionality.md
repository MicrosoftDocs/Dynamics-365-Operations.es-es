---
title: Extender la funcionalidad de Microsoft Dynamics 365 for Talent
description: "Si ha creado alguna aplicación de Microsoft PowerApps, puede iniciarla desde los vínculos de Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: es-es
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="19afc-103">Extender la funcionalidad de Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="19afc-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="19afc-104">Si ha creado alguna aplicación de Microsoft PowerApps, puede iniciarla desde los vínculos de Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="19afc-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="19afc-105">Para configurar el acceso a sus aplicaciones, deberá configurar información en Talent en una página de configuración que pueda abrir desde el espacio de trabajo **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="19afc-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="19afc-106">Combinación de aplicaciones de PowerApps incrustadas en Talent</span><span class="sxs-lookup"><span data-stu-id="19afc-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="19afc-107">Use la página **Establecer aplicaciones incrustadas de Microsoft PowerApps** para configurar las páginas de Talent para iniciar aplicaciones de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="19afc-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="19afc-108">Para abrir la página **Establecer aplicaciones incrustadas de Microsoft PowerApps**, abra el área trabajo **Administración del sistema** y después abra la ficha **Vínculos**. Seleccione **Microsoft PowerApps** del grupo **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="19afc-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="19afc-109">La siguiente información se introduce o se establece en esta página:</span><span class="sxs-lookup"><span data-stu-id="19afc-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="19afc-110">Un nombre descriptivo o un identificador para cada aplicación de PowerApps.</span><span class="sxs-lookup"><span data-stu-id="19afc-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="19afc-111">Un identificador único (GUID) para cada aplicación que agregue a una página de Talent.</span><span class="sxs-lookup"><span data-stu-id="19afc-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="19afc-112">El identificador de la aplicación disponible en el sitio de PowerApps [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="19afc-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="19afc-113">La página desde la que los usuarios pueden abrir una aplicación o un informe.</span><span class="sxs-lookup"><span data-stu-id="19afc-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="19afc-114">No todas las páginas de Talent admiten aplicaciones de PowerApps ni informes de Power BI incrustados.</span><span class="sxs-lookup"><span data-stu-id="19afc-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="19afc-115">Especifique el nombre interno de la página, en lugar del nombre para mostrar que aparece en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="19afc-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="19afc-116">Para buscar el nombre interno, abra la página cuyo nombre interno necesita y haga clic con el botón secundario en cualquier lugar de la página.</span><span class="sxs-lookup"><span data-stu-id="19afc-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="19afc-117">Cuando el menú se abra, mantenga el mouse sobre el elemento **Información del formulario**.</span><span class="sxs-lookup"><span data-stu-id="19afc-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="19afc-118">El nombre del formulario interno aparece junto al elemento **Información del formulario** del menú.</span><span class="sxs-lookup"><span data-stu-id="19afc-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="19afc-119">Especifique el control de formulario desde el que la aplicación puede recuperar datos de contexto.</span><span class="sxs-lookup"><span data-stu-id="19afc-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="19afc-120">Por ejemplo, una solicitud puede usar los datos de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="19afc-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="19afc-121">Si especifica la página **Trabajador** en el campo **Contexto**, la página **Trabajador** se abrirá al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19afc-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="19afc-122">Una entrada en el **Campo de contexto** es opcional.</span><span class="sxs-lookup"><span data-stu-id="19afc-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="19afc-123">Configure el tamaño del cuadro de diálogo en el que la aplicación de PowerApps se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="19afc-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="19afc-124">Los cuadros de diálogo se designan como “pequeño “o “grande” para optimizar la interfaz de usuario cuando su aplicación se ejecuta en un teléfono o un dispositivo mayor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="19afc-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="19afc-125">También puede especificar para qué entidades jurídicas una aplicación estará disponible, o bien ponerla a disposición todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="19afc-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="19afc-126">De forma predeterminada, sus aplicaciones de PowerApps están disponibles para todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="19afc-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="19afc-127">Abrir una aplicación</span><span class="sxs-lookup"><span data-stu-id="19afc-127">Opening an application</span></span>
<span data-ttu-id="19afc-128">Cuando haya configurado las aplicaciones incrustadas de PowerApps, se agregarán vínculos a las aplicaciones que ha especificado en las páginas de Talent.</span><span class="sxs-lookup"><span data-stu-id="19afc-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="19afc-129">Haga clic en un vínculo para abrir una aplicación.</span><span class="sxs-lookup"><span data-stu-id="19afc-129">Click a link to open an application.</span></span> 



