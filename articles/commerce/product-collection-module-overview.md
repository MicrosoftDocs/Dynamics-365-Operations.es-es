---
title: Módulos de colección de productos
description: Este tema proporciona una visión general de los módulos de colección de productos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785476"
---
# <a name="product-collection-modules"></a>Módulos de colección de productos  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema proporciona una visión general de los módulos de colección de productos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El descubrimiento de productos es una herramienta principal que los minoristas usan para interactuar con sus clientes en un sitio web de comercio electrónico. Los módulos de colección de productos ayudan a los minoristas a crear atractivas experiencias de compra al ofrecer una interfaz visual intuitiva que pueda usarse para crear rápidamente colecciones de productos.

Los módulos de colecciones de productos representan servicios y productos físicos en el sitio web. Un módulo de colección de productos se vincula normalmente a una página de detalles en la que los clientes pueden comprar un producto o servicio u obtener más información sobre él. 

Los orígenes de las colecciones de productos pueden ser listas de tres tipos:

- Listas editoriales de productos que se han definido manualmente en Dynamics 365 Retail como productos relacionados de un producto o de listas de productos
- Listas algorítmicas, como listas de productos nuevos, más vendidos o tendencias
- Listas de recomendaciones que se basan en aprendizaje automático

La ilustración siguiente muestra los diferentes tipos de colecciones de productos que se utilizan en un sitio de comercio electrónico.

![Ejemplo de los diferentes tipos de colecciones de productos en un sitio de comercio electrónico](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Use siempre los módulos de colección de productos para mostrar un grupo de productos de un tema o tipo similar.

## <a name="product-collection-modules-and-types"></a>Tipos y módulos de colección de productos

En la siguiente tabla se describen diversos tipos de módulos de colección de productos en Dynamics 365 Commerce.

| Módulo de colección de productos  | Tipo | Descripción |
|----------------------------|------|-------------|
| Exploración de categoría            | Editorial | Este tipo de módulo de colección de productos usa la jerarquía de categoría de navegación que creó el minorista para que un canal minorista muestre un flujo de exploración para productos que se ofrecen en una categoría específica de sitio. |
| Resultados de la búsqueda             | Consulta de búsqueda | Este tipo de módulo de colección de productos muestra una lista de productos que coinciden mejor con la consulta de búsqueda que el cliente ha especificado. |
| Productos relacionados           | Editorial | Este tipo de módulo de colección de productos muestra una lista de productos que un director de comercialización ha configurado como productos relacionados en Retail, para el tipo de relación que el autor ha seleccionado. |
| Listas de productos mantenidas      | Editorial | Este tipo de módulo de colección de productos muestra listas personalizadas que los comerciantes y los editores han creado en Retail. |
| Nuevas                        | Algorítmico | Este tipo de módulo de colección de productos muestra una lista de los productos más nuevos que se han surtido a canales y catálogos. |
| Más vendidos               | Algorítmico | Este tipo de módulo de colección de productos muestra una lista de productos clasificados por el número más elevado de ventas. |
| Tendencias                   | Algorítmico | Este tipo de módulo de colección de productos muestra una lista de los productos con el máximo rendimiento para un período determinado. |
| Los usuarios que compraron este artículo también compraron | Inteligencia artificial/aprendizaje automático | Este tipo de módulo de colección de productos usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que se usan con frecuencia junto con un producto determinado. |
| A la gente también le gustó           | Inteligencia artificial/aprendizaje automático | Este tipo de módulo de colección de productos usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados con un producto determinado. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Agregar un módulo de colección de productos a una página de categoría

Para agregar un módulo de colección de productos a una página de categoría, siga estos pasos.

1. En Dynamics 365 Commerce, vaya al sitio y cree una página que use la misma plantilla que la página de categoría predeterminada.
1. En la página Esquema, seleccione la franja **Pie de página secundario**, los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Contenedor** y **Aceptar**.
1. En el módulo de contenedor, seleccione el botón de puntos suspensivos y **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Colección de productos** y **Aceptar**.
1. Configure los valores seleccionando entradas y un origen de datos adecuados para la colección de productos.
1. En el panel de propiedades del módulo de colección de productos, seleccione **Agregar una lista de productos**.
1. En el cuadro de diálogo **Seleccionar la configuración de la lista de productos**, seleccione el tipo de lista, especifique el número de artículos y seleccione otras opciones que estén disponibles para el tipo de lista. Para obtener más información sobre los tipos de lista, consulte la tabla siguiente. 
1. Seleccione **Aceptar**.
1. Guarde la página y protéjala.

En la tabla siguiente se muestran los tipos de lista disponibles para la selección del cuadro de diálogo **Seleccionar la configuración de la lista de productos**.
   
| Tipo                       | Descripción | Práctica general | Contexto que se puede derivar del contexto de página | Contexto con el que el autor puede reemplazar el contexto de página |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Productos por categoría       | Lista de productos que pertenecen a una categoría dada. Esta categoría se determina del contexto de la página o del contexto que el autor proporciona. | Enriquecer página de categoría, página principal, páginas de carro y finalización de compra y páginas de productos | Categoría | Categoría determinada por autor |
| Productos relacionados           | Lista de productos que un director de comercialización ha configurado como productos relacionados en Retail para el tipo de relación. | Páginas de productos, páginas de finalización de compra y carro, página de lista de deseos y página de cuenta de cliente | Tipo de relación de producto (obligatorio)  | Producto, tipo de relación |
| Mantenida                    | Lista personalizada que los comerciantes y editores han creado en Retail. | Enriquecer página de categoría, página principal, páginas de carro y finalización de compra y páginas de productos | No aplicable | Selector de lista |
| Algorítmico                | <ul><li>**Nuevos**: lista de los productos más nuevos que se han surtido a canales y catálogos.</li><li>**Más vendidos**: lista de productos que están clasificados por el máximo número de ventas.</li><li>**Tendencias**: lista de los productos de mayor rendimiento para un período determinado.</li></ul> | Página principal, enriquecer página de categoría, y páginas de carro y finalización de compra | Categoría | Categoría determinada por autor |
| Los usuarios que compraron este artículo también compraron | Lista que usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que se usan con frecuencia junto con un producto determinado. | Páginas de productos, y páginas de carro y finalización de compra | Producto, carro | Incluir carro |
| A la gente también le gustó           | Lista que usa el aprendizaje automático para analizar patrones de compra de consumidor y recomendar artículos relacionados que están relacionados con un producto determinado. | Páginas de productos, y páginas de carro y finalización de compra | Producto, carro | No aplicable |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

