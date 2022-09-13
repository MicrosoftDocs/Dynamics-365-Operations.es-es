---
title: Lista de productos que reconoce el inventario
description: Este artículo describe cómo las organizaciones pueden configurar páginas de lista de productos en su sitio web de comercio electrónico de Microsoft Dynamics 365 Commerce para que reconozcan el inventario.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: e33a4dd8650ee2e371c51c5a19e955f2d2bdade2
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405567"
---
# <a name="inventory-aware-product-listing"></a>Lista de productos que reconoce el inventario

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artículo describe cómo las organizaciones pueden configurar páginas de lista de productos en su sitio web de comercio electrónico de Microsoft Dynamics 365 Commerce para que reconozcan el inventario. Las páginas de lista de productos incluyen páginas de aterrizaje de categorías y páginas de resultados de búsqueda.

Los compradores generalmente esperan que la detección de productos en un sitio web de comercio electrónico tenga en cuenta el inventario, de modo que puedan decidir qué hacer si se han agotado las existencias de un producto. Se pueden configurar los módulos de resultados de búsqueda y categorías de la [biblioteca de módulos de Commerce](starter-kit-overview.md) para incorporar datos de inventario. De esta forma, pueden proporcionar las siguientes experiencias:

- Muestre etiquetas de nivel de inventario junto con los productos.
- Oculte los productos agotados de la lista de productos.
- Mover productos agotados al final de las páginas de listas de productos.
- Admite el filtrado de productos con reconocimiento de inventario.

Para habilitar estas experiencias, primero debe habilitar la característica **Detección de productos de comercio electrónico mejorados para que reconozcan el inventario** en Commerce headquarters.

> [!NOTE]
> En Commerce versión 10.0.29 y posteriores, la característica **Descubrimiento mejorado de productos de comercio electrónico para tener en cuenta el inventario** está habilitada de forma predeterminada.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Configurar atributo de producto para disponibilidad de inventario

La lista de productos con reconocimiento de inventario utiliza el marco de atributos del producto. Como requisito previo, se debe crear un atributo de producto dedicado para capturar datos de disponibilidad de inventario.

Para configurar atributos de producto para disponibilidad de inventario en Commerce headquarters, siga estos pasos.

1. Vaya a **Retail y Commerce \> Retail y Commerce TI \> Productos e inventario \> Rellenar los atributos del producto con el nivel de inventario**.
1. En el cuadro de diálogo **Rellenar los atributos del producto con el nivel de inventario**, en el campo **Nombre de atributo y tipo de producto**, ingrese un nombre personalizado para el atributo de producto dedicado que se creará para capturar datos de inventario.
1. En el campo **Disponibilidad de inventario basada en**, seleccione el tipo de cantidad en el que se debe basar el cálculo del nivel de inventario: **Físico disponible** o **Total disponible**.
1. Establezca la opción **Procesamiento por lotes** en **Sí**.
1. Seleccione **Aceptar**.

> [!NOTE]
> Para un cálculo uniforme del nivel de inventario en las páginas de su sitio web de comercio electrónico, asegúrese de seleccionar el mismo tipo de cantidad en el campo **Disponibilidad de inventario basada en** para el trabajo **Rellenar los atributos del producto con el nivel de inventario** y el ajuste **Nivel de inventario basado en** en el generador de sitios de Commerce.

Después de crear el atributo de producto dedicado, el siguiente paso es configurar el atributo para el canal en línea.

Para configurar el atributo para el canal en línea en Commerce headquarters, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione el canal en línea para el que habilitar la experiencia de listas de productos con reconocimiento de inventario.
1. Seleccione y abra un grupo de atributos asociado y, a continuación, agréguele el nuevo atributo de producto.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación distribución** y ejecute el trabajo **1150** (**Catálogo**). Recomendamos que programe este trabajo como un proceso por lotes que se ejecuta con la misma frecuencia que el trabajo **Rellenar los atributos del producto con el nivel de inventario**.

> [!NOTE]
> En Commerce versión 10.0.26 y anteriores, después de agregar el atributo de producto de disponibilidad de inventario a un grupo de atributos, también debe seleccionar **Establecer metadatos de atributos** y luego activar las opciones **Mostrar atributo en el canal**, **Recuperable**, **Se puede refinar** y **Se puede consultar** para el nuevo atributo de producto.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Configure el comportamiento de visualización para productos agotados en las páginas de listas de productos

Después de completar todos los pasos de configuración anteriores, los refinadores de las páginas de resultados de búsqueda y categoría tendrán una opción de filtro basada en el inventario. Se mostrará una etiqueta de nivel de inventario para cada ventana de producto que aparece en la página.

La página de resultados de búsqueda y categoría muestra los productos en el nivel maestro, no en el nivel de variante del producto. El nivel de inventario que se muestra junto a cada producto es un nivel de inventario agregado que está determinado por el nivel de inventario de todas las variantes de un producto. El nivel de inventario de una variante se calcula en función del inventario disponible de esa variante en el almacén predeterminado del canal en línea en Commerce headquarters. El nivel de inventario de un producto maestro tiene dos valores posibles que representan estados de existencias y de existencias agotadas. Un producto maestro se considera agotado cuando todas sus variantes están agotadas. De lo contrario, el producto se considera en existencias. La etiqueta del valor se recupera de la definición del [nivel de inventario](inventory-buffers-levels.md). Si no se define ningún nivel de inventario, las etiquetas predeterminadas (en inglés) son **Disponible** y **Agotado**.

Puede configurar el ajuste **Configuración de inventario para páginas de lista de productos** en el generador de sitios de Commerce para controlar cómo el módulo de resultados de búsqueda y categoría muestra los productos agotados. Para obtener más información, consulte [Aplicar configuración de inventario](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
