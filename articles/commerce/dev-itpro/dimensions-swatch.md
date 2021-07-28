---
title: Configurar los valores de las dimensiones del producto para que aparezcan como muestras
description: Este tema describe cómo configurar valores de dimensión de producto como muestras en la sede de Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: 513ec2f48a3c7c81a41fd64a9752067d12eb4ec8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353871"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Configurar los valores de las dimensiones del producto para que aparezcan como muestras

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Este tema describe cómo configurar valores de dimensión de producto como muestras en la sede de Microsoft Dynamics 365 Commerce. Para obtener más información acerca de las dimensiones de productos, vea [Dimensiones de productos](../../supply-chain/pim/product-dimensions.md).

Dynamics 365 Commerce admite el uso de dimensiones de tamaño, estilo y color para representar variantes de productos. Las dimensiones del producto tienen nombres descriptivos que se muestran en las páginas de detalles del producto (PDP) para que se puedan seleccionar las variantes del producto. Ejemplos de estos nombres descriptivos incluyen "Pequeño", "Mediano" y "Grande" para los tamaños y "Negro" y "Marrón" para los colores. Sin embargo, si un producto admite muchas variaciones, se requieren varias selecciones para ver la imagen de cada variante de producto. Por lo tanto, puede resultar lento y tedioso para los clientes buscar y seleccionar variantes de productos.

Cuando las dimensiones se muestran como muestras en los PDP, los clientes obtienen una vista previa visual de las variaciones de un producto. Pueden examinar fácilmente una gran variedad de colores, patrones y texturas, y pueden ver rápidamente diferentes combinaciones de variaciones de productos.

La función de visualización de dimensiones como muestras permite a Commerce utilizar códigos e imágenes hexadecimales (hex) para mostrar las dimensiones como muestras. Además, las dimensiones similares, como los colores, se pueden agrupar en las páginas de la lista de productos. Por ejemplo, un cliente busca productos azules. Si los distintos valores de dimensión azul están agrupados, la página de la lista de resultados de búsqueda muestra productos que tienen diferentes tonos de azul. La agrupación de dimensiones mejora significativamente la experiencia de refinamiento de productos y ayuda a los clientes a encontrar más productos a través de una única consulta de búsqueda de productos.

> [!NOTE]
> La función de dimensiones de la pantalla como muestras está disponible a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.

La siguiente ilustración muestra un ejemplo en el que los colores aparecen como muestras en un PDP de Commerce.

![Ejemplo de colores que se muestran como muestras en la página de detalles de un producto.](../dev-itpro/media/swatch_pdp.png)

La siguiente ilustración muestra un ejemplo en el que los colores aparecen como muestras en una página de lista de resultados de búsqueda de Commerce.

