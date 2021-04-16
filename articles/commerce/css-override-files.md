---
title: Trabajar con archivos de anulación de CSS
description: Este tema describe por qué, cuándo y cómo usar las hojas de estilo en cascada (CSS) para archivos de anulación en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ef96070fe77b46622667301c7c7c402909ee7dfc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799502"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="143dc-103">Trabajar con archivos de anulaciones CSS</span><span class="sxs-lookup"><span data-stu-id="143dc-103">Work with CSS override files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="143dc-104">Este tema describe por qué, cuándo y cómo usar las hojas de estilo en cascada (CSS) para archivos de anulación en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="143dc-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="143dc-105">Los estilos de sitio permanentes generalmente se deben manejar a través del tema de un sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-105">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="143dc-106">Los temas proporcionan lo fundamental para CSS y las configuraciones de estilo para los módulos en cualquier página de su sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-106">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="143dc-107">Los temas se crean utilizando el kit de desarrollo de software en línea (SDK) de Dynamics 365 Commerce, y se implementan en sus sitios web a través de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="143dc-107">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="143dc-108">Las capacidades de depuración de temas y las configuraciones de la interfaz del módulo en el SDK ayudan a los desarrolladores del sitio a crear paquetes de diseño del sitio personalizables y coherentes.</span><span class="sxs-lookup"><span data-stu-id="143dc-108">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="143dc-109">Cuando estos paquetes de diseño se implementan en un sitio, los autores del sitio pueden centrarse en crear, editar y publicar contenido en lugar de desarrollar el sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-109">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="143dc-110">Dado el ciclo de vida habitual de un tema, la dependencia de los desarrolladores para realizar cambios de estilo a través de la canalización de implementación de SDK y LCS puede ser prohibitiva en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="143dc-110">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="143dc-111">Los prototipos o las revisiones del sitio pueden parecer engorrosos si el SDK no está configurado o si no tiene tiempo para esperar una implementación de LCS.</span><span class="sxs-lookup"><span data-stu-id="143dc-111">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="143dc-112">En estos escenarios, los archivos de anulación de CSS pueden ayudar.</span><span class="sxs-lookup"><span data-stu-id="143dc-112">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="143dc-113">En las herramientas de autoría de Commerce, los usuarios autenticados pueden cargar un archivo CSS, ver una vista previa y luego activarlo para anular el tema de un sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-113">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="143dc-114">No se requiere la sobrecarga de la implementación de SDK o LCS.</span><span class="sxs-lookup"><span data-stu-id="143dc-114">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="143dc-115">Las anulaciones que se especifican en un archivo de anulación de CSS pueden ser tan pequeñas como un cambio en un estilo de texto único o tan amplio como una revisión completa de la marca.</span><span class="sxs-lookup"><span data-stu-id="143dc-115">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="143dc-116">Antes de usar los archivos de anulación de CSS, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="143dc-116">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="143dc-117">Solo un archivo de anulación de CSS puede estar activo en un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="143dc-117">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="143dc-118">Por lo tanto, todas las anulaciones activas deben estar presentes en un único archivo de anulación.</span><span class="sxs-lookup"><span data-stu-id="143dc-118">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="143dc-119">Aunque puede obtener una vista previa de las anulaciones en las herramientas de autoría de Commerce, no hay características de depuración dedicadas para ayudar a identificar los errores que introducen las anulaciones.</span><span class="sxs-lookup"><span data-stu-id="143dc-119">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="143dc-120">En otras palabras, cuando usa archivos de anulación de CSS, no tiene el mismo conjunto de herramientas que el SDK proporciona para la validación de módulos y autoría.</span><span class="sxs-lookup"><span data-stu-id="143dc-120">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="143dc-121">Sin embargo, los archivos de anulación de CSS proporcionan una forma rápida de crear un prototipo de un diseño o implementar una revisión antes de desarrollar e implementar una actualización completa del tema.</span><span class="sxs-lookup"><span data-stu-id="143dc-121">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="143dc-122">Crear un archivo de anulación de CSS</span><span class="sxs-lookup"><span data-stu-id="143dc-122">Create a CSS override file</span></span>

<span data-ttu-id="143dc-123">Para crear un archivo de anulación de CSS, puede usar cualquier entorno de desarrollo integrado (IDE), editor de texto o editor de código fuente.</span><span class="sxs-lookup"><span data-stu-id="143dc-123">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="143dc-124">Un enfoque típico es utilizar depuradores web estándar en su navegador para identificar selectores de estilo, propiedades y valores en su sitio existente.</span><span class="sxs-lookup"><span data-stu-id="143dc-124">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="143dc-125">La mayoría de los navegadores le permiten cambiar valores y obtener una vista previa en el depurador.</span><span class="sxs-lookup"><span data-stu-id="143dc-125">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="143dc-126">Después de identificar los cambios que desea realizar, puede guardarlos en su archivo CSS.</span><span class="sxs-lookup"><span data-stu-id="143dc-126">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="143dc-127">Cargar un archivo de anulación de CSS</span><span class="sxs-lookup"><span data-stu-id="143dc-127">Upload a CSS override file</span></span>

