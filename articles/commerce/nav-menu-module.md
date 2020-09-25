---
title: Módulo del menú de navegación
description: En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761421"
---
# <a name="navigation-menu-module"></a>Módulo del menú de navegación

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El propósito principal de los módulos de menú de navegación es permitir que los usuarios del sitio naveguen por productos y páginas del sitio de acuerdo con la jerarquía de navegación del canal definida en la central de Dynamics 365 Commerce. Los elementos configurados en un módulo del menú de navegación aparecen como navegación del encabezado del sitio. Los módulos del menú de navegación también admiten elementos de menú estáticos que se vinculan a otras páginas en un sitio de comercio electrónico.

El módulo de menú de navegación se puede agregar al módulo de encabezado de una página. En el tema Fabrikam, el menú de navegación muestra dos niveles por defecto. En el tema Starter, el menú de navegación muestra tres niveles por defecto. Para cambiar el número de niveles, se requiere una extensión de vista en el tema.

La siguiente ilustración muestra un ejemplo de un menú de navegación para el sitio de Fabrikam con dos niveles de jerarquía de categorías y algunos elementos de menú estáticos.
![Ejemplo de un módulo de menú de navegación](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Propiedades del módulo del menú de navegación

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Origen                  | **Minorista**, **Creación manual**, **Creación minorista y manual** | El valor **Minorista** permite que la jerarquía de navegación del canal de la sede de Commerce se muestre en el menú de navegación. El valor **Autoría manual** permite seleccionar elementos estáticos del menú. El valor **Autoría minorista y manual** permite una combinación de ambos. |
| Mostrar imágenes de categoría | **Verdadero** o **Falso**    | Cuando está habilitada, esta propiedad muestra imágenes de categoría en el menú de navegación como se define en la central de Commerce para cada categoría. Agregado en la versión 10.0.14 de Commerce. |
| Elemento de menú estático| Matriz de valores| Elementos de menú estáticos que asocian un nombre de elemento de menú con un enlace a una página de sitio estática. Puede crear elementos de menú debajo de otros elementos de menú. De forma predeterminada, los menús estáticos aparecen en el nivel raíz y se agregarán a la jerarquía de navegación del canal si existe. |

La siguiente ilustración muestra un ejemplo de una imagen de categoría que se muestra en el menú de navegación del sitio de Fabrikam.
![Ejemplo de un módulo de menú de navegación con imágenes de categoría](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Agregar un módulo de menú de navegación a un módulo de encabezado

Para obtener detalles sobre cómo agregar un módulo de menú de navegación a un módulo de encabezado, consulte [Módulo de encabezado](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Cumplimiento de cookies](cookie-compliance.md)

[Módulo de encabezado](author-header-module.md)
