---
title: Módulos de comparación de productos
description: Este artículo describe los módulos de comparación de productos y cómo implementarlos para que los clientes puedan hacer comparaciones de productos en sitios web de comercio electrónico de Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 6fd851ce6b32d0772c3fe23c4d7bd4dae2616fdc
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474136"
---
# <a name="product-comparison-modules"></a>Módulos de comparación de productos

[!include [banner](../includes/banner.md)]

Este artículo describe los módulos de comparación de productos y cómo implementarlos para que los clientes puedan hacer comparaciones de productos en sitios web de comercio electrónico de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Los módulos de comparación de productos y botón de comparación de productos están disponibles a partir del lanzamiento de la versión 10.0.29 de Dynamics 365 Commerce. Se pueden utilizar tanto para sitios web de empresa a consumidor (B2C) como de empresa a empresa (B2B).

La funcionalidad de comparación de productos permite a los compradores comparar los detalles del producto en una página de comparación de productos para ayudarlos a tomar mejores decisiones de compra. Esta funcionalidad se configura en el creador de sitios de Commerce mediante el módulo de comparación de productos. En las páginas de lista de productos (PLP), como los resultados de categoría, los resultados de búsqueda y las páginas de colecciones de productos, puede configurar un botón para la comparación de productos que permita a los compradores agregar productos a una bandeja de comparación. Esta funcionalidad se configura en el creador de sitios mediante el módulo del botón de comparación de productos, que funciona como el [módulo de vista rápida](quick-view-module.md).

Cuando los usuarios del sitio agregan productos para compararlos seleccionándolos en mosaicos de productos, aparece una bandeja de comparación en la parte inferior de la página. La bandeja de comparación muestra los productos que el comprador está comparando actualmente, junto con vistas previas breves de los productos. Los usuarios del sitio también pueden agregar productos desde las páginas de detalles del producto (PDP) y pueden agregar variantes de productos específicas para comparar con los productos maestros.

Después de que los clientes agreguen algunos productos a la bandeja de comparación, pueden seleccionar **Comparar** para ser redirigido a una página de comparación de productos. La página de comparación de productos muestra los detalles del producto para cada producto seleccionado para que los clientes puedan comparar imágenes, precios, dimensiones del producto (tamaño, estilo y color), información de calificaciones agregadas y otros atributos del producto.

La siguiente ilustración muestra ejemplos del botón Comparar productos, el botón Eliminar de la comparación, la bandeja de comparación y la página de comparación de productos.

