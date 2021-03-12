---
title: Abrir URL en POS
description: En este tema se proporciona una visión general de las mejoras que se han realizado en la funcionalidad de búsqueda de productos y clientes en Dynamics 365 Commerce.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: e4ccb8e03d63a7bd1ab2d118d86633a8c6324d43
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965461"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="df504-103">Abrir dirección URL en el punto de venta</span><span class="sxs-lookup"><span data-stu-id="df504-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="df504-104">Este tema describe cómo puede configurar un botón en Retail POS (PDV) para abrir una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="df504-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="df504-105">Esta función no requiere una personalización de código, y se puede configurar por una persona con un rol que no es un desarrollador.</span><span class="sxs-lookup"><span data-stu-id="df504-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="df504-106">Esta característica permite la configuración de un botón en PDV, mediante el Diseñador de la cuadrícula de botones para abrir una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="df504-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="df504-107">Actualmente, esto se admite en las siguientes configuraciones:</span><span class="sxs-lookup"><span data-stu-id="df504-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="df504-108">Abrir en ventana nueva.</span><span class="sxs-lookup"><span data-stu-id="df504-108">Open in new window.</span></span>
- <span data-ttu-id="df504-109">Abrir dentro de PDV.</span><span class="sxs-lookup"><span data-stu-id="df504-109">Open within POS.</span></span>
- <span data-ttu-id="df504-110">Abrir una aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="df504-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="df504-111">Abrir en ventana nueva</span><span class="sxs-lookup"><span data-stu-id="df504-111">Open in new window</span></span>

<span data-ttu-id="df504-112">Esta configuración define si abrir la dirección URL en una ventana nueva o dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df504-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="df504-113">Cuando está configurado para abrir una dirección URL web dentro de la aplicación, el panel lateral de navegación y la barra de PDV superior están visibles y disponibles para la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="df504-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="df504-114">Cuando está configurada para abrirse en una ventana nueva, la dirección URL se abrirá en Modern POS para Windows y en una nueva ficha del explorador en todos los demás clientes de PDV.</span><span class="sxs-lookup"><span data-stu-id="df504-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="df504-115">Para habilitarla, debe configurar la URL con la opción **Abrir en ventana nueva** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="df504-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="df504-116">Abrir dentro de PDV</span><span class="sxs-lookup"><span data-stu-id="df504-116">Open within POS</span></span>

<span data-ttu-id="df504-117">El abrir una dirección URL web dentro de PDV se admite actualmente solo para Modern POS en Windows.</span><span class="sxs-lookup"><span data-stu-id="df504-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="df504-118">En otros clientes, esta capacidad se encuentra en desarrollo y planificada para su lanzamiento en actualizaciones futuras.</span><span class="sxs-lookup"><span data-stu-id="df504-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="df504-119">Para habilitarlo, debe configurar la URL con la opción **Abrir en ventana nueva** sin seleccionar.</span><span class="sxs-lookup"><span data-stu-id="df504-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="df504-120">Abrir una aplicación nativa</span><span class="sxs-lookup"><span data-stu-id="df504-120">Open a native app</span></span>

