---
title: Módulo de selector de sitios
description: En este tema se trata el modulo de selector de sitios y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ad4d4d5f950d0631059d8f509e9e808a9106eb98
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551703"
---
# <a name="site-picker-module"></a>Módulo de selector de sitios

[!include [banner](includes/banner.md)]

En este tema se trata el modulo de selector de sitios y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Cuando una empresa tiene diferentes sitios en mercados, regiones y locales, los usuarios del sitio necesitan una forma fácil de cambiar entre sitios y seleccionar su sitio de compras preferido. Para hacer posible este escenario, el módulo de selector de sitios permite a los usuarios navegar en varios sitios. También se recomienda un selector de sitios cuando la [geodetección y redirección](geo-detection-redirection.md) se hayan implementado para su sitio de comercio electrónico, para que los clientes tengan una forma de anular la preferencia del sitio que indican mediante el módulo [selector de país/región](country-region-picker-module.md). 

El módulo de selector de sitios debe configurarse con la lista de sitios (mercados, regiones o locales) que los usuarios del sitio pueden explorar. La siguiente ilustración muestra un ejemplo de un módulo de selector de sitios que aparece en el encabezado de una página de sitio.

![Ejemplo de un módulo de selector de sitios en el encabezado de una página de sitio.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Propiedades del módulo de selector de sitios

| Nombre de la propiedad | Valor                 | Description |
|---------------|-----------------------|-------------|
| Encabezado       | Texto                  | El encabezado del módulo. |
| Opciones de sitio  | Nombre, imagen, URL      | Esta propiedad especifica para cada sitio que se incluye en el módulo un nombre, un vínculo a la página de inicio del sitio y una imagen opcional para mostrar. La imagen puede ser una bandera o alguna representación de un mercado, región o localidad. |

## <a name="add-a-site-picker-module-to-a-page"></a>Agregar un módulo de selector de sitios a una página

El módulo de selector de sitios se puede agregar a la franja **Selector de sitios** del [módulo de encabezado](author-header-module.md). Una vez agregado un módulo de selector de sitios, puede definir el encabezado del módulo y las opciones del sitio. Por lo general, un módulo de encabezado está contenido en un fragmento de encabezado que se puede compartir en las páginas de comercio electrónico de un sitio. En el siguiente ejemplo, el módulo selector de sitios se ha agregado a la franja **Selector de sitios** de un módulo de encabezado que está contenido en un fragmento de encabezado que se denomina **HeaderContainer**.

![Ejemplo de un módulo de selector de sitios en un fragmento de encabezado.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de navegación](add-breadcrumb.md)

[Módulo de menú de navegación](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
