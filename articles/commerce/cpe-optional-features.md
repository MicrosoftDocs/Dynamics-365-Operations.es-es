---
title: Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce
description: En este tema se explica cómo configurar características opcionales para un ambiente de evaluación de Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a93429e836d818458f11f6f6821fda237edc291
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936989"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="b53ee-103">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b53ee-104">En este tema se explica cómo configurar características opcionales para un ambiente de evaluación de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b53ee-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b53ee-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b53ee-105">Prerequisites</span></span>

<span data-ttu-id="b53ee-106">Si desea evaluar las características transaccionales de correo electrónico, se deben cumplir los requisitos previos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b53ee-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b53ee-107">Tiene un servidor de correo electrónico disponible (Protocolo simple de transferencia de correo \[SMTP\]), que se puede usar desde la suscripción de Microsoft Azure donde aprovisionó el entorno de evaluación.</span><span class="sxs-lookup"><span data-stu-id="b53ee-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="b53ee-108">Tiene el nombre completamente cualificado del dominio (FQDN)/dirección IP del servidor, el número de puerto de SMTP y detalles de autenticación disponibles.</span><span class="sxs-lookup"><span data-stu-id="b53ee-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="b53ee-109">Configurar el back-end de la imagen</span><span class="sxs-lookup"><span data-stu-id="b53ee-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="b53ee-110">Encuentre su URL de base de medios</span><span class="sxs-lookup"><span data-stu-id="b53ee-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="b53ee-111">Antes de poder completar este procedimiento, debe completar los pasos en [Configure su sitio en Commerce ](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="b53ee-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="b53ee-112">Inicie sesión en el generador de sitios de Commerce utilizando la URL de la que tomó nota cuando inició el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="b53ee-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="b53ee-113">Abra el sitio de **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="b53ee-114">Elija **Biblioteca multimedia** en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b53ee-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="b53ee-115">Seleccione cualquier activo de imagen único.</span><span class="sxs-lookup"><span data-stu-id="b53ee-115">Select any single image asset.</span></span>
1. <span data-ttu-id="b53ee-116">En el inspector de propiedades a la derecha, busque la propiedad **URL pública**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="b53ee-117">El valor es una URL.</span><span class="sxs-lookup"><span data-stu-id="b53ee-117">The value is a URL.</span></span> <span data-ttu-id="b53ee-118">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b53ee-118">Here is an example:</span></span>

    <span data-ttu-id="b53ee-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="b53ee-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="b53ee-120">Reemplazar el último identificador en la dirección URL (**MA1nQC** en el ejemplo anterior) por la cadena **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="b53ee-121">Así es como se ve la URL de ejemplo después de realizar este cambio:</span><span class="sxs-lookup"><span data-stu-id="b53ee-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="b53ee-122">Esta URL es la URL de su base de medios.</span><span class="sxs-lookup"><span data-stu-id="b53ee-122">This URL is your media base URL.</span></span> <span data-ttu-id="b53ee-123">Anótela.</span><span class="sxs-lookup"><span data-stu-id="b53ee-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="b53ee-124">Actualizar la URL base multimedia</span><span class="sxs-lookup"><span data-stu-id="b53ee-124">Update the media base URL</span></span>

