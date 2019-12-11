---
title: Configurar páginas personalizadas para inicios de sesión de usuario
description: Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 644d937ddd3c219ae869f22d977d2846dffc20e1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697575"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="0f932-103">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="0f932-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0f932-104">Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0f932-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="0f932-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="0f932-105">Overview</span></span>

<span data-ttu-id="0f932-106">Para usar páginas personalizadas que se crean en Dynamics 365 Commerce para gestionar los flujos de inicio de sesión de usuario, debe configurar las directivas de Azure AD a las que se hará referencia en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f932-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="0f932-107">Puede configurar las directivas B2C de Azure AD "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña" mediante la aplicación B2C de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0f932-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="0f932-108">Se puede hacer referencia a continuación a los nombres de directiva e inquilino B2C de Azure AD durante el proceso de abastecimiento que se realiza para el entorno de Commerce mediante Lifecycle Services (LCS) de Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="0f932-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="0f932-109">Las páginas personalizadas de Commerce se pueden crean mediante el módulo de restablecimiento de contraseña, edición de perfil de cuenta, registro e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0f932-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="0f932-110">A continuación, se hará referencia a las direcciones URL de página que se publican para estas páginas personalizadas en las configuraciones de directiva B2C de Azure AD en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="0f932-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="0f932-111">Configurar directivas B2C</span><span class="sxs-lookup"><span data-stu-id="0f932-111">Set up B2C policies</span></span>

