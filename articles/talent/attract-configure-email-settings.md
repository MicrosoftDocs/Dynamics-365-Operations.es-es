---
title: Configurar parámetros de correo electrónico en Attract
description: En este tema se explica cómo configurar parámetros para correos electrónicos enviado por Microsoft Dynamcis 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c1ebfaeb2e9bc2836bb70e87afa93484c829b6cb
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833124"
---
# <a name="configure-email-settings-in-attract"></a><span data-ttu-id="a1c34-103">Configurar parámetros de correo electrónico en Attract</span><span class="sxs-lookup"><span data-stu-id="a1c34-103">Configure email settings in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a1c34-104">La marca establece confianza y le ayuda a crear una relación con los candidatos incluso antes de que soliciten sus puestos.</span><span class="sxs-lookup"><span data-stu-id="a1c34-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="a1c34-105">Una percepción positiva de la marca atrae a los mejores talentos y aumenta la fidelidad de los empleados existentes.</span><span class="sxs-lookup"><span data-stu-id="a1c34-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="a1c34-106">Microsoft Dynamics 365 Talent: Attract le permite configurar correos electrónicos de modo que reflejen la marca de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-106">Microsoft Dynamics 365 Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="a1c34-107">Por tanto, puede proporcionar una experiencia coherente a los candidatos al puesto a medida que avanzan en proceso de solicitud.</span><span class="sxs-lookup"><span data-stu-id="a1c34-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="a1c34-108">Attract le permite realizar estas acciones:</span><span class="sxs-lookup"><span data-stu-id="a1c34-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="a1c34-109">Configurar parámetros de correo electrónico para que los utilice la cuenta de servicio de correo electrónico de Microsoft Exchange de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="a1c34-110">De esta manera, los candidatos sabe que los mensajes de correo electrónico proceden de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="a1c34-111">Por ejemplo, puede configurar sus parámetros para que los candidatos reciban correos electrónicos de `recruiting@contoso.com` en lugar de `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="a1c34-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="a1c34-112">Crear una personalización de marca coherente para todas sus comunicaciones realizadas por correo electrónico mediante la configuración de encabezado y un pie de página globales para las plantillas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="a1c34-113">Para configurar Attract de modo que utilice la cuenta de servicio de correo electrónico de su empresa para enviar mensajes de correo electrónico, necesita el complemento de contratación completa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="a1c34-114">Conectar una cuenta de servicio de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a1c34-114">Connect an email service account</span></span>

<span data-ttu-id="a1c34-115">Al conectar la cuenta de servicio de correo electrónico de su empresa, puede crear una experiencia de correo electrónico personalizada para sus candidatos al puesto.</span><span class="sxs-lookup"><span data-stu-id="a1c34-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="a1c34-116">Si no se conecta a la cuenta de su empresa, Attract utiliza la cuenta de servicio de correo electrónico predeterminada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1c34-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="a1c34-117">Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a1c34-118">En la pestaña **Configuración de correo electrónico**, en **Cuentas de servicio de correo electrónico**, seleccione **Conectar una cuenta de empresa**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Conectando la cuenta de servicio de correo electrónico de su empresa en Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="a1c34-120">Para obtener más información sobre cómo crear una cuenta de correo electrónico compartida, consulte [Buzones compartidos en Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="a1c34-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="a1c34-121">En la ventana de inicio de sesión de Microsoft, inicie sesión con sus credenciales corporativas.</span><span class="sxs-lookup"><span data-stu-id="a1c34-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="a1c34-122">Si aún no ha configurado una cuenta de servicio de correo electrónico, o si desea agregar una nueva, seleccione **Agregar nueva cuenta de servicio** e introduzca su información de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="a1c34-123">Si ya ha configurado la cuenta de servicio de correo electrónico que desea utilizar, selecciónela.</span><span class="sxs-lookup"><span data-stu-id="a1c34-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="a1c34-124">Cuando la cuenta de servicio de correo electrónico está configurada correctamente, verá que aparece en **Cuentas de servicio de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="a1c34-125">Desconectar una cuenta de servicio de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a1c34-125">Disconnect an email service account</span></span>

<span data-ttu-id="a1c34-126">Si desea dejar de usar el dominio de su empresa en las comunicaciones por correo electrónico a través para Attract, puede desconectar una cuenta de servicio de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="a1c34-127">Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a1c34-128">En la pestaña **Configuración de correo electrónico**, en **Cuentas de servicio de correo electrónico**, seleccione el botón **Más** (tres puntos verticales) junto a la cuenta de servicio de correo electrónico que desea desconectar.</span><span class="sxs-lookup"><span data-stu-id="a1c34-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="a1c34-129">Seleccione **Desconectar cuenta de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-129">Select **Disconnect email account**.</span></span>

    ![Desconectando la cuenta de servicio de correo electrónico de su empresa](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="a1c34-131">Cuando se le pida que confirme lla operación, seleccione **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Confirmando la desconexión de la cuenta de servicio de correo electrónico de su empresa](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="a1c34-133">Si no se conecta a una cuenta de servicio de correo electrónico diferente, los mensajes de correo electrónico enviados desde Attract utilizarán la cuenta de servicio de correo electrónico predeterminada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1c34-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="a1c34-134">Configurar ajustes de plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a1c34-134">Configure email template settings</span></span>

<span data-ttu-id="a1c34-135">Puede cargar una imagen del logotipo de su empresa y otra información como un encabezado de marca para sus correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="a1c34-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="a1c34-136">También puede proporcionar vínculos a su directiva de privacidad y términos de uso en los pies de página del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="a1c34-137">Debe cumplir toda la legislación aplicable de su país o región, y también la del país o región que rige el destinatario del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="a1c34-138">Esta legislación incluye normativas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1c34-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="a1c34-139">Seleccione **Configuración** (el símbolo de engranaje en la esquina superior derecha) y, a continuación, seleccione **Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="a1c34-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="a1c34-140">En la pestaña **Configuración de correo electrónico**, en **Configuración de plantilla de correo electrónico**, arrastre la imagen que desea utilizar como encabezado de su correo electrónico en el cuadro de imagen, o haga clic en el cuadro de imagen para buscar el archivo.</span><span class="sxs-lookup"><span data-stu-id="a1c34-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="a1c34-141">Para sustituir una imagen existente, primero debe seleccionar **Eliminar** al lado de esta.</span><span class="sxs-lookup"><span data-stu-id="a1c34-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="a1c34-142">La imagen debe ser un archivo JPEG, JPG, PNG o SVG.</span><span class="sxs-lookup"><span data-stu-id="a1c34-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="a1c34-143">El tamaño recomendado para imágenes es entre 25 y 800 píxeles de ancho, y entre 25 y 150 píxeles de alto.</span><span class="sxs-lookup"><span data-stu-id="a1c34-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="a1c34-144">El tamaño máximo del archivo para el encabezado es de 1 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="a1c34-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Agregando una imagen para el encabezado de correo electrónico de su empresa](./media/attract-admin-email-header.png)

3. <span data-ttu-id="a1c34-146">En **Su directiva de privacidad para las comunicaciones**, proporcione un vínculo a la directiva de privacidad de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="a1c34-147">En **Sus términos y condiciones para las comunicaciones**, proporcione un vínculo a las condiciones de uso de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a1c34-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Agregando vínculos a la directiva de privacidad y los términos de uso de su empresa para el pie de página del correo electrónico](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="a1c34-149">Seleccione **Guardar** para guardar la configuración de plantilla de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1c34-149">Select **Save** to save your email template settings.</span></span>
