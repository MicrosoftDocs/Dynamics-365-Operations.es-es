---
title: Administrar atributos y grupos de atributos
description: En este artículo se describe cómo administrar atributos y grupos de atributos para describir productos y sus características en Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386982"
---
# <a name="manage-attributes-and-attribute-groups"></a>Administrar atributos y grupos de atributos

[!include [banner](includes/banner.md)]

En este artículo se describe cómo administrar atributos y grupos de atributos para describir productos y sus características en Microsoft Dynamics 365 Commerce.

Los *atributos* proporcionan una forma de describir los productos y sus características mediante campos definidos por el usuario. Los ejemplos incluyen el tamaño de la memoria, la capacidad del disco duro y el cumplimiento de Energy Star.

Se pueden asociar atributos con distintas entidades de Commerce, como categorías de productos y canales, y se pueden definir valores predeterminados. Cuando los atributos se asocian a categorías de productos o canales, los productos heredan esos atributos y sus valores predeterminados. Los atributos predeterminados se pueden anular en el nivel de producto individual, en el nivel del canal o en un catálogo.

Por ejemplo, un producto de televisión típico puede tener los siguientes atributos.

| Categoría   | Atributo           | Valores permitidos                        | Valor predeterminado |
|------------|---------------------|-------------------------------------------|---------------|
| Televisión y vídeo | Marca               | Cualquier valor de marca válido                     | Ninguna          |
| TV         | Tamaño de pantalla         | 20-85 pulgadas                              | 55 pulgadas     |
|            | Resolución vertical | 4K (2160p), Full HD (1080p) o HD (720p) | 4K (2160p)    |
|            | Intervalo de actualización de la pantalla | 60hz120hz o 240hz                     | 60hz          |
|            | Entradas HDMI         | 0 – 10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Atributos y tipos de atributo

Los atributos se basan en *tipos de atributo*. Un tipo de atributo identifica el tipo de datos que se pueden introducir para un atributo específico. Se admiten los siguientes tipos de atributo en Commerce:

- **Moneda**: este tipo admite un valor de divisa. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
- **DateTime**: este tipo de atributo admite un valor de fecha y hora. Puede estar limitado o dejarse abierto.
- **Decimal** este tipo admite un valor numérico que incluye decimales. También admite una unidad de medida. Puede estar limitado o dejarse abierto.
- **Número entero**: este tipo admite un valor numérico. También admite una unidad de medida. Puede estar limitado o dejarse abierto.
- **Texto**: este tipo admite un valor de texto. También admite un conjunto predefinido de posibles valores cuando se habilita el ajuste **Lista fija**.
- **Booleano**: este tipo admite un valor binario (**verdadero** o **falso**).
- **Referencia**: este tipo hace referencia a otros atributos.

> [!NOTE]
> Debido a las [limitaciones del índice de búsqueda de Azure](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search), el tipo de atributo **Decimal** no es compatible con las experiencias de búsqueda en la nube. Azure Cognitive Search no admite la conversión de los tipos de atributo **Decimal** a tipos de campo de índice de destino **Edm.Double**, porque esta conversión disminuiría la precisión.

### <a name="set-up-attribute-types"></a>Configurar tipos de atributo

Para configurar tipos de atributo, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Gestión de información de productos \> Configuración \> Categorías y atributos \> Tipos de atributo**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Nombre de tipo de atributo**, introduzca **Tipo de bolsa**.
1. En el campo **Tipo**, seleccione **Texto**.
1. Establezca la opción **Lista fija** en **Sí**.
1. En la ficha desplegable **Valores**, seleccione **Agregar**.
1. En la nueva fila, en el campo **Valor**, introduzca **Mochila**.
1. Agregue cinco filas más. En el campo **Valor** de cada uno, introduzca un valor diferente: **Clutch**, **Monedero**, **Mochila**, **Messenger** o **Billetera**.
1. En el panel Acciones, seleccione **Guardar**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Nombre de tipo de atributo**, introduzca **Marca de gafas de sol**.
1. En el campo **Tipo**, seleccione **Texto**.
1. Establezca la opción **Lista fija** en **Sí**.
1. En la ficha desplegable **Valores**, seleccione **Agregar**.
1. En la nueva fila, en el campo **Valor**, introduzca **Ray ban**.
1. Agregue dos filas más. E el campo **Valor** de cada uno, introduzca un valor diferente: **Aviador** u **Oakley**.
1. En el panel Acciones, seleccione **Guardar**.

