---
title: Trabajar con módulos
description: Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c4161e7a40cdbbb40292a6ce9acab58347460bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914803"
---
# <a name="work-with-modules"></a>Trabajar con módulos

Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a>Visión general

Los módulos son bloques de creación lógicos que componen su estructura de página y tienen diversos propósitos y ámbitos. Algunos módulos son contenedores de alto nivel y su único propósito es mantener y organizar otros módulos (módulos secundarios). Otros módulos, como un módulo de ubicación de imagen sencillo, tienen un propósito muy específico. Otros módulos, como un módulo de carrusel, se encuentren en algún lugar entre esas dos categorías.

De manera predeterminada, el sitio de Dynamics 365 Commerce incluye una biblioteca de módulo de kit de inicio que le permite lograr la mayoría de escenarios comercio electrónico básicos. Debería poder crear un sitio de comercio electrónico integral solo con estos módulos. Sin embargo, también podría desea personalizar estos módulos o crear módulos personalizados nuevos para necesidades específicas. Si desea crear módulos personalizados, un kit de desarrollo de software (SDK) de diseño de módulo está disponible para ayudarle a crear una biblioteca de módulo personalizada.

## <a name="container-modules-and-slots"></a>Franjas y módulos de contenedor

Como se mencionó anteriormente, algunos módulos están diseñados para mantener módulos secundarios. Esos módulos se conocen como *contenedores* y permiten jerarquías de módulos anidados. Los módulos de contenedor incluyen *franjas*. Las franjas se usan para administrar el diseño y el propósito de módulos secundarios en el contenedor. Un ejemplo es un módulo de contenedor de página básica (un módulo de nivel superior para cualquier página) que define varias franjas importantes:

- Una franja de encabezado
- Una franja de cuerpo
- Una franja de pie de página

El desarrollador del módulo define estas franjas y determina los módulos secundarios y cuántos módulos secundarios se pueden colocar directamente en él. Por ejemplo, la franja de encabezado solo puede admitir un módulo del tipo **Módulo de encabezado**, mientras que la franja del cuerpo puede admitir un número ilimitado de módulos de cualquier tipo (sin incluir otros módulos de contenedor de página).

En las herramientas de creación, los autores de página no tienen que saber por adelantado qué módulos se pueden y no se pueden colocar en cada franja. Cuando los autores de la página seleccionan una franja e intentan seleccionar un módulo para agregarlo a él, ven una vista filtrada de tipos de módulo que se admiten para esa franja.

## <a name="content-modules"></a>Módulos de contenido

Los módulos de contenido contienen elementos multimedia y de contenido, como texto (por ejemplo, encabezados, párrafos y vínculos) o referencias de activos (por ejemplo, imágenes, vídeo y PDF). Algunos ejemplos de tipos de módulo de contenido típicos son **Elemento principal**, **Característica** y **Banner**. Los módulos de estos tres tipos pueden contener texto o medios, y no requieren módulos secundarios para hacer que algo sea visible en una página.

La mayoría de las actividades de creación de contenido y página típicas y diaria implican módulos de contenido, principalmente porque estos módulos definen el contenido real que se representa en sus módulos de contenedor principal. Hay muchos módulos de contenido disponibles y estos módulos suelen ser las últimos piezas que agregará a la jerarquía de una página de módulos anidados.

La ilustración siguiente muestra cómo los módulos se anidan dentro de franjas de módulo de contenedor principal.

![Anidación de módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Agregar o quitar módulos

Los siguientes procedimientos describen cómo agregar y quitar módulos.

### <a name="add-a-module"></a>Agregar un módulo

Para agregar un módulo a una franja o un contenedor de una página, siga estos pasos.

1. En el panel de esquema de la izquierda, seleccione un contenedor o una franja a la que se pueda agregar un módulo secundario.

    > [!NOTE]
    > El diseñador del módulo define la lista de tipos de módulos que se pueden agregar a una franja específica del módulo. A continuación, los autores de plantilla pueden limitar las opciones de módulo permitidas para ayudar a garantizar la optimización de motor de búsqueda (SEO) coherente y la eficiencia de creación para todas las páginas que se crean a partir de una plantilla específica.

1. Seleccione el botón de puntos suspensivos (**...**) para el módulo y, a continuación, seleccione **Agregar módulo**. Aparece el cuadro **Agregar módulo**. Este cuadro de diálogo se filtra automáticamente de modo que muestre solo los módulos que se admiten en la franja o el contenedor seleccionado. La lista de módulos viene determinada por la plantilla de la página o la definición del módulo de contenedor.

    > [!NOTE]
    > Si un contenedor o franja no admite nuevos módulos secundarios, la opción **Agregar módulo** no está disponible.

1. En el cuadro de diálogo, busque y seleccione un módulo para agregarlo a la página.

    > [!TIP]
    > **Característica** y **Elemento principal** son buenos tipos de módulos para que los principiantes trabajen con ellos.

1. Seleccione **Aceptar** para agregar el módulo seleccionado a la franja o al contenedor seleccionado de su página.

### <a name="remove-a-module"></a>Quitar un módulo

Para eliminar un módulo de una franja o un contenedor de una página, siga estos pasos.

1. En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al módulo que se va a eliminar y, a continuación, seleccione el botón de papelera.
1. Cuando se le pida confirmar que desea quitar el módulo, seleccione **Aceptar**.

## <a name="configure-modules"></a>Configurar módulos

Los siguientes procedimientos describen cómo configurar contenido y módulos de contenedor.

### <a name="configure-a-content-module"></a>Configurar un módulo de contenido

Para configurar un módulo de contenido en una página, siga estos pasos.

1. En el panel de esquema de la izquierda, seleccione un tipo de módulo de contenido (por ejemplo, **Característica**, **Elemento principal** o **Banner**).
1. En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.
1. Si el panel de propiedades tiene una sección **Configuración de datos**, selecciónela para expandirla. De lo contrario, vaya al paso 5.
1. Si hay un botón **Agregar origen de datos**, selecciónelo y seleccione los elementos de contenido que desea agregar.
1. Especificar valores para controles de módulos requeridos o deseados.
1. Seleccione **Guardar**.

### <a name="configure-a-container-module"></a>Configurar un módulo de contenedor

Para configurar un módulo de contenedor en una página, siga estos pasos.

1. Seleccione un módulo de contenedor en su página (por ejemplo, un módulo de contenido de fluido o carrusel).
1. En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.
1. En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del contenedor o de cualquier franja que se encuentre dentro del contenedor y, a continuación, seleccione **Agregar módulo**. A continuación, agregue módulos secundarios al contenedor seleccionado. Para obtener más información, consulte el procedimiento [Agregar un módulo](#add-a-module) descrito anteriormente en este tema.
1. Si existen varios módulos secundarios como elementos del mismo nivel en un contenedor principal, puede cambiar su orden de visualización en el contenedor principal. Seleccione el botón de puntos suspensivos para un módulo y utilice los botones de flecha arriba y flecha abajo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con plantillas](work-with-templates.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Agregar un módulo de contenedor a una página](add-container-module.md)

[Agregar módulos de colocación de contenido a una página](add-content-placement-modules.md)

[Trabajar con grupos de publicación](publish-groups.md)

