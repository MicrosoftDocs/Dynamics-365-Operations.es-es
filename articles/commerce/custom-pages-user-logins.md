---
title: Configurar páginas personalizadas para inicios de sesión de usuario
description: Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 12/05/2019
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
ms.openlocfilehash: 20bfacbc2374003814e12e7737644d118d404cc0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945568"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="03d63-103">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="03d63-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="03d63-104">Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="03d63-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="03d63-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="03d63-105">Overview</span></span>

<span data-ttu-id="03d63-106">Para usar páginas personalizadas que se crean en Dynamics 365 Commerce para gestionar los flujos de inicio de sesión de usuario, debe configurar las directivas de Azure AD a las que se hará referencia en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="03d63-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="03d63-107">Puede configurar las directivas B2C de Azure AD "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña" mediante la aplicación B2C de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="03d63-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="03d63-108">Se puede hacer referencia a continuación a los nombres de directiva e inquilino B2C de Azure AD durante el proceso de abastecimiento que se realiza para el entorno de Commerce mediante Lifecycle Services (LCS) de Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="03d63-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="03d63-109">Las páginas personalizadas de Commerce se pueden crean mediante el módulo de restablecimiento de contraseña, edición de perfil de cuenta, registro e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03d63-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="03d63-110">A continuación, se hará referencia a las direcciones URL de página que se publican para estas páginas personalizadas en las configuraciones de directiva B2C de Azure AD en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="03d63-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="03d63-111">Configurar directivas B2C</span><span class="sxs-lookup"><span data-stu-id="03d63-111">Set up B2C policies</span></span>