<span data-ttu-id="0f932-112">Después de configurar su inquilino B2C de Azure AD y de asociarlo con su entorno de Commerce, vaya a la página **Azure AD B2C** en el portal de Azure y, a continuación, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="0f932-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Comando Flujos de usuario (directivas) del menú](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="0f932-114">Ahora puede configurar los flujos de inicio de sesión de usuario "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña".</span><span class="sxs-lookup"><span data-stu-id="0f932-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="0f932-115">Configurar la directiva “Registrarse e iniciar sesión"</span><span class="sxs-lookup"><span data-stu-id="0f932-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="0f932-116">Para configurar la directiva “Registrarse e iniciar sesión”, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="0f932-117">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Registrarse e iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="0f932-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="0f932-118">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="0f932-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="0f932-119">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0f932-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="0f932-120">Como mínimo, la opción **Registro por correo electrónico** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0f932-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="0f932-121">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico**, **Nombre dado** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="0f932-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="0f932-122">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0f932-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Atributos y notificaciones seleccionadas](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="0f932-124">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="0f932-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="0f932-125">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0f932-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="0f932-126">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="0f932-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Página de propiedades para la nueva directiva](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="0f932-128">Al nombre de la directiva se hará referencia totalmente en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f932-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="0f932-129">(El prefijo **B2C\_1\_** se incluirá en la referencia.) No se puede cambiar el nombre de las directivas una vez se han creado.</span><span class="sxs-lookup"><span data-stu-id="0f932-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="0f932-130">Si va a sustituir una directiva existente para su entorno de Commerce, puede eliminar la directiva original y crear una directiva nueva que tenga el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="0f932-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="0f932-131">También, si el entorno ya se ha aprovisionado, puede enviar el nuevo nombre de directiva a través de una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="0f932-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="0f932-132">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0f932-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="0f932-133">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="0f932-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="0f932-134">Configurar la directiva “Edición de perfiles”</span><span class="sxs-lookup"><span data-stu-id="0f932-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="0f932-135">Para configurar la directiva "Edición de perfiles", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="0f932-136">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Edición de perfiles**.</span><span class="sxs-lookup"><span data-stu-id="0f932-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="0f932-137">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="0f932-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="0f932-138">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0f932-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="0f932-139">Como mínimo, la opción **Inicio de sesión de cuenta local** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0f932-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="0f932-140">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="0f932-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="0f932-141">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0f932-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="0f932-142">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="0f932-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="0f932-143">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0f932-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="0f932-144">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="0f932-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="0f932-145">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0f932-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="0f932-146">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="0f932-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="0f932-147">Configurar la directiva "Restablecimiento de contraseña"</span><span class="sxs-lookup"><span data-stu-id="0f932-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="0f932-148">Para configurar la directiva "Restablecimiento de contraseña", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="0f932-149">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Vista previa**, seleccione la directiva **Restablecimiento de contraseña v1.1**.</span><span class="sxs-lookup"><span data-stu-id="0f932-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Directiva de Restablecimiento de contraseña v1.1 seleccionada en la pestaña Vista previa](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="0f932-151">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="0f932-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="0f932-152">En la sección **Proveedores de identidades**, seleccione **Restablecer contraseña con dirección de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="0f932-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="0f932-153">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0f932-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Notificaciones seleccionadas](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="0f932-155">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="0f932-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="0f932-156">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0f932-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="0f932-157">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="0f932-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="0f932-158">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0f932-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="0f932-159">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="0f932-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="0f932-160">Compilar las páginas personalizadas</span><span class="sxs-lookup"><span data-stu-id="0f932-160">Build the custom pages</span></span>

<span data-ttu-id="0f932-161">Para compilar las páginas personalizada para administrar inicios de sesión de usuario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="0f932-162">En las herramientas de creación de Commerce, vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="0f932-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="0f932-163">Compile las siguientes cinco plantillas y cinco páginas:</span><span class="sxs-lookup"><span data-stu-id="0f932-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="0f932-164">Una plantilla de **Iniciar sesión** y una página que usan el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0f932-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="0f932-165">Una plantilla de **Registrarse** y una página que usan el módulo de registro.</span><span class="sxs-lookup"><span data-stu-id="0f932-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="0f932-166">Una página y plantilla de **Restablecimiento de contraseña** que usan el módulo de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="0f932-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="0f932-167">Una página y plantilla de **Verificación de restablecimiento de contraseña** que usan el módulo de verificación de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="0f932-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="0f932-168">Una página y plantilla de **Edición de perfil** que usan el módulo de edición del perfil de cuenta</span><span class="sxs-lookup"><span data-stu-id="0f932-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="0f932-169">Al compilar las páginas, siga estas directrices:</span><span class="sxs-lookup"><span data-stu-id="0f932-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="0f932-170">Para cada página o módulo, utilice el diseño y el estilo que mejor se adapten a sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="0f932-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="0f932-171">Publique todas las páginas y direcciones URL que se deben usar en la configuración de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0f932-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="0f932-172">Una vez que se publiquen las páginas y las direcciones URL, recoja las direcciones URL que se deben utilizar para las configuraciones de la directiva de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0f932-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="0f932-173">Se agregará un sufijo **?preloadscripts=true** a cada dirección URL cuando se use.</span><span class="sxs-lookup"><span data-stu-id="0f932-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f932-174">No reutilice pies de página y encabezados y universales que tengan vínculos relativos.</span><span class="sxs-lookup"><span data-stu-id="0f932-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="0f932-175">Dado que estas páginas se hospedarán en el dominio de Azure AD B2C cuando se usen, solo se deben usar direcciones URL absolutas para todos los vínculos.</span><span class="sxs-lookup"><span data-stu-id="0f932-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="0f932-176">Configurar directivas de Azure AD B2C con la información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="0f932-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="0f932-177">En el portal de Azure, vuelva a la página de **Azure AD B2C** y, a continuación, en el menú, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="0f932-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="0f932-178">Actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="0f932-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="0f932-179">Para actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="0f932-180">En el directiva **Registrarse e iniciar sesión** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="0f932-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="0f932-181">Seleccione el diseño **Página unificada de inicio de sesión o de registro**.</span><span class="sxs-lookup"><span data-stu-id="0f932-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="0f932-182">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f932-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="0f932-183">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="0f932-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="0f932-184">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="0f932-185">Por ejemplo, escriba **www.\<mi dominio\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-185">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="0f932-186">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="0f932-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="0f932-187">Seleccione el diseño **Página de registro de cuenta local**.</span><span class="sxs-lookup"><span data-stu-id="0f932-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="0f932-188">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f932-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="0f932-189">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="0f932-189">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="0f932-190">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="0f932-191">Por ejemplo, escriba **www.\<mi dominio\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-191">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="0f932-192">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="0f932-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="0f932-193">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0f932-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="0f932-194">Para los atributos **Dirección de correo electrónico**, **Nombre dado** y **Apellido**, seleccione **No** en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="0f932-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="0f932-195">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="0f932-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configuración de la directiva Página de registro de cuenta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="0f932-197">Actualizar la directiva “Edición de perfiles” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="0f932-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="0f932-198">Para actualizar la directiva “Edición de perfiles” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="0f932-199">En el directiva **Edición de perfiles** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="0f932-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="0f932-200">Seleccione el diseño **Página de edición de perfil**.</span><span class="sxs-lookup"><span data-stu-id="0f932-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="0f932-201">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f932-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="0f932-202">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="0f932-202">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="0f932-203">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="0f932-204">Por ejemplo, escriba **www.\<mi dominio\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-204">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="0f932-205">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="0f932-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="0f932-206">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0f932-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="0f932-207">Para los atributos **Dirección de correo electrónico**, **Nombre dado**, seleccione **No**en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="0f932-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="0f932-208">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="0f932-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="0f932-209">Actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="0f932-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="0f932-210">Para actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0f932-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="0f932-211">En el directiva **Restablecimiento de página** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="0f932-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="0f932-212">Seleccione el diseño **Página de contraseña nueva**.</span><span class="sxs-lookup"><span data-stu-id="0f932-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="0f932-213">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f932-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="0f932-214">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="0f932-214">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="0f932-215">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="0f932-216">Por ejemplo, escriba **www.\<mi dominio\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-216">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="0f932-217">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="0f932-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="0f932-218">Seleccione el diseño **Página de verificación de la cuenta**.</span><span class="sxs-lookup"><span data-stu-id="0f932-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="0f932-219">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0f932-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="0f932-220">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="0f932-220">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="0f932-221">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="0f932-222">Por ejemplo, escriba **www.\<mi dominio\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="0f932-222">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="0f932-223">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="0f932-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="0f932-224">Personalizar cadenas de texto predeterminada para etiquetas y descripciones</span><span class="sxs-lookup"><span data-stu-id="0f932-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="0f932-225">En el kit de inicio, los módulos de inicio de sesión se llenan previamente con cadenas de texto predeterminadas para las etiquetas y descripciones.</span><span class="sxs-lookup"><span data-stu-id="0f932-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="0f932-226">Puede personalizar estas cadenas en el kit de desarrollo de software (SDK) actualizando los valores en el archivo global.json para el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0f932-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="0f932-227">Por ejemplo, el texto predeterminado para el vínculo de contraseña olvidada es **¿Olvidó la contraseña?**.</span><span class="sxs-lookup"><span data-stu-id="0f932-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="0f932-228">Lo siguiente muestra este texto predeterminado en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0f932-228">The following shows this default text on the sign-in page.</span></span>

![Texto predeterminado para el vínculo de contraseña olvidada en la página de inicio de sesión](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="0f932-230">Sin embargo, en el archivo global.json para el módulo de inicio de sesión del kit de inicio, puede editar el texto en **¿Olvidó la contraseña?**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="0f932-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Texto de vínculo actualizado en el archivo global.json del módulo de inicio de sesión](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="0f932-232">Después de actualizar el archivo global.json y publicar los cambios, el nuevo texto del vínculo aparece en el módulo de inicio de sesión tanto en Commerce como en la página de inicio de sesión activa.</span><span class="sxs-lookup"><span data-stu-id="0f932-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f932-233">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0f932-233">Additional resources</span></span>

[<span data-ttu-id="0f932-234">Visión general de la tienda en línea</span><span class="sxs-lookup"><span data-stu-id="0f932-234">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="0f932-235">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="0f932-235">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="0f932-236">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="0f932-236">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="0f932-237">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="0f932-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="0f932-238">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="0f932-238">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="0f932-239">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="0f932-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="0f932-240">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="0f932-240">Enable location-based store detection</span></span>](enable-store-detection.md)
