---
title: Módulo de resultados de búsqueda
description: En este artículo se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405303"
---
# <a name="search-results-module"></a>Módulo de resultados de búsqueda

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de resultados de búsqueda devuelve resultados de búsqueda de productos y una lista de refinadores aplicables a los productos. Los módulos de resultados de búsqueda en Dynamics 365 Commerce se pueden utilizar para representar páginas en los siguientes escenarios:

- Resultados de búsqueda iniciados por la búsqueda de un usuario
- Resultados de búsqueda que muestran un conjunto específico de productos, como "Comprar looks similares"
- Listas de productos que pertenecen a una categoría

Para obtener más información sobre las páginas de resultados de búsqueda y categorías, consulte [Página de aterrizaje de categoría predeterminada y descripción general de la página de resultados de búsqueda](category-search-page-overview.md).

La siguiente ilustración muestra un ejemplo de una página de resultados de búsqueda para una categoría del sitio de Fabrikam.

![Ejemplo de página de resultados de búsqueda en el sitio de Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Propiedades del módulo de resultados de búsqueda

La tabla siguiente enumera las propiedades de los módulos de resultados de búsqueda, junto con sus valores y descripciones.

| Propiedad | Valores | Descripción |
|----------|--------|-------------|
| Artículos por página | Entero | Número de elementos que deben mostrarse en cada página. |
| Volver a activar PDP | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, cuando un usuario seleccione un producto en la página de resultados de búsqueda, la ruta de navegación de la página de detalles del producto (PDP) que se abre mostrará un vínculo "Volver a los resultados". |
| Expandir refinadores | **Todos**, **1**, **2**, **3** o **4** | Número de refinadores principales que deben expandirse al cargar una página. Por ejemplo, si esta propiedad se establece en **3**, se ampliarán los tres primeros refinadores de la página. |
| Ocultar visualización de jerarquía de categoría | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, se ocultará la visualización de la jerarquía de categorías en la página. Esta propiedad debe establecerse en **Verdadero** si se usa el [módulo de ruta de navegación](add-breadcrumb.md) para mostrar la jerarquía de categorías.|
| Incluir atributos del producto en los resultados de búsqueda | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, se devolverán atributos de los productos en los resultados de búsqueda. Aunque estos atributos se pueden mostrar en un sitio de Commerce, se requiere una extensión.|
| Mostrar precios de afiliación | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, los precios de afiliación de los productos se mostrarán en los resultados de búsqueda cuando un usuario que haya iniciado sesión navegue por la página. |
| Actualizar el panel del refinador | **Verdadero** o **Falso** | Si esta propiedad se establece en **Cierto**, el panel del refinador se actualizará cuando se seleccionen los refinadores. En este modo, algunos refinadores de selección múltiple se comportarán como refinadores de selección única cuando se actualice el panel del refinador. |

> [!IMPORTANT]
> En Commerce versión 10.0.16 y posteriores, se puede usar la opción de configuración **Mostrar precios de afiliación** para mostrar los precios de afiliación en la página.
>
> En la versión de Commerce 10.0.20 y posteriores, la configuración **Actualizar el panel del refinador** se puede utilizar para actualizar el panel del refinador durante la selección del refinador.

## <a name="supported-modules"></a>Módulos admitidos

El módulo de resultados de la búsqueda admite el [módulo de vista rápida](quick-view-module.md), que permite a los usuarios ver información de productos y agregar artículos al carro desde una página de resultados de la búsqueda.

## <a name="add-a-search-results-module-to-a-category-page"></a>Agregar un módulo de resultados de la búsqueda a una página de categoría

Para agregar un módulo de resultados de la búsqueda a una página de categoría en el constructor de sitio, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, escriba el nombre **Resultados de la búsqueda** y seleccione **Aceptar**.
1. En la entrada **Cuerpo**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En la entrada **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Ruta de navegación** y, a continuación, **Aceptar**.
1. En el panel de propiedades **Ruta de navegación**, introduzca el valor **1** para **Ocurre lo mín.**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Resultados de la búsqueda** y, a continuación, seleccione **Aceptar**.
1. En el panel de propiedades **Resultados de la búsqueda**, introduzca el valor **1** para **Ocurre lo mín.** y establezca los valores de las demás propiedad necesarias para el módulo de resultados de búsqueda. Al establecer estas propiedades en la plantilla, se asegura de que cualquier personalización de una página de categoría específica incluirá automáticamente esta configuración.
1. Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca **Página de categoría** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione la plantilla **Resultados de búsqueda** que ha creado y, a continuación, seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="inventory-aware-search-results-module"></a>Módulo de resultados de búsqueda con reconocimiento de inventario

El módulo de resultados de búsqueda se puede configurar para que incorpore datos de inventario y proporcione las siguientes experiencias:

- Muestre etiquetas de nivel de inventario junto con los productos.
- Oculte los productos agotados de la lista de productos.
- Muestre los productos agotados al final de la lista de productos.
- Admite el filtrado de productos con reconocimiento de inventario.

Para habilitar estas experiencias, primero debe habilitar la característica **Detección de productos de comercio electrónico mejorados** y, a continuación, configurar algunos ajustes de requisitos previos en Commerce Headquarters. Para obtener más información, consulte [Lista de productos con reconocimiento de inventario](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>Recursos adicionales

[Información general de la página de aterrizaje de la categoría predeterminada y la página de resultados de la búsqueda](category-search-page-overview.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de vista rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
