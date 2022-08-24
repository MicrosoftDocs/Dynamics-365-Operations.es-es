---
title: Módulo de selector de sitios
description: En este artículo se trata el modulo de selector de sitios y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: efd58206d88618aedb6b574afb47da1e9e578ef1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276758"
---
# <a name="site-picker-module"></a>Módulo de selector de sitios

[!include [banner](includes/banner.md)]

En este artículo se trata el modulo de selector de sitios y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Cuando una empresa tiene diferentes sitios en mercados, regiones y locales, los usuarios del sitio necesitan una forma fácil de cambiar entre sitios y seleccionar su sitio de compras preferido. Para hacer posible este escenario, el módulo de selector de sitios permite a los usuarios navegar en varios sitios. También se recomienda un selector de sitios cuando la [geodetección y redirección](geo-detection-redirection.md) se hayan implementado para su sitio de comercio electrónico, para que los clientes tengan una forma de anular la preferencia del sitio que indican mediante el módulo [selector de país/región](country-region-picker-module.md). 

El módulo de selector de sitios debe configurarse con la lista de sitios (mercados, regiones o locales) que los usuarios del sitio pueden explorar. La siguiente ilustración muestra un ejemplo de un módulo de selector de sitios que aparece en el encabezado de una página de sitio.

![Ejemplo de un módulo de selector de sitios en el encabezado de una página de sitio.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Propiedades del módulo de selector de sitios

| Nombre de la propiedad | Valor                 | Description |
|---------------|-----------------------|-------------|
| Encabezado       | Texto                  | El encabezado del módulo. |
| Opciones de sitio  | Nombre, imagen, URL      | Esta propiedad especifica para cada sitio que se incluye en el módulo un nombre, un vínculo a la página de inicio del sitio y una imagen opcional para mostrar. La imagen puede ser una bandera o alguna representación de un mercado, región o localidad. |

## <a name="add-a-site-picker-module-to-a-page"></a>Agregar un módulo de selector de sitios a una página

El módulo de selector de sitios se puede agregar a la franja **Selector de sitios** del [módulo de encabezado](author-header-module.md). Una vez agregado un módulo de selector de sitios, puede definir el encabezado del módulo y las opciones del sitio. Por lo general, un módulo de encabezado está contenido en un fragmento de encabezado que se puede compartir en las páginas de comercio electrónico de un sitio. 

Para agregar el módulo de selector de sitios a un módulo de encabezado, siga estos pasos.

1. En la ranura **Selector de sitios** del módulo de encabezado del fragmento de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, agregue un módulo **Selector de sitios** y luego seleccione **Aceptar**.
1. En el panel de propiedades **Selector de sitios**, seleccione **Agregar lista de opciones del sitio**. Aparece una opción editable **Lista de opciones del sitio**.
1. Seleccione **Lista de opciones de sitio**. Aparece el cuadro de diálogo **Lista de opciones del sitio**.
1. Bajo **Nombre del sitio**, ingrese el texto del nombre del sitio que se mostrará en la lista desplegable del selector de sitios.
1. Bajo **URL de redireccionamiento del sitio**, seleccione **Añadir un enlace**. Aparece el panel del elemento emergente **Agregar enlace**.
1. En el panel flotante **Añadir un enlace**, seleccione **Página personalizada** y luego seleccione **Siguiente**.
1. En la lista de URL del sitio, seleccione la URL con la ruta que creó al agregar el canal al sitio (por ejemplo, `www.adventure-works.com/fr-ca`) y luego seleccione **Aplicar**.
1. Seleccione **Aceptar**.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar** para publicar la página.

En el siguiente ejemplo, el módulo selector de sitios se ha agregado a la franja **Selector de sitios** de un módulo de encabezado que está contenido en un fragmento de encabezado que se denomina **HeaderContainer**.

![Ejemplo de un módulo de selector de sitios en un fragmento de encabezado.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de navegación](add-breadcrumb.md)

[Módulo de menú de navegación](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
