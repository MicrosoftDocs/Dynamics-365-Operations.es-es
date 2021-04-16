---
title: Configurar páginas personalizadas para inicios de sesión de usuario
description: Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0318814f421ab862559965bb4b003308d6279812
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799454"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Configurar páginas personalizadas para inicios de sesión de usuario

[!include [banner](includes/banner.md)]

Este tema describe cómo crear páginas personalizadas en Microsoft Dynamics 365 Commerce que administran inicios de sesión personalizados para usuarios de inquilinos de negocio a consumidor (B2C) de Azure Active Directory (Azure AD).

Para usar páginas personalizadas que se crean en Dynamics 365 Commerce para gestionar los flujos de inicio de sesión de usuario, debe configurar las directivas de Azure AD a las que se hará referencia en el entorno de Commerce. Puede configurar las directivas B2C de Azure AD "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña" mediante la aplicación B2C de Azure AD. Se puede hacer referencia a continuación a los nombres de directiva e inquilino B2C de Azure AD durante el proceso de abastecimiento que se realiza para el entorno de Commerce mediante Lifecycle Services (LCS) de Microsoft Dynamics.

Las páginas personalizadas de Commerce se pueden crean mediante el módulo de restablecimiento de contraseña, edición de perfil de cuenta o módulos AAD genéricos. A continuación, se hará referencia a las direcciones URL de página que se publican para estas páginas personalizadas en las configuraciones de directiva B2C de Azure AD en el portal de Azure.

> [!WARNING] 
> Azure AD B2C retirará los flujos de usuarios antiguos (heredados) antes del 1 de agosto de 2021. Por lo tanto, debe planear migrar sus flujos de usuarios a la nueva versión recomendada. La nueva versión proporciona paridad de funciones y nuevas funciones. Para obtener más información, vea [Flujos de usuario en Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/user-flow-overview).

>La biblioteca de módulos para Commerce versión 10.0.15 o superior debe usarse con los flujos de usuarios B2C recomendados. Las páginas de política de usuario predeterminadas que se ofrecen en Azure AD B2C también se puede utilizar y permitir cambios adicionales en la imagen de fondo, el logotipo y el color de fondo relacionados con la marca de la empresa. Aunque más limitadas en capacidades de diseño, las páginas de políticas de usuario predeterminadas proporcionan funcionalidad de directivas a Azure AD B2C sin crear y configurar páginas personalizadas dedicadas. 

## <a name="set-up-b2c-policies"></a>Configurar directivas B2C

Después de configurar su inquilino B2C de Azure AD y de asociarlo con su entorno de Commerce, vaya a la página **Azure AD B2C** en el portal de Azure y, a continuación, en **Directivas**, seleccione **Flujos de usuario (directivas)**.

![Comando Flujos de usuario (directivas) del menú](./media/B2C_CustomPage_PoliciesMenu.png)

Ahora puede configurar los flujos de inicio de sesión de usuario "Registrarse e iniciar sesión", "Edición de perfiles" y "Restablecimiento de contraseña".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurar la directiva “Registrarse e iniciar sesión"

Para configurar la directiva “Registrarse e iniciar sesión”, siga estos pasos.

1. Seleccione **Nuevo flujo de usuario**, seleccione **Iniciar sesión e iniciar sesión**, seleccione la pestaña **Recomendado** y después seleccione **Crear**.
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

1. Seleccione **Nuevo flujo de usuario**, seleccione **Editar perfil**, seleccione la pestaña **Recomendado** y después seleccione **Crear**.
1. Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_EditProfile**).
1. En la sección **Proveedores de identidades**, seleccione los proveedores de identidades que se utilizarán para la directiva. Como mínimo, la opción **Inicio de sesión de cuenta local** debe estar seleccionada.
1. En la columna **Recopilar atributo**, seleccione las casillas para **Nombre** y **Apellido**.
1. En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Proveedor de identidades**, **Apellido** e **Id. de objeto de usuario**.
1. Seleccione **Aceptar** para crear la directiva.
1. Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.
1. Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.

Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas. Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.

### <a name="configure-the-password-reset-policy"></a>Configurar la directiva "Restablecimiento de contraseña"

Para configurar la directiva "Restablecimiento de contraseña", siga estos pasos.

1. Seleccione **Nuevo flujo de usuarios**, luego seleccione la opción **Restablecimiento de contraseña**, elija la pestaña **Recomendado** pestaña y haga clic en **Crear**.
1. Especifique un nombre para la directiva (por ejemplo, **B2C\_1\_ForgetPassword**).
1. En la sección **Proveedores de identidades**, seleccione **Restablecer contraseña con dirección de correo electrónico**.
1. En la columna **Notificación de devolución**, seleccione las casillas para **Direcciones de correo electrónico**, **Nombre dado**, **Apellido** e **Id. de objeto de usuario**.
1. Seleccione **Aceptar** para crear la directiva.
1. Haga doble clic en el nuevo nombre de la directiva y, a continuación, en el panel de navegación, seleccione **Propiedades**.
1. Establezca la opción **Habilitar JavaScript aplicando el diseño de página (versión preliminar)** en **Activado**.

