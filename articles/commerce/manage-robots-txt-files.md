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
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: afd7982179dc9845c9adc24e8c7c9951a04460a3
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477717"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="a5208-103">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="a5208-103">Manage robots.txt files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5208-104">En este tema se describe cómo administrar los archivos robots.txt en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5208-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a5208-105">El estándar de exclusión de robots, o robots.txt, es un estándar que los sitios web utilizan para comunicarse con los robots web.</span><span class="sxs-lookup"><span data-stu-id="a5208-105">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="a5208-106">Da instrucciones a los robots web sobre las áreas de un sitio web que no se deben visitar.</span><span class="sxs-lookup"><span data-stu-id="a5208-106">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="a5208-107">Los motores de búsqueda suelen utilizar robots para indexar sitios web.</span><span class="sxs-lookup"><span data-stu-id="a5208-107">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="a5208-108">Para excluir el acceso de los robots a un servidor se crea un archivo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a5208-108">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="a5208-109">En este archivo se especifica una directiva de acceso para robots.</span><span class="sxs-lookup"><span data-stu-id="a5208-109">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="a5208-110">El archivo debe ser accesible a través de HTTP en la URL local **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="a5208-110">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="a5208-111">El archivo robots.txt ayuda a los motores de búsqueda a indexar el contenido de su sitio.</span><span class="sxs-lookup"><span data-stu-id="a5208-111">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="a5208-112">Dynamics 365 Commerce le permite cargar un archivo robots.txt para su dominio.</span><span class="sxs-lookup"><span data-stu-id="a5208-112">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="a5208-113">En cada dominio en su entorno de Commerce puede cargar un archivo robots.txt y asociárselo a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="a5208-113">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="a5208-114">Para obtener más información sobre el archivo robots.txt, visite [Las páginas de robots web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="a5208-114">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="a5208-115">Cargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="a5208-115">Upload a robots.txt file</span></span>

<span data-ttu-id="a5208-116">Después de haber creado y editado su archivo robots.txt de acuerdo con el [estándar de exclusión de robots](https://www.robotstxt.org/orig.html), asegúrese de que el archivo sea accesible en el equipo en el que va a utilizar las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5208-116">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="a5208-117">El archivo debe llamarse **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="a5208-117">The file must be named **robots.txt**.</span></span> <span data-ttu-id="a5208-118">Para obtener los mejores resultados debe tener en el formato que se indica en el estándar.</span><span class="sxs-lookup"><span data-stu-id="a5208-118">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="a5208-119">Cada cliente de Commerce es responsable de validar y mantener el contenido de su archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="a5208-119">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="a5208-120">Para cargar un archivo robots.txt debe iniciar sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="a5208-120">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="a5208-121">Para cargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a5208-121">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a5208-122">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="a5208-122">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="a5208-123">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="a5208-123">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="a5208-124">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="a5208-124">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="a5208-125">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-125">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="a5208-126">Seleccione **Administrar** para cargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-126">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="a5208-127">En el menú de la derecha, seleccione el botón **Cargar** (la flecha que apunta hacia arriba) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="a5208-127">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="a5208-128">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5208-128">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="a5208-129">En el cuadro de diálogo, busque y seleccione el archivo robots.txt que desea cargar para el dominio asociado y, a continuación, seleccione **Abrir** para completar la carga.</span><span class="sxs-lookup"><span data-stu-id="a5208-129">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="a5208-130">Durante la carga, Commerce comprueba que el archivo sea un archivo de texto, pero no valida el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="a5208-130">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="a5208-131">Descargar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="a5208-131">Download a robots.txt file</span></span>

<span data-ttu-id="a5208-132">Para descargar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a5208-132">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a5208-133">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="a5208-133">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="a5208-134">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="a5208-134">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="a5208-135">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="a5208-135">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="a5208-136">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-136">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="a5208-137">Seleccione **Administrar** para descargar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-137">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="a5208-138">En el menú de la derecha, seleccione el botón **Descargar** (la flecha que apunta hacia abajo) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="a5208-138">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="a5208-139">Se abre un cuadro de diálogo de explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5208-139">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="a5208-140">En el cuadro de diálogo, vaya a la ubicación deseada en su unidad local, confirme o escriba un nombre de archivo y, a continuación, seleccione **Guardar** para completar la descarga.</span><span class="sxs-lookup"><span data-stu-id="a5208-140">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="a5208-141">Este procedimiento se puede utilizar para descargar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5208-141">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="a5208-142">Eliminar un archivo robots.txt</span><span class="sxs-lookup"><span data-stu-id="a5208-142">Delete a robots.txt file</span></span>

<span data-ttu-id="a5208-143">Para eliminar un archivo robots.txt en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a5208-143">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a5208-144">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="a5208-144">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="a5208-145">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="a5208-145">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="a5208-146">En **Configuración del suscriptor**, seleccione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="a5208-146">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="a5208-147">En la parte principal de la ventana aparece una lista de todos los dominios asociados a su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-147">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="a5208-148">Seleccione **Administrar** para eliminar un archivo robots.txt en un dominio de su entorno.</span><span class="sxs-lookup"><span data-stu-id="a5208-148">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="a5208-149">En el menú de la derecha, seleccione el botón **Eliminar** (el símbolo de la papelera) situado junto al dominio asociado con el archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="a5208-149">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="a5208-150">Aparece una ventana del Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="a5208-150">A file browser window appears.</span></span>
6. <span data-ttu-id="a5208-151">En la ventana del explorador de archivos, busque y seleccione el archivo robots.txt que desea eliminar para el dominio y, a continuación, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a5208-151">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="a5208-152">Aparece un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="a5208-152">A warning message box appears.</span></span>
7. <span data-ttu-id="a5208-153">En el cuadro de mensaje, seleccione **Eliminar** para confirmar la eliminación del archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="a5208-153">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="a5208-154">Este procedimiento se puede utilizar para eliminar solo archivos robots.txt que se cargaron previamente a través de las herramientas de creación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5208-154">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5208-155">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a5208-155">Additional resources</span></span>

[<span data-ttu-id="a5208-156">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="a5208-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="a5208-157">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="a5208-157">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="a5208-158">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="a5208-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="a5208-159">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="a5208-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="a5208-160">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="a5208-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="a5208-161">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="a5208-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="a5208-162">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="a5208-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="a5208-163">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="a5208-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="a5208-164">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="a5208-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="a5208-165">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="a5208-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
