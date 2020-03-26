---
title: Configurar páginas personalizadas para inicios de sesión de usuario
description: Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 03/02/2020
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
ms.openlocfilehash: 210a7d1c2b0a9a9606723b48681cca3a50fcc05b
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096806"
---
# <a name="set-up-custom-pages-for-user-logins"></a>Configurar páginas personalizadas para inicios de sesión de usuario


[!include [banner](includes/banner.md)]

Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).

## <a name="overview"></a>Visión general

Para usar páginas personalizadas que se crean en Dynamics 365 Commerce para gestionar los flujos de inicio de sesión de usuario, debe configurar las directivas de Azure AD a las que se hará referencia en el entorno de Commerce. Puede configurar las directivas B2C de Azure AD "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña" mediante la aplicación B2C de Azure AD. Se puede hacer referencia a continuación a los nombres de directiva e inquilino B2C de Azure AD durante el proceso de abastecimiento que se realiza para el entorno de Commerce mediante Lifecycle Services (LCS) de Microsoft Dynamics.

Las páginas personalizadas de Commerce se pueden crean mediante el módulo de restablecimiento de contraseña, edición de perfil de cuenta, registro e inicio de sesión. A continuación, se hará referencia a las direcciones URL de página que se publican para estas páginas personalizadas en las configuraciones de directiva B2C de Azure AD en el portal de Azure.

## <a name="set-up-b2c-policies"></a>Configurar directivas B2C

Después de configurar su inquilino B2C de Azure AD y de asociarlo con su entorno de Commerce, vaya a la página **Azure AD B2C** en el portal de Azure y, a continuación, en **Directivas**, seleccione **Flujos de usuario (directivas)**.

![Comando Flujos de usuario (directivas) del menú](./media/B2C_CustomPage_PoliciesMenu.png)

Ahora puede configurar los flujos de inicio de sesión de usuario "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurar la directiva “Registrarse e iniciar sesión"

Para configurar la directiva “Registrarse e iniciar sesión”, siga estos pasos.

1. Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Registrarse e iniciar sesión**.
1. Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_SignInSignUp**).
1. En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva. Como mínimo, la opción **Registro por correo electrónico** debe estar seleccionada.
1. En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico**, **Nombre dado** y **Apellido**.
1. En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.

    ![Atributos y notificaciones seleccionadas](./media/B2C_SignInSignUp_Attributes.png)

1. Seleccione **Aceptar** para crear la directiva.
1. Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.
1. Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.

    ![Página de propiedades para la nueva directiva](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> Al nombre de la directiva se hará referencia totalmente en el entorno de Commerce. (El prefijo **B2C\_1\_** se incluirá en la referencia.) No se puede cambiar el nombre de las directivas una vez se han creado. Si va a sustituir una directiva existente para su entorno de Commerce, puede eliminar la directiva original y crear una directiva nueva que tenga el mismo nombre. También, si el entorno ya se ha aprovisionado, puede enviar el nuevo nombre de directiva a través de una solicitud de servicio.

Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas. Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurar la directiva “Edición de perfiles”

Para configurar la directiva "Edición de perfiles", siga estos pasos.

1. Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Recomendado**, seleccione la directiva **Edición de perfiles**.
1. Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_EditProfile**).
1. En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva. Como mínimo, la opción **Inicio de sesión de cuenta local** debe estar seleccionada.
1. En la columna **Recopilar atributo**, seleccione las casillas para **Dirección de correo electrónico** y **Apellido**.
1. En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.
1. Seleccione **Aceptar** para crear la directiva.
1. Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.
1. Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.

Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas. Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.

### <a name="configure-the-password-reset-policy"></a>Configurar la directiva "Restablecimiento de contraseña"

Para configurar la directiva "Restablecimiento de contraseña", siga estos pasos.

1. Seleccione **Nuevo flujo de usuario** y, a continuación, en la pestaña **Vista previa**, seleccione la directiva **Restablecimiento de contraseña v1.1**.

    ![Directiva de Restablecimiento de contraseña v1.1 seleccionada en la pestaña Vista previa](./media/B2C_ForgetPassword_Menu.png)

1. Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_ForgetPassword**).
1. En la sección **Proveedores de identidades**, seleccione **Restablecer contraseña con dirección de correo electrónico**.
1. En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Apellido** e **Id. de objeto de usuario**.

    ![Notificaciones seleccionadas](./media/B2C_ForgetPassword_Attributes.png)

1. Seleccione **Aceptar** para crear la directiva.
1. Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.
1. Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.

Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas. Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.

