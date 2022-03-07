---
title: Personalizar navegación del sitio
description: Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8af68fff17f2f92356ade356da0e75867ed54950d744c6cbe730ad8db4ac3975
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755891"
---
# <a name="customize-site-navigation"></a>Personalizar navegación del sitio

[!include [banner](includes/banner.md)]

Este tema describe cómo crear una jerarquía de navegación en línea personalizada para organizar sus productos para examinar en su sitio de Microsoft Dynamics 365 Commerce.

Los escaparates en línea normalmente permiten a los clientes detectan y examinar productos navegando por categorías de productos. Esta capacidad es suele proporcionar mediante fichas en la parte superior de la página o por una barra de navegación a la izquierda. En Dynamics 365 Commerce, puede crear y gestionar la estructura jerárquica de su navegación de categorías y los productos que se incluyen en las diversas categorías.

## <a name="create-a-channel-navigation-hierarchy"></a>Crear una jerarquía de navegación de canales

Para crear una jerarquía de navegación de canales, siga estos pasos.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Administración de categorías y productos**.
1. Seleccione **Jerarquías de categorías** y después **Nuevo**.
1. Asigne un nombre a la jerarquía.

    > [!NOTE]
    > La categoría superior que cree es el nodo de categoría raíz. No se mostrará en el sitio. Para crear una jerarquía de categoría donde se muestre un solo nodo de nivel superior en el sitio, cree y asigne un nombre a la categoría como elemento secundario de la categoría raíz.

1. Seleccione **Nodo de categoría nueva** y asigne un nombre a la categoría.
1. Continúe creando categorías secundarias y elemento del mismo nivel como sea necesario.

Ahora puede asignar productos a cada categoría que ha creado en la categoría de nivel superior.

## <a name="customize-the-order-of-categories"></a>Personalizar el orden de categorías

De manera predeterminada, las categorías que defina aparecerán en orden alfabético en su sitio. Sin embargo, también puede personalizar el orden de visualización de las categorías.

## <a name="assign-a-category-hierarchy-type"></a>Asignación de un tipo de jerarquía de categoría

1. Vaya a **Retail y Commerce \> Productos y categorías \> Administración de categorías y productos**.
1. Seleccione **Jerarquías de categorías**.
1. En el panel de acciones, en la pestaña **Jerarquía de categoría** del grupo **Configurar**, seleccione **Asociar tipo de jerarquía**.
1. Seleccione **Nuevo**.
1. En el campo **Tipo de jerarquía de categorías**, seleccione **Jerarquía de navegación de canales**.
1. En el campo **Jerarquía de categoría**, seleccione la jerarquía de navegación de canales que creó anteriormente.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Publicar jerarquías de navegación nuevas o actualizadas

Para poner la jerarquía de navegación a disposición de su escaparate en línea, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. En el árbol de la izquierda, seleccione su tienda en línea.
1. Seleccione **Publicar actualizaciones de canal**.
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. En la lista, busque y seleccione **Trabajo 1040**.
1. Seleccione **Ejecutar ahora**.
1. Repita los pasos 5 y 6 para los trabajos 1070 y 1150.

## <a name="show-categories-on-your-site"></a>Mostrar categorías en su sitio

Para mostrar su jerarquía de categoría en su escaparate en línea, debe agregar el módulo de menú de navegación en la ubicación adecuada en una plantilla o fragmento. El módulo de menú de navegación mostrará a continuación la jerarquía de navegación, siempre que haya publicado la jerarquía de navegación para el canal al que está enlazado el sitio.

> [!NOTE]
> El módulo de menú de navegación que se incluye en la biblioteca de módulos permite a los usuarios navegar solo a las categorías que no tienen subcategorías. Si sus clientes deben poder navegar a las categorías con subcategorías, debe personalizar el módulo del menú de navegación.

## <a name="add-custom-navigation-options"></a>Agregar opciones de navegación personalizadas

En el menú de navegación, puede agregar opciones de navegación que no forman parte de la jerarquía de categoría de productos. Por ejemplo, al final de la lista de categorías de productos, puede agregar un elemento **Ponerse en contacto con nosotros** que apunte a una página de contacto que haya creado para el sitio.

Para agregar opciones de navegación personalizadas al menú de navegación, siga estos pasos.

1. En la plantilla o el fragmento que desea personalizar, seleccione el módulo del menú de navegación.
1. En el panel de propiedades, en la pestaña **Datos**, seleccione **Agregar artículo** para crear un artículo nuevo de navegación del sistema de gestión de contenidos (CMS).
1. Especificar el texto del vínculo y una dirección URL.
1. Repita los pasos 2 y 3 para agregar más opciones de navegación personalizadas.
1. Cuando haya terminado, seleccione **Guardar** para guardar la plantilla o el fragmento y luego seleccione **Finalizar edición** para protegerlos.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con plantillas](work-with-templates.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Trabajar con módulos](work-with-modules.md)

[Crear un URL de página](create-page-url.md)

[Trabajar con grupos de publicación](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
