---
title: Dominios en Dynamics 365 Commerce
description: Este artículo describe cómo se manejan los dominios en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 08/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: 08d6d52175bb7a77259cbd38b15f466deeab0846
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336709"
---
# <a name="domains-in-dynamics-365-commerce"></a>Dominios en Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo describe cómo se manejan los dominios en Microsoft Dynamics 365 Commerce.

Los dominios son direcciones web que se utilizan para navegar a sitios de Dynamics 365 Commerce en un explorador web. Usted controla la administración de su dominio con un proveedor de servidor de nombres de dominio (DNS) elegido. Se hace referencia a los dominios en todo el creador de sitios de Dynamics 365 Commerce para coordinar cómo se accederá a un sitio cuando se publique. Este artículo revisa cómo se manejan y se hace referencia a los dominios a lo largo del ciclo de vida del desarrollo y lanzamiento del sitio de Commerce.

> [!NOTE]
> A partir del 6 de mayo de 2022, todos los entornos creados en Dynamics 365 Commerce se aprovisionarán con el dominio de `.dynamics365commerce.ms`, reemplazando el patrón anterior de `.commerce.dynamics.com`. Entornos existentes aprovisionados con el dominio de `.commerce.dynamics.com` seguirá funcionando.

## <a name="provisioning-and-supported-host-names"></a>Aprovisionamiento y nombres de host admitidos

Al aprovisionar un ambiente de comercio electrónico en [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), el cuadro **Nombres de host admitidos** en la pantalla de aprovisionamiento de comercio electrónico se utiliza para especificar dominios que se asociarán con el ambiente de Commerce implementado. Estos dominios serán los nombres del servidor de nombres de dominio (DNS) de cara al cliente donde se hospedarán los sitios web de comercio electrónico. Especificar un dominio en esta etapa no empieza a desviar el tráfico del dominio hacia Dynamics 365 Commerce. El tráfico de un dominio solo se enrutará al punto final de Commerce cuando el registro CNAME de DNS se actualice para usar el punto final de Commerce con el dominio.

> [!NOTE]
> Se pueden especificar varios dominios en el cuadro **Nombres de host admitidos** separándolos con punto y coma.

La siguiente ilustración muestra la pantalla de aprovisionamiento de comercio electrónico LCS con el cuadro **Nombres de host admitidos** resaltado. 

![Pantalla de aprovisionamiento de comercio electrónico de LCS con el cuadro **Nombres de host admitidos** resaltado.](./media/Domains_ProvisioningeCommerceScreen_publish.png)

Puede crear una solicitud de servicio para agregar dominios adicionales a un ambiente si ya se ha realizado el aprovisionamiento. Para crear una solicitud de servicio en LCS, en su ambiente vaya a **Soporte \> Problemas de soporte** y seleccione **Presentar un incidente**.

## <a name="commerce-generated-urls"></a>URL generadas por Commerce

Al aprovisionar un ambiente de comercio electrónico de Dynamics 365 Commerce, Commerce generará una URL que será la dirección de trabajo para el ambiente. Se hace referencia a esta URL en el enlace del sitio de comercio electrónico que se muestra en LCS después de que se aprovisiona el ambiente. Una URL generada por Commerce tiene el formato `https://<e-commerce tenant name>.dynamics365commerce.ms`, donde el nombre del inquilino de comercio electrónico es el nombre especificado en LCS para el ambiente de Commerce.

También puede utilizar los nombres de host del sitio de producción en un ambiente de espacio aislado. Esta opción es ideal cuando va a copiar un sitio desde un ambiente de espacio aislado a producción.

## <a name="site-setup"></a>Configuración del sitio

Una vez que se aprovisiona su ambiente de comercio electrónico, debe configurar su sitio en el creador de sitios de Commerce para asociar su sitio a la URL de trabajo.

Cuando configura por primera vez un sitio en el creador de sitios, el cuadro de diálogo **Configurar su sitio** aparecerá.

La siguiente ilustración muestra el cuadro de diálogo **Configurar su sitio** para un sitio llamado "predeterminado" cuando accede al sitio por primera vez en el creador de sitios.

![Cuadro de diálogo **Configurar su sitio**.](./media/Domains_SetupyoursiteScreen.png)

El cuadro de diálogo **Seleccionar un dominio** le permite asociar uno de los nombres de host admitidos proporcionados para su sitio en LCS a su sitio en el creador de sitios.

El cuadro **Ruta de acceso** se puede dejar en blanco o se puede agregar una cadena de ruta de acceso adicional que se reflejará en su URL de trabajo. Si deja el cuadro de diálogo **Ruta de acceso** vacío, se asocia la URL base generada por Commerce con el sitio que se está configurando en el creador de sitios. Las rutas de acceso deben ser únicas para cada par de sitio/dominio. Dentro del sitio y dominio seleccionados, solo un sitio en el ambiente puede usar la ruta de acceso vacía o asociarse con una cadena de ruta de acceso única. Cualquier cadena agregada al campo **Ruta de acceso** durante la configuración del sitio se convertirá en una ruta de acceso secundaria de la dirección URL base generada por Commerce que se utiliza para acceder al sitio en un explorador web.

