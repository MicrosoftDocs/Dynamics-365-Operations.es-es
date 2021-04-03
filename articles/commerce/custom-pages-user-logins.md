---
title: Configurar páginas personalizadas para inicios de sesión de usuario
description: Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3328fad5328ae1954a6749f9a5eebcb71c723698
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477957"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a><span data-ttu-id="fcccb-103">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="fcccb-103">Set up custom pages for user sign-ins</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fcccb-104">Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fcccb-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

<span data-ttu-id="fcccb-105">Para usar páginas personalizadas que se crean en Dynamics 365 Commerce para gestionar los flujos de inicio de sesión de usuario, debe configurar las directivas de Azure AD a las que se hará referencia en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="fcccb-105">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="fcccb-106">Puede configurar las directivas B2C de Azure AD "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña" mediante la aplicación B2C de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fcccb-106">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="fcccb-107">Se puede hacer referencia a continuación a los nombres de directiva e inquilino B2C de Azure AD durante el proceso de abastecimiento que se realiza para el entorno de Commerce mediante Lifecycle Services (LCS) de Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="fcccb-107">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="fcccb-108">Las páginas personalizadas de Commerce se pueden crean mediante el módulo de restablecimiento de contraseña, edición de perfil de cuenta, registro e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fcccb-108">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="fcccb-109">A continuación, se hará referencia a las direcciones URL de página que se publican para estas páginas personalizadas en las configuraciones de directiva B2C de Azure AD en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="fcccb-109">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="fcccb-110">Configurar directivas B2C</span><span class="sxs-lookup"><span data-stu-id="fcccb-110">Set up B2C policies</span></span>

