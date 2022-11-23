---
title: Actualizar la sede de Commerce con la nueva información de Azure AD B2C
description: Este artículo describe cómo actualizar Microsoft Dynamics 365 Commerce headquarters con la nueva información de empresa a consumidor (B2C) de Azure Active Directory (Azure AD).
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785327"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Actualizar la sede de Commerce con la nueva información de Azure AD B2C

[!include [banner](includes/banner.md)]

Este artículo describe cómo actualizar Microsoft Dynamics 365 Commerce headquarters con la nueva información de empresa a consumidor (B2C) de Azure Active Directory (Azure AD).

Una vez completados los pasos de aprovisionamiento de Azure AD B2C antes mencionados, la aplicación Azure AD B2C debe registrarse en su entorno de Dynamics 365 Commerce.

Para actualizar la sede con la nueva información de Azure AD B2C, siga estos pasos.

1. En Commerce, vaya a **Parámetros compartidos de Commerce** y seleccione **Proveedores de identidad** en el menú de la izquierda.
1. En **Proveedores de identidad**, haga lo siguiente:
    1. En el cuadro **Emisor**, introduzca la dirección de la cadena del emisor del proveedor de identidad. Para encontrar su cadena de emisor, consulte [Obtener cadena de emisor para la configuración de la sede central](#obtain-issuer-string-for-headquarters-setup) más abajo.
    1. En el cuadro **Nombre**, escriba un nombre para el registro de emisor.
    1. En el cuadro **Tipo**, introduzca **Azure AD B2C (id_token)**.
1. En **Partes dependientes**, con el elemento de proveedor de identidad B2C anterior seleccionado, haga lo siguiente:
    1. En el cuadro **ClientID**, escriba su id. de aplicación B2C, que puede encontrar en el cuadro **Id. de aplicación** de la página de propiedades de su aplicación B2C.
    1. En el cuadro **Tipo**, introduzca **Público**.
    1. En el cuadro **Tipo de usuario**, introduzca **Cliente**.
1. En el panel de acciones, seleccione **Guardar**.
1. En el cuadro de búsqueda de Commerce, busque **Programación de distribución**
1. En el menú de navegación izquierdo de la página **Programaciones de distribución**, seleccione el trabajo **1110 Configuración global**.
1. En el panel de acciones, seleccione **Ejecutar ahora**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Obtener cadena de emisor para la configuración de la sede central

Para obtener la cadena del emisor de proveedor de identidad, siga estos pasos.

1. En la página Azure AD B2C del portal de Azure, vaya a su flujo de usuario **Registro e inicio de sesión**.
1. Seleccione **Diseños de página** en el menú de navegación de la izquierda, en **Nombre del diseño** seleccione **Página unificada de registro o inicio de sesión** y luego seleccione **Ejecutar el flujo de usuarios**.
1. Asegúrese de que su aplicación esté configurada para su aplicación Azure AD B2C creada anteriormente y luego seleccione el enlace del flujo de usuario que aparece en el encabezado **Ejecutar el flujo de usuarios** que incluye ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (No seleccione **Ejecutar flujo de usuarios**). Se abrirá una nueva pestaña que muestra los metadatos de la directiva para recopilar la cadena del emisor.
1. En la página de metadatos que se muestra en la pestaña de su navegador, copie la cadena del emisor del proveedor de identidad (el valor para **emisor** empezando con "https://" y que termina con "/v2.0/") que se parece al siguiente ejemplo.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**O**: para construir la misma URL de metadatos manualmente, siga los siguientes pasos.

1. Utilice su directiva y su inquilino de B2C para crear una dirección URL de metadatos con el siguiente formato: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Ejemplo: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Introduzca la dirección URL de metadatos en la barra de direcciones del explorador.
1. En los metadatos, copie la dirección URL del emisor del proveedor de identidad (el valor de **"emisor"**).
    - Ejemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un inquilino B2C en Commerce, continúe con [Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
