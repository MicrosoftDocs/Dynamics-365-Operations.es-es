---
title: Configurar múltiples inquilinos B2C en un entorno de Commerce
description: Este tema describe cuándo y cómo configurar múltiples inquilinos de empresa a consumidor (B2C) por canal Microsoft Azure Active Directory (Azure AD) para la autenticación de usuarios en un entorno dedicado Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: d0b14e0c662af74464768b66c1c86d03d2944014
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976025"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a>Configurar múltiples inquilinos B2C en un entorno de Commerce

[!include [banner](includes/banner.md)]

Este tema describe cuándo y cómo configurar múltiples inquilinos de empresa a consumidor (B2C) por canal Microsoft Azure Active Directory (Azure AD) para la autenticación de usuarios en un entorno dedicado Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Dynamics 365 Commerce usa el servicio de identidad en la nube Azure AD B2C para admitir credenciales de usuario y flujos de autenticación. Los usuarios pueden usar los flujos de autenticación para registrarse, iniciar sesión y restablecer su contraseña. Azure AD B2C almacena la información confidencial de autenticación de un usuario, como su nombre de usuario y contraseña. El registro de usuario es exclusivo de cada inquilino B2C y utiliza credenciales de nombre de usuario (dirección de correo electrónico) o credenciales de proveedor de identidad social.

En la mayoría de los casos, solo se usa un inquilino Azure AD B2C en un entorno de Commerce. Los clientes de Commerce pueden crear y publicar múltiples sitios en el mismo entorno de Commerce, y las mismas credenciales de clientes se utilizarán en estos sitios. Sin embargo, si los sitios en el entorno deben tratarse como marcas diferentes y aparecer a los usuarios como negocios separados, se puede configurar un inquilino B2C para el canal que se utiliza para la separación sitio / marca.

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a>Consideraciones cuando se configuran múltiples inquilinos B2C por canal

A menudo, cuando cada canal o sitio se trata como un negocio separado, la mejor opción con respecto a los flujos de autenticación de usuarios en Commerce es usar entidades legales separadas. Sin embargo, si desea mantener cada canal / sitio en el mismo entorno y entidad legal, pero desea tener una autenticación de usuario separada para cada sitio, es importante que considere los siguientes puntos antes de continuar:

- Los usuarios tendrán sus propias credenciales distintas para cada canal / sitio.

    La misma persona puede tener dos cuentas separadas por canal / sitio, porque cada cuenta será una entrada única en un inquilino B2C separado.

- En el entorno Microsoft Dynamics se devolverán registros de clientes separados para búsquedas de registros globales.

    Si un usuario usa la misma dirección de correo electrónico en todos los canales / sitios, las búsquedas globales de clientes arrojarán resultados para cada canal / sitio. (Se mostrará un indicador de canal).

- La libreta de direcciones se puede usar para ayudar a los usuarios del grupo, de modo que puedan rastrearse por canal.
- El número de registros de clientes por canal podría aumentar, y este aumento podría afectar el rendimiento de las búsquedas globales de clientes.
- Los inquilinos B2C deben asignarse cuidadosamente a un canal, para ayudar a prevenir situaciones en las que los clientes se inscriban en un inquilino incorrecto. De lo contrario, pueden surgir problemas de confusión o seguimiento.

La siguiente ilustración muestra múltiples inquilinos B2C en un entorno de Commerce.

![Múltiples inquilinos B2C en un entorno de Commerce](media/MultiB2C_In_Environment.png)

Si decide que su negocio requiere inquilinos B2C distintos por canal en el mismo entorno de Commerce, complete los procedimientos en las siguientes secciones para solicitar esta función.

## <a name="request-that-b2c-per-channel-be-enabled-in-your-environment"></a>Solicite que se habilite B2C por canal en su entorno

Actualmente, si desea que distintos inquilinos B2C por canal estén disponibles en el mismo entorno de Commerce, debe enviar una solicitud a Dynamics 365 Commerce. Para más información, consulte [Obtenga soporte para Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) o discuta este problema con su contacto de soluciones de Commerce.

## <a name="configure-b2c-tenants-in-your-environment"></a>Configure inquilinos B2C en su entorno

Para configurar inquilinos B2C en su entorno, complete los procedimientos relevantes en esta sección.

### <a name="add-an-azure-ad-b2c-tenant"></a>Agregar un inquilino Azure AD B2C

Para agregar un inquilino Azure AD B2C para su entorno, siga estos pasos.

