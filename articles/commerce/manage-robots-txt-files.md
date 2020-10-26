---
title: Administrar archivos robots.txt
description: En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1f7a779d69bf49d3416de3e92d4414cfabf358eb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983632"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="2d444-103">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="2d444-103">Manage robots.txt files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2d444-104">En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d444-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2d444-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2d444-105">Overview</span></span>

<span data-ttu-id="2d444-106">El estándar de exclusión de robots, o robots.txt, es un estándar que los sitios web utilizan para comunicarse con los robots web.</span><span class="sxs-lookup"><span data-stu-id="2d444-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="2d444-107">Da instrucciones a los robots web sobre las áreas de un sitio web que no se deben visitar.</span><span class="sxs-lookup"><span data-stu-id="2d444-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="2d444-108">Los motores de búsqueda suelen utilizar robots para indexar sitios web.</span><span class="sxs-lookup"><span data-stu-id="2d444-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="2d444-109">Para excluir el acceso de los robots a un servidor se crea un archivo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2d444-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="2d444-110">En este archivo se especifica una directiva de acceso para robots.</span><span class="sxs-lookup"><span data-stu-id="2d444-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="2d444-111">El archivo debe ser accesible a través de HTTP en la URL local **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2d444-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="2d444-112">El archivo robots.txt ayuda a los motores de búsqueda a indexar el contenido de su sitio.</span><span class="sxs-lookup"><span data-stu-id="2d444-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="2d444-113">Dynamics 365 Commerce le permite cargar un archivo robots.txt para su dominio.</span><span class="sxs-lookup"><span data-stu-id="2d444-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="2d444-114">En cada dominio en su entorno de Commerce puede cargar un archivo robots.txt y asociárselo a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="2d444-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="2d444-115">Para obtener más información sobre el archivo robots.txt, visite [Las páginas de robots web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="2d444-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="2d444-116">Cargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="2d444-116">Upload a robots.txt file</span></span>

<span data-ttu-id="2d444-117">Después de haber creado y editado su archivo robots.txt de acuerdo con el [estándar de exclusión de robots](https://www.robotstxt.org/orig.html), asegúrese de que el archivo sea accesible en el equipo en el que va a utilizar las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d444-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="2d444-118">El archivo debe llamarse **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2d444-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="2d444-119">Para obtener los mejores resultados debe tener en el formato que se indica en el estándar.</span><span class="sxs-lookup"><span data-stu-id="2d444-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="2d444-120">Cada cliente de Commerce es responsable de validar y mantener el contenido de su archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2d444-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="2d444-121">Para cargar un archivo robots.txt debe iniciar sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d444-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="2d444-122">Para cargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2d444-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2d444-123">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d444-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2d444-124">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="2d444-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2d444-125">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2d444-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2d444-126">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2d444-127">Seleccione **Administrar** para cargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2d444-128">En el menú de la derecha, seleccione el botón **Cargar** (la flecha que apunta hacia arriba) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2d444-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2d444-129">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d444-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="2d444-130">En el cuadro de diálogo, busque y seleccione el archivo robots.txt que desea cargar para el dominio asociado y, a continuación, seleccione **Abrir** para completar la carga.</span><span class="sxs-lookup"><span data-stu-id="2d444-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="2d444-131">Durante la carga, Commerce comprueba que el archivo sea un archivo de texto, pero no valida el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="2d444-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="2d444-132">Descargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="2d444-132">Download a robots.txt file</span></span>

<span data-ttu-id="2d444-133">Para descargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2d444-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2d444-134">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d444-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2d444-135">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="2d444-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2d444-136">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2d444-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2d444-137">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2d444-138">Seleccione **Administrar** para descargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2d444-139">En el menú de la derecha, seleccione el botón **Descargar** (la flecha que apunta hacia abajo) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2d444-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2d444-140">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d444-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="2d444-141">En el cuadro de diálogo, vaya a la ubicación deseada en su unidad local, confirme o escriba un nombre de archivo y, a continuación, seleccione **Guardar** para completar la descarga.</span><span class="sxs-lookup"><span data-stu-id="2d444-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="2d444-142">Este procedimiento se puede utilizar para descargar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d444-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="2d444-143">Eliminar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="2d444-143">Delete a robots.txt file</span></span>

<span data-ttu-id="2d444-144">Para eliminar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2d444-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2d444-145">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d444-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="2d444-146">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="2d444-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="2d444-147">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="2d444-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="2d444-148">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="2d444-149">Seleccione **Administrar** para eliminar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="2d444-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="2d444-150">En el menú de la derecha, seleccione el botón **Eliminar** (el símbolo de la papelera) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2d444-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="2d444-151">Aparece una ventana del Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="2d444-151">A file browser window appears.</span></span>
6. <span data-ttu-id="2d444-152">En la ventana del explorador de archivos, busque y seleccione el archivo robots.txt que desea eliminar para el dominio y, a continuación, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2d444-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="2d444-153">Aparece un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="2d444-153">A warning message box appears.</span></span>
7. <span data-ttu-id="2d444-154">En el cuadro de mensaje, seleccione **Eliminar** para confirmar la eliminación del archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="2d444-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="2d444-155">Este procedimiento se puede utilizar para eliminar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d444-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d444-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2d444-156">Additional resources</span></span>

[<span data-ttu-id="2d444-157">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="2d444-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="2d444-158">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="2d444-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="2d444-159">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="2d444-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="2d444-160">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="2d444-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="2d444-161">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="2d444-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="2d444-162">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="2d444-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="2d444-163">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="2d444-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="2d444-164">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="2d444-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="2d444-165">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="2d444-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="2d444-166">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="2d444-166">Enable location-based store detection</span></span>](enable-store-detection.md)
