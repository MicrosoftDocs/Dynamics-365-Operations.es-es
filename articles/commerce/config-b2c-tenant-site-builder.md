---
title: Configurar su inquilino de B2C en el generador de sitios de Commerce
description: En este artículo se describe cómo configurar el inquilino de empresa a consumidor (B2C) en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785314"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurar su inquilino de B2C en el generador de sitios de Commerce

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar el inquilino de empresa a consumidor (B2C) en el generador de sitios de Microsoft Dynamics 365 Commerce.

Una vez configurado el inquilino de Azure AD B2C, debe configurar el inquilino de B2C en el generador de sitios de Commerce. Los pasos de configuración incluyen recopilar información de la aplicación B2C desde el portal de Azure, introducir esa información de la aplicación B2C en el generador de sitios y, a continuación, asociar la aplicación B2C a su sitio y canal.

### <a name="collect-the-required-application-information"></a>Recopilar la información de aplicación necesaria

Para recopilar la información de la aplicación necesaria, siga estos pasos.

1. En el portal de Azure, vaya a **Inicio \> Azure AD B2C - Registros de aplicaciones**.
1. Seleccione la aplicación y, a continuación, en el panel de navegación izquierdo, seleccione **Información general** para obtener los detalles de la aplicación.
1. En la referencia **Id. de (cliente de) aplicación**, recopile el Id. de la aplicación B2C creada en el inquilino de B2C. Posteriormente, este identificador se introducirá como **GUID de cliente** en el generador de sitios.
1. Seleccione **URI de redirección** y recopile la URL de respuesta que se muestra para su sitio (la URL de respuesta ingresada en la configuración).
1. Vaya a **Inicio \> Azure AD B2C - Flujos de usuario (directivas)** y, a continuación, recopile los nombres completos de cada directiva de flujo de usuario.

La siguiente imagen muestra un ejemplo de la página de información general **Azure AD B2C - Registros de aplicaciones**.

![Azure AD B2C: página de resumen de registros de aplicaciones con el ID de la aplicación (cliente) resaltado](./media/ClientGUID_Application_AzurePortal.png)

La siguiente imagen muestra un ejemplo de directivas de flujo de usuario en la página **Azure AD B2C - Flujos de usuarios (directivas)**.

![Recopilar los nombres de cada flujo de directiva de B2C.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Introducir en Commerce la información de su aplicación de inquilino de Azure AD B2C

Debe introducir los detalles del inquilino de Azure AD B2C en el generador de sitios de Commerce antes de asociar el inquilino de B2C a sus sitios.

Para agregar a Commerce la información de su aplicación de inquilino de Azure AD B2C, siga estos pasos.

1. Inicie sesión como administrador en el generador de sitios de Commerce para su entorno.
1. En el panel de navegación izquierdo, seleccione el nodo **Configuración de inquilino** para expandirlo.
1. Bajo **Configuración del inquilino**, seleccione **Configuración de la autenticación del sitio**. 
1. En la ventana principal junto a **Perfiles de autenticación del sitio**, seleccione **Gestionar**. (Si su inquilino aparece en la lista de perfiles de autenticación del sitio, significa que ya lo agregó un administrador. Compruebe que los elementos del paso 6 a continuación correspondan a los de la configuración B2C prevista. También se puede crear un nuevo perfil usando similares Inquilinos de Azure AD B2C o aplicaciones para tener en cuenta diferencias menores, como diferentes ID de políticas de usuario).
1. Seleccione **Agregar perfil de autenticación de sitio**.
1. Introduzca los siguientes elementos obligatorios en el formulario que se muestra, utilizando los valores del inquilino de B2C y la aplicación B2C. Los campos que no son obligatorios (los que no muestran un asterisco) pueden dejarse en blanco.

    - **Nombre de la aplicación**: el nombre de la aplicación B2C (por ejemplo, "Fabrikam B2C").
    - **Nombre del inquilino**: el nombre de su inquilino B2C (por ejemplo, use "fabrikam" si el dominio aparece como "fabrikam.onmicrosoft.com" para el inquilino B2C). 
    - **Id. de directiva de restablecimiento de contraseña**: el id. de la directiva del flujo de usuario de restablecimiento de contraseña (por ejemplo, "B2C_1_PasswordReset").
    - **Id. de directiva de registro e inicio de sesión**: el id. de la directiva de registro e inicio de sesión (por ejemplo, "B2C_1_signup_signin").
    - **GUID del cliente**: el id. de la aplicación B2C (por ejemplo, "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6").
    - **Id. de directiva de edición de perfil**: el id. de la directiva del flujo de usuario de edición de perfil (por ejemplo, "B2C_1A_ProfileEdit").

1. Seleccione **Aceptar**. Ahora debería ver el nombre de su aplicación B2C en la lista.
1. Seleccione **Guardar** para guardar los cambios.

El campo opcional **Iniciar sesión dominio personalizado** solo debe usarse si está configurando un dominio personalizado para el inquilino B2C de Azure AD. Para detalles adicionales y consideraciones sobre el uso del campo **Iniciar sesión dominio personalizado**, vea [Información B2C adicional](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Asociar la aplicación B2C a su sitio y canal

> [!WARNING]
> - Si su sitio ya está asociado a una aplicación B2C, al cambiar a una aplicación B2C distinta se eliminarán las referencias actuales establecidas para los usuarios que ya se han registrado en este entorno. Si se hace el cambio, las credenciales asociadas con la aplicación B2C asignada actualmente no estarán disponibles para los usuarios. 
> - Solo debe actualizar la aplicación B2C si va a configurar la aplicación B2C del canal por primera vez o si tiene la intención de hacer que los usuarios vuelvan a registrarse con nuevas credenciales para este canal con la nueva aplicación B2C. Tenga cuidado al asociar canales a aplicaciones B2C, y asigne nombres claros a las aplicaciones. Si un canal no se asocia a una aplicación B2C en los pasos siguientes, los usuarios que inicien sesión en ese canal del sitio se introducirán en la aplicación B2C que se muestra como **predeterminada** en la lista **Configuración del inquilino \> Configuración de B2C** de aplicaciones B2C.

Para asociar la aplicación B2C a su sitio y canal, siga estos pasos.

1. Vaya a su sitio en el generador de sitios de Commerce.
1. En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo
1. Bajo **Configuración del sitio**, seleccione **Canales**.
1. En la ventana principal bajo **Canales**, seleccione su canal.
1. En el panel de propiedades del canal a la derecha, seleccione el nombre de su aplicación B2C en el menú desplegable **Seleccionar aplicación B2C**.
1. Seleccione **Cerrar** y, a continuación, seleccione **Guardar y publicar**.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un arrendatario B2C en Commerce, vaya a [Información B2C adicional](additional-b2c-info.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
