---
title: Administrar archivos robots.txt
description: En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: e472f3612bd6860e7262bb128035f2aed3b39372
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946076"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="42bc3-103">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="42bc3-103">Manage robots.txt files</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="42bc3-104">En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42bc3-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="42bc3-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="42bc3-105">Overview</span></span>

<span data-ttu-id="42bc3-106">El estándar de exclusión de robots, o robots.txt, es un estándar que los sitios web utilizan para comunicarse con los robots web.</span><span class="sxs-lookup"><span data-stu-id="42bc3-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="42bc3-107">Da instrucciones a los robots web sobre las áreas de un sitio web que no se deben visitar.</span><span class="sxs-lookup"><span data-stu-id="42bc3-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="42bc3-108">Los motores de búsqueda suelen utilizar robots para indexar sitios web.</span><span class="sxs-lookup"><span data-stu-id="42bc3-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="42bc3-109">Para excluir el acceso de los robots a un servidor se crea un archivo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="42bc3-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="42bc3-110">En este archivo se especifica una directiva de acceso para robots.</span><span class="sxs-lookup"><span data-stu-id="42bc3-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="42bc3-111">El archivo debe ser accesible a través de HTTP en la URL local **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="42bc3-112">El archivo robots.txt ayuda a los motores de búsqueda a indexar el contenido de su sitio.</span><span class="sxs-lookup"><span data-stu-id="42bc3-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="42bc3-113">Dynamics 365 Commerce le permite cargar un archivo robots.txt para su dominio.</span><span class="sxs-lookup"><span data-stu-id="42bc3-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="42bc3-114">En cada dominio en su entorno de Commerce puede cargar un archivo robots.txt y asociárselo a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="42bc3-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="42bc3-115">Para obtener más información sobre el archivo robots.txt, visite [Las páginas de robots web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="42bc3-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="42bc3-116">Cargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="42bc3-116">Upload a robots.txt file</span></span>

<span data-ttu-id="42bc3-117">Después de haber creado y editado su archivo robots.txt de acuerdo con el [estándar de exclusión de robots](https://www.robotstxt.org/orig.html), asegúrese de que el archivo sea accesible en el equipo en el que va a utilizar las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="42bc3-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="42bc3-118">El archivo debe llamarse **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="42bc3-119">Para obtener los mejores resultados debe tener en el formato que se indica en el estándar.</span><span class="sxs-lookup"><span data-stu-id="42bc3-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="42bc3-120">Cada cliente de Commerce es responsable de validar y mantener el contenido de su archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="42bc3-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="42bc3-121">Para cargar un archivo robots.txt debe iniciar sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="42bc3-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="42bc3-122">Para cargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="42bc3-123">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="42bc3-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="42bc3-124">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="42bc3-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="42bc3-125">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="42bc3-126">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="42bc3-127">Seleccione **Administrar** para cargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="42bc3-128">En el menú de la derecha, seleccione el botón **Cargar** (la flecha que apunta hacia arriba) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="42bc3-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="42bc3-129">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="42bc3-130">En el cuadro de diálogo, busque y seleccione el archivo robots.txt que desea cargar para el dominio asociado y, a continuación, seleccione **Abrir** para completar la carga.</span><span class="sxs-lookup"><span data-stu-id="42bc3-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="42bc3-131">Durante la carga, Commerce comprueba que el archivo sea un archivo de texto, pero no valida el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="42bc3-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="42bc3-132">Descargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="42bc3-132">Download a robots.txt file</span></span>

<span data-ttu-id="42bc3-133">Para descargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="42bc3-134">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="42bc3-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="42bc3-135">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="42bc3-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="42bc3-136">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="42bc3-137">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="42bc3-138">Seleccione **Administrar** para descargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="42bc3-139">En el menú de la derecha, seleccione el botón **Descargar** (la flecha que apunta hacia abajo) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="42bc3-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="42bc3-140">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="42bc3-141">En el cuadro de diálogo, vaya a la ubicación deseada en su unidad local, confirme o escriba un nombre de archivo y, a continuación, seleccione **Guardar** para completar la descarga.</span><span class="sxs-lookup"><span data-stu-id="42bc3-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="42bc3-142">Este procedimiento se puede utilizar para descargar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="42bc3-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="42bc3-143">Eliminar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="42bc3-143">Delete a robots.txt file</span></span>

<span data-ttu-id="42bc3-144">Para eliminar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="42bc3-145">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="42bc3-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="42bc3-146">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="42bc3-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="42bc3-147">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="42bc3-148">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="42bc3-149">Seleccione **Administrar** para eliminar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="42bc3-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="42bc3-150">En el menú de la derecha, seleccione el botón **Eliminar** (el símbolo de la papelera) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="42bc3-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="42bc3-151">Aparece una ventana del Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="42bc3-151">A file browser window appears.</span></span>
6. <span data-ttu-id="42bc3-152">En la ventana del explorador de archivos, busque y seleccione el archivo robots.txt que desea eliminar para el dominio y, a continuación, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="42bc3-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="42bc3-153">Aparece un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="42bc3-153">A warning message box appears.</span></span>
7. <span data-ttu-id="42bc3-154">En el cuadro de mensaje, seleccione **Eliminar** para confirmar la eliminación del archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="42bc3-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="42bc3-155">Este procedimiento se puede utilizar para eliminar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="42bc3-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42bc3-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42bc3-156">Additional resources</span></span>

[<span data-ttu-id="42bc3-157">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="42bc3-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="42bc3-158">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42bc3-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="42bc3-159">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42bc3-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="42bc3-160">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="42bc3-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="42bc3-161">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="42bc3-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="42bc3-162">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="42bc3-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="42bc3-163">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="42bc3-163">Enable location-based store detection</span></span>](enable-store-detection.md)
