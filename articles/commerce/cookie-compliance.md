---
title: Cumplimiento de cookies
description: Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 95c5801e69396b21a36c4ae12ce17801e6f7fd88
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993509"
---
# <a name="cookie-compliance"></a>Cumplimiento de cookies

[!include [banner](includes/banner.md)]

Este tema describe consideraciones para el cumplimiento de cookies y las políticas predeterminadas que se incluyen en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La privacidad es un factor importante cuando se utilizan tecnologías de seguimiento que afectan a los clientes de comercio electrónico. Debido a los estándares de cumplimiento de privacidad, como el Reglamento General de Protección de Datos (GDPR) en la Unión Europea (UE), se deben tener en cuenta las pautas de privacidad electrónica para cualquier sitio que esté activo en la actualidad. Debido a que muchos sitios de comercio electrónico son accesibles globalmente de manera predeterminada, es importante que revise los estándares de cumplimiento para su sitio de comercio electrónico.

Para obtener más información sobre los principios básicos que utiliza Microsoft para el cumplimiento de cookies, visite el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center). En ese sitio, también puede obtener más información sobre las áreas de cumplimiento y privacidad.

La siguiente tabla muestra la lista de referencia actual de cookies colocadas por sitios de Dynamics 365 Commerce.

| Nombre de la cookie                               | Uso                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Almacena las cookies de autenticación de Microsoft Azure Active Directory (Azure AD) para el inicio de sesión único (SSO). Almacena la información principal del usuario cifrada (nombre, apellidos, correo electrónico). |
| &#95;msdyn365___cart&#95;                           | Almacene el identificador del carrito de la compra para obtener la lista de productos agregados a la instancia del carrito. |
| &#95;msdyn365___ucc&#95;                            | Seguimiento del consentimiento del cumplimiento de cookies.                          |
| ai_session                                  | Detecta cuántas sesiones de actividad del usuario han incluido ciertas páginas y características de la aplicación. |
| ai_user                                     | Detecta cuántas personas usaron la aplicación y sus características. Los usuarios se cuentan utilizando identificaciones anónimos. |
| b2cru                                       | Almacena de forma dinámica las URL de redireccionamiento.                              |
| JSESSIONID                                  | Utilizado por el conector de pago Adyen para almacenar la sesión del usuario.       |
| OpenIdConnect.nonce.&#42;                       | Autentificación                                               |
| x-ms-cpim-cache:.&#42;                          | Se utiliza para mantener el estado de la solicitud.                      |
| x-ms-cpim-csrf                              | Token de falsificación de solicitud entre sitios (CRSF) utilizado para la protección contra CRSF.     |
| x-ms-cpim-dc                                | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. |
| x-ms-cpim-rc.&#42;                              | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. |
| x-ms-cpim-slice                             | Se utiliza para enrutar solicitudes a la instancia del servidor de autenticación de producción adecuada. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Se usa para mantener la sesión SSO.                        |
| x-ms-cpim-trans                             | Se utiliza para llevar el seguimiento de transacciones (el número de pestañas abiertas que se autentican en un sitio de empresa a cliente (B2C)), incluida la transacción actual. |

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