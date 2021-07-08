---
title: Novedades o cambios en la aplicación móvil Warehouse Management
description: Este tema enumera las funciones nuevas y modificadas para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261798"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="5cd89-103">Novedades o cambios en la aplicación móvil Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="5cd89-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5cd89-104">Este tema enumera las nuevas funciones, las revisiones, las mejoras y los problemas conocidos para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5cd89-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="5cd89-105">Versión 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="5cd89-106">Nuevas funciones, correcciones y mejoras en la versión 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="5cd89-107">Esta versión introduce las características nuevas, correcciones y mejoras siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cd89-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="5cd89-108">El modo de demostración ahora muestra todas las etiquetas en el idioma del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5cd89-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="5cd89-109">Es menos probable que reciba el siguiente mensaje de error: "No se puede encontrar una vista adecuada para el tamaño especificado".</span><span class="sxs-lookup"><span data-stu-id="5cd89-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="5cd89-110">Se ha aumentado la altura mínima para las tarjetas de trabajo (para los casos en los que se configuran tres o menos campos para aparecer en la lista de trabajo).</span><span class="sxs-lookup"><span data-stu-id="5cd89-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="5cd89-111">Se han mejorado los márgenes (se desvanecen) en la parte inferior de las tarjetas de detalles.</span><span class="sxs-lookup"><span data-stu-id="5cd89-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="5cd89-112">Los símbolos no válidos en los archivos XML que se intercambian con el servidor ahora se manejan correctamente.</span><span class="sxs-lookup"><span data-stu-id="5cd89-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="5cd89-113">(Por ejemplo, los caracteres no imprimibles ahora se manejan con elegancia y ya no hacen que la aplicación deje de responder).</span><span class="sxs-lookup"><span data-stu-id="5cd89-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="5cd89-114">Los errores HTTP (como el "error 503") cuando se envía una solicitud del servidor ahora se manejan correctamente.</span><span class="sxs-lookup"><span data-stu-id="5cd89-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="5cd89-115">Mientras se muestra un error, la lista de opciones ya no se muestra automáticamente para los controles del cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="5cd89-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="5cd89-116">La aplicación ya no deja de responder debido a la orientación de la pantalla que se selecciona en la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="5cd89-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="5cd89-117">Las imágenes de productos ahora se muestran en entornos de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="5cd89-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="5cd89-118">(Este cambio se aplica solo a las versiones de baja resolución.</span><span class="sxs-lookup"><span data-stu-id="5cd89-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="5cd89-119">El servicio de administración de archivos no admite imágenes de tamaño completo en entornos de autoservicio).</span><span class="sxs-lookup"><span data-stu-id="5cd89-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="5cd89-120">Se solucionó un problema que involucraba selecciones cortas de cantidad cero.</span><span class="sxs-lookup"><span data-stu-id="5cd89-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="5cd89-121">La aplicación ya no deja de responder cuando una tarjeta de detalles muestra varios campos idénticos.</span><span class="sxs-lookup"><span data-stu-id="5cd89-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="5cd89-122">Problemas conocidos en la versión 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="5cd89-123">Existen los siguientes problemas conocidos en esta versión:</span><span class="sxs-lookup"><span data-stu-id="5cd89-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="5cd89-124">La aplicación (especialmente la lista de trabajo) se vuelve más lenta con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="5cd89-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="5cd89-125">**Versión de Windows:** cuando se utiliza una pistola USB para escanear en Windows, los resultados inconsistentes hacen que los símbolos escaneados se confundan.</span><span class="sxs-lookup"><span data-stu-id="5cd89-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="5cd89-126">Versión 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-126">Version 2.0.5.0</span></span>

<span data-ttu-id="5cd89-127">Esta versión introduce las características nuevas, correcciones y mejoras siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cd89-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="5cd89-128">El secreto del cliente ya no está oculto en la configuración de la conexión.</span><span class="sxs-lookup"><span data-stu-id="5cd89-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="5cd89-129">Ahora puede mantener presionado cualquier texto para verlo por completo.</span><span class="sxs-lookup"><span data-stu-id="5cd89-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="5cd89-130">Se ha mejorado el mensaje de error cuando faltan los permisos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5cd89-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="5cd89-131">Se han agregado nuevas secuencias de control para algunos flujos.</span><span class="sxs-lookup"><span data-stu-id="5cd89-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="5cd89-132">El botón enviar ya no está disponible incorrectamente debido al tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="5cd89-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="5cd89-133">Los controles deslizantes ahora pueden continuar en pantallas más pequeñas cuando se utilizan botones de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="5cd89-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="5cd89-134">La superposición de cuatro botones ya no se corta.</span><span class="sxs-lookup"><span data-stu-id="5cd89-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="5cd89-135">El teclado ahora admite el botón Eliminar.</span><span class="sxs-lookup"><span data-stu-id="5cd89-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="5cd89-136">Se solucionó un problema de brillo que podría ocurrir cuando se presiona el teclado.</span><span class="sxs-lookup"><span data-stu-id="5cd89-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="5cd89-137">Se han solucionado varios problemas con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5cd89-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="5cd89-138">Se solucionó un problema que afectaba a los campos numéricos en la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="5cd89-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="5cd89-139">El teclado de la pantalla ya no desaparece ocasionalmente en algunos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5cd89-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="5cd89-140">Se han corregido varios errores de la interfaz de usuario (UI), como errores que afectaban el color de fondo y la posición.</span><span class="sxs-lookup"><span data-stu-id="5cd89-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="5cd89-141">Se ha mejorado la interfaz de usuario en ruso.</span><span class="sxs-lookup"><span data-stu-id="5cd89-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="5cd89-142">Se han solucionado varios problemas que provocaban que el sistema dejara de responder.</span><span class="sxs-lookup"><span data-stu-id="5cd89-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="5cd89-143">Se solucionó un problema relacionado con la reapertura de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="5cd89-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="5cd89-144">**Versión Android:** Un problema que causó que Android 4.4 dejara de responder al inicio se ha corregido.</span><span class="sxs-lookup"><span data-stu-id="5cd89-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="5cd89-145">**Versión Android:** La escala mínima se ha reducido al 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="5cd89-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="5cd89-146">Versión 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-146">Version 2.0.4.0</span></span>

<span data-ttu-id="5cd89-147">La versión 2.0.4.0 fue la primera versión disponible en general de la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="5cd89-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="5cd89-148">Nuevas funciones, correcciones y mejoras en la versión 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="5cd89-149">Esta versión presenta las siguientes funciones nuevas, correcciones y mejoras que no estaban disponibles en la versión preliminar:</span><span class="sxs-lookup"><span data-stu-id="5cd89-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="5cd89-150">Si una tarjeta de detalles incluye dos etiquetas que tienen datos idénticos, una de las etiquetas está oculta.</span><span class="sxs-lookup"><span data-stu-id="5cd89-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="5cd89-151">Los caracteres especiales ahora se muestran de forma predeterminada y la opción para ocultarlos se ha eliminado de la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="5cd89-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="5cd89-152">Los botones de envío deshabilitados ahora se muestran como no disponibles en la vista compacta sostenida por el brazo.</span><span class="sxs-lookup"><span data-stu-id="5cd89-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="5cd89-153">Un cambio en la lógica de secuenciación de los controles garantiza un escalado más fluido entre los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5cd89-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="5cd89-154">Por lo tanto, hay menos necesidad de ajustar la escala de fuentes o botones.</span><span class="sxs-lookup"><span data-stu-id="5cd89-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="5cd89-155">El tema de color predeterminado se ha cambiado a *Oscuro*.</span><span class="sxs-lookup"><span data-stu-id="5cd89-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="5cd89-156">El icono que falta para el botón de envío deshabilitado se ha agregado en la vista de cinta.</span><span class="sxs-lookup"><span data-stu-id="5cd89-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="5cd89-157">Las excepciones de tiempo de espera ahora lo llevan a la página de conexión en lugar de mostrar un error en línea.</span><span class="sxs-lookup"><span data-stu-id="5cd89-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="5cd89-158">Si no hay ninguna acción de envío disponible (como **OK**, **Sí**, **Aceptar**, **Hecho** o **Terminado**), el botón de enviar se desactivará.</span><span class="sxs-lookup"><span data-stu-id="5cd89-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="5cd89-159">Se ha mejorado la estabilidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cd89-159">App stability has been improved.</span></span>
- <span data-ttu-id="5cd89-160">Hay una solución para la vulnerabilidad de seguridad [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="5cd89-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="5cd89-161">**Versión de Windows:** se ha solucionado un problema en Windows, donde los menús no respondían después de cambiar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="5cd89-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="5cd89-162">Problema conocido en la versión 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="5cd89-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="5cd89-163">Existe el siguiente problema conocido en esta versión:</span><span class="sxs-lookup"><span data-stu-id="5cd89-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="5cd89-164">Esta versión tiene un problema con los dispositivos que usan Android 4.4.</span><span class="sxs-lookup"><span data-stu-id="5cd89-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="5cd89-165">Es posible que experimente problemas al usar la aplicación en esta versión de Android.</span><span class="sxs-lookup"><span data-stu-id="5cd89-165">You might experience issues when you use the app on this Android version.</span></span>
