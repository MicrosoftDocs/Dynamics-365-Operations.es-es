---
title: Información de B2C adicional
description: Este artículo proporciona información adicional sobre cómo configurar su arrendatario de empresa a consumidor (B2C) en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785273"
---
# <a name="additional-b2c-information"></a>Información de B2C adicional

[!include [banner](includes/banner.md)]

Este artículo proporciona información adicional sobre cómo configurar su arrendatario de empresa a consumidor (B2C) en Microsoft Dynamics 365 Commerce.

### <a name="customer-migration"></a>Migración de clientes

Si se está planteando la posibilidad de migrar registros de clientes desde una plataforma de proveedor de identidad anterior, trabaje con el equipo de Dynamics 365 Commerce para revisar sus necesidades de migración de clientes.

Para adicional obtener documentación adicional de Azure AD B2C sobre migración de clientes, consulte [Migrar usuarios a Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Directivas personalizadas

Para obtener información adicional sobre la personalización de las interacciones y los flujo de directiva de Azure AD más allá de lo que ofrecen las directivas estándar de B2C, consulte [Directivas personalizadas en Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrador secundario

Se puede agregar una cuenta de administrador secundario opcional en la sección **Usuarios** del inquilino de B2C. Puede ser una cuenta directa o una cuenta general. Si necesita compartir una cuenta entre los recursos del equipo, también puede crear una cuenta común. Por la confidencialidad de los datos almacenados en Azure AD B2C, una cuenta común debe supervisarse estrechamente siguiendo los procedimientos de seguridad de la empresa.

### <a name="set-up-a-custom-sign-in-domain"></a>Configurar un dominio de inicio de sesión personalizado

Azure AD B2C le permite configurar un dominio de inicio de sesión personalizado para el inquilino B2C de Azure AD. Para obtener instrucciones, consulte [Habilitar dominios personalizados para Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

Si usa un dominio de inicio de sesión personalizado, el dominio debe ingresarse en el creador de sitios de Commerce.

Para introducir un dominio de inicio de sesión en el generador de sitios, siga estos pasos.

1. En la esquina superior derecha del generador de sitios, seleccione el conmutador de sitios y luego seleccione **Administrar sitios**.
1. En el panel de navegación izquierdo, seleccione **Configuración de inquilino \> Configuración de autenticación del sitio**.
1. En la sección **Perfiles de autenticación del sitio**, seleccione **Gestionar**.
1. En el menú desplegable de la derecha, seleccione el botón **Editar** (símbolo de lápiz) junto al perfil de autenticación del sitio para el que desea ingresar un dominio personalizado.
1. En el cuadro de diálogo **Editar perfil de autenticación del sitio**, bajo **Iniciar sesión dominio personalizado**, ingrese su dominio de inicio de sesión personalizado (por ejemplo, 'login.fabrikam.com').

> [!WARNING]
> Cuando actualiza a un dominio personalizado para el Arrendatario de Azure AD B2C, el cambio afecta los detalles del emisor del arrendatario para el token generado. Los detalles del emisor incluirán el dominio personalizado en lugar del dominio predeterminado proporcionado por Azure AD B2C. Una configuración de **Editor** diferente en la sede de Comercio (**Retail y Commerce \> Configuración de la sede \> Parámetros \> Parámetros compartidos de Commerce \> Proveedores de identidad**) cambia la interacción del sistema con los usuarios del sitio, creando potencialmente un nuevo registro de cliente si un usuario se está autenticando contra el nuevo emisor. Cualquier cambio de dominio personalizado debe probarse a fondo antes de cambiar al dominio personalizado en un entorno de Azure AD B2C activo.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md)

[Crear o vincular un inquilino de Azure AD B2C existente en el portal de Azure](create-link-aad-b2c-tenant.md)

[Crear la aplicación B2C](create-b2c-app.md)

[Crear directivas de flujo de usuario](create-user-flow-policies.md)

[Agregar proveedores de identidad social (opcional)](add-social-identity-providers.md)

[Actualizar Commerce headquarters con la nueva información de Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurar su inquilino de B2C en el generador de sitios de Commerce](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
