---
title: Atributos, grupos de atributos y sus asociaciones con diversas entidades minoristas en Finance and Operations
description: "Este tema describe cómo usar atributos para proporcionar una forma de describir un producto y sus características a través de campos definidos por el usuario."
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5e04b1f6ef58836eeac85be074e295e6d1f42c52
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="attributes-attribute-groups-and-their-associations-with-various-retail-entities-in-finance-and-operations"></a>Atributos, grupos de atributos y sus asociaciones con diversas entidades minoristas en Finance and Operations

[!include [banner](includes/banner.md)]

*Atributos* proporciona una forma de describir adicionalmente un producto y sus características a través de campos definidos por el usuario (como **Tamaño de la memoria**, **Capacidad del disco duro**, **Cumple con Energy Star**, etc.). En Microsoft Dynamics 365 for Finance and Operations, los atributos se pueden asociar con las distintas entidades de Retail, como categorías de productos y canales de venta minorista, y se pueden definir valores predeterminados. A continuación, los productos heredan los atributos y los valores predeterminados para dichos atributos cuando se asocian a las categorías de productos o canales de venta minorista. Los valores predeterminados se pueden anular en el nivel de producto individual, en el nivel del canal de venta minorista o en un catálogo de venta minorista.
 
Por ejemplo, un producto de televisión típico puede tener los siguientes atributos.

| Categoría   | Atributo                | Valores permitidos          | Valor predeterminado |
|------------|--------------------------|-----------------------------|---------------|
| Televisión y vídeo | Marca                    | Cualquier valor de marca válido       | Sin ordenar          |
| Televisión         | Tamaño de pantalla              | 20-80 pulgadas                | Sin ordenar          |
|            | Resolución vertical      | 480i, 720p, 1080i o 1080p | 1080p         |
|            | Intervalo de actualización de la pantalla      | 60hz120hz o 240hz       | 60hz          |
|            | Entradas HDMI              | 0 – 10                        | 3             |
|            | Entradas DVI               | 0 – 10                        | 1             |
|            | Entradas compuestas         | 0 – 10                        | 2             |
|            | Entradas del componente         | 0 – 10                        | 1             |
| LCD        | Preparada para 3D                 | Sí o No                   | Sí           |
|            | Habilitada para 3D               | Sí o No                   | N.º            |
| Plasma     | Temporalidad de operación desde      | 32–110 grados              | 32            |
|            | Temporalidad de operación hasta        | 32–110 grados              | 100           |
| Proyección | Garantía de tubo de proyección | 612 o 18 meses         | 12            |
|            | # de tubos de proyección    | 1 – 5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Atributos y tipos de atributo

Los atributos se basan en *tipos de atributo*. El tipo de atributo identifica el tipo de datos que se pueden introducir para un atributo específico. Finance and Operations admite actualmente los siguientes tipos de atributo:

- **Moneda**: este tipo admite un valor de divisa. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
- **DateTime**: este tipo de atributo admite un valor de fecha y hora. Puede estar limitado o dejarse abierto.
- **Decimal** este tipo admite un valor numérico que incluye decimales. También admite una unidad de medida. Puede estar limitado o dejarse abierto.
- **Número entero**: este tipo admite un valor numérico. También admite una unidad de medida. Puede estar limitado o dejarse abierto.
- **Texto**: este tipo admite un valor de texto. También admite un conjunto predefinido de valores posibles (es decir, una *enumeración*).
- **Booleano**: este tipo admite un valor binario (**verdadero** o **falso**).
- **Referencia**: este tipo hace referencia a otros atributos.

### <a name="set-up-attribute-types-in-finance-and-operations"></a>Configurar tipos de atributo en Finance and Operations

1. Inicie sesión en el cliente de la oficina administrativa de Finance and Operations como encargado de comercialización.
2. Vaya a **Gestión de información de productos** &gt; **Configuración** &gt; **Categorías y atributos** &gt; **Tipos de atributo**.
3. Cree dos tipos de atributo del tipo **Texto**, establezca la opción **Lista fija** en **Sí** y, a continuación, agregue una lista de valores:

    - Nombre un tipo de atributo **Forma de la lente** y agregue los siguientes valores: **Óvalo**, **Cuadrado** y **Rectángulo**.
    - Nombre el otro tipo de atributo **Marca de gafas de sol** y agregue los siguientes valores: **Ray Ban**, **Aviador** y **Oakley**.