<span data-ttu-id="03d63-112">Después de configurar su inquilino B2C de Azure AD y de asociarlo con su entorno de Commerce, vaya a la página **Azure AD B2C** en el portal de Azure y, a continuación, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="03d63-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Comando Flujos de usuario (directivas) del menú](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="03d63-114">Ahora puede configurar los flujos de inicio de sesión de usuario "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña".</span><span class="sxs-lookup"><span data-stu-id="03d63-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="03d63-115">Configurar la directiva “Registrarse e iniciar sesión"</span><span class="sxs-lookup"><span data-stu-id="03d63-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="03d63-116">Para configurar la directiva “Registrarse e iniciar sesión”, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="03d63-117">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Registrarse e iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="03d63-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="03d63-118">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="03d63-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="03d63-119">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="03d63-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="03d63-120">Como mínimo, la opción **Registro por correo electrónico** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="03d63-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="03d63-121">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico**, **Nombre dado** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="03d63-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="03d63-122">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="03d63-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Atributos y notificaciones seleccionadas](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="03d63-124">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="03d63-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="03d63-125">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03d63-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="03d63-126">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="03d63-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Página de propiedades para la nueva directiva](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="03d63-128">Al nombre de la directiva se hará referencia totalmente en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="03d63-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="03d63-129">(El prefijo **B2C\_1\_** se incluirá en la referencia.) No se puede cambiar el nombre de las directivas una vez se han creado.</span><span class="sxs-lookup"><span data-stu-id="03d63-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="03d63-130">Si va a sustituir una directiva existente para su entorno de Commerce, puede eliminar la directiva original y crear una directiva nueva que tenga el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="03d63-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="03d63-131">También, si el entorno ya se ha aprovisionado, puede enviar el nuevo nombre de directiva a través de una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="03d63-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="03d63-132">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="03d63-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="03d63-133">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="03d63-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="03d63-134">Configurar la directiva “Edición de perfiles”</span><span class="sxs-lookup"><span data-stu-id="03d63-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="03d63-135">Para configurar la directiva "Edición de perfiles", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="03d63-136">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Edición de perfiles**.</span><span class="sxs-lookup"><span data-stu-id="03d63-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="03d63-137">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="03d63-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="03d63-138">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="03d63-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="03d63-139">Como mínimo, la opción **Inicio de sesión de cuenta local** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="03d63-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="03d63-140">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="03d63-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="03d63-141">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="03d63-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="03d63-142">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="03d63-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="03d63-143">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03d63-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="03d63-144">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="03d63-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="03d63-145">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="03d63-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="03d63-146">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="03d63-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="03d63-147">Configurar la directiva "Restablecimiento de contraseña"</span><span class="sxs-lookup"><span data-stu-id="03d63-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="03d63-148">Para configurar la directiva "Restablecimiento de contraseña", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="03d63-149">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Vista previa**, seleccione la directiva **Restablecimiento de contraseña v1.1**.</span><span class="sxs-lookup"><span data-stu-id="03d63-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Directiva de Restablecimiento de contraseña v1.1 seleccionada en la pestaña Vista previa](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="03d63-151">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="03d63-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="03d63-152">En la sección **Proveedores de identidades**, seleccione **Restablecer contraseña con dirección de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="03d63-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="03d63-153">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="03d63-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Notificaciones seleccionadas](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="03d63-155">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="03d63-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="03d63-156">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="03d63-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="03d63-157">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="03d63-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="03d63-158">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="03d63-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="03d63-159">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="03d63-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="03d63-160">Compilar las páginas personalizadas</span><span class="sxs-lookup"><span data-stu-id="03d63-160">Build the custom pages</span></span>

<span data-ttu-id="03d63-161">Para compilar las páginas personalizada para administrar inicios de sesión de usuario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="03d63-162">En las herramientas de creación de Commerce, vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="03d63-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="03d63-163">Compile las siguientes cinco plantillas y cinco páginas:</span><span class="sxs-lookup"><span data-stu-id="03d63-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="03d63-164">Una plantilla de **Iniciar sesión** y una página que usan el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03d63-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="03d63-165">Una plantilla de **Registrarse** y una página que usan el módulo de registro.</span><span class="sxs-lookup"><span data-stu-id="03d63-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="03d63-166">Una página y plantilla de **Restablecimiento de contraseña** que usan el módulo de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="03d63-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="03d63-167">Una página y plantilla de **Verificación de restablecimiento de contraseña** que usan el módulo de verificación de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="03d63-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="03d63-168">Una página y plantilla de **Edición de perfil** que usan el módulo de edición del perfil de cuenta</span><span class="sxs-lookup"><span data-stu-id="03d63-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="03d63-169">Al compilar las páginas, siga estas directrices:</span><span class="sxs-lookup"><span data-stu-id="03d63-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="03d63-170">Para cada página o módulo, utilice el diseño y el estilo que mejor se adapten a sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="03d63-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="03d63-171">Publique todas las páginas y direcciones URL que se deben usar en la configuración de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="03d63-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="03d63-172">Una vez que se publiquen las páginas y las direcciones URL, recoja las direcciones URL que se deben utilizar para las configuraciones de la directiva de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="03d63-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="03d63-173">Se agregará un sufijo **?preloadscripts=true** a cada dirección URL cuando se use.</span><span class="sxs-lookup"><span data-stu-id="03d63-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03d63-174">No reutilice pies de página y encabezados y universales que tengan vínculos relativos.</span><span class="sxs-lookup"><span data-stu-id="03d63-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="03d63-175">Dado que estas páginas se hospedarán en el dominio de Azure AD B2C cuando se usen, solo se deben usar direcciones URL absolutas para todos los vínculos.</span><span class="sxs-lookup"><span data-stu-id="03d63-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="03d63-176">Configurar directivas de Azure AD B2C con la información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="03d63-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="03d63-177">En el portal de Azure, vuelva a la página de **Azure AD B2C** y, a continuación, en el menú, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="03d63-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="03d63-178">Actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="03d63-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="03d63-179">Para actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="03d63-180">En el directiva **Registrarse e iniciar sesión** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="03d63-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="03d63-181">Seleccione el diseño **Página unificada de inicio de sesión o de registro**.</span><span class="sxs-lookup"><span data-stu-id="03d63-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="03d63-182">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="03d63-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="03d63-183">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="03d63-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="03d63-184">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="03d63-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="03d63-185">Por ejemplo, escriba ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="03d63-185">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="03d63-186">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="03d63-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="03d63-187">Seleccione el diseño **Página de registro de cuenta local**.</span><span class="sxs-lookup"><span data-stu-id="03d63-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="03d63-188">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="03d63-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="03d63-189">En el campo **URI de página personalizado**, especifique la dirección URL de registro completa.</span><span class="sxs-lookup"><span data-stu-id="03d63-189">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="03d63-190">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="03d63-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="03d63-191">Por ejemplo, escriba ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="03d63-191">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="03d63-192">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="03d63-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="03d63-193">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="03d63-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="03d63-194">Para los atributos **Dirección de correo electrónico**, **Nombre dado** y **Apellido**, seleccione **No** en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="03d63-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="03d63-195">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="03d63-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configuración de la directiva Página de registro de cuenta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="03d63-197">Actualizar la directiva “Edición de perfiles” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="03d63-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="03d63-198">Para actualizar la directiva “Edición de perfiles” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="03d63-199">En el directiva **Edición de perfiles** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="03d63-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="03d63-200">Seleccione el diseño **Página de edición de perfil**.</span><span class="sxs-lookup"><span data-stu-id="03d63-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="03d63-201">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="03d63-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="03d63-202">En el campo **URI de página personalizado**, especifique la dirección URL completa de edición de perfil.</span><span class="sxs-lookup"><span data-stu-id="03d63-202">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="03d63-203">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="03d63-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="03d63-204">Por ejemplo, escriba ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="03d63-204">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="03d63-205">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="03d63-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="03d63-206">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="03d63-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="03d63-207">Para los atributos **Dirección de correo electrónico**, **Nombre dado**, seleccione **No**en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="03d63-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="03d63-208">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="03d63-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="03d63-209">Actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="03d63-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="03d63-210">Para actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="03d63-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="03d63-211">En el directiva **Restablecimiento de página** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="03d63-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="03d63-212">Seleccione el diseño **Página de contraseña nueva**.</span><span class="sxs-lookup"><span data-stu-id="03d63-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="03d63-213">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="03d63-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="03d63-214">En el campo **URI de página personalizado**, especifique la dirección URL completa de restauración de contraseña.</span><span class="sxs-lookup"><span data-stu-id="03d63-214">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="03d63-215">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="03d63-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="03d63-216">Por ejemplo, escriba ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="03d63-216">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="03d63-217">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="03d63-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="03d63-218">Seleccione el diseño **Página de verificación de la cuenta**.</span><span class="sxs-lookup"><span data-stu-id="03d63-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="03d63-219">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="03d63-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="03d63-220">En el campo **URI de página personalizado**, especifique la dirección URL completa de verificación de restauración de contraseña.</span><span class="sxs-lookup"><span data-stu-id="03d63-220">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="03d63-221">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="03d63-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="03d63-222">Por ejemplo, escriba ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="03d63-222">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="03d63-223">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="03d63-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="03d63-224">Personalizar cadenas de texto predeterminada para etiquetas y descripciones</span><span class="sxs-lookup"><span data-stu-id="03d63-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="03d63-225">En el kit de inicio, los módulos de inicio de sesión se llenan previamente con cadenas de texto predeterminadas para las etiquetas y descripciones.</span><span class="sxs-lookup"><span data-stu-id="03d63-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="03d63-226">Puede personalizar estas cadenas en el kit de desarrollo de software (SDK) actualizando los valores en el archivo global.json para el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03d63-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="03d63-227">Por ejemplo, el texto predeterminado para el vínculo de contraseña olvidada es **¿Olvidó la contraseña?**.</span><span class="sxs-lookup"><span data-stu-id="03d63-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="03d63-228">Lo siguiente muestra este texto predeterminado en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="03d63-228">The following shows this default text on the sign-in page.</span></span>

![Texto predeterminado para el vínculo de contraseña olvidada en la página de inicio de sesión](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="03d63-230">Sin embargo, en el archivo global.json para el módulo de inicio de sesión del kit de inicio, puede editar el texto en **¿Olvidó la contraseña?**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="03d63-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Texto de vínculo actualizado en el archivo global.json del módulo de inicio de sesión](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="03d63-232">Después de actualizar el archivo global.json y publicar los cambios, el nuevo texto del vínculo aparece en el módulo de inicio de sesión tanto en Commerce como en la página de inicio de sesión activa.</span><span class="sxs-lookup"><span data-stu-id="03d63-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03d63-233">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="03d63-233">Additional resources</span></span>

[<span data-ttu-id="03d63-234">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="03d63-234">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="03d63-235">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="03d63-235">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="03d63-236">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="03d63-236">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="03d63-237">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="03d63-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="03d63-238">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="03d63-238">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="03d63-239">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="03d63-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="03d63-240">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="03d63-240">Enable location-based store detection</span></span>](enable-store-detection.md)