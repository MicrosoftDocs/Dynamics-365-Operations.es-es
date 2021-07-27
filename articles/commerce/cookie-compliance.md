---
title: Cumplimiento de cookies
description: Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/01/2021
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
ms.openlocfilehash: 71b2e0e8d0a7db6cbbc8b9b4024b067bd5c6a2a1
ms.sourcegitcommit: 43962e6fedaf55aab2f28f53bc38a69d2ff58403
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2021
ms.locfileid: "6333078"
---
# <a name="cookie-compliance"></a>Cumplimiento de cookies

[!include [banner](includes/banner.md)]

Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.

La privacidad es un factor importante cuando se utilizan tecnologías de seguimiento que afectan a los clientes de comercio electrónico. Debido a los estándares de cumplimiento de privacidad, como el Reglamento General de Protección de Datos (GDPR) en la Unión Europea (UE), se deben tener en cuenta las pautas de privacidad electrónica para cualquier sitio que esté activo en la actualidad. Debido a que muchos sitios de comercio electrónico son accesibles globalmente de manera predeterminada, es importante que revise los estándares de cumplimiento para su sitio de comercio electrónico.

Para obtener más información sobre los principios básicos que utiliza Microsoft para el cumplimiento de cookies, visite el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center). En ese sitio, también puede obtener más información sobre las áreas de cumplimiento y privacidad.

La siguiente tabla muestra la lista de referencia actual de cookies colocadas por sitios de Dynamics 365 Commerce.

| Nombre de la cookie                               | Uso                                                        | Duración |
| ------------------------------------------- | ------------------------------------------------------------ |  ------- |
| .AspNet.Cookies                             | Almacena las cookies de autenticación de Microsoft Azure Active Directory (Azure AD) para el inicio de sesión único (SSO). Almacena la información principal del usuario cifrada (nombre, apellidos, correo electrónico). | Sesión |
| \_msdyn365___cart_                           | Almacene el identificador del carrito de la compra para obtener la lista de productos agregados a la instancia del carrito. | Sesión |
| \_msdyn365___checkout_cart_                           | Almacene el identificador del carrito de la compra de pago para obtener la lista de productos agregados a la instancia del carrito de pago. | Sesión |
| \_msdyn365___ucc_                            | Seguimiento del consentimiento del cumplimiento de cookies.                          | 1 año |
| ai_session                                  | Detecta cuántas sesiones de actividad del usuario han incluido ciertas páginas y características de la aplicación. | 30 minutos |
| ai_user                                     | Detecta cuántas personas usaron la aplicación y sus características. Los usuarios se cuentan utilizando identificaciones anónimos. | 1 año |
| b2cru                                       | Almacena de forma dinámica las URL de redireccionamiento.                              | Sesión |
| JSESSIONID                                  | Utilizado por el conector de pago Adyen para almacenar la sesión del usuario.       | Sesión |
| OpenIdConnect.nonce.&#42;                       | Autentificación                                               | 11 minutos |
| x-ms-cpim-cache:.&#42;                          | Se utiliza para mantener el estado de la solicitud.                      | Sesión |
| x-ms-cpim-csrf                              | Token de falsificación de solicitud entre sitios (CRSF) utilizado para la protección contra CRSF.     | Sesión |
| x-ms-cpim-dc                                | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. | Sesión |
| x-ms-cpim-rc.&#42;                              | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. | Sesión |
| x-ms-cpim-slice                             | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. | Sesión |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Se usa para mantener la sesión SSO.                        | Sesión |
| x-ms-cpim-trans                             | Se utiliza para llevar el seguimiento de transacciones (el número de pestañas abiertas que se autentican en un sitio de empresa a cliente (B2C)), incluida la transacción actual. | Sesión |
| \_msdyn365___muid_                            | Se utiliza si la experimentación está activada para el entorno usado como id. de usuario con fines de experimentación. | 1 año |
| \_msdyn365___exp_                             | Se utiliza si la experimentación está activada para el medio ambiente; utilizado para medir el rendimiento del equilibrio de carga.         | 1 hora |
| d365mkt                                       | Se usa si la detección basada en la ubicación para rastrear la dirección IP de un usuario para sugerencias de ubicación de la tienda está habilitada en el creador de sitios de Commerce en **Configuración del sitio \> General \> Habilitar la detección de tiendas basada en la ubicación**.      | 1 hora |

Si un usuario del sitio selecciona cualquier enlace de redes sociales dentro de un sitio, las cookies de la siguiente tabla también se rastrearán en su navegador.