<span data-ttu-id="143dc-128">Para subir un archivo de CSS a su sitio en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="143dc-128">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="143dc-129">En las herramientas de creación, vaya al sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-129">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="143dc-130">En el panel de navegación de la izquierda, seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="143dc-130">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="143dc-131">Dependiendo de la versión de las herramientas de creación de Commerce que esté utilizando, es posible que deba expandir **Configuraciones** en el panel de navegación antes de que pueda seleccionar **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="143dc-131">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="143dc-132">En la parte superior del panel de diseño principal, seleccione la pestaña **anular CSS**, si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="143dc-132">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="143dc-133">En **Anulaciones CSS disponibles**, seleccione **Cargar archivo CSS**.</span><span class="sxs-lookup"><span data-stu-id="143dc-133">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="143dc-134">Aparecerá una ventana del Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="143dc-134">A File Explorer window appears.</span></span>
1. <span data-ttu-id="143dc-135">En el Explorador de archivos, busque y seleccione un archivo CSS y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="143dc-135">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="143dc-136">El archivo subido CSS ahora aparece debajo de **Anulaciones CSS disponibles**.</span><span class="sxs-lookup"><span data-stu-id="143dc-136">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="143dc-137">Vista previa de un archivo de anulación de CSS</span><span class="sxs-lookup"><span data-stu-id="143dc-137">Preview a CSS override file</span></span>

<span data-ttu-id="143dc-138">Para obtener una vista previa de un archivo de anulación de CSS antes de activarlo en su sitio activo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="143dc-138">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="143dc-139">En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS del que desea obtener una vista previa.</span><span class="sxs-lookup"><span data-stu-id="143dc-139">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="143dc-140">Al lado del nombre del archivo CSS, seleccione **Vista previa del sitio**.</span><span class="sxs-lookup"><span data-stu-id="143dc-140">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="143dc-141">En el cuadro de diálogo **Seleccione una URL**, seleccione la URL del sitio en el que desea ver la anulación aplicada y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="143dc-141">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="143dc-142">Si hay varias variantes para la URL seleccionada, seleccione la variante deseada en el cuadro de diálogo **Vista previa de variaciones** que aparece.</span><span class="sxs-lookup"><span data-stu-id="143dc-142">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="143dc-143">Se abre una nueva pestaña o ventana del navegador, donde puede validar sus anulaciones de estilo en su sitio.</span><span class="sxs-lookup"><span data-stu-id="143dc-143">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="143dc-144">Luego puede compartir la URL con otros usuarios de Commerce autenticados para su revisión y comentarios.</span><span class="sxs-lookup"><span data-stu-id="143dc-144">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="143dc-145">Activar un archivo de anulación de CSS en su sitio en activo</span><span class="sxs-lookup"><span data-stu-id="143dc-145">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="143dc-146">Después de haber visto y aprobado el archivo de anulación de CSS, puede activarlo en su sitio en activo.</span><span class="sxs-lookup"><span data-stu-id="143dc-146">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="143dc-147">Solo un archivo de anulación de CSS puede estar activo en su sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="143dc-147">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="143dc-148">Si activa un nuevo archivo de anulación, el archivo de anulación anterior se desactiva.</span><span class="sxs-lookup"><span data-stu-id="143dc-148">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="143dc-149">Por lo tanto, asegúrese de que todas las anulaciones requeridas estén presentes en una solo archivo de anulación de CSS.</span><span class="sxs-lookup"><span data-stu-id="143dc-149">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="143dc-150">Para activar un archivo de anulación de CSS, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="143dc-150">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="143dc-151">En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS que desea activar.</span><span class="sxs-lookup"><span data-stu-id="143dc-151">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="143dc-152">En el nombre del archivo CSS, seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="143dc-152">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="143dc-153">El archivo de anulación se activa inmediatamente en su sitio activo.</span><span class="sxs-lookup"><span data-stu-id="143dc-153">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="143dc-154">Desactivar un archivo de anulación de CSS en su sitio en activo</span><span class="sxs-lookup"><span data-stu-id="143dc-154">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="143dc-155">Para desactivar un archivo de anulación de CSS en su sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="143dc-155">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="143dc-156">En el panel de navegación a la izquierda, seleccione **Diseño**, y luego, en la pestaña **Anulación CSS**, en **Anulaciones CSS disponibles**, encuentre el archivo CSS que desea desactivar.</span><span class="sxs-lookup"><span data-stu-id="143dc-156">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="143dc-157">En el nombre del archivo CSS, seleccione **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="143dc-157">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="143dc-158">El archivo de anulación se desactiva inmediatamente en su sitio activo.</span><span class="sxs-lookup"><span data-stu-id="143dc-158">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="143dc-159">Para acceder a opciones adicionales para los archivos de anulación de CSS, seleccione los puntos suspensivos (**...**) al lado del nombre del archivo CSS.</span><span class="sxs-lookup"><span data-stu-id="143dc-159">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="143dc-160">Las opciones **Descargar**, **Renombrar** y **Reemplazar** son útiles para realizar cambios rápidos en un archivo de anulación de CSS.</span><span class="sxs-lookup"><span data-stu-id="143dc-160">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="143dc-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="143dc-161">Additional resources</span></span>

[<span data-ttu-id="143dc-162">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="143dc-162">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="143dc-163">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="143dc-163">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="143dc-164">Trabajar con preajustes de estilo</span><span class="sxs-lookup"><span data-stu-id="143dc-164">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="143dc-165">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="143dc-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="143dc-166">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="143dc-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="143dc-167">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="143dc-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="143dc-168">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="143dc-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="143dc-169">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="143dc-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