1. <span data-ttu-id="b53ee-125">Iniciar sesión en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="b53ee-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="b53ee-126">Use el menú de la izquierda, para ir a **Módulos \> Retail y Commerce \> Configuración de canal \> Perfiles del canal**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="b53ee-127">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-127">Select **Edit**.</span></span>
1. <span data-ttu-id="b53ee-128">En **Propiedades del perfil**, reemplace el valor de propiedad para **Dirección URL base del servidor multimedia** por la URL base de medios que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b53ee-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="b53ee-129">Seleccione el canal denominado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="b53ee-130">En **Propiedades del perfil**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="b53ee-131">Para la propiedad que se agregó, seleccione **URL base del servidor de medios** como la clave de propiedad</span><span class="sxs-lookup"><span data-stu-id="b53ee-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="b53ee-132">Como valor de la propiedad, introduzca la URL de la base de medios que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b53ee-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="b53ee-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="b53ee-134">Configurar y probar el servidor de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b53ee-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="b53ee-135">El servidor SMTP o servicio de correo electrónico que especifica aquí debe ser accesible dentro de la suscripción de Azure que está usando para el entorno.</span><span class="sxs-lookup"><span data-stu-id="b53ee-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="b53ee-136">Iniciar sesión en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="b53ee-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="b53ee-137">Use el menú de la izquierda para ir a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="b53ee-138">En la pestaña **Configuraciones SMTP**, en el campo **Servidor de correo saliente**, introduzca el FQDN o la dirección IP de su servidor SMTP o servicio de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b53ee-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="b53ee-139">En el campo **Número de puerto SMTP**, especifique el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="b53ee-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="b53ee-140">(Si no está utilizando la Capa de sockets seguros \[SSL \], el número de puerto predeterminado es **25**).</span><span class="sxs-lookup"><span data-stu-id="b53ee-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="b53ee-141">Si se requiere autenticación, introduzca valores en los campos **Nombre de usuario** y **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="b53ee-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-142">Select **Save**.</span></span>
1. <span data-ttu-id="b53ee-143">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="b53ee-144">En la pestaña **Correo electrónico de prueba**, en el campo **Proveedor de correo electrónico**, seleccione **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="b53ee-145">En el campo **Enviar a**, escriba la dirección de correo electrónico donde desea que se entregue el correo electrónico de prueba.</span><span class="sxs-lookup"><span data-stu-id="b53ee-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="b53ee-146">Seleccione **Enviar correo electrónico de prueba**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="b53ee-147">Configurar plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b53ee-147">Configure email templates</span></span>

<span data-ttu-id="b53ee-148">Para cada evento transaccional para el que desea enviar mensajes de correo electrónico se tiene que actualizar la plantilla de correo electrónico con una dirección de correo electrónico de remitente válida.</span><span class="sxs-lookup"><span data-stu-id="b53ee-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="b53ee-149">Iniciar sesión en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="b53ee-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="b53ee-150">Use el menú de la izquierda, para ir a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Plantillas de correo electrónico de la organización**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="b53ee-151">Seleccione **Mostrar lista**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-151">Select **Show list**.</span></span>
1. <span data-ttu-id="b53ee-152">Para cada plantilla en la lista, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b53ee-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="b53ee-153">A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="b53ee-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="b53ee-154">Opcional: en el campo **Nombre del remitente**, introduzca el nombre que debe usarse como el nombre del remitente.</span><span class="sxs-lookup"><span data-stu-id="b53ee-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="b53ee-155">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="b53ee-156">Personalizar plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b53ee-156">Customize email templates</span></span>

<span data-ttu-id="b53ee-157">Es posible que desee personalizar las plantillas de correo electrónico para que utilicen imágenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="b53ee-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="b53ee-158">O puede que desee actualizar los vínculos en las plantillas para que vayan a su entorno de evaluación.</span><span class="sxs-lookup"><span data-stu-id="b53ee-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="b53ee-159">Este procedimiento explica cómo descargar plantillas predeterminadas, personalizarlas y actualizar las plantillas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="b53ee-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="b53ee-160">En un explorador web, descargue el [archivo .zip de correo electrónico predeterminado de evaluación de Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="b53ee-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="b53ee-161">Este archivo contiene los siguientes documentos HTML:</span><span class="sxs-lookup"><span data-stu-id="b53ee-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="b53ee-162">Plantilla de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-162">Order confirmation template</span></span>
    - <span data-ttu-id="b53ee-163">Emitir plantilla de tarjeta regalo</span><span class="sxs-lookup"><span data-stu-id="b53ee-163">Issue gift card template</span></span>
    - <span data-ttu-id="b53ee-164">Nueva plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-164">New order template</span></span>
    - <span data-ttu-id="b53ee-165">Empaquetar plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-165">Pack order template</span></span>
    - <span data-ttu-id="b53ee-166">Recoger plantilla de pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-166">Pick order template</span></span>