> [!NOTE]
> La ruta de acceso también se conoce como la **Ruta de acceso de coincidencia** al agregar un canal en la sección de configuración **Configuración del sitio \> Canales** del creador de sitios.

Por ejemplo, si tiene un sitio en el creador de sitios llamado "fabrikam" en un inquilino de comercio electrónico llamado "xyz", y si configura el sitio con una ruta de acceso vacía, entonces accederá al contenido del sitio publicado en un explorador web yendo directamente a la URL base generada por Commerce:

`https://xyz.dynamics365commerce.ms`

Alternativamente, si hubiera agregado una ruta de "fabrikam" durante la configuración de este mismo sitio, accedería al contenido del sitio publicado en un navegador web usando la siguiente URL:

`https://xyz.dynamics365commerce.ms/fabrikam`

## <a name="pages-and-urls"></a>Páginas y direcciones URL

Una vez que su sitio está configurado con una ruta de acceso, todas las direcciones URL asociadas con las páginas en el creador de sitios se basarán en la dirección URL de trabajo (la dirección URL generada por Commerce o la URL generada por Commerce más la ruta de acceso) para el sitio. Crear una nueva dirección URL en el creador de sitios (**URLS /> +Nuevo**) seleccionando una página de la lista en el cuadro de diálogo **Dirección URL nueva** y especificar la ruta de la dirección URL para esa página asociará esa dirección URL con la página seleccionada. El valor de la ruta de acceso de la URL luego se agrega a la dirección URL de trabajo del sitio para acceder a la página, y se etiqueta como `./<URL path>` en la lista de dirección URL de la página **Direcciones URL** en el creador de sitios.

La siguiente ilustración muestra el cuadro de diálogo **Dirección URL nueva** en el creador de sitios con una ruta de la dirección URL de ejemplo resaltada. 

![Cuadro de diálogo **Nueva dirección URL** en el creador de sitios.](./media/Domains_PageSetup2a.png)

La siguiente ilustración muestra la página **Direcciones URL** en el creador de sitios con una ruta de la dirección URL de ejemplo resaltada en la lista.

