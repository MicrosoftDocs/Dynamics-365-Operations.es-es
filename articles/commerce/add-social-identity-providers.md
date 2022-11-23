---
title: Agregar proveedores de identidad social
description: Este artículo describe cómo agregar proveedores de identidad social en el portal de Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785278"
---
# <a name="add-social-identity-providers"></a>Agregar proveedores de identidad social

[!include [banner](includes/banner.md)]

Este artículo describe cómo agregar proveedores de identidad social en el portal de Microsoft Azure.

Los proveedores de identidad social permiten a los usuarios usar sus cuentas sociales para la autenticación. La adición de autenticación de proveedor de identidad social es opcional en Dynamics 365 Commerce. 

Si no se agrega la autenticación de proveedor de identidad social, los perfiles predeterminados de Azure Active Directory (Azure AD) B2C serán los perfiles principales para su base de usuarios. Los usuarios seleccionarán su propio nombre de usuario (su dirección de correo electrónico preferida) y establecerán una contraseña. Azure AD B2C autenticará a los usuarios directamente. 

Si se agrega la autenticación de proveedor de identidad social y un usuario elige uno de los proveedores de identidad social ofrecidos, se sigue creando una entidad en el inquilino de Azure AD B2C. Azure AD B2C autenticará las credenciales del usuario con el proveedor de identidad social.

> [!NOTE]
> El inicio de sesión del proveedor de identidad crea un registro en el inquilino de B2C, pero con un formato diferente al de las cuentas locales, ya que llamará a la referencia del proveedor de identidad social externo para la autenticación. El usuario puede usar la misma dirección de correo electrónico en todos los proveedores de identidad social, lo que significa que el nombre de usuario del correo electrónico utilizado para la autenticación puede no ser exclusivo del inquilino. Azure AD B2C solo exigirá que los usuarios tengan una dirección de correo electrónico única en las cuentas locales de B2C.

Antes de poder agregar un proveedor de identidad social para la autenticación, debe ir al portal del proveedor de identidad y configurar una aplicación de proveedor de identidad como se indica en la documentación de Azure AD B2C. A continuación se proporciona una lista de vínculos a la documentación.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Inquilino único)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Cuenta Microsoft](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Agregar y configurar un proveedor de identidad social

> [!NOTE]
> Agregar proveedores de identidad social es un paso opcional al configurar un arrendatario de empresa a consumidor (B2C) en Microsoft Dynamics 365 Commerce.

Para agregar y configurar un proveedor de identidad social, siga estos pasos.  

1. En el portal de Azure, vaya a **Proveedores de identidad**.
1. Seleccione **Agregar**. Aparece la pantalla **Agregar proveedor de identidad**.
1. En **Nombre**, introduzca el nombre que se mostrará a los usuarios en la pantalla de inicio de sesión.
1. En **Tipo de proveedor de identidad**, seleccione un proveedor de identidad de la lista.
1. Seleccione **Aceptar**.
1. Seleccione **Configurar este proveedor de identidad** para acceder a la pantalla **Configurar el proveedor de identidad social**.
1. En **Id. de cliente**, introduzca el identificador de cliente que se obtuvo de la configuración de la aplicación de proveedor de identidad.
1. En **Secreto de cliente**, introduzca el secreto que se obtuvo de la configuración de la aplicación de proveedor de identidad.
1. Adjunte el flujo de usuario para las directivas de inicio de sesión:
1. Vaya a **Azure AD B2C - Flujos de usuarios (directivas) \> {su directiva de inicio de sesión} \> Proveedores de identidad**.
1. Para adjuntar la directiva de flujo de usuario de registro e inicio de sesión, seleccione cada proveedor de identidad que haya configurado para su cuenta. Para probar los flujos, seleccione **Ejecutar flujo de usuario** para cada proveedor de identidad. Una nueva pestaña muestra la página de inicio de sesión con el nuevo cuadro de selección del proveedor de identidad.

La siguiente imagen muestra ejemplos de pantallas **Agregar proveedor de identidad** y **Configurar el proveedor de identidad social** en Azure AD B2C.

![Agregar un proveedor de identidad social a su aplicación.](./media/B2CImage_14.png)

La siguiente imagen muestra un ejemplo de cómo seleccionar proveedores de identidad en la página **Proveedores de identidad** de Azure AD B2C.

![Seleccionar cada proveedor de identidad social que hay que habilitar para su directiva.](./media/B2CImage_16.png)

La siguiente imagen muestra un ejemplo de pantalla de inicio de sesión predeterminada con un botón de inicio de sesión del proveedor de identidad social.

> [!NOTE]
> Si utiliza las páginas personalizadas creadas en Commerce para sus flujos de usuario, los botones para proveedores de identidad social deberán agregarse utilizando las funciones de extensibilidad de la biblioteca del módulo de Commerce. Además, al configurar sus aplicaciones con un proveedor de identidad social específico, en algunos casos la URL o las cadenas de configuración pueden distinguir entre mayúsculas y minúsculas. Consulte las instrucciones de conexión de su proveedor de identidad social para obtener más información.
 
![Ejemplo de pantalla de inicio de sesión predeterminada que muestra el botón de inicio de sesión del proveedor de identidad social.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un arrendatario B2C en Commerce, vaya a [Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