![Información general sobre la cmparación de productos que muestra ejemplos del botón Comparar productos, el botón Eliminar de la comparación, el panel de la bandeja de comparación y la página de comparación de productos.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - La página de comparación de productos compara un conjunto predeterminado de propiedades de productos y todos los atributos que se pueden ver en un PDP para un producto determinado.
> - Las propiedades como el modo de entrega, el inventario disponible y la unidad de medida no se pueden ver en una página de comparación de productos.
> - Los clientes pueden agregar productos de diferentes categorías a la bandeja de comparación, siempre que los productos sean del mismo catálogo.
> - La función de comparación de productos actualmente se limita a comparar productos en un catálogo individual. Los usuarios del sitio no pueden hacer comparaciones entre catálogos.
> - Debes asegurarte de que la propiedad **Lado del cliente del módulo de procesamiento** se borra para todos los módulos de comparación de productos.
> - Debe asegurarse de que el almacenamiento en caché en el nivel de página esté deshabilitado para todas las páginas en las que se utilice el módulo de comparación de productos. Estas páginas incluyen PDP, PLP y páginas de comparación de productos. Para más información, consulte [Configurar el almacenamiento en caché de páginas](e-commerce-extensibility/page-caching.md).

En la ilustración siguiente se muestra un ejemplo de una página de comparación de productos.

![Página de comparación de productos.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Agregar el módulo de comparación de productos a una nueva página de comparación de productos

Puede crear una página de comparación de productos dedicada agregando un módulo de comparación de productos al cuerpo de una página. Además de permitir que los clientes comparen los detalles de productos de diferentes productos, puede configurar el módulo de comparación de productos para brindarles a los clientes la opción de completar rápidamente su compra después de comparar productos. El módulo de comparación de productos también contiene una ranura **Comparación vacía**, donde puede agregar un módulo de bloque de contenido que describe el estado vacío (por ejemplo, "Su comparación de productos está vacía").

Para agregar un módulo de comparación de productos a una página nueva de comparación de productos, siga estos pasos.

1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca un nombre de página apropiada (por ejemplo, **Comparación de productos**) y después seleccione **Siguiente**.
1. En **Elegir una plantilla**, seleccione la plantilla adecuada (por ejemplo, la que utiliza su página de categoría predeterminada) y después seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si debe editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**.
1. En la **Franja principal**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Comparación de productos** y, a continuación, **Aceptar**.
1. En la ranura **Botón Vista rápida**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Vista rápida de los productos** y, a continuación, seleccione **Aceptar**.
1. En el panel de propiedades de la derecha, configure las propiedades del módulo **Vista rápida de los productos**.
1. En el espacio **Comparación vacía**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Bloque de contenido** y, a continuación, **Aceptar**.
1. En el panel de propiedades de la derecha, configure las propiedades del módulo **Bloque de contenido**. 
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

La siguiente ilustración muestra un ejemplo de una página de comparación vacía en el generador de sitios.

![Módulo de comparación de productos.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Agregue un botón de comparación de productos a los mosaicos de productos en las páginas de resultados de búsqueda y categoría

El botón de comparación de productos permite a los usuarios agregar rápidamente un producto a la bandeja de comparación cuando buscan productos en una página de lista. Pueden agregar uno o más productos a la bandeja de comparación desde una página de lista sin tener que ir a un PDP.

El botón de comparación de productos es compatible con los módulos de colección de productos, resultados de búsqueda y caja de compra de PDP.

Para agregar un botón de comparación de productos a los mosaicos de productos en las páginas de resultados de búsqueda y categoría, siga estos pasos.

1. En el creador de sitios, vaya a **Páginas** y abra la página de categoría a la que desea agregar un botón de comparación de productos.
1. En la **Franja principal**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Resultados de la búsqueda** y, a continuación, seleccione **Aceptar**.
1. En el espacio **Botón de comparación de productos** del módulo **Resultados de búsqueda**, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Botón de comparación de productos** y, a continuación, **Aceptar**.
1. En el panel de propiedades de la derecha, configure las propiedades del módulo **Botón de comparación de productos**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Especifique el número máximo de productos para mostrar en la bandeja de comparación

Puede especificar el número máximo de productos para mostrar en la bandeja de comparación yendo a **Configuración del sitio \> Extensiones** en el generador del sitio. Puede configurar límites máximos separados para las vistas de escritorio y móvil/tableta. De forma predeterminada, no se aplicará ningún límite si no se define un límite máximo.

> [!NOTE]
> Para una experiencia de navegación óptima, le recomendamos que establezca el número máximo de productos en la bandeja de comparación en **2** para la ventana gráfica móvil y **4** para que la ventana gráfica del escritorio reduzca la cantidad de desplazamiento horizontal necesario.

Para especificar el número máximo de productos para mostrar en la bandeja de comparación, siga estos pasos.

1. En el generador de sitios, vaya a **Configuración del sitio \> Extensiones**.
1. Para la propiedad **Productos en el límite de comparación: dispositivos de escritorio**, ingrese la cantidad máxima de productos que deben mostrarse en la bandeja de comparación para las ventanas gráficas de escritorio.
1. Para la propiedad **Productos en el límite de comparación: dispositivos móviles y tabletas**, ingrese la cantidad máxima de productos que deben mostrarse en la bandeja de comparación para las ventanas gráficas de móviles y tabletas.
1. En la barra de comandos, seleccione **Guardar y publicar**.

![Configuración del sitio para limitar productos en la bandeja de comparación.](./media/Site-settings-to-limit-products-in-comparison-tray.png)
