---
title: Módulo de resultados de búsqueda
description: En este tema se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bae825ed7093494c48abac119c480be0dba4f951
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919483"
---
# <a name="search-results-module"></a>Módulo de resultados de búsqueda

[!include [banner](includes/banner.md)]


En este tema se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

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

Para agregar un módulo de resultados de la búsqueda a una página de categoría, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, escriba el nombre **Resultados de la búsqueda** y seleccione **Aceptar**.
1. En la entrada **Cuerpo**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En la entrada **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Navegación** y, a continuación, **Aceptar**.
1. En el panel de propiedades **Ruta de navegación**, introduzca el valor **1** para **Ocurre lo mín.**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Resultados de la búsqueda** y, a continuación, seleccione **Aceptar**.
1. En el panel de propiedades **Resultados de la búsqueda**, introduzca el valor **1** para **Ocurre lo mín.** y establezca los valores de las demás propiedad necesarias para el módulo de resultados de búsqueda. Al establecer estas propiedades en la plantilla, se asegura de que cualquier personalización de una página de categoría específica incluirá automáticamente esta configuración.
1. Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Resultados de la búsqueda** creada anteriormente, escriba **Página de categoría** para **Nombre de página** y, a continuación, seleccione **Aceptar**. Puesto que todos los valores se establecen en la plantilla, la página está lista para publicarse.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Habilitar el conocimiento del inventario para el módulo de resultados de búsqueda

Los clientes generalmente esperan que un sitio de comercio electrónico tenga en cuenta el inventario durante toda la experiencia de navegación, de modo que puedan decidir qué hacer si no hay inventario para un producto. El módulo de resultados de búsqueda se puede mejorar para que incorpore datos de inventario y proporcione las siguientes experiencias:

- Muestre una etiqueta de disponibilidad de inventario junto con los productos.
- Ocultar productos agotados.
- Muestre los productos agotados al final de la lista de resultados de búsqueda.
    
Para habilitar estas experiencias, debe configurar los siguientes requisitos previos en la sede de Commerce.

### <a name="enable-the-enhanced-e-commerce-product-discovery-to-be-inventory-aware-feature"></a>Habilitar la característica de detección de productos de comercio electrónico mejorados para que reconozcan el inventario

> [!NOTE]
> La característica **Descubrimiento mejorado de productos de comercio electrónico para tener en cuenta el inventario** está disponible a partir de la versión 10.0.20 de Commerce.

Para habilitar la característica **Descubrimiento mejorado de productos de comercio electrónico para tener en cuenta el inventario** en la sede de Comercio, siga estos pasos.

1. Vaya a **Espacios de trabajo \> Administración de características**.
1. Busque la característica **Descubrimiento mejorado de productos de comercio electrónico para tener en cuenta el inventario** y habilítela.

### <a name="configure-the-populate-product-attributes-with-inventory-level-job"></a>Configurar los atributos del producto con el trabajo de nivel de inventario

El trabajo **Completar los atributos del producto con el nivel de inventario** crea un nuevo atributo de producto para capturar la disponibilidad del inventario y luego establece ese atributo en el último valor de nivel de inventario para cada producto maestro. Debido a que la disponibilidad de inventario de un producto o surtido que se vende cambia constantemente, le recomendamos encarecidamente que programe el trabajo como un proceso por lotes.

Para configurar el trabajo **Completar los atributos del producto con el nivel de inventario** en la sede de Comercio, siga estos pasos.

1. Vaya a **Retail y Commerce \> Retail y Commerce TI \> Productos e inventario**.
1. Seleccione **Rellenar los atributos del producto con el nivel de inventario**.
1. En el cuadro de diálogo **Completar los atributos del producto con el nivel de inventario**, siga estos pasos:

    1. Debajo de **Parámetros**, en el campo **Atributo del producto y nombre del tipo**, especifique un nombre para el atributo de producto dedicado que se creará para capturar la disponibilidad del inventario.
    1. Debajo de **Parámetros**, en el campo **Disponibilidad de inventario basada en**, seleccione la cantidad en la que se debe basar el cálculo del nivel de inventario (por ejemplo, **Físico disponible**).
    1. Debajo de **Ejecutar en segundo plano**, configure el trabajo para que se ejecute en segundo plano y, opcionalmente, active la opción **Procesamiento por lotes**. 

> [!NOTE]
> Para un cálculo uniforme del nivel de inventario en los PDP y las páginas de la lista de productos en su sitio de comercio electrónico, asegúrese de seleccionar la misma opción de cantidad para los ajustes **Disponibilidad de inventario basada en** en la sede de Comercio y **Nivel de inventario basado en** en el creador de sitios de Commerce. Para obtener más información sobre la configuración de inventario en el generador de sitios, consulte [Aplicar configuración de inventario](inventory-settings.md).

### <a name="configure-the-new-product-attribute"></a>Configurar el nuevo atributo de producto

Después de ejecutar el trabajo **Completar los atributos del producto con el nivel de inventario**, debe configurar el atributo de producto recién creado en el sitio de comercio electrónico donde desea habilitar el conocimiento del inventario para el módulo de resultados de búsqueda.

Para configurar el nuevo atributo de producto en la sede central de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto** y seleccione un sitio de comercio electrónico.
1. Seleccione y abra un grupo de atributos asociado, agregue el atributo de producto recién creado y luego cierre la página.
1. Seleccione **Establecer metadatos de atributos**, seleccione el atributo de producto recién agregado y luego active las opciones **Mostrar atributo en el canal**, **Recuperable**, **Puede ser refinado** y **Puede ser consultado**.

> [!NOTE]
> Para los productos que se muestran en el módulo de resultados de búsqueda, el nivel de inventario se ingresa en el nivel de producto maestro en lugar del nivel de variante individual. Tiene solo dos valores posibles: "disponible" y "agotado". El texto real de los valores se recupera de la definición del [perfil de nivel de inventario](inventory-buffers-levels.md). Un producto maestro se considera agotado solo cuando todas sus variantes están agotadas. El nivel de inventario de una variante se determina en función de la definición del perfil de nivel de inventario del producto. 

Una vez completados todos los pasos de configuración anteriores, los refinadores de las páginas de resultados de búsqueda mostrarán un filtro basado en el inventario y el módulo de resultados de la búsqueda recuperará los datos del inventario entre bastidores. A continuación, puede configurar el ajuste **Configuración de inventario para páginas de lista de productos** en el creador de sitios de Commerce para controlar cómo el módulo de resultados de búsqueda muestra los productos agotados. Para obtener más información, consulte [Aplicar configuración de inventario](inventory-settings.md).

## <a name="additional-resources"></a>Recursos adicionales

[Información general de la página de aterrizaje de la categoría predeterminada y la página de resultados de la búsqueda](category-search-page-overview.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de vista rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
