---
title: Información general del sitio de comercio electrónico
description: Este artículo proporciona una visión general de la compatibilidad para sitios de comercio electrónico en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9b7e4d09eaa4f91478d27cbca5eaea48af86e676
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899130"
---
# <a name="e-commerce-site-overview"></a>Información general del sitio de comercio electrónico

[!include [banner](includes/banner.md)]

Este artículo proporciona una visión general de la compatibilidad para sitios de comercio electrónico en Microsoft Dynamics 365 Commerce. Incluye información sobre cómo se inicializan y gestionan las tiendas en línea de comercio electrónico en Dynamics 365 Commerce. También proporciona vínculos a información adicional sobre tiendas en línea e información sobre cómo definir y configurar un sito de comercio electrónico. Aunque este artículo cubre muchos de los conceptos básicos, no cubre todo lo que se requiere para configurar un sitio de comercio electrónico de producción. Se pueden encontrar artículos más avanzados en la documentación de Dynamics 365 Commerce.

## <a name="online-store-channel"></a>Canal de la tienda en línea

Para poder crear su sitio en Dynamics 365 Commerce debe configurar al menos un canal de la tienda en línea. Para más información, vea [Configurar un canal en línea](channel-setup-online.md). 

En Dynamics 365 Commerce utiliza un canal de la tienda en línea para establecer los productos, precios, idiomas, métodos de pago, modos de entrega, centros de cumplimiento y otros aspectos de la experiencia en línea que deben estar disponibles para sus clientes.

Solo tiene que configurar un canal de la tienda en línea para poder empezar a trabajar con Dynamics 365 Commerce. Sin embargo, un solo sitio de comercio electrónico puede proporcionar la experiencia en línea para múltiples tiendas en línea. Por ejemplo, si se configuran varias tiendas en línea para cubrir distintas regiones geográficas, se puede usar un solo conjunto de páginas de comercio electrónico para proporcionar las experiencias únicas que definen cada tienda. Para obtener más información sobre cómo configurar un sitio para cubrir varias tiendas en línea, consulte [Asociar un sitio en línea con un canal](associate-site-online-store.md).

Después de configurar una tienda en línea, se puede asociar con el sitio de Dynamics 365 Commerce que servirá como escaparate en línea. Para obtener más información sobre las tiendas en línea y cómo configurarlas, consulte [Configurar tiendas en línea](/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Implementar un inquilino nuevo de comercio electrónico

Durante la inicialización de un sitio de comercio electrónico, se le solicita un nombre de dominio. Para obtener más información sobre los dominios en Commerce, consulte [Configurar tu nombre de dominio](configure-your-domain-name.md) y [Dominios en Dynamics 365 Commerce](domains-commerce.md). Para implementar un nuevo inquilino de comercio electrónico mediante [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide), siga los pasos en [Implementar un nuevo inquilino de comercio electrónico](deploy-ecommerce-site.md). Después de que su inquilino de comercio electrónico esté configurado en LCS, se proporcionará un enlace al generador de sitios de Commerce. A continuación, puede utilizar el generador de sitios de Commerce para inicializar y configurar sus sitios de comercio electrónico.

## <a name="initialize-your-e-commerce-site"></a>Inicializar su sitio de comercio electrónico

Cuando inicia el generador de sitios de Commerce desde LCS, aparece la página **Sitios**. Esta página incluye dos sitios preconfigurados, **predefinido** y **fabrikam**, como se muestra en el ejemplo de la siguiente ilustración.

![Página de sitios en el generador de sitios de Commerce.](media/e-commerce-site-01.png)

Cuando selecciona uno de estos sitios, se le solicita que seleccione un nombre de dominio, un canal de tienda en línea predeterminado, un idioma admitido para el canal seleccionado y una ruta de acceso. Si solo se utiliza un canal, puede dejar la ruta en blanco. Se pueden configurar más canales o idiomas de la tienda en línea más adelante en el generador de sitios de Commerce. Cada canal o idioma adicional requerirá una ruta de acceso única. Por ejemplo, tiene dos canales en línea asociados con un único sitio y el nombre de dominio del sitio es `www.fabrikam.com`. En este caso, la ruta de acceso de un canal puede ser el valor predeterminado que no tiene ruta (`https://www.fabrikam.com`), y el segundo canal se puede configurar en una nueva ruta, como **site2**, que tendrá la URL `https://www.fabrikam.com/site2`. La siguiente ilustración muestra un ejemplo de un cuadro de diálogo de inicialización del sitio en el generador de sitios de Commerce.

![Cuadro de diálogo de inicialización del sitio en el generador de sitios de Commerce.](media/e-commerce-site-02.png)

La página **Sitios** también incluye un botón **Nuevo sitio**. El cuadro de diálogo que aparece cuando selecciona este botón se parece al cuadro de diálogo de inicialización del sitio, pero se utiliza para crear un nuevo sitio. Los sitios nuevos están en blanco. No incluyen las mismas plantillas, fragmentos, páginas e imágenes predeterminadas que se proporcionan con los sitios **predeterminado** y **fabrikam**. Sin embargo, según lo requiera, puede abrir una incidencia de soporte técnico para solicitar que se agregue una copia del contenido predeterminado a un nuevo sitio en blanco. Para más información, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).

