---
title: Módulos de colección de productos
description: Este tema proporciona una visión general de los módulos de colección de productos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/07/2020
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
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 31307035014f2fae6146f33bc23e3e06103f82eb
ms.sourcegitcommit: c237123ad94d9418994ac095fbd8634c05a927b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "2943272"
---
# <a name="product-collection-modules"></a>Módulos de colección de productos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema proporciona una visión general de los módulos de colección de productos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El descubrimiento de productos es una herramienta principal que los minoristas usan para interactuar con sus clientes en un sitio web de comercio electrónico. Los módulos de colección de productos ayudan a los minoristas a crear atractivas experiencias de compra al ofrecer una interfaz visual intuitiva que pueda usarse para crear rápidamente colecciones de productos.

Los módulos de colecciones de productos representan servicios y productos físicos en el sitio web. Un módulo de colección de productos se vincula normalmente a una página de detalles en la que los clientes pueden comprar un producto o servicio u obtener más información sobre él. 

Los orígenes de las colecciones de productos pueden ser listas de los cuatro tipos siguientes:

- Listas editoriales de productos que se han definido manualmente en Dynamics 365 Retail como productos relacionados de un producto o de listas de productos
- Listas algorítmicas, como listas de productos nuevos, más vendidos o tendencias
- Listas de recomendaciones que se basan en aprendizaje automático
- Listas de personalización que admiten resultados personalizados para un cliente. Los clientes deben iniciar sesión en el sitio de comercio electrónico para ver resultados personalizados. Los usuarios invitados no ven resultados personalizados. Los clientes pueden renunciar a la personalización en la [página de gestión de cuentas](account-management.md).

La ilustración siguiente muestra los diferentes tipos de colecciones de productos que se utilizan en un sitio de comercio electrónico.

![Ejemplo de los diferentes tipos de colecciones de productos en un sitio de comercio electrónico](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Use siempre los módulos de colección de productos para mostrar un grupo de productos de un tipo similar.

## <a name="product-collection-modules-and-types"></a>Tipos y módulos de colección de productos

En la siguiente tabla se describen diversos tipos de módulos de colección de productos en Dynamics 365 Commerce.

| Módulo de colección de productos  | Tipo | Descripción |
|----------------------------|------|-------------|
| Categoría                   | Categoría | Este módulo muestra una lista de productos en una categoría, según lo definido por la jerarquía de categorías de navegación que el minorista creó para un canal minorista. |
| Productos relacionados           | Editorial | Este módulo muestra una lista de productos que un director de comercialización ha configurado como productos relacionados en Retail, para el tipo de relación que el autor ha seleccionado. |
| Listas de productos mantenidas      | Editorial | Este módulo muestra listas personalizadas que los comerciantes y editores han creado en Retail. |
| Nuevas                        | Algorítmico | Este módulo muestra una lista de los productos más recientes que se han surtido a canales y catálogos. Esta lista puede mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción. |
| Más vendidos               | Algorítmico | Este módulo muestra una lista de productos que están clasificados por el número máximo de ventas. Esta lista puede mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción. |
| Tendencias                   | Algorítmico | Este módulo muestra una lista de los productos de mayor rendimiento para un período determinado. Esta lista puede mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción. |
| Los usuarios que compraron este artículo también compraron | Inteligencia artificial/aprendizaje automático | Este módulo usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que se compran con frecuencia junto con un producto determinado. Esta lista puede mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción. |
| A la gente también le gustó           | Inteligencia artificial/aprendizaje automático | Este módulo usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que están relacionados con un producto determinado. Esta lista puede mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción. |
| Picking para usted              | Inteligencia artificial/aprendizaje automático | Este módulo usa el aprendizaje automático para analizar los patrones de compra del usuario que ha iniciado sesión y proporcionar recomendaciones personalizadas basadas en esos patrones de compra. Para un usuario invitado, esta lista se contraerá. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Agregar un módulo de colección de productos a una página de categoría

Para agregar un módulo de colección de productos a una página de categoría, siga estos pasos.

1. En Dynamics 365 Commerce, vaya al sitio y cree una página que use la misma plantilla que la página de categoría predeterminada.
1. En la página Esquema, seleccione la franja **Pie de página secundario**, los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Contenedor** y **Aceptar**.
1. En el módulo de contenedor, seleccione el botón de puntos suspensivos y **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Colección de productos** y **Aceptar**.  
![Ejemplo de flujo de asistente de módulo de colección de productos](./media/productCollectionModule.png)
1. Configure los valores seleccionando entradas y un origen de datos adecuados para la colección de productos.
1. En el panel de propiedades del módulo de colección de productos, seleccione **Agregar una lista de productos**.
1. En el cuadro de diálogo **Seleccionar la configuración de la lista de productos**, seleccione el tipo de lista, especifique el número de artículos y seleccione otras opciones que estén disponibles para el tipo de lista. Para obtener más información sobre los tipos de lista, consulte la tabla siguiente. 
1. Seleccione **Aceptar**.
1. Guarde la página y protéjala.

En la tabla siguiente se muestran los tipos de lista disponibles para la selección del cuadro de diálogo **Seleccionar la configuración de la lista de productos**.

| Tipo                       | Descripción | Uso | Contexto de la página | Contexto específico | Personalización |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Productos por categoría       | Lista de productos que pertenecen a una categoría dada. Esta categoría se determina del contexto de la página o del contexto que el autor proporciona. | Este tipo de lista se puede utilizar en cualquier página (por ejemplo, una página de inicio, una página de categoría, una página de marketing o una página de detalles del producto \[PDP\]) para promover una categoría específica de productos. | Categoría del contexto de la página, donde esté disponible (por ejemplo, una página de categoría) | El autor puede proporcionar una categoría específica como contexto para la lista. | No aplicable |
| Productos relacionados           | Lista de productos que un director de comercialización ha configurado como productos relacionados para el tipo de relación en Retail. | Este tipo de lista se usa principalmente en PDP, pero se puede usar en cualquier página si se proporciona un producto principal. | Producto de la página, tipo de relación (obligatorio) | El producto se puede seleccionar en el selector y se utiliza el tipo de relación. | No aplicable |
| Mantenida                    | Lista personalizada que los comerciantes y editores han creado en Retail. | Enriquecer página de categoría, página principal, páginas de carro y finalización de compra y páginas de productos | No aplicable | No aplicable | No aplicable |
| Algorítmico                | <ul><li>**Nuevos**: lista de los productos más nuevos que se han surtido a canales y catálogos.</li><li>**Más vendidos**: lista de productos que están clasificados por el máximo número de ventas.</li><li>**Tendencias**: lista de los productos de mayor rendimiento para un período determinado.</li></ul> | Página principal, enriquecer página de categoría, y páginas de carro y finalización de compra | Categoría del contexto de la página (por ejemplo, una página de categoría) | La categoría determinada por el autor del sitio | Compatible |
| Los usuarios que compraron este artículo también compraron | Lista que usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que se compran con frecuencia junto con un producto determinado. | Este tipo de lista solo es aplicable a la página de carro. | Carro | No aplicable | Compatible |
| A la gente también le gustó           | Lista que usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que están relacionados con un producto determinado. | Este tipo de lista se utiliza en PDP para mostrar productos que otros clientes han comprado. | Contexto del producto desde la página | El producto proporcionado por el autor del sitio | Compatible |
| Picking para usted              | Lista que utiliza el aprendizaje automático para determinar las preferencias del cliente. | Este tipo de lista se puede usar en cualquier página. | No aplicable| No aplicable | Compatible | 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Visión general de recomendaciones de producto](product-recommendations.md)
