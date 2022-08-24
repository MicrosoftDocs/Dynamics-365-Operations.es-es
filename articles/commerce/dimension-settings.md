---
title: Aplicar la configuración de visualización para las dimensiones del producto
description: Este artículo cubre la configuración de pantalla para las dimensiones del producto y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 9324518fff35d357f845c08cba25e2faded2f381
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269980"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Aplicar la configuración de visualización para las dimensiones del producto

[!include [banner](includes/banner.md)]


Este artículo cubre la configuración de pantalla para las dimensiones del producto y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce admite el uso de dimensiones de tamaño, estilo y color para distinguir variantes de productos. Las dimensiones se muestran normalmente como valores de texto, como "Pequeño", "Mediano" y "Grande" para los tamaños y "Negro" y "Marrón" para los colores. Sin embargo, si un producto admite muchas variaciones, puede ser difícil examinar variantes, porque se requieren varias selecciones para ver la imagen de cada variante. Para facilitar la búsqueda de variantes de productos, la versión 10.0.20 de Commerce puede usar imágenes y códigos hexadecimales (hex) para mostrar las dimensiones como muestras.

En el creador de sitios de Commerce, la configuración del inventario se define en **Configuración del sitio \> Extensiones \> Configuración de dimensión**. La siguiente ilustración muestra un ejemplo de configuración de dimensiones en el creador de sitios.

![Ejemplo de configuración del sitio en el creador de sitios de Commerce.](./dev-itpro/media/swatch_site_settings.PNG)

Hay dos configuraciones de dimensión disponibles:

- **Dimensiones para mostrar como imagen**: especifique qué dimensiones deben aparecer como muestras en las páginas del sitio de comercio electrónico, como las páginas de detalles del producto (PDP) y las páginas de la lista de resultados de búsqueda. Cualquier combinación de dimensiones de color, tamaño y estilo se puede mostrar como muestra. Si se selecciona una dimensión para mostrarla como muestra, la representación del módulo de Commerce buscará una configuración disponible de una muestra de código hexadecimal. Si no se configura ningún código hexadecimal, la lógica del sistema buscará una configuración de una muestra de URL de imagen. Si no se configura ni un código hexadecimal ni una URL de imagen, se mostrará texto.

    La siguiente ilustración muestra un ejemplo en el que un PDP en un sitio de comercio electrónico incluye muestras de color y tamaño. En este ejemplo, se configura un código hexadecimal para la dimensión de color. Por lo tanto, las muestras se muestran como colores. Sin embargo, ni un código hexadecimal ni una URL de imagen están configurados para la dimensión de tamaño. Por tanto, se muestra texto.

    ![Ejemplo de la dimensión de color que se muestra como muestras en una página de detalles de un producto de comercio electrónico.](./dev-itpro/media/swatch_pdp.png)

- **Dimensiones para mostrar en la ficha del producto**: especifique qué dimensiones deben aparecer en las tarjetas de productos que se muestran en las listas y en las páginas de listas. Antes de que una dimensión pueda aparecer en una tarjeta de producto, esta configuración debe estar habilitada para esa dimensión. La configuración **Dimensiones para mostrar como imagen** también debe estar habilitada. El comportamiento de selección de muestras en las tarjetas de productos está optimizado para la dimensión del color. Para otras dimensiones, es posible que se requiera una extensión de vista para personalizar el comportamiento de selección de muestras.

    La siguiente ilustración muestra un ejemplo en el que una página de lista en un sitio de comercio electrónico contiene tarjetas de productos que incluyen muestras de color.

    ![Ejemplo de la dimensión de color que se muestra como muestras en una página de lista de comercio electrónico.](./dev-itpro/media/swatch_searchresults.PNG)

Para obtener información sobre cómo configurar las dimensiones del producto para que se muestren como muestras en las páginas del sitio, consulte [Configurar los valores de las dimensiones del producto para que aparezcan como muestras](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de resultados de búsqueda](search-result-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Configurar los valores de las dimensiones del producto para que aparezcan como muestras](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