Se le devolverá a esta directiva para terminar la configuración después de haber creado las páginas personalizadas. Por ahora, cierre la directiva para volver a la página **Flujos de usuario (directivas)** del portal de Azure.

## <a name="build-the-custom-pages"></a>Compilar las páginas personalizadas

Los módulos dedicados de Azure AD se incluyen en Commerce para crear páginas personalizadas para directivas de usuario de Azure AD B2C. Las páginas se pueden crear específicamente para el diseño de la página de la política de cada usuario utilizando los módulos Azure AD B2C detallados a continuación. Alternativamente, el módulo **AAD genérico** se puede utilizar para todos los diseños de página y políticas en Azure AD B2C (incluso para opciones de diseño de página dentro de políticas que no se enumeran a continuación). 

- Los módulos específicos de página de Azure AD están vinculados a elementos de entrada de datos representados por Azure AD B2C. Estos módulos le dan más control sobre el posicionamiento de los elementos en sus páginas. Sin embargo, es posible que sea necesario crear más páginas y extensiones de módulo para tener en cuenta las variaciones más allá de la configuración predeterminada que se describe a continuación.
- El módulo **AAD genérico** crea el elemento "div" para Azure AD B2C para representar todos los elementos en el diseño de la página de la directiva del usuario, dando más flexibilidad a las funciones B2C de la página, pero menos control del posicionamiento y estilo (aunque CSS se puede utilizar para que coincida con la apariencia de su sitio).

Puede crear una sola página con el módulo **AAD genérico** y utilícelo para todas sus páginas de políticas de usuario, o puede crear páginas específicas utilizando módulos Azure AD individuales para inicio de sesión, registro, edición de perfil, restablecimiento de contraseña y verificación de restablecimiento de contraseña. También puede usar una combinación de ambos, usando páginas específicas de Azure AD para los diseños de página que se indican a continuación y la página del módulo AAD genérico para los diseños de página restantes dentro de estas u otras páginas de directivas de usuario.

Para aprender más sobre los módulos Azure AD que se envían con la biblioteca de módulos, lea más en [Páginas y módulos de gestión de identidad](identity-mgmt-modules.md).

Para compilar las páginas personalizada con módulos de identidad específicos para administrar inicios de sesión de usuario, siga estos pasos.

1. En el generador de sitios de Commerce, vaya a su sitio.
1. Cree las siguientes cinco plantillas y páginas (si aún no están presentes en su sitio):
    - Una plantilla de **Iniciar sesión** y una página que usan el módulo de inicio de sesión.
    - Una plantilla de **Registrarse** y una página que usan el módulo de registro.
    - Una página y plantilla de **Restablecimiento de contraseña** que usan el módulo de restablecimiento de contraseña.
    - Una página y plantilla de **Verificación de restablecimiento de contraseña** que usan el módulo de verificación de restablecimiento de contraseña.
    - Una página y plantilla de **Edición de perfil** que usan el módulo de edición del perfil de cuenta.

Al compilar las páginas, siga estas directrices:

- Para cada página o módulo, utilice el diseño y el estilo que mejor se adapten a sus requisitos empresariales.
- Publique todas las páginas y direcciones URL que se deben usar en la configuración de Azure AD B2C.
- Una vez que se publiquen las páginas y las direcciones URL, recoja las direcciones URL que se deben utilizar para las configuraciones de la directiva de Azure AD B2C. Se agregará un sufijo **?preloadscripts=true** a cada dirección URL cuando se use.

> [!IMPORTANT]
> Páginas creadas para ser referenciadas en Azure AD B2C se sirven directamente desde el dominio del inquilino de Azure AD B2C. No reutilice pies de página y encabezados y universales que tengan vínculos relativos. Dado que estas páginas se hospedarán en el dominio de Azure AD B2C cuando se usen, solo se deben usar direcciones URL absolutas para todos los vínculos. Se recomienda crear un encabezado y pie de página específicos con URL absolutas para sus páginas personalizadas relacionadas con Azure AD, con cualquier módulo específico de Commerce que requiera conexión a Retail Server eliminado. Por ejemplo, los favoritos, la barra de búsqueda, el enlace de inicio de sesión y los módulos de carrito no deben incluirse en ninguna página que se utilizará en flujos de usuario de Azure AD B2C.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurar directivas de Azure AD B2C con la información de página personalizada 

En el portal de Azure, vuelva a la página de **Azure AD B2C** y, a continuación, en el menú, en **Directivas**, seleccione **Flujos de usuario (directivas)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada

Para actualizar la directiva “Registrarse e iniciar sesión” con información de página personalizada, siga estos pasos.