<span data-ttu-id="df504-121">Esta función también le permite especificar URL que no son de Web para abrir una aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="df504-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="df504-122">Por ejemplo, puede especificar protocolos de URL como Mailto, SIP, IM o MSTEAMS, que se pueden administrar mediante aplicaciones nativas respectivas en el dispositivo del host.</span><span class="sxs-lookup"><span data-stu-id="df504-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="df504-123">Para habilitarla, debe configurar la URL con la opción **Abrir en ventana nueva** seleccionada.</span><span class="sxs-lookup"><span data-stu-id="df504-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="df504-124">Para los equipos de Windows, consulte [Exportar o importar asociaciones de aplicaciones predeterminadas](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) para establecer las asociaciones predeterminadas de protocolos si configura su equipo utilizando la Administración y mantenimiento de imágenes de implementación (DISM).</span><span class="sxs-lookup"><span data-stu-id="df504-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="df504-125">Si utiliza MDM, como Intune para administrar los equipos de Windows, consulte [Directiva CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="df504-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="df504-126">Si es desarrollador de software que crea una página Web personalizada, consulte [Iniciar la aplicación predeterminada para URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="df504-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="df504-127">Abrir una aplicación nativa fácilmente</span><span class="sxs-lookup"><span data-stu-id="df504-127">Open a native app seamlessly</span></span>

<span data-ttu-id="df504-128">Windows, IOS y, Android también permiten abrir aplicaciones más fácilmente, en función de la asociación del protocolo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df504-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="df504-129">Si su aplicación no está ya configurada para gestionar la apertura desde un explorador web, puede necesitar que un programador la configure.</span><span class="sxs-lookup"><span data-stu-id="df504-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="df504-130">Para Windows, consulte [Habilitar aplicaciones de páginas Web mediante controladores de URI de la aplicación](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="df504-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="df504-131">Para IOS, consulte [Vínculos universales para los desarrolladores](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="df504-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="df504-132">Para Android, consulte [Administrar vínculos de la aplicación de Android](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="df504-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="df504-133">Cliente</span><span class="sxs-lookup"><span data-stu-id="df504-133">Client</span></span>                | <span data-ttu-id="df504-134">Abrir en ventana nueva</span><span class="sxs-lookup"><span data-stu-id="df504-134">Open in new window</span></span> | <span data-ttu-id="df504-135">Abrir una aplicación nativa</span><span class="sxs-lookup"><span data-stu-id="df504-135">Open native app</span></span> | <span data-ttu-id="df504-136">Abrir dentro de PDV</span><span class="sxs-lookup"><span data-stu-id="df504-136">Open within POS</span></span> | <span data-ttu-id="df504-137">Detalles</span><span class="sxs-lookup"><span data-stu-id="df504-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="df504-138">Modern POS en Windows</span><span class="sxs-lookup"><span data-stu-id="df504-138">Modern POS on Windows</span></span> | <span data-ttu-id="df504-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="df504-139">✓\*</span></span>                | <span data-ttu-id="df504-140">✓</span><span class="sxs-lookup"><span data-stu-id="df504-140">✓</span></span>               | <span data-ttu-id="df504-141">✓</span><span class="sxs-lookup"><span data-stu-id="df504-141">✓</span></span>              | <span data-ttu-id="df504-142">\* Se abre en una nueva ventana de Modern POS</span><span class="sxs-lookup"><span data-stu-id="df504-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="df504-143">PDV en la nube</span><span class="sxs-lookup"><span data-stu-id="df504-143">Cloud POS</span></span>             | <span data-ttu-id="df504-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="df504-144">✓\*</span></span>                | <span data-ttu-id="df504-145">✓</span><span class="sxs-lookup"><span data-stu-id="df504-145">✓</span></span>               | <span data-ttu-id="df504-146">X</span><span class="sxs-lookup"><span data-stu-id="df504-146">X</span></span>              | <span data-ttu-id="df504-147">\* Se abre en una nueva pestaña del explorador</span><span class="sxs-lookup"><span data-stu-id="df504-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="df504-148">Modern POS en iOS</span><span class="sxs-lookup"><span data-stu-id="df504-148">Modern POS on iOS</span></span>     | <span data-ttu-id="df504-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="df504-149">✓\*</span></span>                | <span data-ttu-id="df504-150">✓</span><span class="sxs-lookup"><span data-stu-id="df504-150">✓</span></span>               | <span data-ttu-id="df504-151">X</span><span class="sxs-lookup"><span data-stu-id="df504-151">X</span></span>              | <span data-ttu-id="df504-152">\* Se abre en una nueva pestaña del explorador</span><span class="sxs-lookup"><span data-stu-id="df504-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="df504-153">Modern POS en Android</span><span class="sxs-lookup"><span data-stu-id="df504-153">Modern POS on Android</span></span> | <span data-ttu-id="df504-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="df504-154">✓\*</span></span>                | <span data-ttu-id="df504-155">✓</span><span class="sxs-lookup"><span data-stu-id="df504-155">✓</span></span>               | <span data-ttu-id="df504-156">X</span><span class="sxs-lookup"><span data-stu-id="df504-156">X</span></span>              | <span data-ttu-id="df504-157">\* Se abre en una nueva pestaña del explorador</span><span class="sxs-lookup"><span data-stu-id="df504-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="df504-158">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="df504-158">Before you begin</span></span>

<span data-ttu-id="df504-159">Antes de empezar, revise cómo configurar [Diseños para Pantalla del punto de venta (PDV)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="df504-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="df504-160">Abrir URL en POS</span><span class="sxs-lookup"><span data-stu-id="df504-160">Open URL in POS</span></span>

<span data-ttu-id="df504-161">Para configurar una dirección URL para ser abierta en PDV, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="df504-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="df504-162">En la oficina central vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Diseños de pantalla**.</span><span class="sxs-lookup"><span data-stu-id="df504-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="df504-163">Seleccione **Cuadrículas de botones \> diseñador**.</span><span class="sxs-lookup"><span data-stu-id="df504-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="df504-164">Cree un botón nuevo.</span><span class="sxs-lookup"><span data-stu-id="df504-164">Create a new button.</span></span>
4. <span data-ttu-id="df504-165">Seleccione las propiedades de **botón**.</span><span class="sxs-lookup"><span data-stu-id="df504-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="df504-166">Seleccione **Abrir URL** como la acción.</span><span class="sxs-lookup"><span data-stu-id="df504-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="df504-167">Especifique la dirección URL que desee usar.</span><span class="sxs-lookup"><span data-stu-id="df504-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="df504-168">Configurar si abrir la dirección URL en una ventana nueva.</span><span class="sxs-lookup"><span data-stu-id="df504-168">Configure whether to open the URL in a new window.</span></span>