![Opción Ejecutar flujo de usuario en flujo de directiva.](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Dominios en el creador de sitios

Los valores de nombres de host admitidos están disponibles para asociarse como un dominio al configurar un sitio. Al seleccionar un valor de nombre de host compatible como dominio, verá el dominio elegido referenciado en todo el creador de sitios. Este dominio es solo una referencia dentro del ambiente de Commerce, el tráfico en vivo para ese dominio aún no se reenviará a Dynamics 365 Commerce.

Al trabajar con sitios en el creador de sitios, si tiene dos sitios configurados con dos dominios diferentes, puede agregar el atributo **?domain=** a su dirección URL de trabajo para acceder al contenido del sitio publicado en un navegador.

Por ejemplo, se ha aprovisionado el ambiente "xyz" y se han creado y asociado dos sitios en el creador de sitios: uno con el dominio `www.fabrikam.com` y el otro con el dominio `www.constoso.com`. Cada sitio se configuró utilizando una ruta de acceso vacía. A continuación, se puede acceder a estos dos sitios en un navegador web de la siguiente manera utilizando el atributo **?domain=**:
- `https://xyz.dynamics365commerce.ms?domain=www.fabrikam.com`
- `https://xyz.dynamics365commerce.ms?domain=www.contoso.com`

Cuando no se proporciona una cadena de consulta de dominio en un ambiente con varios dominios proporcionados, Commerce utiliza el primer dominio que proporcionó. Por ejemplo, si la ruta de acceso "fabrikam" se proporcionó primero durante la configuración del sitio, la dirección URL `https://xyz.dynamics365commerce.ms` podría utilizarse para acceder al contenido del sitio publicado por `www.fabrikam.com`.

## <a name="traffic-forwarding-in-production"></a>Reenvío de tráfico en producción

Puede simular varios dominios utilizando parámetros de cadena de consulta de dominio en el propio punto de conexión commerce.dynamics.com. Pero cuando necesita comenzar a funcionar en producción, debe reenviar el tráfico de su dominio personalizado al punto de conexión `<e-commerce tenant name>.dynamics365commerce.ms`.

El punto de conexión `<e-commerce tenant name>.dynamics365commerce.ms` no es compatible con Secure Sockets Layers (SSL) de dominio personalizado, por lo que debe configurar dominios personalizados mediante un servicio de puerta principal o una red de entrega de contenido (CDN). 

Para configurar dominios personalizados usando un servicio de puerta principal o CDN, tiene dos opciones:

- Configure un servicio de puerta de entrada como Azure Front Door para manejar el tráfico front-end y conectarse a su ambiente de Commerce. Esto proporciona un mayor control sobre la gestión de certificados y dominios y políticas de seguridad más granulares.

> [!NOTE]
> Si está utilizando un CDN externo o un servicio de puerta de entrada, asegúrese de que la solicitud llegue a la plataforma de Commerce con el nombre de host proporcionado por Commerce, pero con el encabezado X-Forwarded-Host (XFH) \<custom-domain\>. Por ejemplo, si su punto final de Commerce es `xyz.dynamics365commerce.ms` y el dominio personalizado es `www.fabrikam.com`, el encabezado de host de la solicitud reenviada debe ser `xyz.dynamics365commerce.ms` y el encabezado XFH debe ser `www.fabrikam.com`.

- Use la instancia de Azure Front Door proporcionada por Commerce. Esto requiere coordinar la acción con el equipo de Dynamics 365 Commerce para la verificación del dominio y la obtención de certificados SSL para su dominio de producción.

Para obtener información sobre cómo configurar un servicio CDN directamente, consulte [Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md).

Para usar la instancia de Azure Front Door proporcionada por Commerce, debe crear una solicitud de servicio para la asistencia de configuración de CDN del equipo de incorporación de Commerce. 

- Deberá proporcionar el nombre de su empresa, el dominio de producción, el identificador del ambiente y el nombre del inquilino de comercio electrónico de producción. 
- Deberá confirmar si se trata de un dominio existente (utilizado para un sitio actualmente activo) o un dominio nuevo. 
- Para un nuevo dominio, la verificación del dominio y el certificado SSL se pueden lograr en un solo paso. 
- Para un dominio que sirve a un sitio web existente, se requiere un proceso de varios pasos para establecer la verificación del dominio y el certificado SSL. Este proceso tiene un acuerdo de nivel de servicio (SLA) de 7 días hábiles para que un dominio entre en funcionamiento, ya que incluye varios pasos secuenciales.

Para crear una solicitud de servicio en LCS, en su ambiente vaya a **Soporte \> Problemas de soporte** y seleccione **Presentar un incidente**.

> [!NOTE]
> Los dominios personalizados con SSL solo se admiten en ambientes de producción. Para ambientes que no son de producción, como los ambientes aislados y pruebas de aceptación de usuarios (UAT), use la URL generada por Commerce para acceder al contenido publicado en un navegador web.

## <a name="ssl-certificate-process"></a>Proceso de certificado SSL

Cuando se presenta una solicitud de servicio, el equipo de Commerce coordinará los siguientes pasos con usted.

Para nuevos dominios:
- El equipo de Commerce configurará la instancia de Azure Front Door (hospedada en Commerce).
- El equipo de Commerce le proporcionará el registro CNAME para señalar su dominio personalizado.
- Después de que se actualice el registro CNAME, la instancia de Azure Front Door alojada en Commerce podrá verificar la propiedad del dominio y obtener el certificado SSL.

Para dominios existentes y activos:
- El equipo de Commerce le indicará que agregue un registro CNAME `afdverify.<custom-domain>` para proporcionar a su proveedor de DNS de dominio.
- Cuando se complete, el equipo de Commerce agregará el dominio para la instancia de Azure Front Door y proporcionará registros TXT de DNS adicionales que se agregarán al DNS del dominio.
- Una vez completados los registros TXT, el equipo de Commerce completará las actualizaciones de Azure Front Door para el dominio que configurará el certificado SSL.

## <a name="apex-domains"></a>Dominios Apex

La instancia de Azure Front Door proporcionada por Commerce no admite dominios apex (dominios raíz que no contienen subdominios). Los dominios apex requieren una dirección IP para resolverse y la instancia de Azure Front Door de Commerce existe solo con puntos de conexión virtuales. Para usar un dominio apex, tiene las siguientes opciones:

- **Opción 1**: utilice su proveedor de DNS para redirigir el dominio apex a un dominio "www". Por ejemplo, fabrikam.com redirige a `www.fabrikam.com` donde `www.fabrikam.com` es el registro CNAME que apunta a la instancia de Azure Front Door hospedada en Commerce.

- **Opcion 2** - Si su proveedor de DNS admite registros ALIAS, puede apuntar el dominio principal al extremo de la puerta principal. Esto garantiza que se refleje el cambio de IP por parte del extremo de la puerta principal.
  
- **Opción 3** - Si su proveedor de DNS no admite registros ALIAS, debe configurar una CDN o una instancia de puerta de entrada por su cuenta para alojar el dominio principal.

> [!NOTE]
> Si usa Azure Front Door, también debe configurar una instancia de Azure DNS en la misma suscripción. El dominio apex alojado en Azure DNS puede apuntar a su instancia Azure Front Door como un registro de alias. Esta es la única solución alternativa, ya que los dominios apex siempre deben apuntar a una dirección IP.
  
Si tiene alguna pregunta sobre los dominios de Apex, comuníquese con [Soporte técnico de Microsoft](https://support.microsoft.com/).

  ## <a name="additional-resources"></a>Recursos adicionales

  [Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

  [Configurar un canal de la tienda en línea](./channel-setup-online.md)

  [Crear un sitio de comercio electrónico](create-ecommerce-site.md)

  [Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

  [Administrar archivos robots.txt](manage-robots-txt-files.md)

  [Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

  [Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

  [Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

  [Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

  [Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

  [Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
