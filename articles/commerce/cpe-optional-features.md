---
title: Configurar características opcionales para un entorno de vista previa de Dynamics 365 Commerce
description: Este tema explica cómo configurar características opcionales para una vista previa del entorno de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 43b23b9ef881b2ab2f3d005d4ba761848a7fa4ed
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024738"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="87a8c-103">Configurar características opcionales para un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-103">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="87a8c-104">Este tema explica cómo configurar características opcionales para una vista previa del entorno de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87a8c-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87a8c-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="87a8c-105">Prerequisites</span></span>

<span data-ttu-id="87a8c-106">Si desea evaluar las características transaccionales de correo electrónico, se deben cumplir los requisitos previos siguientes:</span><span class="sxs-lookup"><span data-stu-id="87a8c-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="87a8c-107">Tiene un servidor de correo electrónico disponible (Protocolo de transferencia de correo simple \[SMTP\]), que se puede usar desde la suscripción de Microsoft Azure donde aprovisiona el entorno de la versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="87a8c-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="87a8c-108">Tiene el nombre completamente cualificado del dominio (FQDN)/dirección IP del servidor, el número de puerto de SMTP y detalles de autenticación disponibles.</span><span class="sxs-lookup"><span data-stu-id="87a8c-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="87a8c-109">Si desea evaluar las características de la Gestión de activos digitales ingiriendo nuevas imágenes omnicanal, debe tener disponible el nombre del inquilino de su sistema de gestión de contenido (CMS).</span><span class="sxs-lookup"><span data-stu-id="87a8c-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="87a8c-110">Las instrucciones para encontrar este nombre se proporcionan más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="87a8c-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="87a8c-111">>>> (P: ¿dónde están las instrucciones?)</span><span class="sxs-lookup"><span data-stu-id="87a8c-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="87a8c-112">Configurar el back-end de la imagen</span><span class="sxs-lookup"><span data-stu-id="87a8c-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="87a8c-113">Encuentre su URL de base de medios</span><span class="sxs-lookup"><span data-stu-id="87a8c-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="87a8c-114">Antes de poder completar este procedimiento, debe completar los pasos en [Configure su sitio en Commerce ](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="87a8c-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="87a8c-115">Inicie sesión en la herramienta de administración del sitio de Commerce utilizando la URL de la que tomó nota cuando inició el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico ](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="87a8c-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="87a8c-116">Abra el sitio de **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="87a8c-117">Elija **Activos** en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="87a8c-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="87a8c-118">Seleccione cualquier activo de imagen único.</span><span class="sxs-lookup"><span data-stu-id="87a8c-118">Select any single image asset.</span></span>
1. <span data-ttu-id="87a8c-119">En el inspector de propiedades a la derecha, busque la propiedad **URL pública**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="87a8c-120">El valor es una URL.</span><span class="sxs-lookup"><span data-stu-id="87a8c-120">The value is a URL.</span></span> <span data-ttu-id="87a8c-121">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="87a8c-121">Here is an example:</span></span>

    <span data-ttu-id="87a8c-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="87a8c-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="87a8c-123">Reemplazar el último identificador en la dirección URL (**MA1nQC** en el ejemplo anterior) por la cadena **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="87a8c-124">Así es como se ve la URL de ejemplo después de realizar este cambio:</span><span class="sxs-lookup"><span data-stu-id="87a8c-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="87a8c-125">Esta URL es la URL de su base de medios.</span><span class="sxs-lookup"><span data-stu-id="87a8c-125">This URL is your media base URL.</span></span> <span data-ttu-id="87a8c-126">Anótela.</span><span class="sxs-lookup"><span data-stu-id="87a8c-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="87a8c-127">Actualizar la URL base multimedia</span><span class="sxs-lookup"><span data-stu-id="87a8c-127">Update the media base URL</span></span>

1. <span data-ttu-id="87a8c-128">Inicie sesión en Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="87a8c-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="87a8c-129">Use el menú de la izquierda, para ir a **Módulos \> Retail \> Configuración de canal \> Perfiles del canal**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="87a8c-130">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-130">Select **Edit**.</span></span>
1. <span data-ttu-id="87a8c-131">En **Propiedades del perfil**, reemplace el valor de propiedad para **Dirección URL base del servidor multimedia** por la URL base de medios que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="87a8c-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="87a8c-132">En la lista de la izquierda, en el canal **Predeterminado** seleccione el otro canal.</span><span class="sxs-lookup"><span data-stu-id="87a8c-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="87a8c-133">En **Propiedades del perfil**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="87a8c-134">Para la propiedad que se agregó, seleccione **URL base del servidor de medios** como la clave de propiedad</span><span class="sxs-lookup"><span data-stu-id="87a8c-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="87a8c-135">Como valor de la propiedad, introduzca la URL de la base de medios que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="87a8c-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="87a8c-136">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="87a8c-137">Configurar el servidor de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87a8c-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="87a8c-138">El servidor SMTP o servicio de correo electrónico que especifica aquí debe ser accesible dentro de la suscripción de Azure que está usando para el entorno.</span><span class="sxs-lookup"><span data-stu-id="87a8c-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="87a8c-139">Inicie sesión en Retail.</span><span class="sxs-lookup"><span data-stu-id="87a8c-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="87a8c-140">Use el menú de la izquierda, para ir a **Módulos \> Administración del sistema \> Configuración \> Correo electrónico \> Parámetros de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="87a8c-141">En la pestaña **Configuraciones SMTP**, en el campo **Servidor de correo saliente**, introduzca el FQDN o la dirección IP de su servidor SMTP o servicio de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87a8c-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="87a8c-142">En el campo **Número de puerto SMTP**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="87a8c-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="87a8c-143">(Si no está utilizando la Capa de sockets seguros \[SSL \], el número de puerto predeterminado es **25**).</span><span class="sxs-lookup"><span data-stu-id="87a8c-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="87a8c-144">Si se requiere autenticación, introduzca valores en los campos **Nombre de usuario** y **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="87a8c-145">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-145">Select **Save**.</span></span>
1. <span data-ttu-id="87a8c-146">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="87a8c-147">En la pestaña **Correo electrónico de prueba**, en el campo **Proveedor de correo electrónico**, seleccione **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="87a8c-148">En el campo **Enviar a**, escriba la dirección de correo electrónico donde desea que se entregue el correo electrónico de prueba.</span><span class="sxs-lookup"><span data-stu-id="87a8c-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="87a8c-149">Seleccione **Enviar correo electrónico de prueba**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="87a8c-150">Configurar plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87a8c-150">Configure email templates</span></span>

<span data-ttu-id="87a8c-151">Para cada evento transaccional para el que desea enviar mensajes de correo electrónico se tiene que actualizar la plantilla de correo electrónico con una dirección de correo electrónico de remitente válida.</span><span class="sxs-lookup"><span data-stu-id="87a8c-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="87a8c-152">Inicie sesión en Retail.</span><span class="sxs-lookup"><span data-stu-id="87a8c-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="87a8c-153">Use el menú de la izquierda, para ir a **Módulos \> Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="87a8c-154">Seleccione **Mostrar lista**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-154">Select **Show list**.</span></span>
1. <span data-ttu-id="87a8c-155">Para cada plantilla en la lista, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="87a8c-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="87a8c-156">A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="87a8c-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="87a8c-157">Opcional: en el campo **Nombre del remitente**, introduzca el nombre que debe usarse como el nombre del remitente.</span><span class="sxs-lookup"><span data-stu-id="87a8c-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="87a8c-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="87a8c-159">Personalizar plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87a8c-159">Customize email templates</span></span>

<span data-ttu-id="87a8c-160">Es posible que desee personalizar las plantillas de correo electrónico para que utilicen imágenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="87a8c-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="87a8c-161">O puede que desee actualizar los enlaces en las plantillas para que vayan a su entorno de vista previa.</span><span class="sxs-lookup"><span data-stu-id="87a8c-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="87a8c-162">Este procedimiento explica cómo descargar plantillas predeterminadas, personalizarlas y actualizar las plantillas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="87a8c-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="87a8c-163">En un explorador web, descargue [el archivo .zip de correo electrónico predeterminado de la versión preliminar de Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="87a8c-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="87a8c-164">Este archivo contiene los siguientes documentos HTML:</span><span class="sxs-lookup"><span data-stu-id="87a8c-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="87a8c-165">Plantilla de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-165">Order confirmation template</span></span>
    - <span data-ttu-id="87a8c-166">Emitir plantilla de tarjeta regalo</span><span class="sxs-lookup"><span data-stu-id="87a8c-166">Issue gift card template</span></span>
    - <span data-ttu-id="87a8c-167">Nueva plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-167">New order template</span></span>
    - <span data-ttu-id="87a8c-168">Empaquetar plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-168">Pack order template</span></span>
    - <span data-ttu-id="87a8c-169">Recoger plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-169">Pick order template</span></span>

1. <span data-ttu-id="87a8c-170">Personalice las plantillas mediante un editor HTML o de texto.</span><span class="sxs-lookup"><span data-stu-id="87a8c-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="87a8c-171">Vea la lista de [tokens compatibles ](#supported-tokens-in-the-email-template) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="87a8c-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="87a8c-172">Inicie sesión en Retail.</span><span class="sxs-lookup"><span data-stu-id="87a8c-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="87a8c-173">Use el menú de la izquierda, para ir a **Módulos \> Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="87a8c-174">Expanda la lista de la izquierda para ver todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="87a8c-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="87a8c-175">Para cada plantilla que desee personalizar, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="87a8c-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="87a8c-176">Seleccione la plantilla en la lista.</span><span class="sxs-lookup"><span data-stu-id="87a8c-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="87a8c-177">En **Contenido del mensaje de correo electrónico**, seleccione la versión de idioma adecuada en la lista.</span><span class="sxs-lookup"><span data-stu-id="87a8c-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="87a8c-178">(El valor de plantilla predeterminado es **en-us**).</span><span class="sxs-lookup"><span data-stu-id="87a8c-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="87a8c-179">En **Contenido del mensaje de correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="87a8c-180">Aparecerá el panel **Subir plantilla de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="87a8c-181">Seleccione **Explorar** y busque el archivo HTML que tiene el contenido personalizado.</span><span class="sxs-lookup"><span data-stu-id="87a8c-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="87a8c-182">Seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-182">Select **Upload**.</span></span> <span data-ttu-id="87a8c-183">La plantilla se carga en el sistema y se muestra una vista previa.</span><span class="sxs-lookup"><span data-stu-id="87a8c-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="87a8c-184">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-184">Select **OK**.</span></span>
    1. <span data-ttu-id="87a8c-185">Opcional: personalizar la propiedad **Asunto** de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="87a8c-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="87a8c-186">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="87a8c-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="87a8c-187">Tokens compatibles en la plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87a8c-187">Supported tokens in the email template</span></span>

<span data-ttu-id="87a8c-188">Estos tokens se reemplazarán en el momento de la representación de correo electrónico con los valores reales que se aplican al cliente y su pedido.</span><span class="sxs-lookup"><span data-stu-id="87a8c-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="87a8c-189">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="87a8c-189">Sales order</span></span>

<span data-ttu-id="87a8c-190">Los siguientes tokens se aplican al pedido de ventas general.</span><span class="sxs-lookup"><span data-stu-id="87a8c-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="87a8c-191">Nombre del token</span><span class="sxs-lookup"><span data-stu-id="87a8c-191">Name of the token</span></span> | <span data-ttu-id="87a8c-192">Token de </span><span class="sxs-lookup"><span data-stu-id="87a8c-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="87a8c-193">Número de pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-193">Order number</span></span>      | <span data-ttu-id="87a8c-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="87a8c-194">%salesid%</span></span> |
| <span data-ttu-id="87a8c-195">Nombre del cliente</span><span class="sxs-lookup"><span data-stu-id="87a8c-195">Customer's name</span></span>   | <span data-ttu-id="87a8c-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="87a8c-196">%customername%</span></span> |
| <span data-ttu-id="87a8c-197">Dirección de entrega</span><span class="sxs-lookup"><span data-stu-id="87a8c-197">Delivery address</span></span>  | <span data-ttu-id="87a8c-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="87a8c-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="87a8c-199">Dirección de facturación</span><span class="sxs-lookup"><span data-stu-id="87a8c-199">Billing address</span></span>   | <span data-ttu-id="87a8c-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="87a8c-200">%customeraddress%</span></span> |
| <span data-ttu-id="87a8c-201">Fecha del pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-201">Order date</span></span>        | <span data-ttu-id="87a8c-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="87a8c-202">%shipdate%</span></span> |
| <span data-ttu-id="87a8c-203">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="87a8c-203">Delivery mode</span></span>     | <span data-ttu-id="87a8c-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="87a8c-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="87a8c-205">Descuento</span><span class="sxs-lookup"><span data-stu-id="87a8c-205">Discount</span></span>          | <span data-ttu-id="87a8c-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="87a8c-206">%discount%</span></span> |
| <span data-ttu-id="87a8c-207">Impuestos</span><span class="sxs-lookup"><span data-stu-id="87a8c-207">Sales tax</span></span>         | <span data-ttu-id="87a8c-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="87a8c-208">%tax%</span></span> |
| <span data-ttu-id="87a8c-209">Total del pedido</span><span class="sxs-lookup"><span data-stu-id="87a8c-209">Order total</span></span>       | <span data-ttu-id="87a8c-210">%total%</span><span class="sxs-lookup"><span data-stu-id="87a8c-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="87a8c-211">Línea de ventas</span><span class="sxs-lookup"><span data-stu-id="87a8c-211">Sales line</span></span>

<span data-ttu-id="87a8c-212">Los siguientes tokens se sustituyen con valores para cada producto del pedido.</span><span class="sxs-lookup"><span data-stu-id="87a8c-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="87a8c-213">Ponga el token **Lista de productos - inicio** al comienzo del bloque HTML que se repite para cada producto y coloque el token **Lista de productos - final** al final del bloque.</span><span class="sxs-lookup"><span data-stu-id="87a8c-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="87a8c-214">Nombre del token</span><span class="sxs-lookup"><span data-stu-id="87a8c-214">Name of the token</span></span>      | <span data-ttu-id="87a8c-215">Token de </span><span class="sxs-lookup"><span data-stu-id="87a8c-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="87a8c-216">Lista de productos: inicio</span><span class="sxs-lookup"><span data-stu-id="87a8c-216">Product list - start</span></span>   | <span data-ttu-id="87a8c-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="87a8c-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="87a8c-218">Lista de productos: final</span><span class="sxs-lookup"><span data-stu-id="87a8c-218">Product list - end</span></span>     | <span data-ttu-id="87a8c-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="87a8c-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="87a8c-220">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="87a8c-220">Product name</span></span>           | <span data-ttu-id="87a8c-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="87a8c-221">%lineproductname%</span></span> |
| <span data-ttu-id="87a8c-222">Descripción</span><span class="sxs-lookup"><span data-stu-id="87a8c-222">Description</span></span>            | <span data-ttu-id="87a8c-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="87a8c-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="87a8c-224">Cantidad</span><span class="sxs-lookup"><span data-stu-id="87a8c-224">Quantity</span></span>               | <span data-ttu-id="87a8c-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="87a8c-225">%linequantity%</span></span> |
| <span data-ttu-id="87a8c-226">Unidad de precio de línea</span><span class="sxs-lookup"><span data-stu-id="87a8c-226">Line unit price</span></span>        | <span data-ttu-id="87a8c-227">%lineprice% (comprobar)</span><span class="sxs-lookup"><span data-stu-id="87a8c-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="87a8c-228">total de artículo de línea</span><span class="sxs-lookup"><span data-stu-id="87a8c-228">line item total</span></span>        | <span data-ttu-id="87a8c-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="87a8c-229">%linenetamount%</span></span> |
| <span data-ttu-id="87a8c-230">descuento de línea</span><span class="sxs-lookup"><span data-stu-id="87a8c-230">line discount</span></span>          | <span data-ttu-id="87a8c-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="87a8c-231">%linediscount%</span></span> |
| <span data-ttu-id="87a8c-232">Fecha de envío</span><span class="sxs-lookup"><span data-stu-id="87a8c-232">Ship date</span></span>              | <span data-ttu-id="87a8c-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="87a8c-233">%lineshipdate%</span></span> |
| <span data-ttu-id="87a8c-234">Método de compras</span><span class="sxs-lookup"><span data-stu-id="87a8c-234">Procurement method</span></span>     | <span data-ttu-id="87a8c-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="87a8c-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="87a8c-236">dirección de entrega</span><span class="sxs-lookup"><span data-stu-id="87a8c-236">delivery address</span></span>       | <span data-ttu-id="87a8c-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="87a8c-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="87a8c-238">Unidad de ventas de la línea</span><span class="sxs-lookup"><span data-stu-id="87a8c-238">Sales unit of the line</span></span> | <span data-ttu-id="87a8c-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="87a8c-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="87a8c-240">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87a8c-240">Additional resources</span></span>

[<span data-ttu-id="87a8c-241">Información general del entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-241">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="87a8c-242">Aprovisionar un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-242">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="87a8c-243">Configurar un entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-243">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="87a8c-244">Preguntas frecuentes sobre el entorno de vista previa de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-244">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="87a8c-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="87a8c-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="87a8c-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="87a8c-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="87a8c-247">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="87a8c-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="87a8c-248">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="87a8c-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