1. En el directiva **Registrarse e iniciar sesión** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página unificada de inicio de sesión o de registro**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL de inicio de sesión completa. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. En el campo **Versión de diseño de página**, seleccione la versión **2.1.0** o posterior (requiere biblioteca de módulos para Commerce versión 10.0.15 o superior).
1. Seleccione **Guardar**.
1. Seleccione el diseño **Página de registro de cuenta local**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL de registro completa. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. En el campo **Versión de diseño de página**, seleccione la versión **2.1.0** o posterior (requiere biblioteca de módulos para Commerce versión 10.0.15 o superior).
1. En la sección **Atributos de usuario**, siga estos pasos:
    1. Para los atributos **Nombre** y **Apellido**, seleccione **No** en la columna **Requiere verificación**.
    1. Para el atributo **Dirección de correo electrónico**, se recomienda dejar el valor predeterminado en **Sí** seleccionado en la columna **Requiere Verificación**. Esta opción garantiza que los usuarios que se registren con una dirección de correo electrónico determinada verifiquen que son propietarios de la dirección de correo electrónico.
    1. Para los atributos **Dirección de correo electrónico**, **Nombre dado** y **Apellido**, seleccione **No** en la columna **Opcional**.
1. Seleccione **Guardar**.

    ![Configuración de la directiva Página de registro de cuenta local](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Actualizar la directiva “Edición de perfiles” con información de página personalizada

Para actualizar la directiva “Edición de perfiles” con información de página personalizada, siga estos pasos.

1. En el directiva **Edición de perfiles** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página de edición de perfil** (puede requerir desplazarse hacia abajo más allá de otras opciones de diseño, según su pantalla).
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL completa de edición de perfil. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Para **Versión de diseño de página**, seleccione la versión **2.1.0** o superior (requiere biblioteca de módulos para Commerce versión 10.0.15 o superior).
1. En la sección **Atributos de usuario**, siga estos pasos:
    1. Para los atributos **Nombre dado** y **Apellido**, seleccione **No** en la columna **Opcional**.
    1. Para los atributos **Nombre** y **Apellido**, seleccione **No** en la columna **Requiere verificación**.
1. Seleccione **Guardar**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada

Para actualizar la directiva “Restablecimiento de contraseña” con información de página personalizada, siga estos pasos.

1. En el directiva **Restablecimiento de página** que ha configurado anteriormente, en el panel de navegación, seleccione **Diseños de página**.
1. Seleccione el diseño **Página de contraseña olvidada**.
1. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
1. En el campo **URI de página personalizado**, especifique la dirección URL completa de verificación de restauración de contraseña. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. En el campo **Versión de diseño de página**, seleccione la versión **2.1.0** o superior (requiere biblioteca de módulos para Commerce versión 10.0.15 o superior).
2. Seleccione **Guardar**.
3. Seleccione el diseño **Página de cambio de contraseña**.
4. Establezca la opción **Usar contenido de la página personalizada** en **Sí**.
5. En el campo **URI de página personalizado**, especifique la dirección URL completa de restauración de contraseña. Incluir el sufijo **?preloadscripts=true**. Por ejemplo, escriba ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. En el campo **Versión de diseño de página**, seleccione la versión **2.1.0** o superior (requiere biblioteca de módulos para Commerce versión 10.0.15 o superior).
7. Seleccione **Guardar**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizar cadenas de texto predeterminada para etiquetas y descripciones

En la biblioteca de módulos, los módulos de inicio de sesión se llenan previamente con cadenas de texto predeterminadas para las etiquetas y descripciones. Puede personalizar las cadenas en el panel de propiedades del módulo en el que está trabajando. Cadenas adicionales en la página (como el enlace de texto **¿Contraseña olvidada?** o el texto de llamada a la acción **Crea una cuenta**) requerirá el uso del kit de desarrollo de software (SDK) de Commerce y la actualización de los valores en el archivo global.json para el módulo de inicio de sesión.

Por ejemplo, el texto predeterminado para el vínculo de contraseña olvidada es **¿Olvidó la contraseña?**. Lo siguiente muestra este texto predeterminado en la página de inicio de sesión.

![Texto predeterminado para el vínculo de contraseña olvidada en la página de inicio de sesión](./media/B2C_SignUp_ModuleFace.png)

Sin embargo, en el archivo global.json para el módulo de inicio de sesión de la biblioteca de módulos, puede editar el texto en **¿Olvidó la contraseña?**, como se muestra en la siguiente ilustración.

![Texto de vínculo actualizado en el archivo global.json del módulo de inicio de sesión](./media/B2C_CustomizingStringsForModule.png)

Después de actualizar el archivo global.json y publicar los cambios, el nuevo texto del vínculo aparece en el módulo de inicio de sesión tanto en Commerce como en la página de inicio de sesión activa.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