1. <span data-ttu-id="b53ee-167">Personalice las plantillas mediante un editor HTML o de texto.</span><span class="sxs-lookup"><span data-stu-id="b53ee-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="b53ee-168">Vea la lista de [tokens compatibles ](#supported-tokens-in-the-email-template) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="b53ee-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="b53ee-169">Iniciar sesión en Commerce.</span><span class="sxs-lookup"><span data-stu-id="b53ee-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="b53ee-170">Use el menú de la izquierda, para ir a **Módulos \> Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="b53ee-171">Expanda la lista de la izquierda para ver todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="b53ee-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="b53ee-172">Para cada plantilla que desee personalizar, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b53ee-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="b53ee-173">Seleccione la plantilla en la lista.</span><span class="sxs-lookup"><span data-stu-id="b53ee-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="b53ee-174">En **Contenido del mensaje de correo electrónico**, seleccione la versión de idioma adecuada en la lista.</span><span class="sxs-lookup"><span data-stu-id="b53ee-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="b53ee-175">(El valor de plantilla predeterminado es **en-us**).</span><span class="sxs-lookup"><span data-stu-id="b53ee-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="b53ee-176">En **Contenido del mensaje de correo electrónico**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="b53ee-177">Aparecerá el panel **Subir plantilla de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="b53ee-178">Seleccione **Explorar** y busque el archivo HTML que tiene el contenido personalizado.</span><span class="sxs-lookup"><span data-stu-id="b53ee-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="b53ee-179">Seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-179">Select **Upload**.</span></span> <span data-ttu-id="b53ee-180">La plantilla se carga en el sistema y se muestra una vista previa.</span><span class="sxs-lookup"><span data-stu-id="b53ee-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="b53ee-181">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-181">Select **OK**.</span></span>
    1. <span data-ttu-id="b53ee-182">Opcional: personalizar la propiedad **Asunto** de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b53ee-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="b53ee-183">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b53ee-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="b53ee-184">Tokens compatibles en la plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b53ee-184">Supported tokens in the email template</span></span>

<span data-ttu-id="b53ee-185">Estos tokens se reemplazarán en el momento de la representación de correo electrónico con los valores reales que se aplican al cliente y su pedido.</span><span class="sxs-lookup"><span data-stu-id="b53ee-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="b53ee-186">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="b53ee-186">Sales order</span></span>

<span data-ttu-id="b53ee-187">Los siguientes tokens se aplican al pedido de ventas general.</span><span class="sxs-lookup"><span data-stu-id="b53ee-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="b53ee-188">Nombre del token</span><span class="sxs-lookup"><span data-stu-id="b53ee-188">Name of the token</span></span> | <span data-ttu-id="b53ee-189">Token</span><span class="sxs-lookup"><span data-stu-id="b53ee-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="b53ee-190">Número de pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-190">Order number</span></span>      | <span data-ttu-id="b53ee-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="b53ee-191">%salesid%</span></span> |
| <span data-ttu-id="b53ee-192">Nombre del cliente</span><span class="sxs-lookup"><span data-stu-id="b53ee-192">Customer's name</span></span>   | <span data-ttu-id="b53ee-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="b53ee-193">%customername%</span></span> |
| <span data-ttu-id="b53ee-194">Dirección de entrega</span><span class="sxs-lookup"><span data-stu-id="b53ee-194">Delivery address</span></span>  | <span data-ttu-id="b53ee-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="b53ee-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="b53ee-196">Dirección de facturación</span><span class="sxs-lookup"><span data-stu-id="b53ee-196">Billing address</span></span>   | <span data-ttu-id="b53ee-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="b53ee-197">%customeraddress%</span></span> |
| <span data-ttu-id="b53ee-198">Fecha del pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-198">Order date</span></span>        | <span data-ttu-id="b53ee-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="b53ee-199">%shipdate%</span></span> |
| <span data-ttu-id="b53ee-200">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="b53ee-200">Delivery mode</span></span>     | <span data-ttu-id="b53ee-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="b53ee-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="b53ee-202">Descuento</span><span class="sxs-lookup"><span data-stu-id="b53ee-202">Discount</span></span>          | <span data-ttu-id="b53ee-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="b53ee-203">%discount%</span></span> |
| <span data-ttu-id="b53ee-204">Impuestos</span><span class="sxs-lookup"><span data-stu-id="b53ee-204">Sales tax</span></span>         | <span data-ttu-id="b53ee-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="b53ee-205">%tax%</span></span> |
| <span data-ttu-id="b53ee-206">Total del pedido</span><span class="sxs-lookup"><span data-stu-id="b53ee-206">Order total</span></span>       | <span data-ttu-id="b53ee-207">%total%</span><span class="sxs-lookup"><span data-stu-id="b53ee-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="b53ee-208">Línea de ventas</span><span class="sxs-lookup"><span data-stu-id="b53ee-208">Sales line</span></span>