![Ejemplo de colores que se muestran como muestras en la página de resultados de búsqueda.](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Habilite la función de dimensiones de visualización como muestras en la sede de Commerce

Para habilitar la función de dimensiones de visualización como muestras en la sede de Commerce, vaya a **Espacios de trabajo \> Gestión de funciones** y active la característica **Habilitar la compatibilidad de imágenes para los valores de dimensión del producto**. Cuando esta marca de función está habilitada, se agregan tres nuevos campos para cada dimensión en las tablas correspondientes en la sede de Commerce: **Código hexadecimal**, **URL** (para imágenes) y **RefinerGroup**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Configurar valores de dimensión en la sede de Commerce

La función de dimensiones de visualización como muestras es compatible con las dimensiones de tamaño, estilo y color. Los valores de URL de imagen y código hexadecimal para las dimensiones adecuadas se pueden especificar en la sede de Commerce. De forma predeterminada, si el código hexadecimal y los valores de URL de imagen no se proporcionan para una dimensión, el sistema mostrará el texto del nombre descriptivo de la dimensión.

La configuración se puede realizar en cualquiera de los siguientes niveles:

- **Dimensión** - En la sede de Commerce, abra la página de una dimensión buscando por **Color**, **Tamaño**, o **Estilo**. En cada página, una cuadrícula enumera los valores de dimensión. Puede administrar el orden de visualización, el código hexadecimal y los valores de URL de la imagen. La ilustración siguiente muestra un ejemplo configuración en la página **Colores**.

    ![Ejemplo de configuración de dimensiones en la página Colores.](../dev-itpro/media/swatch_Color.PNG)

- **Grupo de dimensiones** - En Dynamics 365 Commerce, puede usar la propiedad **RefinerGroup** para crear grupos de dimensiones. Si se definen grupos de dimensiones, abra la página correspondiente buscando **Grupo de colores**, **Grupo de tamaño**, o **Grupo de estilo**. En cada página, puede administrar el código hexadecimal, la URL de la imagen y los valores del grupo refinador. La ilustración siguiente muestra un ejemplo configuración en la página **Grupos de color**.

    ![Ejemplo de configuración de dimensiones en la página Grupos de color.](../dev-itpro/media/swatch_colorGroup.PNG)

- **Dimensión del producto (durante la creación del producto)** - Cuando crea un nuevo producto, puede utilizar la página **Dimensiones del producto** para introducir los valores de dimensión. Para los productos existentes, los campos **Código hexadecimal**, **URL** (para imágenes) y **RefinerGroup** es posible que ya estén configurados. Sin embargo, puede cambiar los valores si es necesario. La ilustración siguiente muestra un ejemplo configuración en la página **Dimensiones del producto**.

    ![Ejemplo de configuración de dimensiones en la página Dimensiones del producto.](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> El proceso de gestión de configuraciones de URL de imagen y código hexadecimal sigue el mismo patrón que se utiliza para gestionar el orden de visualización de las dimensiones.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Configurar valores de dimensión mediante códigos hexadecimales

Para la mayoría de las dimensiones de color, se debe proporcionar un valor de color de código hexadecimal en las páginas de dimensiones en la sede de Commerce. Por ejemplo, el color negro debe tener un valor de código hexadecimal de **#00000**. Cuando Commerce representa la página de un sitio, el código hexadecimal se representa mediante una muestra de color.

La siguiente ilustración muestra un ejemplo en el que las dimensiones de color se configuran mediante valores de código hexadecimal.

![Ejemplo de configuración de dimensión que usa códigos hexadecimales.](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Configurar valores de dimensión usando URL de imagen

Algunas dimensiones de color representan patrones, no colores sólidos. Por ejemplo, una dimensión de color podría describirse como "leopardo". En estos casos, puede representar de manera más eficaz las dimensiones de color mediante el uso de imágenes publicadas en lugar de códigos hexadecimales para las muestras.

Debe cargar cada imagen en el creador de sitios de Commerce y publicarla. Luego introduzca la URL de imagen para la imagen publicada en las páginas de dimensiones apropiadas en la sede de Commerce. Si se ha seleccionado una dimensión para mostrarla como muestra, pero no se ha definido un código hexadecimal, Commerce buscará una imagen cuando muestre la página. Si la búsqueda de imágenes falla, Commerce mostrará el texto del nombre descriptivo de la dimensión.

La ilustración siguiente muestra un ejemplo en el que se usan URL de imágenes para la configuración en la página **Colores**.

![Ejemplo de configuración de dimensión que usa códigos URL de imagen.](../dev-itpro/media/swatch_color_urls.PNG)

Puede utilizar una plantilla de medios para definir las URL de las imágenes, al igual que para las imágenes de productos y categorías. Cuando carga imágenes en el creador de sitios, las convenciones de nombres de archivo y las rutas de archivo deben ser coherentes.

La ilustración siguiente muestra un ejemplo en el que se usan URL de imágenes para la configuración de una plantilla de medios.

![Ejemplo de configuración de plantilla de medios.](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Configurar valores de dimensión usando URL de imagen y códigos hexadecimales

Para la mayoría de las dimensiones de color, puede configurar tanto códigos hexadecimales como URL de imágenes. La lógica de respaldo de representación de Commerce buscará automáticamente un código hexadecimal o una URL de imagen para mostrar una muestra de color. Utilizar códigos hexadecimales y URL de imágenes para configurar las dimensiones de color, ayuda a simplificar la gestión de imágenes cuando la cantidad de colores es grande.

La ilustración siguiente muestra un ejemplo en el que se usan tanto códigos hexadecimales como URL de imágenes para la configuración en la página **Colores**.

![Ejemplo de configuración de dimensión que usa tanto códigos hexadecimales como URL de imagen.](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Configurar grupos de refinadores

Cuando define un código hexadecimal o una URL de imagen para un valor de dimensión, también puede especificar un valor para el campo **RefinerGroup**. Este campo define la dimensión que debe usarse para agrupar valores de dimensión similares en la experiencia del refinador.

Por ejemplo, si sus valores de dimensión de color son "azul", "tela escocesa azul", "lavado azul" y "azul oscuro", cada valor se asigna a un código hexadecimal o URL de imagen diferente. Por lo tanto, cada valor aparecerá como un color diferente en los PDP y las tarjetas de producto para los productos correspondientes. Sin embargo, si asigna todos esos valores de dimensión de color a un valor **RefinerGroup** de **Azul**, una búsqueda de productos "azules" generará resultados de búsqueda en la página de lista para productos que tienen valores de color de dimensión de "azul", "tela escocesa azul", "lavado azul" y "azul oscuro".

El ejemplo de la siguiente ilustración muestra la relación entre las propiedades **Color** y **RefinerGroup** en la sede de Commerce.

![Ejemplo de gestión de un grupo refinador.](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Administrar imágenes en el generador de sitios de Commerce

Si se utilizan URL de imagen para cualquier valor de dimensión, las imágenes correspondientes deben cargarse en el creador de sitios de Commerce. La ubicación de cada imagen debe coincidir con el nombre del archivo y la ruta de la carpeta que se definen para la imagen en la sede de Commerce. Los archivos de imagen deben cargarse en las ubicaciones de categoría adecuadas en el creador de sitios. Por ejemplo, las imágenes en color deben cargarse en la carpeta de categoría **Color**. Para obtener más información sobre cómo cargar imágenes al creador de sitios, consulte [Cargar imágenes](../dam-upload-images.md).

La siguiente ilustración muestra un ejemplo donde el cuadro de diálogo **Cargar archivos** el cuadro de diálogo se está utilizando para cargar imágenes en la biblioteca de medios del creador de sitios. Destaca las categorías **Tamaño**, **Color**, y **Estilo** que están disponibles para su selección.

![Ejemplo de categorías de archivos de imagen durante la carga a la biblioteca de medios del creador de sitios.](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Habilitar la visualización de muestras en las páginas del sitio de comercio electrónico

Antes de que las muestras puedan aparecer en las páginas del sitio de comercio electrónico que requieren la selección de dimensiones, como PDP y páginas de lista, debe configurar los parámetros del sitio de dimensiones en la sede de Commerce. Para más información, ver [Aplicar la configuración del sitio para las dimensiones](../dimension-settings.md).

Además, debe habilitar la propiedad **Incluir atributos de productos en los resultados de búsqueda** para módulos de resultados de búsqueda. Si su sitio utiliza páginas de categorías personalizadas, debe actualizar los módulos de resultados de búsqueda que se utilizan en esas páginas, de modo que la propiedad **Incluir atributos de productos en los resultados de búsqueda** está habilitada. Para obtener más información, consulte [Módulo de resultados de búsqueda](../search-result-module.md).

## <a name="display-swatches-in-pos-and-other-channels"></a>Muestra muestras en PDV y otros canales

Actualmente, Commerce no tiene una implementación lista para usar que admita la visualización de muestras en el punto de venta (PDV) y otros canales. Sin embargo, puede implementar la funcionalidad de visualización de muestras como una extensión que hace que las API de canal devuelvan los códigos hexadecimales y las URL de imagen que se requieren para representar las muestras.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de resultados de búsqueda](../search-result-module.md)

[Aplicar la configuración del sitio para las dimensiones](../dimension-settings.md)

[Dimensiones de producto](../../supply-chain/pim/product-dimensions.md)

[Cargar imagen](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
