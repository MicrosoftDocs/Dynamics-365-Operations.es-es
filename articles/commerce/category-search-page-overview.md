---
title: Visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda
description: Este tema ofrece una visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda en Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2a7eab8e7f5d300930f8a093afff2d848d8a2db7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997858"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda

[!include [banner](includes/banner.md)]

Este tema ofrece una visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda en comercio electrónico de Microsoft Dynamics 365 Commerce.

## <a name="default-category-landing-page"></a>Página de aterrizaje de categoría predeterminada

La página de aterrizaje de categoría predeterminada es la página a la que se llevan normalmente a los usuarios de sitio web cuando seleccionan una categoría en la jerarquía de navegación. La página de categoría le permite examinar, y también puede limitar y ordenar los productos clasificados.

![Página de aterrizaje de categoría predeterminada](./media/SimpleCategoryLandingDressCategory.png)

En la parte superior de la página se encuentra un encabezado que muestra todas las categorías de producto y otras páginas que el administrador de comercialización ha clasificado. La configuración se realiza como parte de la configuración de la jerarquía de navegación de canal. En la parte inferior de la página hay un pie de página que incluye vínculos rápidos a diversos temas en los que un comprador puede estar interesado.

Los siguientes componentes son esenciales para una categoría:

- **Iconos de colocación de producto** muestran los productos que el administrador de comercialización ha definido en una categoría como parte de la configuración de la jerarquía de navegación.
- **Refinadores y resumen de opciones** son filtros que proporcionan recuentos y que se pueden utilizar para limitar artículos. El administrador de comercialización los configura como parte de la configuración de los metadatos relacionados con las categorías de canal y los atributos de producto.
- **Opciones de ordenación** se usan por los visitantes del sitio web para ordenar los productos. De forma predeterminada, están disponibles las siguientes opciones de ordenación:

    - Precio: de menor a mayor
    - Precio: de mayor a menor
    - Nombre de producto: \[A-Z\]
    - Nombre de producto: \[Z-A\]
    - Clasificaciones: de menor a mayor
    - Clasificaciones: de mayor a menor

- **Paginación** permite a los visitantes del sitio web pasar de una página de resultados de productos clasificados a otra página.
- **Recuento total** proporciona el número total de productos definidos en una categoría.

## <a name="enrich-a-category-landing-page"></a>Enriquecer una página de aterrizaje de categoría

Si desea que una página de aterrizaje de categoría tener una experiencia más adaptada para una categoría específica, puede “enriquecer” la página de aterrizaje de categoría para dicha categoría. Por ejemplo, puede agregar un vídeo de marketing y alguna narración de la categoría para obtener la atención del comprador. Para obtener más información, consulte [Enriquecer una página de aterrizaje de categoría](enrich-category-page.md).

![Página de aterrizaje de categoría enriquecida](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Sugerencia automática y páginas de resultados de la búsqueda

Los usuarios del sitio web pueden explorar un sitio yendo a una categoría de la jerarquía de navegación o introduciendo un término de búsqueda en el campo de búsqueda.

En cuanto los usuarios empiezan a escribir en el campo de búsqueda, experimentan la funcionalidad inmersiva de sugerencia automática que sugiere términos de búsqueda.

A continuación se muestran algunos de los tipos de sugerencias que es posible que se muestren:

- **Palabras clave** se usan para buscar artículos en todos los productos surtidos al canal.
- **Productos** proporcionan vínculos directos a la página de detalles de productos.
- **Sugerencias de búsqueda de categorías con ámbito** muestran diversas categorías y permiten a los usuarios la búsqueda de palabra clave en una categoría específica.

![Sugerencia automática inmersiva](./media/ImmersiveAutoSuggestUX.png)

Cuando los usuarios seleccionan una de las sugerencias de búsqueda de categoría con ámbito o palabra clave, o cuando no hay sugerencias para el término de búsqueda que introducen, se redirigen a una página de resultados de la búsqueda. A continuación, los usuarios pueden examinar, ordenar y limitar la lista de resultados de la búsqueda para encontrar el artículo deseado.

![Aterrizaje de búsqueda](./media/SearchLanding.png)

Los siguientes componentes son esenciales para una página de resultados de la búsqueda:

- **Iconos de colocación de producto** muestran los productos para la búsqueda del usuario. De forma predeterminada, estos iconos se ordenan por la puntuación de relevancia de búsqueda con tecnología de nube para la búsqueda del usuario.
- **Refinadores y resumen de opciones** son filtros que proporcionan recuentos y que se pueden utilizar para limitar artículos. El administrador de comercialización los configura como parte de la configuración de los metadatos de "categorías de canal y atributos de producto".
- **Opciones de ordenación** se usan por los visitantes del sitio web para ordenar los productos. De forma predeterminada, están disponibles las siguientes opciones de ordenación:

    - Precio: de menor a mayor
    - Precio: de mayor a menor
    - Nombre de producto: \[A-Z\]
    - Nombre de producto: \[Z-A\]
    - Clasificaciones: de menor a mayor
    - Clasificaciones: de mayor a menor
    - Predeterminada

- **Paginación** permite a los visitantes del sitio web pasar de una página de resultados de productos clasificados a otra página.
- **Recuento total** proporciona el número total de productos definidos en una categoría y que coinciden con los criterios de búsqueda.

>[!NOTE]
>Estas capacidades de búsqueda basadas en la nube están disponibles a partir de la versión 10.0.8. Asegúrese de que en **Parámetros de Commerce > Parámetros de configuración** hay una entrada para "ProductSearch.UseAzureSearch establecido en 'true'". 
![Parámetros de configuración para búsqueda en la nube](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la búsqueda con tecnología de nube](cloud-powered-search-overview.md)

[Visión general de la página principal](quick-tour-home-page.md)

[Visión general de las páginas de detalles de producto](quick-tour-pdp.md)

[Visión general de las páginas del carro y de la finalización de la compra](quick-tour-cart-checkout.md)

[Visión general de las páginas de la gestión de cuentas](quick-tour-account-management.md)