<span data-ttu-id="fcccb-111">Después de configurar su inquilino B2C de Azure AD y de asociarlo con su entorno de Commerce, vaya a la página **Azure AD B2C** en el portal de Azure y, a continuación, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-111">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Comando Flujos de usuario (directivas) del menú](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="fcccb-113">Ahora puede configurar los flujos de inicio de sesión de usuario "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña".</span><span class="sxs-lookup"><span data-stu-id="fcccb-113">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="fcccb-114">Configurar la directiva “Registrarse e iniciar sesión"</span><span class="sxs-lookup"><span data-stu-id="fcccb-114">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="fcccb-115">Para configurar la directiva “Registrarse e iniciar sesión”, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-115">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-116">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Registrarse e iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-116">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="fcccb-117">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="fcccb-117">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="fcccb-118">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="fcccb-118">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="fcccb-119">Como mínimo, la opción **Registro por correo electrónico** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fcccb-119">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="fcccb-120">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico**, **Nombre dado** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-120">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="fcccb-121">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-121">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Atributos y notificaciones seleccionadas](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="fcccb-123">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="fcccb-123">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="fcccb-124">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-124">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="fcccb-125">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-125">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Página de propiedades para la nueva directiva](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="fcccb-127">Al nombre de la directiva se hará referencia totalmente en el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="fcccb-127">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="fcccb-128">(El prefijo **B2C\_1\_** se incluirá en la referencia.) No se puede cambiar el nombre de las directivas una vez se han creado.</span><span class="sxs-lookup"><span data-stu-id="fcccb-128">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="fcccb-129">Si va a sustituir una directiva existente para su entorno de Commerce, puede eliminar la directiva original y crear una directiva nueva que tenga el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="fcccb-129">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="fcccb-130">También, si el entorno ya se ha aprovisionado, puede enviar el nuevo nombre de directiva a través de una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="fcccb-130">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="fcccb-131">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fcccb-131">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="fcccb-132">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="fcccb-132">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="fcccb-133">Configurar la directiva “Edición de perfiles”</span><span class="sxs-lookup"><span data-stu-id="fcccb-133">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="fcccb-134">Para configurar la directiva "Edición de perfiles", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-134">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-135">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Edición de perfiles**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-135">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="fcccb-136">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="fcccb-136">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="fcccb-137">En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva.</span><span class="sxs-lookup"><span data-stu-id="fcccb-137">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="fcccb-138">Como mínimo, la opción **Inicio de sesión de cuenta local** debe estar seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fcccb-138">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="fcccb-139">En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico** y **Apellido**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-139">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="fcccb-140">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-140">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="fcccb-141">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="fcccb-141">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="fcccb-142">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-142">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="fcccb-143">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-143">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="fcccb-144">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fcccb-144">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="fcccb-145">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="fcccb-145">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="fcccb-146">Configurar la directiva "Restablecimiento de contraseña"</span><span class="sxs-lookup"><span data-stu-id="fcccb-146">Configure the "Password reset" policy</span></span>

<span data-ttu-id="fcccb-147">Para configurar la directiva "Restablecimiento de contraseña", siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-147">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-148">Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Vista previa**, seleccione la directiva **Restablecimiento de contraseña v1.1**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-148">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Directiva de Restablecimiento de contraseña v1.1 seleccionada en la pestaña Vista previa](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="fcccb-150">Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="fcccb-150">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="fcccb-151">En la sección **Proveedores de identidades**, seleccione **Restablecer contraseña con dirección de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-151">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="fcccb-152">En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Apellido** e **Id. de objeto de usuario**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-152">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Notificaciones seleccionadas](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="fcccb-154">Seleccione **Aceptar** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="fcccb-154">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="fcccb-155">Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-155">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="fcccb-156">Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-156">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="fcccb-157">Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fcccb-157">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="fcccb-158">Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="fcccb-158">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="fcccb-159">Compilar las páginas personalizadas</span><span class="sxs-lookup"><span data-stu-id="fcccb-159">Build the custom pages</span></span>

<span data-ttu-id="fcccb-160">Para compilar las páginas personalizada para administrar inicios de sesión de usuario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-160">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-161">En las herramientas de creación de Commerce, vaya a su sitio.</span><span class="sxs-lookup"><span data-stu-id="fcccb-161">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="fcccb-162">Compile las siguientes cinco plantillas y cinco páginas:</span><span class="sxs-lookup"><span data-stu-id="fcccb-162">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="fcccb-163">Una plantilla de **Iniciar sesión** y una página que usan el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fcccb-163">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="fcccb-164">Una plantilla de **Registrarse** y una página que usan el módulo de registro.</span><span class="sxs-lookup"><span data-stu-id="fcccb-164">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="fcccb-165">Una página y plantilla de **Restablecimiento de contraseña** que usan el módulo de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="fcccb-165">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="fcccb-166">Una página y plantilla de **Verificación de restablecimiento de contraseña** que usan el módulo de verificación de restablecimiento de contraseña.</span><span class="sxs-lookup"><span data-stu-id="fcccb-166">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="fcccb-167">Una página y plantilla de **Edición de perfil** que usan el módulo de edición del perfil de cuenta</span><span class="sxs-lookup"><span data-stu-id="fcccb-167">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="fcccb-168">Al compilar las páginas, siga estas directrices:</span><span class="sxs-lookup"><span data-stu-id="fcccb-168">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="fcccb-169">Para cada página o módulo, utilice el diseño y el estilo que mejor se adapten a sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="fcccb-169">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="fcccb-170">Publique todas las páginas y direcciones URL que se deben usar en la configuración de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fcccb-170">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="fcccb-171">Una vez que se publiquen las páginas y las direcciones URL, recoja las direcciones URL que se deben utilizar para las configuraciones de la directiva de Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fcccb-171">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="fcccb-172">Se agregará un sufijo **?preloadscripts=true** a cada dirección URL cuando se use.</span><span class="sxs-lookup"><span data-stu-id="fcccb-172">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcccb-173">No reutilice pies de página y encabezados y universales que tengan vínculos relativos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-173">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="fcccb-174">Dado que estas páginas se hospedarán en el dominio de Azure AD B2C cuando se usen, solo se deben usar direcciones URL absolutas para todos los vínculos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-174">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="fcccb-175">Configurar directivas de Azure AD B2C con la información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="fcccb-175">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="fcccb-176">En el portal de Azure, vuelva a la página de **Azure AD B2C** y, a continuación, en el menú, en **Directivas**, seleccione **Flujos de usuario (directivas)**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-176">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="fcccb-177">Actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="fcccb-177">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="fcccb-178">Para actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-178">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-179">En el directiva **Registrarse e iniciar sesión** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-179">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="fcccb-180">Seleccione el diseño **Página unificada de inicio de sesión o de registro**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-180">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="fcccb-181">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-181">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="fcccb-182">En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa.</span><span class="sxs-lookup"><span data-stu-id="fcccb-182">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="fcccb-183">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-183">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="fcccb-184">Por ejemplo, escriba ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="fcccb-184">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="fcccb-185">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-185">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="fcccb-186">Seleccione el diseño **Página de registro de cuenta local**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-186">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="fcccb-187">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-187">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="fcccb-188">En el campo **URI de página personalizado**, especifique la dirección URL de registro completa.</span><span class="sxs-lookup"><span data-stu-id="fcccb-188">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="fcccb-189">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-189">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="fcccb-190">Por ejemplo, escriba ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="fcccb-190">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="fcccb-191">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-191">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="fcccb-192">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fcccb-192">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="fcccb-193">Para los atributos **Dirección de correo electrónico**, **Nombre dado** y **Apellido**, seleccione **No** en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-193">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="fcccb-194">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="fcccb-194">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configuración de la directiva Página de registro de cuenta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="fcccb-196">Actualizar la directiva “Edición de perfiles” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="fcccb-196">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="fcccb-197">Para actualizar la directiva “Edición de perfiles” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-197">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-198">En el directiva **Edición de perfiles** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-198">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="fcccb-199">Seleccione el diseño **Página de edición de perfil**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-199">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="fcccb-200">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-200">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="fcccb-201">En el campo **URI de página personalizado**, especifique la dirección URL completa de edición de perfil.</span><span class="sxs-lookup"><span data-stu-id="fcccb-201">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="fcccb-202">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-202">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="fcccb-203">Por ejemplo, escriba ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="fcccb-203">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="fcccb-204">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-204">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="fcccb-205">En la sección **Atributos de usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fcccb-205">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="fcccb-206">Para los atributos **Dirección de correo electrónico**, **Nombre dado**, seleccione **No** en el campo **Requiere verificación**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-206">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="fcccb-207">Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**</span><span class="sxs-lookup"><span data-stu-id="fcccb-207">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="fcccb-208">Actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada</span><span class="sxs-lookup"><span data-stu-id="fcccb-208">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="fcccb-209">Para actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fcccb-209">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="fcccb-210">En el directiva **Restablecimiento de página** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-210">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="fcccb-211">Seleccione el diseño **Página de contraseña nueva**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-211">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="fcccb-212">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-212">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="fcccb-213">En el campo **URI de página personalizado**, especifique la dirección URL completa de restauración de contraseña.</span><span class="sxs-lookup"><span data-stu-id="fcccb-213">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="fcccb-214">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-214">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="fcccb-215">Por ejemplo, escriba ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="fcccb-215">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="fcccb-216">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-216">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="fcccb-217">Seleccione el diseño **Página de verificación de la cuenta**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-217">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="fcccb-218">Establezca la opción **Usar contenido de la página personalizada** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-218">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="fcccb-219">En el campo **URI de página personalizado**, especifique la dirección URL completa de verificación de restauración de contraseña.</span><span class="sxs-lookup"><span data-stu-id="fcccb-219">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="fcccb-220">Incluir el sufijo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-220">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="fcccb-221">Por ejemplo, escriba ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="fcccb-221">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="fcccb-222">En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-222">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="fcccb-223">Personalizar cadenas de texto predeterminada para etiquetas y descripciones</span><span class="sxs-lookup"><span data-stu-id="fcccb-223">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="fcccb-224">En la biblioteca de módulos, los módulos de inicio de sesión se llenan previamente con cadenas de texto predeterminadas para las etiquetas y descripciones.</span><span class="sxs-lookup"><span data-stu-id="fcccb-224">In the module library, sign-in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="fcccb-225">Puede personalizar estas cadenas en el kit de desarrollo de software (SDK) actualizando los valores en el archivo global.json para el módulo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fcccb-225">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="fcccb-226">Por ejemplo, el texto predeterminado para el vínculo de contraseña olvidada es **¿Olvidó la contraseña?**.</span><span class="sxs-lookup"><span data-stu-id="fcccb-226">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="fcccb-227">Lo siguiente muestra este texto predeterminado en la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fcccb-227">The following shows this default text on the sign-in page.</span></span>

![Texto predeterminado para el vínculo de contraseña olvidada en la página de inicio de sesión](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="fcccb-229">Sin embargo, en el archivo global.json para el módulo de inicio de sesión de la biblioteca de módulos, puede editar el texto en **¿Olvidó la contraseña?**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="fcccb-229">However, in the global.json file for the module library sign-in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Texto de vínculo actualizado en el archivo global.json del módulo de inicio de sesión](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="fcccb-231">Después de actualizar el archivo global.json y publicar los cambios, el nuevo texto del vínculo aparece en el módulo de inicio de sesión tanto en Commerce como en la página de inicio de sesión activa.</span><span class="sxs-lookup"><span data-stu-id="fcccb-231">After you update the global.json file and publish your changes, the new link text appears in the sign-in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fcccb-232">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fcccb-232">Additional resources</span></span>

[<span data-ttu-id="fcccb-233">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="fcccb-233">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="fcccb-234">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="fcccb-234">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="fcccb-235">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="fcccb-235">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="fcccb-236">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="fcccb-236">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="fcccb-237">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="fcccb-237">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="fcccb-238">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="fcccb-238">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="fcccb-239">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="fcccb-239">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="fcccb-240">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="fcccb-240">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="fcccb-241">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="fcccb-241">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="fcccb-242">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="fcccb-242">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
