---
title: Crear directivas de flujo de usuario
description: Este artículo describe cómo crear políticas de flujo de usuarios en el portal de Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785309"
---
# <a name="create-user-flow-policies"></a>Crear directivas de flujo de usuario

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear políticas de flujo de usuarios en el portal de Microsoft Azure.

Los flujos de usuario son las directivas que usa Azure Active Directory (Azure AD) B2C utiliza para proporcionar experiencias de usuario de inicio de sesión seguro, registro, edición de perfil y restablecimiento de contraseña. Dynamics 365 Commerce utiliza estos flujos para realizar las acciones de directiva a fin de interactuar con el inquilino de Azure AD B2C. Cuando un usuario interactúa con estas directivas, se redirigen al inquilino de Azure AD B2C para realizar las acciones.

Azure AD B2C proporciona tres tipos básicos de flujo de usuario:
- Registro e inicio de sesión
- Edición de perfil
- Contraseña restablecida

Puede optar por usar los flujos de usuario predeterminados proporcionados por Azure AD, que mostrarán una página hospedad en Azure AD B2C. Como alternativa, puede crear una página HTML para controlar la apariencia de estas experiencias de flujo de usuario. 

Para personalizar las páginas de directiva de usuario con páginas incluidas en Dynamics 365 Commerce, consulte [Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md). Para obtener más información, consulte [Personalizar las experiencias de interfaz de usuario en Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Crear una directiva de flujo de usuario registro e inicio de sesión

Para crear una directiva de flujo de usuario de registro e inicio de sesión, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione la directiva **Registro e iniciar sesión** y después seleccione la versión **Recomendada**.
1. En **Nombre**, escriba un nombre de directiva. Este nombre se mostrará posteriormente con un prefijo asignado por el portal (por ejemplo, "B2C_1_").
1. Bajo **Proveedores de identidad**, en la sección **Cuentas locales**, seleccione **Registro de correo electrónico**. La autenticación de correo electrónico se usa en los escenarios más comunes para Commerce. Si también está utilizando la autenticación del proveedor de identidad social, también puede seleccionarlo en este momento.
1. En **Autenticación multifactor**, seleccione la opción adecuada para su empresa. 
1. En **Atributos y devoluciones de usuario**, seleccione opciones para recopilar atributos o notificaciones de devolución, según corresponda. Seleccione **Mostrar más...** para obtener la lista completa de atributos y opciones de notificaciones. Commerce requiere las siguientes opciones predeterminadas:

    | **Recopilar atributo** | **Notificación de devolución** |
    | ---------------------- | ----------------- |
    | Dirección de correo electrónico          | Direcciones de correo electrónico   |
    | Nombre propio             | Nombre propio        |
    |                        | Proveedor de identidades |
    | Apellido                | Apellido           |
    |                        | ID de objeto del usuario  |

1. Seleccione **Crear**.

La siguiente imagen es un ejemplo de flujo de usuario de registro e inicio de sesión de Azure AD B2C.

![Configuración de la directiva de registro e inicio de sesión.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Crear una directiva de flujo de usuario de edición de perfil

Para crear una directiva de flujo de usuario de edición de perfil, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione **Edición de perfil** y luego seleccione la versión **Recomendado**.
1. En **Nombre**, introduzca el flujo de usuario de edición de perfil. Este nombre se mostrará posteriormente con un prefijo asignado por el portal (por ejemplo, "B2C_1_").
1. Bajo **Proveedores de identidad**, en la sección **Cuentas locales**, seleccione **SignIn de correo electrónico**.
1. En **Atributos de usuario**, active las siguientes casillas:
    
    | **Recopilar atributo** | **Notificación de devolución** |
    | ---------------------- | ----------------- |
    |                        | Direcciones de correo electrónico   |
    | Nombre propio             | Nombre propio        |
    |                        | Proveedor de identidades |
    | Apellido                | Apellido           |
    |                        | ID de objeto del usuario  |
    
1. Seleccione **Crear**.

La siguiente imagen muestra un ejemplo de flujo de usuario de edición de perfil de Azure AD B2C.

![Ejemplo del flujo de usuario de edición de perfil de Azure AD B2C](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Crear una directiva de flujo de usuario de restablecimiento de contraseña

Para crear una directiva de flujo de usuario de restablecimiento de contraseña, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione **Restablecer contraseña** y luego seleccione la versión **Recomendado**.
1. En **Nombre**, introduzca un nombre para el flujo de usuario de restablecimiento de contraseña.
1. En **Proveedores de identidad**, seleccione **Restablecer contraseña con dirección de correo electrónico**.
1. Seleccione **Crear**.
1. En **Notificaciones de aplicación**, active las siguientes casillas:
    - **Direcciones de correo electrónico**
    - **Nombre propio**
    - **Apellido**
    - **ID de objeto del usuario**
1. Seleccione **Crear**.

La siguiente imagen muestra dónde se establece **Restablecer contraseña con dirección de correo electrónico** en el flujo de usuario de restablecimiento de contraseña de Azure AD B2C.

![Establezca "Restablecer contraseña con dirección de correo electrónico" en la directiva de restablecimiento de contraseña](./media/B2CImage_13.png)

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un arrendatario B2C en Commerce, vaya a [Agregar proveedores de identidad sociales](add-social-identity-providers.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
