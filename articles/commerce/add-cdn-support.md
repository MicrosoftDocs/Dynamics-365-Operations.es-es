---
title: Agregar soporte para una red de entrega de contenido (CDN)
description: Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0e888fca4a5401f1df6e61b10358489846ad4b0e
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517217"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Agregar soporte para una red de entrega de contenido (CDN)


[!include [banner](includes/banner.md)]

Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Al configurar un entorno de comercio electrónico en Dynamics 365 Commerce, puede definirlo para trabajar con su servicio de CDN. 

Su dominio personalizado se puede habilitar durante el proceso de aprovisionamiento para su entorno de comercio electrónico. Como alternativa, puede usar una solicitud de servicio para configurarlo una vez que se ha completado el proceso de aprovisionamiento. El proceso de aprovisionamiento para el entorno de comercio electrónico genera un nombre de host que esté asociado al entorno. Este nombre de host tiene el siguiente formato, donde \<*e-commerce-tenant-name*\> es el nombre del entorno:

&lt;nombre-inquilino-comercio-electrónico&gt;.commerce.dynamics.com

El nombre de host o el extremo que se genera durante el proceso de aprovisionamiento admite un certificado de capa de sockets seguros (SSL) solo para \*.commerce.dynamics.com. No admite SSL para dominios personalizados. Por lo tanto, debe finalizar SSL para los dominios personalizados en su CDN y reenviar el tráfico desde la CDN al nombre de host o extremo que Commerce generó. 

Además, los (archivos JavaScript o de hojas de estilo CSS \[CSS\] ) *estáticos* de Commerce se sirven desde el extremo que Commerce generó (\*.commerce.dynamics.com). La estática solo se puede almacenar en caché si el nombre de host o extremo que Commerce generó se coloca detrás de la CDN.

## <a name="set-up-ssl"></a>Configurar SSL

Para ayudar a garantizar que SSL está configurado, y que la estática se almacena en caché, debe configurar su CDN para que se asocie al nombre de host que Commerce generó para su entorno. También debe almacenar en caché el siguiente patrón solo para estática: 

/\_msdyn365/\_scnr/\*

Tras aprovisionar su entorno de Commerce con el dominio personalizado que se proporciona, o una vez que proporciona el dominio personalizado para su entorno usando una solicitud de servicio, apunte su dominio personalizado al nombre de host o extremo que Commerce generó.

Como se ha mencionado anteriormente, el nombre de host o extremo generado admite un certificado SSL solo para \*.commerce.dynamics.com. No admite SSL para dominios personalizados.

## <a name="cdn-services"></a>Servicios CDN

Cualquier servicio de CDN se puede usar con un entorno de Commerce. Estos son dos ejemplos:

- **Microsoft Azure Front Door Service**: la solución de CDN de Azure. Para obtener más información acerca de Azure Front Door Service, consulte [Documentación de Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Acelerador de sitios dinámicos de Akamai**: para obtener más información, consulte [Acelerador de sitios dinámicos](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Configuración de CDN

El proceso de configuración de CDN consta de estos pasos generales:

1. Agregue un host front-end.
1. Configure un grupo back-end.
1. Configurar reglas para enrutamiento y almacenamiento en caché.

### <a name="add-a-front-end-host"></a>Agregar un host front-end

Se puede usar cualquier servicio de CDN, pero para el ejemplo que se muestra en este tema, se usa Azure Front Door Service. 

Para obtener información acerca de cómo configurar Azure Front Door Service, consulte [Inicio rápido: crear una puerta delantera para una aplicación web global de alta disponibilidad](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Configurar un grupo back-end en Azure Front Door Service

Para configurar un grupo back-end en Azure Front Door Service, siga estos pasos.

1. Agregue **&lt;nombre-comercio-electrónico-inquilino&gt;.commerce.dynamics.com** a un grupo back-end como host personalizado que tenga un encabezado de host de back-end vacío.
1. En **Equilibrio de carga**, deje los valores predeterminados.

En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con el nombre de host del back-end.

![Cuadro de diálogo Agregar un grupo back-end](./media/CDN_BackendPool.png)

En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con los valores de equilibrio de carga predeterminados.

![Cuadro de diálogo Agregar un grupo back-end (continuación)](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a>Configurar reglas en Azure Front Door Service

Para configurar una regla de ruta en Azure Front Door Service, siga estos pasos.

1. Agregar una regla de ruta.
1. En el campo **Nombre**, especifique **predeterminado**.
1. En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.
1. En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.
1. En **Patrones de coincidencia**, en el campo superior, especifique **/\** _.
1. En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.
1. En el campo **Grupo back-end**, seleccione **ecom-backend**.
1. En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**. 
1. Establezca la opción **URL Rewrite** en **Deshabilitado**.
1. Establezca la opción **Memoria caché** en **Deshabilitado**.

Para configurar una regla de almacenamiento en caché en Azure Front Door Service, siga estos pasos.

1. Agregue una regla de almacenamiento en caché.
1. En el campo **Nombre**, especifique **estática**.
1. En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.
1. En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.
1. En **Patrones de coincidencia**, en el campo superior, especifique **/\_msdyn365/\_scnr/\** _.
1. En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.
1. En el campo **Grupo back-end**, seleccione **ecom-backend**.
1. En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.
1. Establezca la opción **URL Rewrite** en **Deshabilitado**.
1. Establezca la opción **Memoria caché** en **Deshabilitado**.
1. En el campo **Comportamiento del almacenamiento en caché de cadenas de consulta**, seleccione **Almacenar en caché todas las URL únicas**.
1. En el grupo del campo **Compresión dinámica**, seleccione la opción **Habilitado**.

En la ilustración siguiente se muestra el cuadro de diálogo **Agregar una regla** en Azure Front Door Service.

![Cuadro de diálogo Agregar una regla](./media/CDN_CachingRule.png)

> [!WARNING]
> Si el dominio que usará ya está activo y en funcionamiento, cree una incidencia de soporte técnico desde el icono **Soporte técnico** en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obtener asistencia para sus próximos pasos. Para más información, consulte [Obtener soporte técnico para aplicaciones de Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Si su dominio es nuevo y no es un dominio activo preexistente, puede agregar su dominio personalizado a la configuración de Azure Front Door Service. Esto permitirá que el tráfico web se dirija a su sitio a través de la instancia de Azure Front Door. Para agregar el dominio personalizado (por ejemplo, `www.fabrikam.com`), debe configurar un nombre canónico (CNAME) para el dominio.

En la ilustración siguiente se muestra el cuadro de diálogo **Configuración de CNAME** en Azure Front Door Service.

![Cuadro de diálogo Configuración de CNAME](./media/CNAME_Configuration.png)

Puede usar Azure Front Door Service para administrar el certificado o usar su propio certificado para el dominio personalizado.

En la ilustración siguiente se muestra el cuadro de diálogo **Personalizar HTTPS de dominio** en Azure Front Door Service.

![Cuadro de diálogo Personalizar HTTPS de dominio](./media/Custom_Domain_HTTPS.png)

Para obtener instrucciones detalladas sobre cómo agregar un dominio personalizado a Azure Front Door, consulte [Agregar un dominio personalizado a su instancia de Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).

Su CDN debe estar ahora configurado correctamente para que se pueda usar con su sitio de Commerce.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)