![Página de tipos de atributo.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Configurar un atributo

Para configurar un atributo, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Gestión de información de productos \> Configuración \> Categorías y atributos \> Atributos**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Nombre**, especifique **Tipo de Bolsa**.
1. En el campo **Nombre de tipo de atributo**, seleccione **Tipo de bolsa**.
1. En el panel Acciones, seleccione **Guardar**.

![Página de atributos.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Metadatos de atributos

*Metadatos del atributo* le permite seleccionar opciones para especificar cómo deben comportarse los atributos para cada producto. Por ejemplo, puede especificar si los atributos son obligatorios, si se pueden usar para las búsquedas y si se pueden usar como filtro.

Para productos, la configuración de los metadatos del atributo se pueden anular en el nivel de canal.

En la página **Atributos** del atributo incluye varias opciones relacionadas con los metadatos de los atributos. Por ejemplo, si establece la opción **Se puede refinar** en **Sí** en **Metadatos de atributos para canales de Commerce**, el atributo se mostrará para refinar o filtrar los productos en los resultados de la búsqueda y en las páginas de exploración por categorías. Para configurar un atributo como refinable, primero debe seleccionar **Parámetros de filtro** en el panel de acciones y confirmar la configuración del filtro para el atributo.

## <a name="filter-settings-for-attributes"></a>Parámetros de filtro para atributos

Los parámetros de filtro de los atributos le permiten definir cómo se muestran los filtros de los atributos en el punto de venta (PDV). Para acceder a los parámetros de filtro para un atributo, en la página **Atributos** del atributo, en el panel de acciones, seleccione **Parámetros de filtro**.

La página **Parámetros de filtro** incluye los siguientes campos:

- **Nombre**: de forma predeterminada, este campo se establece con el nombre del atributo. Sin embargo, se puede cambiar este valor.
- **Opción de visualización**: están disponibles las siguientes opciones:

    - **Valor único**: esta opción está disponible para los siguientes tipos de atributo: **Booleano**, **Divisa**, **Decimal**, **Entero** y **Texto**. Permite seleccionar un solo valor para los refinadores en las páginas de listas de productos, como la exploración por categorías y las páginas de resultados de búsqueda de productos.
    - **Varios valores**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal**, **Entero** y **Texto**. Permite seleccionar varios valores para el atributo en el cliente, para refinarlo.

- **Control de visualización**: están disponibles las siguientes opciones:

    - **Lista**: esta opción está disponible para todos los tipos de atributo.
    - **Intervalo**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**.
    - **Control deslizante**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**.
    - **Control deslizante con barras**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**.

- **Valor de umbral**: esta configuración es necesaria si seleccionó **Intervalo** como el tipo de control de pantalla. Puede definir valores utilizando un punto y coma (;) como delimitador.

    Por ejemplo, para un atributo **Volumen de bolsa** que tiene un tipo de atributo de **Entero**, el valor de umbral podría ser **10; 20; 50; 100; 200; 500; 1000; 5000**. En este caso, el PDV mostrará los siguientes intervalos. Los intervalos que no tengan ningún producto en el conjunto de resultados aparecerán atenuados.

    - Inferior a 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 o más

Los parámetros de filtro para los atributos son aplicables solo a los atributos de los productos y pueden utilizarse para refinar los resultados de la búsqueda de productos y de la exploración por categorías. No se aplican a la búsqueda de clientes ni a la búsqueda de pedidos, aunque los mismos atributos pueden utilizarse para enriquecer la información de los clientes o de los pedidos.

En los módulos predeterminados de Commerce, no se dispone de compatibilidad con los parámetros de filtro **Control de visualización** como **Rango**, **Control deslizante** y **Control deslizante con barras**. Los ajustes **Rango** y **Control deslizante** siguen siendo compatibles con las soluciones de punto de venta, mientras que el ajuste **Control deslizante con barras** es aplicable a los escaparates en línea heredados de SharePoint y sigue estando disponible para la integración de terceros y los escenarios personalizados.

Le recomendamos que los atributos refinables tengan un atributo del tipo **Texto** en el que esté activada la opción **Lista fija** y que mantenga la lista manejable (hasta 100-200 valores únicos). Si un refinador va a tener 1.000 o más valores únicos, es más apropiado utilizar un atributo del tipo **Texto** en el que la opción **Lista fija** está desactivada.

Las traducciones son fundamentales para los nombres de los atributos y sus valores. Para los atributos del tipo **Texto** en los que la opción **Lista fija** está activada, puede definir traducciones para los valores del atributo en **Tipo de atributo**. Para cualquier otro tipo de atributo, puede definir las traducciones en la página donde se definen los valores del atributo. Por ejemplo, para un atributo del tipo **Texto**, puede definir traducciones para el valor predeterminado en la página **Atributos**. Sin embargo, si anula el valor predeterminado a nivel de producto, puede definir traducciones para el atributo en la página **Atributos del producto**.

Después de que un atributo se haya marcado como refinable para un canal, no debe actualizar el tipo de atributo. De lo contrario, afectará a la publicación de los datos del producto en el índice de búsqueda. En su lugar, le recomendamos que cree un nuevo atributo para un nuevo tipo de refinador y retire el anterior eliminándolo de otros grupos de atributos.

Se admite la búsqueda por atributos, pero solo se obtienen resultados para las coincidencias exactas de las palabras de búsqueda. Por ejemplo, un atributo **Tejido** tiene un valor de **Algodón de cachemira**. Si un cliente busca "Cach" no se recuperará ningún producto que tenga **Algodón de cachemira** como tejido. Sin embargo, si un cliente busca productos de "Cachemira", "Algodón" o "Algodón de cachemira" que tienen **Algodón de cachemira** como tejido, se recuperarán.

### <a name="additional-attribute-metadata-options"></a>Opciones adicionales de metadatos de atributos

> [!NOTE]
> Estas opciones de metadatos de atributos solo son aplicables a la tienda en línea heredada de SharePoint y a las integraciones externas. Para obtener más información acerca de estas opciones de metadatos de atributos, consulte [Visión general del esquema de búsqueda en SharePoint Server 2013](/SharePoint/search/search-schema-overview).

Las siguientes opciones de metadatos de atributos adicionales también están disponibles en la página **Atributos**:

- Se puede buscar
- Se puede recuperar
- Se puede consultar
- Se puede ordenar
- Ignorar caso y formato
- Coincidencia completa

Estas opciones estaban destinadas originalmente a mejorar la funcionalidad de búsqueda de los escaparates en línea heredados basados en SharePoint. No se aplican necesariamente a los sitios web de comercio electrónico de Commerce ni a los terminales PDV. Dado que la integración sin cabeza sigue siendo compatible, estas opciones están disponibles para exportar metadatos de atributos utilizando el kit de desarrollo de software (SDK) de Commerce. Puede utilizar el SDK de Commerce para incluir productos en un índice de búsqueda externo personalizado y optimizado. De esta forma, puede asegurarse de que solo se indexen los atributos que deben indexarse.

## <a name="attribute-groups"></a>Grupos de atributos

Un *grupo de atributos* se usa para agrupar los atributos individuales de un componente o subcomponente en un modelo de configuración de productos. Un atributo puede incluirse en más de un grupo de atributos. Los grupos de atributos pueden ayudar a los usuarios a configurar productos, ya que las distintas selecciones se organizan en un contexto específico. Los grupos de atributos se pueden asignar a categorías o canales. También puede configurar valores predeterminados para los atributos en un grupo de atributos.

![Página de grupos de atributos.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Crear un grupo de atributos

Para crear un grupo de atributos, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Gestión de información de productos \> Configuración \> Categorías y atributos \> Grupos de atributos**.
1. Cree un grupo de atributos que se denomine **Camisas de vestir**.
1. Agregue los siguiente atributos: **MétodoLimpieza**, **TipoCuello**, **Colección** y **Diseño**.

> [!NOTE]
> Los valores de orden de visualización de los atributos en el grupo de atributos no influyen ni se aplican al orden de los refinadores en los resultados de búsqueda y exploración de categorías. Son aplicables solo al escenario de "atributos de orden".

### <a name="assign-attribute-groups-to-categories"></a>Asignar grupos de atributos a las categorías

Se pueden asociar uno o más grupos de atributos con nodos de categoría en los siguientes tipos de jerarquías de categoría:

- Jerarquía de productos de comercio
- Jerarquía de categoría de navegación de canales
- Jerarquía de categoría de productos complementaria

Cuando los productos se categorizan en categorías asociadas con grupos de atributos, heredan los atributos que se incluyen en esos grupos de atributos.

![Ficha desplegable de grupos de atributos de productos en la página de jerarquía de productos de Commerce.](media/AGRetailProdHierarchy_2022Series.png)

Para asignar grupos de atributos a las categorías en la jerarquía de productos de Commerce, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Retail y Commerce \> Productos y categorías \> Jerarquía de productos de Commerce**.
1. Seleccione Jerarquía de navegación **Moda**.
1. En **Ropa de hombre**, seleccione la categoría **Pantalones** y, a continuación, en la pestaña desplegable **Grupos de atributos del producto**, agregue un grupo de atributos que se denomine **Cinturón de hombre**.
1. Seleccione la categoría **Gafas de sol modernas** y compruebe los nuevos atributos en el grupo de atributos **Gafas de sol modernas** seleccionando **Ver atributos**. El grupo de atributos debe mostrar los nuevos atributos **Forma de la lente** y **Marca de gafas de sol**.
1. Seleccione la categoría **Pantalones** y verifique los atributos para el grupo de atributos **Cinturón de hombre** seleccionando **Ver atributos**. El grupo de atributos debe mostrar los atributos **Marca de cinturón de hombre**, **Tejido del cinturón** y **Tamaño del cinturón**.

El mismo procedimiento básico también se puede usar para asignar grupos de atributos a categorías en la jerarquía de categoría de navegación de canales y la jerarquía de categoría de productos complementarios. Sin embargo, en el paso 2, use una de las siguientes rutas, según la jerarquía a la que desee asignar grupos de atributos:

- **Jerarquía de categoría de navegación de canales:** Vaya a **Venta minorista y comercio \> Administración de categorías y productos \> Categorías de navegación de canales**.
- **Jerarquía de categoría de productos complementarios.:** Vaya a **Venta minorista y comercio \> Administración de categorías y productos \> Categorías de productos complementarias**.

> [!NOTE]
> Asegúrese de que sólo asocia grupos de atributos en una jerarquía de categorías en la ficha desplegable **Grupos de atributos del producto**, no en la ficha desplegable **Valores de atributo de la categoría**. Si aparecen atributos en la ficha desplegable **Valores de atributo de la categoría**, seleccione **Editar jerarquía de categoría** en el panel de acciones. A continuación, en la ficha desplegable **Grupos de atributos de categoría**, seleccione los nodos de categoría y seleccione **Quitar**. No hay soporte para la obtención de atributos por categoría a través de la Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identificar los atributos visibles y refinables para los canales de Commerce para la colección de productos predeterminada

Después de haber asociado varios grupos de atributos con categorías en varias jerarquías (jerarquía de productos de Commerce o categorías de navegación del canal) y de haber definido los valores de los atributos para cada producto, basándose en la asociación de categorías, debe activar el indicador **Mostrar atributo en el canal** para que esos atributos sean visibles en un canal específico.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione **Configurar metadatos de atributos** y, a continuación, seleccione un atributo en el panel de navegación izquierdo.
1. En la ficha desplegable **Atributos de producto del canal** (no en la ficha desplegable **Atributos de categoría**), ajuste la opción **Mostrar atributo en el canal** en **Sí** para que el atributo sea visible.
1. Si desea que el atributo también se pueda refinar, configure la opción **Se puede refinar** en **Sí**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Controle la visibilidad de los refinadores basados en las dimensiones, como el tamaño, el estilo y el color

Las dimensiones del producto, como el tamaño, el estilo y el color, son los refinadores más utilizados. Para que estas dimensiones de producto estén disponibles como refinadores, debe asociar un grupo de atributos a nivel de canal que contenga una referencia a un tipo de atributo que herede automáticamente los valores de las dimensiones de producto.

Puede especificar que las dimensiones de los productos sean visibles y refinables actualizando las banderas en la página **Categorías de canal y atributos de producto**. Seleccione el nodo raíz en el panel de navegación y, a continuación, en la ficha desplegable **Atributos de producto del canal**, ajuste la opción **Mostrar atributo en el canal** en **Sí** para los atributos **Tamaño**, **Estilo** y **Color**. Si desea que esos atributos también se puedan refinar, configure la opción **Se puede refinar** en **Sí** para cada uno.

![Configuración de metadatos de atributos para refinadores de dimensiones.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Para habilitar los atributos para que estén disponibles en el canal de Houston basado en datos de demostración, siga los pasos de este procedimiento de ejemplo.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione el canal **Houston**.
1. En el panel de acciones, seleccione **Establecer metadatos del atributo**.
1. Seleccione el nodo de categoría **Moda** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.
1. Seleccione el nodo de categoría **Accesorios de moda**, seleccione la categoría **Gafas de sol modernas** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.
1. Seleccione el nodo de categoría **Ropa de hombre**, seleccione la categoría **Pantalones** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.
1. Después de actualizar los metadatos de atributos para los atributos y refinadores previstos, asegúrese de guardar los cambios y ejecutar el trabajo **Publicar actualizaciones de canal**. A continuación, después de que se publiquen las actualizaciones, deberá ejecutar los siguientes trabajos: **1070** (**Configuración del canal**), **1040** (**Productos**), and **1150** (**Catálogo**).

> [!NOTE]
> - Si su empresa requiere que agregue o elimine con frecuencia productos en la jerarquía de navegación, o que realice cambios como la actualización de los valores de los pedidos de visualización, la adición de nuevas categorías y la adición de nuevos grupos de atributos a las categorías, le recomendamos que configure el trabajo **Publicar actualizaciones de canal** para que se ejecute como un trabajo por lotes frecuente. Alternativamente, actualice manualmente el trabajo **Publicar actualizaciones de cana** y, a continuación, los siguientes trabajos Commerce Data Exchange (CDX): **1070** (**Configuración del canal**), **1040** (**Productos**) y **1150** (**Catálogo**).
> - Una opción **Heredar** le permite especificar que un canal debe heredar los grupos de atributos de su canal principal en la jerarquía. Si establece la opción **Heredar** en **Sí**, el nodo secundario del canal hereda todos los grupos de atributos y todos los atributos en esos grupos de atributos.
> - Si el botón **Configurar metadatos de atributos** en el panel Acciones no está disponible, asegúrese de que la **Jerarquía de navegación** esté asociada con su canal en la ficha desplegable **General**.
> - No debe asociar ningún grupo de atributos excepto los grupos de atributos basados en las dimensiones a nivel de canal (por ejemplo, en **Grupos de atributos** en la página **Categorías de canales y atributos de productos**).
> - Tras la introducción de la compatibilidad con los catálogos de empresa a empresa (B2B) específicos para cada cliente en la versión 10.0.27 de Commerce, se espera que identifique el refinador y las configuraciones de atributos para cada catálogo B2B de la misma manera que se describe en este artículo.

## <a name="override-attribute-values"></a>Anular valores de atributos

Los valores predeterminados de atributos se pueden anular para productos individuales en el nivel de producto. También se pueden anular para los productos individuales en los catálogos específicos que se dirigen a los canales específicos.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Anular los valores de atributo de un producto individual

Para anular los valores de atributo de un producto individual, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Venta minorista y comercio \> Administración de categorías y productos \> Productos liberados por categoría**.
1. Seleccione **Moda \> Accesorios de moda \> Gafas de sol modernas**.
1. Seleccione el artículo requerido en la cuadrícula. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Atributos del producto**.
1. Seleccione un atributo en el panel izquierdo y, a continuación, actualice su valor en el panel derecho.

![Página de valores de atributos del producto.](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Anular los valores de atributo de todos los productos en un catálogo

Para anular los valores de atributo de todos los productos en un catálogo, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Venta minorista y comercio \> Administración de catálogos \> Todos los catálogos**.
1. Seleccione el catálogo **Catálogo de la base de Fabrikam**.
1. Seleccione **Moda \> Accesorios de moda \> Gafas de sol modernas**.
1. En la pestaña desplegable **Productos**, seleccione el producto requerido y, a continuación, seleccione **Atributos** encima de la cuadrícula del producto.
1. En las pestañas desplegables siguientes, actualice los valores de los atributos necesarios:

    - Medios del producto compartido
    - Atributos del producto compartido
    - Canal de medios
    - Atributos de producto del canal

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Anular los valores de atributo de todos los productos en un canal

Para anular los valores de atributo de todos los productos en un canal, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione el canal **Houston**.
1. En la pestaña desplegable **Productos**, seleccione el producto requerido y, a continuación, seleccione **Atributos** encima de la cuadrícula del producto.
1. Si no hay productos disponibles, seleccione **Agregar** en la ficha desplegable **Productos** y, a continuación, seleccione los productos necesarios en el cuadro de diálogo **Agregar productos**.
1. En las pestañas desplegables siguientes, actualice los valores de los atributos necesarios:

    - Medios del producto compartido
    - Atributos del producto compartido
    - Canal de medios
    - Atributos de producto del canal

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Definir valores de atributos específicos de la variante y definir valores múltiples para los atributos del producto

Para definir los valores de los atributos específicos de la variante y para definir múltiples valores para los atributos del producto, siga los pasos de este procedimiento de ejemplo.

1. Inicie sesión en Commerce headquarters como encargado de comercialización.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione el canal **Houston**.
1. En la ficha desplegable **Productos**, seleccione la variante del producto requerida y, a continuación, seleccione **Atributos** encima de la cuadrícula del producto.
1. Si no hay productos disponibles, seleccione **Agregar** en la ficha desplegable **Productos** y, a continuación, seleccione las variantes del producto requeridas en el cuadro de diálogo **Agregar productos**.
1. En las pestañas desplegables siguientes, actualice los valores de los atributos necesarios:

    - Medios del producto compartido
    - Atributos del producto compartido
    - Canal de medios
    - Atributos de producto del canal

#### <a name="example-of-variant-specific-attribute-configuration"></a>Ejemplo de configuración de atributos específicos de la variante
        
En este ejemplo, el producto **P001-Master** es calzado para múltiples actividades que tiene tres variantes: **Correr**, **Caminatas** y **Senderismo**. Para cada variante, desea definir de forma exclusiva el valor del atributo **Actividad**. En la ficha desplegable **Productos** de la página **Categorías de canal y atributos de producto** para su canal, puede definir el valor del atributo **Actividad** para las variantes como se muestra en la siguiente tabla.

| Variante     | Valor de atributo de actividad |
|-------------|--------------------------|
| P001-Master | Deportes                   |
| P001-1      | En ejecución                  |
| P001-2      | Caminar                  |
| P001-3      | Senderismo                 |

Si un usuario busca "zapato", aparecerá el producto **P001-Master** en los resultados de la búsqueda. Si ha configurado el atributo **Actividad** como refinable, el refinador **Actividad** solo mostrará **Deportes** como valor refinable, porque el valor se ha definido para el atributo **Actividad** en el nivel de producto **P001-Master**.

De forma predeterminada, los atributos de nivel de variante están destinados a usarse solo en las páginas de detalles del producto (PDP). Cuando selecciona una variante de producto específica en un PDP, las especificaciones del producto en el PDP se actualizan para esa variante específica.

Para que los refinadores recopilen los valores de los atributos definidos en el nivel de la variante del producto, debe definir un atributo en el nivel del maestro del producto, seleccionar la casilla **Permitir varios valores** y establecer el tipo de atributo en **Texto**.

A continuación, debe determinar todos los valores posibles para las variantes de su producto. Para el atributo **Actividad** que se utiliza en este ejemplo, los posibles valores podrían ser **Correr**, **Caminar**, **Excursionismo**, **Senderismo**, **Camping**, **Deportes acuáticos** y **Deportes de nieve**.

Una vez que haya determinado cuáles deben ser los valores de los atributos de las variantes, puede definirlos en el nivel maestro del producto mediante el uso de valores separados por barras verticales. Para el atributo **Actividad**, puede definir el valor del atributo en el producto maestro como **Correr|Caminar|Excursionismo|Senderismo|Camping|Deportes acuáticos|Deportes de nieve**.

Luego, para cada variante, puede definir valores de atributo ingresando valores separados por barras verticales o valores individuales. Para el atributo **Actividad**, puede configurar una variante de producto individual como **Correr|Caminar|Excursionismo**, **Correr**, **Correr|Excursionismo|Deportes acuáticos**, etc.

Después de definir los valores de atributo de variante en la página **Categorías de canal y atributos de producto**, en el panel Acciones, seleccione **Publicar actualizaciones de canal** y, a continuación, ejecute los trabajos **1150**, **1040** y **1070**.

Una vez que se completan los trabajos y se actualiza el índice de búsqueda, todos los valores esperados deben aparecer en los resultados de búsqueda y en los resultados de exploración de categorías.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
