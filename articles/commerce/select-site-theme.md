---
title: Seleccionar un tema de sitio
description: Este tema describe cómo establecer o cambiar el tema del sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c54a3e9471fdeb56f27fe7c567c7cd7f0b7fd218
ms.sourcegitcommit: 2ef23dcd4e42362186b9951e675010d97d55c6bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4556438"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="20c04-103">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="20c04-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="20c04-104">Este tema describe cómo establecer o cambiar el tema del sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="20c04-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="20c04-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="20c04-105">Overview</span></span>

<span data-ttu-id="20c04-106">El diseño y el estilo de un sitio (por ejemplo, fuentes, tamaños y colores) se definen por el tema que seleccione y aplica al sitio.</span><span class="sxs-lookup"><span data-stu-id="20c04-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="20c04-107">Un tema se creado y se implementa por un desarrollador de su empresa.</span><span class="sxs-lookup"><span data-stu-id="20c04-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="20c04-108">Para obtener una descripción general de los temas, consulte [Visión general de creación de temas](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="20c04-108">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="20c04-109">Para obtener más información acerca de cómo crear e implementar temas, consulte [Crear un tema nuevo](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="20c04-109">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="20c04-110">De forma predeterminada, al crear un sitio por primera vez, utiliza un tema con el nombre **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="20c04-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="20c04-111">Este tema predeterminado se proporciona como parte de la biblioteca de módulos de Commerce.</span><span class="sxs-lookup"><span data-stu-id="20c04-111">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="20c04-112">Una vez haya implementado temas adicionales para su sitio, puede configurar el sitio de modo que use uno de ellos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="20c04-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="20c04-113">Seleccionar el tema de sitio</span><span class="sxs-lookup"><span data-stu-id="20c04-113">Select the site theme</span></span>

<span data-ttu-id="20c04-114">Para seleccionar el tema que se aplica al sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="20c04-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="20c04-115">En el entorno de creación de sitios, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="20c04-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="20c04-116">Vaya a **Administración del sitio** \> **Extensibilidad**.</span><span class="sxs-lookup"><span data-stu-id="20c04-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="20c04-117">En **Tema**, seleccione un tema en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="20c04-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="20c04-118">Para aplicar el tema seleccionado al sitio, seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="20c04-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="20c04-119">El tema que seleccione se publica en el sitio en cuanto seleccione **Guardar y publicar** en la página **Extensibilidad**.</span><span class="sxs-lookup"><span data-stu-id="20c04-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="20c04-120">Para obtener una vista previa de un tema de su sitio antes de aplicarlo, puede usar su entorno de espacio aislado o desarrollo.</span><span class="sxs-lookup"><span data-stu-id="20c04-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="20c04-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="20c04-121">Additional resources</span></span>

[<span data-ttu-id="20c04-122">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="20c04-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="20c04-123">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="20c04-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="20c04-124">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="20c04-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="20c04-125">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="20c04-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="20c04-126">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="20c04-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="20c04-127">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="20c04-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="20c04-128">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="20c04-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="20c04-129">Visión general de creación de temas</span><span class="sxs-lookup"><span data-stu-id="20c04-129">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="20c04-130">Crear un tema nuevo</span><span class="sxs-lookup"><span data-stu-id="20c04-130">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)