Después de inicializar un nuevo sitio, aparece la página **Inicio** del generador de sitios de Commerce. Esta página incluye vínculos a acciones comunes y contenido de orientación, como se muestra en el ejemplo de la siguiente ilustración.

![Enlaces en la página de inicio del generador de sitios de Commerce.](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Modifique los canales de la tienda en línea o agregue canales de la tienda en línea a un sitio de comercio electrónico

Una vez creado un sitio de comercio electrónico, puede cambiar el canal al que está asociado siguiendo los pasos de [Asociar un sitio de comercio electrónico con un canal en línea](associate-site-online-store.md). El ejemplo de la siguiente ilustración muestra cómo se puede cambiar un número de unidad operativa del canal (OUN) en la página **Canales** (**Configuración del sitio \> Canales**). Una vez que haya terminado de realizar un cambio, asegúrese de seleccionar **Guardar y publicar**. De esta forma, se asegura de que se publique el cambio.

![Página de canales en el generador de sitios de Commerce.](media/e-commerce-site-04.png)

Puede agregar nuevos canales seleccionando **Agregar un canal**. Para agregar nuevos idiomas a un canal, seleccione el canal y luego seleccione **Agregar una configuración regional** en el cuadro de diálogo del canal que aparece. Antes de que las configuraciones regionales puedan aparecer en el cuadro de diálogo, deben estar preconfiguradas para el canal de la tienda en línea en la sede central de Commerce.

![Cuadro de diálogo del canal en el generador de sitios de Commerce.](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Configurar un inquilino de Azure B2C

Dynamics 365 Commerce usa el modelo B2C (empresa a consumidor) de Azure Active Directory (Azure AD) para admitir credenciales de usuario y flujos de autenticación. Para obtener información sobre cómo configurar su inquilino de Azure B2C, consulte [Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md), [Configurar páginas personalizadas para inicios de sesión de usuarios](custom-pages-user-logins.md) y [Configurar varios inquilinos B2C en un entorno de Commerce](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Descripción general de las páginas del sitio predeterminadas

Los sitios **predeterminado** y **fabrikam** incluyen plantillas, fragmentos y páginas preconfigurados para ayudarle a comenzar. Para obtener más información, consulte los siguientes artículos:

- [Información general de la página principal](quick-tour-home-page.md)
- [Visión general de la página de detalles de producto](quick-tour-pdp.md)
- [Visión general de las páginas del carro y de la finalización de la compra](quick-tour-cart-checkout.md)
- [Visión general de las páginas de la gestión de cuentas](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Administrar la configuración del sitio

Para obtener información acerca de cómo administrar la configuración del sitio, vea los siguientes artículos:

- [Administrar usuarios y roles de comercio electrónico](manage-ecommerce-users-roles.md)
- [Consideraciones de optimización de motor de búsqueda (SEO) para su sitio](search-engine-optimization-considerations.md)
- [Administrar la directiva de seguridad de contenido (CSP)](manage-csp.md)
- [Seleccionar un tema de sitio](select-site-theme.md)

## <a name="manage-site-content"></a>Administrar el contenido del sitio

Para obtener información acerca de cómo administrar el contenido del sitio, vea los siguientes artículos:

- [Glosario del modelo de página](page-elements-overview.md)
- [Estados y ciclo de vida de documentos](document-states-overview.md)
- [Plantillas y diseño](templates-layouts-overview.md)
- [Trabajar con fragmentos](work-with-fragments.md)
- [Trabajar con módulos](work-with-modules.md)
- [Visión general de la administración de activos digitales](dam-overview.md)
- [Descripción general de la biblioteca de módulos](starter-kit-overview.md)

## <a name="additional-resources"></a>Recursos adicionales

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]