![Tipos de atributo](media/AttributeType.png)

### <a name="set-up-an-attribute-in-finance-and-operations"></a>Configurar un atributo en Finance and Operations

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya a **Gestión de información de productos** &gt; **Configuración** &gt; **Categorías y atributos** &gt; **Atributos**.
3. Cree un atributo con el nombre **Lente**.
4. Establezca el campo **Tipo de atributo** en **Forma de la lente**.

![Atributos](media/Attribute.png)

## <a name="attribute-metadata"></a>Metadatos de atributos

*Metadatos del atributo* le permite seleccionar opciones para especificar cómo deben comportarse los atributos para cada producto. Por ejemplo, puede especificar si los atributos son obligatorios, si se pueden usar para las búsquedas y si se pueden usar como filtro.

Para productos minoristas, la configuración de los metadatos del atributo se pueden anular en el nivel de canal. Esta capacidad discutirá más adelante en este tema.

Como puede observar, la página **Atributos** incluye opciones relacionadas con los metadatos de los atributos. En **Metadatos del atributos para PDV**, una opción que se denomina **"Se puede refinar"** afecta al comportamiento de los valores de los atributos en el punto de venta (PDV) minorista o el modo en que el sistema trata esos valores de los atributos. Solo los atributos para los que puede establecer la opción **"Se puede refinar"** en **"Sí" “** aparecerán para el refinamiento o el filtrado de productos en el PDV comercial.

Aquí se muestran las opciones restantes de los metadatos de atributos en la página **Atributos**:

- Se puede buscar
- Se puede recuperar
- Se puede consultar
- Se puede ordenar
- Permitir varios valores
- Ignorar caso y formato
- Coincidencia completa

Estas opciones estaban pensadas originalmente para mejorar la funcionalidad de búsqueda para el escaparate en línea. Aunque Finance and Operations no incluye el escaparete en línea lista para usar, incluye el kit de desarrollo de software (SDK) de publicación de comercio electrónico. Los clientes pueden usar este SDK para poner productos en un índice de búsqueda de su elección. Aunque los datos del productos son importados, los clientes aún deben poder distinguir los datos que se pueden buscar, los datos que se pueden consultar, etc. De esa manera, pueden crear un índice óptimo para asegurarse de que solo indexan los atributos que, *en su opinión*, deben indexarse.