<span data-ttu-id="b53ee-209">Los siguientes tokens se sustituyen con valores para cada producto del pedido.</span><span class="sxs-lookup"><span data-stu-id="b53ee-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="b53ee-210">Ponga el token **Lista de productos - inicio** al comienzo del bloque HTML que se repite para cada producto y coloque el token **Lista de productos - final** al final del bloque.</span><span class="sxs-lookup"><span data-stu-id="b53ee-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="b53ee-211">Nombre del token</span><span class="sxs-lookup"><span data-stu-id="b53ee-211">Name of the token</span></span>      | <span data-ttu-id="b53ee-212">Token</span><span class="sxs-lookup"><span data-stu-id="b53ee-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="b53ee-213">Lista de productos: inicio</span><span class="sxs-lookup"><span data-stu-id="b53ee-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="b53ee-214">Lista de productos: final</span><span class="sxs-lookup"><span data-stu-id="b53ee-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="b53ee-215">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b53ee-215">Product name</span></span>           | <span data-ttu-id="b53ee-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="b53ee-216">%lineproductname%</span></span> |
| <span data-ttu-id="b53ee-217">Descripción</span><span class="sxs-lookup"><span data-stu-id="b53ee-217">Description</span></span>            | <span data-ttu-id="b53ee-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="b53ee-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="b53ee-219">Cantidad</span><span class="sxs-lookup"><span data-stu-id="b53ee-219">Quantity</span></span>               | <span data-ttu-id="b53ee-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="b53ee-220">%linequantity%</span></span> |
| <span data-ttu-id="b53ee-221">Unidad de precio de línea</span><span class="sxs-lookup"><span data-stu-id="b53ee-221">Line unit price</span></span>        | <span data-ttu-id="b53ee-222">%lineprice% (comprobar)</span><span class="sxs-lookup"><span data-stu-id="b53ee-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="b53ee-223">total de artículo de línea</span><span class="sxs-lookup"><span data-stu-id="b53ee-223">line item total</span></span>        | <span data-ttu-id="b53ee-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="b53ee-224">%linenetamount%</span></span> |
| <span data-ttu-id="b53ee-225">descuento de línea</span><span class="sxs-lookup"><span data-stu-id="b53ee-225">line discount</span></span>          | <span data-ttu-id="b53ee-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="b53ee-226">%linediscount%</span></span> |
| <span data-ttu-id="b53ee-227">Fecha de envío</span><span class="sxs-lookup"><span data-stu-id="b53ee-227">Ship date</span></span>              | <span data-ttu-id="b53ee-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="b53ee-228">%lineshipdate%</span></span> |
| <span data-ttu-id="b53ee-229">Método de compras</span><span class="sxs-lookup"><span data-stu-id="b53ee-229">Procurement method</span></span>     | <span data-ttu-id="b53ee-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="b53ee-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="b53ee-231">dirección de entrega</span><span class="sxs-lookup"><span data-stu-id="b53ee-231">delivery address</span></span>       | <span data-ttu-id="b53ee-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="b53ee-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="b53ee-233">Unidad de ventas de la línea</span><span class="sxs-lookup"><span data-stu-id="b53ee-233">Sales unit of the line</span></span> | <span data-ttu-id="b53ee-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="b53ee-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="b53ee-235">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b53ee-235">Additional resources</span></span>

[<span data-ttu-id="b53ee-236">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="b53ee-237">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="b53ee-238">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="b53ee-239">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="b53ee-240">Preguntas frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="b53ee-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="b53ee-241">Microsoft Lifecycle Services (LCS)</span></span>](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="b53ee-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="b53ee-242">Retail Cloud Scale Unit (RCSU)</span></span>](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="b53ee-243">Portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b53ee-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="b53ee-244">Sitio web de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b53ee-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]