1. Inicie sesión en Commerce Site Builder para su entorno como administrador del sistema. Para configurar inquilinos Azure AD B2C, debe ser administrador del sistema para el entorno de Commerce.
1. En el panel de navegación izquierdo, seleccione **Configuración de inquilino** para expandirlo.
1. Seleccione **Configuración B2C**, y después seleccione **Administrar**.
1. Seleccione **Agregar aplicación B2C** y después introduzca la información siguiente:

    - **Nombre de la aplicación**: introduzca el nombre que se debe usar para la aplicación en el contexto de su administración en Commerce. Le recomendamos que utilice el nombre de la aplicación que eligió cuando configuró la aplicación Azure AD B2C en el portal de Azure. De esta forma, puede ayudar a reducir la confusión al administrar inquilinos B2C en Commerce.
    - **Nombre del inquilino** : introduzca el nombre del inquilino B2C tal como aparece en Azure Portal.
    - **Id. de directiva de restablecimiento de contraseña** : introduzca el id. de la directiva (el nombre de la directiva en Azure Portal).
    - **Registrar ID de inicio de sesión de política**: introduzca el id. de la directiva (el nombre de la directiva en Azure Portal).
    - **GUID del cliente**: introduzca el Id. de inquilino de Azure AD B2C tal como aparece en Azure Portal (no el Id. de aplicación para el inquilino B2C).
    - **Editar perfil de ID de política**: introduzca el ID de la política (el nombre de la política en Azure Portal).

1. Cuando haya terminado de introducir esta información, seleccione **Aceptar** para guardar sus cambios.

> [!NOTE]
> Debe dejar campos como **Alcance**, **ID de política no interactiva**, **ID de cliente no interactivo**, **Iniciar sesión dominio personalizado** e **ID de política de registro** en blanco a menos que el equipo de Dynamics 365 Commerce le indique que los configure.
Su nuevo inquilino Azure AD B2C ahora debería aparecer en la lista debajo de **Administrar aplicaciones B2C**.

### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a>Administrar o eliminar un inquilino de Azure AD B2C

1. Inicie sesión en Commerce Site Builder para su entorno como administrador del sistema. Para configurar inquilinos Azure AD B2C, debe ser administrador del sistema para el entorno de Commerce.
1. En el panel de navegación izquierdo, seleccione **Configuración de inquilino** para expandirlo.
1. Seleccione **Configuración B2C**, y después seleccione **Administrar**.
1. Para editar un inquilino B2C, seleccione el símbolo de lápiz junto a él. Para eliminar un inquilino B2C, seleccione el símbolo de la papelera junto a él.
1. Seleccione **Guardar** y luego seleccione **Publicar** para activar sus cambios.

> [!WARNING]
> Cuando un inquilino B2C está configurado para un sitio en vivo / publicado, los usuarios pueden haberse registrado utilizando cuentas que están presentes en el inquilino. Si elimina un inquilino configurado en el menú **Configuración del inquilino \> Inquilino B2C**, elimina la asociación de ese inquilino B2C de los sitios que están asociados con cualquier canal del inquilino. En este caso, es posible que sus usuarios ya no puedan iniciar sesión en sus cuentas. Por lo tanto, tenga mucho cuidado cuando elimine un inquilino configurado.
>
> Cuando se elimina un inquilino configurado, el inquilino B2C y los registros continuarán manteniéndose, pero la configuración del sistema de Commerce de ese inquilino se cambiará o eliminará. Los usuarios que intenten registrarse o iniciar sesión en el sitio crearán un nuevo registro de cuenta en el inquilino B2C predeterminado o recién asociado que está configurado para el canal del sitio.
## <a name="configure-your-channel-with-a-b2c-tenant"></a>Configure su canal con un inquilino B2C

1. Inicie sesión en Commerce Site Builder para su entorno como administrador del sistema. Para configurar inquilinos Azure AD B2C, debe ser administrador del sistema para el entorno de Commerce.
1. En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo
1. Seleccione **Canales** y luego seleccione el canal a configurar.
1. En el panel de propiedades a la derecha, en el campo **Seleccionar aplicación B2C**, seleccione el inquilino de Azure AD B2C configurado para usar para este canal.
1. En la barra de comandos, seleccione **Guardar y publicar** para confirmar la configuración nueva o actualizada.

> [!WARNING]
> Si cambia la aplicación B2C que está asignada al canal, elimina las referencias actuales que se han establecido para cualquier usuario que ya se haya registrado en el entorno. En este caso, las credenciales asociadas con la aplicación B2C asignada actualmente no estarán disponibles para los usuarios. Por lo tanto, cambie la configuración de un canal Azure AD B2C solo si está configurando el canal por primera vez y ningún usuario ha podido registrarse. De lo contrario, los usuarios podrían tener que registrarse nuevamente para establecer un registro en el nuevo inquilino Azure AD B2C.
## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)