Para obtener información acerca del propósito de estas opciones restantes, consulte [Visión general del esquema de búsqueda en SharePoint Server 2013](https://technet.microsoft.com/en-us/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Parámetros de filtro para atributos

Los parámetros de filtro para atributos le permiten definir cómo se muestran los filtros para atributos en el PDV comercial. Para acceder a los parámetros de filtro para un atributo, en la página **Atributos** en Finance and Operations, seleccione el atributo y, a continuación, en el panel de acciones, seleccione **Parámetros de filtro**.

La página **Preferencias de visualización de filtros** incluye los siguientes campos:

- **Nombre**: de forma predeterminada, este campo se establece con el nombre del atributo. Sin embargo, se puede cambiar este valor.
- **Opción de visualización**: están disponibles las siguientes opciones:

    - **Valor único**: esta opción está disponible para los siguientes tipos de atributo: **Booleano**, **Divisa**, **Decimal**, **Entero** y **Texto**. Esta opción habilita la selección de valor único para estos atributos en el cliente para el refinamiento.
    - **Varios valores**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal**, **Entero** y **Texto**. Esta opción habilita la selección de varios valores para este atributo en el cliente para el refinamiento.

- **Control de visualización**: están disponibles las siguientes opciones:

    - **Lista**: esta opción está disponible para todos los tipos de atributo.
    - **Intervalo**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**. 
    - **Control deslizante**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**.
    - **Control deslizante con barras**: esta opción está disponible para los siguientes tipos de atributo: **Divisa**, **Decimal** y **Entero**.

- **Valor de umbral**: esta configuración es necesaria si seleccionó **Intervalo** como el tipo de control de pantalla. Puede definir valores utilizando un punto y coma (;) como delimitador.

    Por ejemplo, para el filtro como **Volumen de bolsa**, un valor de umbral puede ser **10; 20; 50; 100; 200; 500; 1000; 5000**. En este caso, el PDV comercial mostrará los siguientes intervalos. Cualquier intervalo que no tenga ningún producto en el conjunto de resultados aparecerá atenuado.

    - Inferior a 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 o más

![Parámetros de filtro de atributos](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Grupos de atributos

Después de que se hayan definido los atributos, estos se pueden asignar a grupos de atributos. Un *grupo de atributos* se usa para agrupar los atributos individuales de un componente o subcomponente en un modelo de configuración de productos. Un atributo puede incluirse en más de un grupo de atributos. Los grupos de atributos pueden ayudar a los usuarios a configurar productos, ya que las distintas selecciones se organizan en un contexto específico. Los grupos de atributos se pueden asignar a categorías o canales comerciales.

También puede configurar valores predeterminados para los atributos incluidos en un grupo de atributos. Por ejemplo, puede agregar un atributo de color para un grupo de atributos y seleccionar **Azul** como el valor de atributo predeterminado. En este caso, cuando se agrega el grupo de atributos a un producto al por menor que incluye el color como uno de sus atributos, aparece **Azul** como el color predeterminado para ese producto.

![Grupos de atributos](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Crear un grupo de atributos

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya a **Gestión de información de productos** &gt; **Configuración** &gt; **Categorías y atributos** &gt; **Grupos de atributos**.
3. Creae un grupo de atributos que se denomine **Gafas de sol modernas**.
4. Agregue los siguientes atributos: **Forma de la lente** y **Marca de gafas de sol**.

### <a name="assign-attribute-groups-to-retail-categories"></a>Asignar grupos de atributos a las categorías de venta minorista

Se pueden asociar uno o más grupos de atributos a los nodos de categorías en los siguientes tipos de jerarquías de categorías al por menor: jerarquía de productos al por menor, jerarquía de categoría de navegación de canales y jerarquía de categoría de productos complementarios. A continuación, cuando se han clasificado los productos, heredan los atributos incluidos en los grupos de atributos.

![Jerarquía de productos al por menor – Grupos de atributos del producto](media/AGRetailProdHierarchy.PNG)

Siga estos pasos para asignar grupos de atributos a las categorías de la jerarquía de producto al por menor.

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya al **Ventas al por menor** &gt; **Administración de categorías y productos** &gt; **Jerarquía de producto al por menor**.
3. Seleccione **Jerarquía de navegación de moda**.
4. En **Ropa de hombre**, seleccione la categoría **Pantalones** y, a continuación, en la pestaña desplegable **Grupos de atributos del producto**, agregue un grupo de atributos que se denomine **Cinturón de hombre**.
5. Seleccione la categoría **Gafas de sol modernas** y compruebe los nuevos atributos en el grupo de atributos **Gafas de sol modernas** seleccionando **Ver atributos**.

    El grupo de atributos debe mostrar los nuevos atributos **Forma de la lente** y **Marca de gafas de sol**.

6. En **Ropa de hombre**, seleccione la categoría **Pantalones** y compruebe los atributos para el grupo de atributos **Cinturón de hombre** seleccionando **Ver atributos**.

    El grupo de atributos debe mostrar los atributos **Marca de cinturón de hombre**, **Tejido del cinturón** y **Tamaño del cinturón**.

> [!NOTE]
> Este procedimiento también se puede usar para asignar grupos de atributos a categorías en la jerarquía de categoría de navegación de canales y la jerarquía de categoría de productos complementarios. En el paso 2, use las siguientes rutas de navegación:
>
> - **Ventas al por menor** &gt; **Administración de categorías y productos** &gt; **Categorías de navegación de canales**
> - **Ventas al por menor** &gt; **Administración de categorías y productos** &gt; **Categorías de productos complementarios**

### <a name="assign-attribute-groups-to-retail-stores"></a>Asignar grupos de atributos a las tiendas de venta minorista

Uno o más grupos de atributos se pueden asociar a una o más tiendas de venta minorista en la jerarquía de tiendas de venta minorista. A continuación, cuando se enriquecen los productos para tiendas de enta minorista concretas, heredan los atributos incluidos en los grupos de atributos.

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya a **Venta al por menor** &gt; **Configuración de canal** &gt; **Categorías de canal y atributos de producto**.
3. Asignar grupos de atributos al canal de Houston:

    1. Seleccione el canal **Houston**.
    2. En la pestaña desplegable **Grupo de atributos**, seleccione **Añadir** y, a continuación, en el campo **Nombre**, seleccione **SharePointProvisionedProductAttributeGroup**.
    3. Seleccione **Añadir** de nuevo y, a continuación, en el campo **Nombre**, seleccione **Cinturón de hombre**.
    4. Seleccione **Añadir** de nuevo y, a continuación, en el campo **Nombre**, seleccione **Gafas de sol modernas**.

        > [!NOTE]
        > Una opción le permite especificar que este canal debe heredar los grupos de atributos de su canal principal en la jerarquía. Si establece la opción **Heredar** en **Sí**, el nodo secundario del canal hereda todos los grupos de atributos y todos los atributos en esos grupos de atributos.

4. Habilite los atributos de modo que estén disponibles en el canal de Houston:

    1. En el panel de acciones, seleccione **Establecer metadatos del atributo**.
    2. Seleccione el nodo de categoría **Moda** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.
    3. Seleccione el nodo de categoría **Accesorios de moda**, seleccione la categoría **Gafas de sol modernas** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.
    4. Seleccione el nodo de categoría **Ropa de hombre**, seleccione la categoría **Pantalones** y, a continuación, en la pestaña desplegable **Atributos de producto del canal**, seleccione **Incluir atributo** para cada atributo.

![Categorías de canal y atributos de producto – Grupos de atributos](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Anular valores de atributos

Los valores predeterminados de atributos se pueden anular para productos individuales en el nivel de producto. Los valores predeterminados de atributos también se pueden anular para los productos individuales en los catálogos específicos que se dirigen a los canales de venta minorista específicos.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Anular los valores de atributo de un producto individual

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya a **Ventas al por menor** &gt; **Administración de categorías y productos** &gt; **Productos liberados por categoría**.
3. Seleccione el nodo de categoría **Moda** &gt; **Accesorios de moda** &gt; **Gafas de sol modernas**.
4. Seleccione el artículo requerido en la cuadrícula. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Atributos del producto**.
5. Seleccione un atributo en el panel izquierdo y, a continuación, actualice su valor en el panel derecho.

![Página de detalles del producto – Grupos de atributos del producto](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Anular los valores de atributo de productos en un catálogo

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya al **Ventas al por menor** &gt; **Administración de catálogo** &gt; **Todos los catálogos**.
3. Seleccione el catálogo **Catálogo de la base de Fabrikam**.
4. Seleccione el nodo de categoría **Moda** &gt; **Accesorios de moda** &gt; **Gafas de sol modernas**.
5. En la pestaña desplegable **Productos**, seleccione el producto requerido y, a continuación, seleccione **Atributos** encima de la cuadrícula del producto.
6. En las pestañas desplegables siguientes, actualice los valores de los atributos necesarios:

   - Medios del producto compartido
   - Atributos del producto compartido
   - Canal de medios
   - Atributos de producto del canal

     > [!NOTE]
     > Si se crean medios del producto compartido y atributos del producto compartido en Finance and Operations, se aplican a todos los productos al por menor.

![Grupos de atributos del producto de catálogo](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Anular los valores de atributo de productos en un canal

1. Inicie sesión en el cliente de la oficina administrativa como encargado de comercialización.
2. Vaya a **Venta al por menor** &gt; **Configuración de canal** &gt; **Categorías de canal y atributos de producto**.
3. Seleccione el canal **Houston**.
4. En la pestaña desplegable **Productos**, seleccione el producto requerido y, a continuación, seleccione **Atributos** encima de la cuadrícula del producto.

    > [!NOTE]
    > Si no hay productos disponibles, agregue productos seleccionando **Añadir** en la pestaña desplegable **Productos** y, a continuación, seleccionando los productos necesarios en el cuadro de diálogo **Agregar productos**.

5. En las pestañas desplegables siguientes, actualice los valores de los atributos necesarios:

   - Medios del producto compartido
   - Atributos del producto compartido
   - Canal de medios
   - Atributos de producto del canal

     > [!NOTE]
     > Si se crean medios del producto compartido y atributos del producto compartido en Finance and Operations, se aplican a todos los productos al por menor.

