---
title: Crear una aplicación B2C
description: Este artículo describe cómo crear una aplicación de empresa a consumidor (B2C) en el portal de Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785291"
---
# <a name="create-a-b2c-application"></a>Crear una aplicación B2C

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear una aplicación de empresa a consumidor (B2C) en el portal de Microsoft Azure.

Cuando se haya creado su inquilino de B2C, usted podrá crear una aplicación B2C en su nuevo inquilino de Azure Active Directory (Azure AD) para interactuar con Commerce.

Para crear la aplicación B2C, siga estos pasos.

1. En Azure Portal, seleccione **Registros de aplicaciones** y luego seleccione **Nuevo registro**.
1. En **Nombre**, introduzca el nombre para darle a esta aplicación Azure AD B2C.
1. En **Tipos de cuenta admitidos**, seleccione **Cuentas en cualquier proveedor de identidad o directorio organizacional (para autenticar usuarios con flujos de usuarios)**.
1. Para **Redirigir URI**, introduzca sus URL de respuesta dedicadas como tipo **Web**. Para obtener información sobre las URL de respuesta y qué formato aplicarles, consulte [Direcciones URL de respuesta](#reply-urls) a continuación. Se debe ingresar un URI de redirección/URL de respuesta para habilitar las redirecciones desde Azure AD B2C vuelve a su sitio cuando un usuario se autentica. La URL de respuesta se puede agregar durante el proceso de registro o se puede agregar más tarde seleccionando el enlace **Agregar un URI de redirección** desde el menú **Descripción general** en la sección **Descripción general** aplicación B2C.
1. Para **Permisos**, seleccione **Otorgar consentimiento del administrador a los permisos openid y offline_access**.
1. Seleccione **Registrar**.
1. Seleccione la aplicación recién creada y navegue hasta el menú **Autenticación**. 
1. Si se introduce una URL de respuesta, en **Concesión implícita y flujos híbridos** seleccione las dos opciones **Tokens de acceso** y **Tokens de identificación** para habilitarlas para la aplicación y, a continuación, seleccione **Guardar**. Si no se ingresó una URL de respuesta durante el registro, también se puede agregar en esta página seleccionando **Agregar una plataforma**, seleccionando **Web** y luego introduciendo el URI de redirección de la aplicación. La sección **Concesión implícita y flujos híbridos** estará disponible para seleccionar las dos opciones **Tokens de acceso** y **Tokens de identificación**.
1. Vaya al menú **Visión general** menú de Azure Portal y copie el **ID de aplicación (cliente)**. Anote esta ID para los pasos de configuración posteriores (a la que se hace referencia más adelante como **GUID del cliente**).

Para obtener más información sobre los registros de aplicaciones en Azure AD B2C, consulte [La nueva experiencia de registro de aplicaciones para Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>Direcciones URL de respuesta

Las direcciones URL de respuesta son importantes, ya que ofrecen una lista de permitidos de los dominios de retorno cuando su sitio llama a Azure AD B2C para autenticar a un usuario. Esto posibilita que el usuario autenticado regrese al dominio desde el que inició sesión (el dominio de su sitio). 

En el cuadro **Dirección URL de respuesta** de la pantalla **Azure AD B2C - Aplicaciones \> Nueva aplicación** debe agregar líneas independientes para el dominio de su sitio y (una vez que se haya aprovisionado el entorno) la dirección URL generada por Commerce. Estas direcciones URL siempre deben usar un formato de URL válido y deben ser direcciones URL base únicamente (sin barras diagonales ni rutas). Hay que agregar a las direcciones URL base la cadena ``/_msdyn365/authresp``, como en los siguientes ejemplos.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (El dominio debe coincidir completamente con el dominio de comercio electrónico. Si tiene varios dominios, debe agregar esta URL para cada dominio.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>Pasos siguientes

Para continuar con el proceso de configuración de un arrendatario B2C en Commerce, vaya a [Crear directivas de flujo de usuario](create-user-flow-policies.md).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)

[Información de B2C adicional](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