| Dominio                      | Cookie               | Descripción                                                  | Origen                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | Sincronización de ID de anuncios de LinkedIn                                      | Etiqueta de información y noticias de LinkedIn                                |
| .linkedin.com               | li_sugr                  | El identificador del navegador                                           | Etiqueta de LinkedIn Insight si la dirección IP no se encuentra en un país designado |
| .linkedin.com               | BizographicsOptOut       | Determina el estado de exclusión voluntaria para el seguimiento de terceros.              | Controles de invitados de LinkedIn y páginas de exclusión voluntaria de la industria           |
| .linkedin.com               | \_guid                    | Identificador de navegador de Google Ads.                            | Feed de LinkedIn                                                |
| .linkedin.com               | li_oatml                 | Identificador indirecto de miembro para seguimiento de conversiones, reorientación y análisis. | Etiquetas de información y anuncios de LinkedIn                                |
| Varios dominios propios | li_fat_id                | Identificador indirecto de miembro para seguimiento de conversiones, reorientación y análisis. | Etiquetas de información y anuncios de LinkedIn                                |
| .adsymptotic.com            | U                        | El identificador del navegador                                           | Etiqueta de LinkedIn Insight si la dirección IP no se encuentra en un país designado |
| .linkedin.com                | bcookie                  | Cookie de identificación del navegador                                            | Solicitudes a LinkedIn                                         |
| .linkedin.com                | bscookie                 | Cookie de navegador segura                                        | Solicitudes a LinkedIn                                         |
| .linkedin.com               | lang                     | Establece la configuración regional y el idioma predeterminados.                                 | Solicitudes a LinkedIn                                         |
| .linkedin.com                | lidc                     | Se utiliza para enrutamiento.                                             | Solicitudes a LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Cookie de administrador de audiencia de Adobe                                                     | Establecer para sincronización de ID                                              |
| .linkedin.com               | \_ga                      | Cookie de Google Analytics                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Cookie de Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Cookie de Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | La cookie contiene el ID de usuario del usuario que ha iniciado sesión actualmente.  |   Facebook                                                           |
| .facebook.com               | datr                     | Se utiliza para identificar el navegador web que se utiliza para conectarse a Facebook independientemente del usuario que inició sesión. | Facebook                                                             |
| .facebook.com               | wd                       | Almacena las dimensiones de la ventana del navegador y lo utiliza Facebook para optimizar la representación de la página. | Facebook                                                             |
| .facebook.com               | xs                       | Número de dos dígitos que representa el número de sesión. La segunda parte del valor es un secreto de sesión. |  Facebook                                                            |
| .facebook.com               | fr                       | Contiene un navegador y una identificación de usuario únicos, que se utilizan para publicidad dirigida. |  Facebook                                                            |
| .facebook.com               | sb                       | Usado para mejorar sugerencias de amigos de Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | La cookie contiene el ID de usuario del usuario que ha iniciado sesión actualmente.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | La cookie contiene el ID de usuario del usuario que ha iniciado sesión actualmente.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | La cookie contiene páginas cuando el usuario selecciona el botón Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | La cookie contiene páginas cuando el usuario selecciona el botón Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Contiene un ID de usuario y la marca de tiempo cuando se creó la cookie. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | La cookie contiene páginas cuando el usuario selecciona el botón Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | La cookie contiene páginas cuando el usuario selecciona el botón Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Almacenamiento local            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Trabadores de servicios          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consentimiento de cookies del usuario del sitio en un sitio de comercio electrónico 

Si una característica o módulo de un sitio de comercio electrónico utiliza una cookie no esencial, se debe obtener el consentimiento del usuario del sitio antes de rastrear la cookie. Para permitir que los usuarios del sitio proporcionen consentimiento de cookies en el sitio de comercio electrónico, el autor del sitio debe agregar y configurar un módulo de consentimiento de cookies en el módulo de encabezado de la página para garantizar que se solicite y se reciba el consentimiento. Se debe dar el consentimiento del usuario del sitio antes de que una función o módulo que utilice una cookie no esencial se pueda representar en una página del sitio.

## <a name="additional-resources"></a>Recursos adicionales

[Características y funcionalidades de accesibilidad](accessibility.md)

[Información general sobre cumplimiento](compliance-overview.md)

[Agregar una página de directivas de privacidad](add-privacy-page.md)

[Reemplazar id. de usuario asociado con cambios de contenido con seguimiento](replace-IDs-tracked-changes.md)

[Módulo de consentimiento de cookies](cookie-consent-module.md) 
 
[Módulo de encabezado](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