## <a name="build-the-custom-pages"></a>Compilar las páginas personalizadas

Para compilar las páginas personalizada para administrar inicios de sesión de usuario, siga estos pasos.

1. En las herramientas de creación de Commerce, vaya a su sitio.
1. Compile las siguientes cinco plantillas y cinco páginas:

    - Una plantilla de **Iniciar sesión** y una página que usan el módulo de inicio de sesión.
    - Una plantilla de **Registrarse** y una página que usan el módulo de registro.
    - Una página y plantilla de **Restablecimiento de contraseña** que usan el módulo de restablecimiento de contraseña.
    - Una página y plantilla de **Verificación de restablecimiento de contraseña** que usan el módulo de verificación de restablecimiento de contraseña.
    - Una página y plantilla de **Edición de perfil** que usan el módulo de edición del perfil de cuenta

Al compilar las páginas, siga estas directrices:

- Para cada página o módulo, utilice el diseño y el estilo que mejor se adapten a sus requisitos empresariales.
- Publique todas las páginas y direcciones URL que se deben usar en la configuración de Azure AD B2C.
- Una vez que se publiquen las páginas y las direcciones URL, recoja las direcciones URL que se deben utilizar para las configuraciones de la directiva de Azure AD B2C. Se agregará un sufijo **?preloadscripts=true** a cada dirección URL cuando se use.

> [!IMPORTANT]
> No reutilice pies de página y encabezados y universales que tengan vínculos relativos. Dado que estas páginas se hospedarán en el dominio de Azure AD B2C cuando se usen, solo se deben usar direcciones URL absolutas para todos los vínculos.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurar directivas de Azure AD B2C con la información de página personalizada 

En el portal de Azure, vuelva a la página de **Azure AD B2C** y, a continuación, en el menú, en **Directivas**, seleccione **Flujos de usuario (directivas)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada

Para actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada, siga estos pasos.

1. En el directiva **Registrarse e iniciar sesión** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página unificada de inicio de sesión o de registro**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.
1. Seleccione el diseño **Página de registro de cuenta local**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL de registro completa. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.
1. En la sección **Atributos de usuario**, siga estos pasos:

    1. Para los atributos **Dirección de correo electrónico**, **Nombre dado** y **Apellido**, seleccione **No** en el campo **Requiere verificación**.
    1. Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**

    ![Configuración de la directiva Página de registro de cuenta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Actualizar la directiva “Edición de perfiles” con información de página personalizada

Para actualizar la directiva “Edición de perfiles” con información de página personalizada, siga estos pasos.

1. En el directiva **Edición de perfiles** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página de edición de perfil**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL completa de edición de perfil. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.
1. En la sección **Atributos de usuario**, siga estos pasos:

    1. Para los atributos **Dirección de correo electrónico**, **Nombre dado**, seleccione **No**en el campo **Requiere verificación**.
    1. Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en el campo **Opcional**

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada

Para actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada, siga estos pasos.

1. En el directiva **Restablecimiento de página** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página de contraseña nueva**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL completa de restauración de contraseña. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.
1. Seleccione el diseño **Página de verificación de la cuenta**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL completa de verificación de restauración de contraseña. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. En el campo **Versión de Diseño de página (versión preliminar)**, seleccione **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizar cadenas de texto predeterminada para etiquetas y descripciones

En el kit de inicio, los módulos de inicio de sesión se llenan previamente con cadenas de texto predeterminadas para las etiquetas y descripciones. Puede personalizar estas cadenas en el kit de desarrollo de software (SDK) actualizando los valores en el archivo global.json para el módulo de inicio de sesión.

Por ejemplo, el texto predeterminado para el vínculo de contraseña olvidada es **¿Olvidó la contraseña?**. Lo siguiente muestra este texto predeterminado en la página de inicio de sesión.

![Texto predeterminado para el vínculo de contraseña olvidada en la página de inicio de sesión](./media/B2C_SignUp_ModuleFace.png)

Sin embargo, en el archivo global.json para el módulo de inicio de sesión del kit de inicio, puede editar el texto en **¿Olvidó la contraseña?**, como se muestra en la siguiente ilustración.

![Texto de vínculo actualizado en el archivo global.json del módulo de inicio de sesión](./media/B2C_CustomizingStringsForModule.png)

Después de actualizar el archivo global.json y publicar los cambios, el nuevo texto del vínculo aparece en el módulo de inicio de sesión tanto en Commerce como en la página de inicio de sesión activa.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Configurar un canal de la tienda en línea](online-stores.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)
