---
title: Trabajar con módulos
description: Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eddee09fa81c18bc464b7768921981e6b5159a3e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210908"
---
# <a name="work-with-modules"></a>Trabajar con módulos

[!include [banner](includes/banner.md)]

Este tema describe cómo y cuándo usar módulos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los módulos son bloques de creación lógicos que componen su estructura de página y tienen diversos propósitos y ámbitos. Algunos módulos son contenedores de alto nivel y su único propósito es mantener y organizar otros módulos (módulos secundarios). Otros módulos, como un módulo de ubicación de imagen sencillo, tienen un propósito muy específico. Otros módulos, como un módulo de carrusel, se encuentren en algún lugar entre esas dos categorías.

De manera predeterminada, el sitio de Dynamics 365 Commerce incluye una biblioteca de módulos que le permite obtener la mayoría de los escenarios de comercio electrónico básicos. Debería poder crear un sitio de comercio electrónico integral solo con estos módulos. Sin embargo, también podría desea personalizar estos módulos o crear módulos personalizados nuevos para necesidades específicas. Si desea crear módulos personalizados, un kit de desarrollo de software (SDK) de diseño de módulo está disponible para ayudarle a crear una biblioteca de módulo personalizada.

## <a name="container-modules-and-slots"></a>Franjas y módulos de contenedor

Como se mencionó anteriormente, algunos módulos están diseñados para mantener módulos secundarios. Esos módulos se conocen como *contenedores* y permiten jerarquías de módulos anidados. Los módulos de contenedor incluyen *franjas*. Las franjas se usan para administrar el diseño y el propósito de módulos secundarios en el contenedor. Un ejemplo es un módulo de contenedor de página básica (un módulo de nivel superior para cualquier página) que define varias franjas importantes:

- Una franja de encabezado
- Una franja de subencabezado
- Una franja principal
- Una franja de pie de página
- Una franja de subpie de página

El desarrollador del módulo define estas franjas y determina los módulos secundarios y cuántos módulos secundarios se pueden colocar directamente en él. Por ejemplo, la franja de encabezado solo puede admitir un módulo del tipo **Módulo de encabezado**, mientras que la franja del cuerpo puede admitir un número ilimitado de módulos de cualquier tipo (sin incluir otros módulos de contenedor de página).

En las herramientas de creación, los autores de página no tienen que saber por adelantado qué módulos se pueden y no se pueden colocar en cada franja. Cuando los autores de la página seleccionan una franja e intentan seleccionar un módulo para agregarlo a él, ven una vista filtrada de tipos de módulo que se admiten para esa franja.

## <a name="content-modules"></a>Módulos de contenido

Los módulos de contenido contienen elementos multimedia y de contenido, como texto (por ejemplo, encabezados, párrafos y vínculos) o referencias de activos (por ejemplo, imágenes, vídeo y PDF). Los tipos de módulos de contenido típicos incluyen bloques de contenido, bloques de texto y módulos de banner promocional. Los módulos de estos tres tipos pueden contener texto o medios, y no requieren módulos secundarios para hacer que algo sea visible en una página.

La mayoría de las actividades de creación de contenido y página típicas y diaria implican módulos de contenido, principalmente porque estos módulos definen el contenido real que se representa en sus módulos de contenedor principal. Hay muchos módulos de contenido disponibles y estos módulos suelen ser las últimos piezas que agregará a la jerarquía de una página de módulos anidados.

La ilustración siguiente muestra cómo los módulos se anidan dentro de franjas de módulo de contenedor principal.

![Anidación de módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Agregar o quitar módulos

Los siguientes procedimientos describen cómo agregar y quitar módulos.

### <a name="add-a-module"></a>Agregar un módulo

Para agregar un módulo a una franja o un contenedor de una página, siga estos pasos.

1. En el panel de esquema de la izquierda o directamente en el lienzo principal, seleccione un contenedor o una franja a la que se pueda agregar un módulo secundario.

    > [!NOTE]
    > El diseñador del módulo define la lista de tipos de módulos que se pueden agregar a una franja específica del módulo. A continuación, los autores de plantilla pueden limitar las opciones de módulo permitidas para ayudar a garantizar la optimización de motor de búsqueda (SEO) coherente y la eficiencia de creación para todas las páginas que se crean a partir de una plantilla específica. Cuando agregue un módulo a una franja, el cuadro de diálogo **Agregar módulo** se filtra automáticamente de modo que muestre solo los módulos que se admiten en la franja o el contenedor seleccionado. Esta lista de módulos permitidos viene determinada por la plantilla de la página o la definición del módulo de contenedor.

1. Si usa el panel de contorno, seleccione los puntos suspensivos (**...**) junto al nombre del módulo y luego seleccione **Agregar módulo**. Si usa los controles directamente dentro del lienzo, seleccione el símbolo más (**+**) en una franja vacía o adyacente al módulo seleccionado actualmente, y luego seleccione **Agregar módulo**.

    > [!NOTE]
    > Si un contenedor o franja no admite nuevos módulos secundarios, la opción **Agregar módulo** no está disponible.

1. En el cuadro de diálogo **Agregar módulo**, seleccione un módulo para agregarlo a la página.

    > [!TIP]
    > **Bloque de contenido** es un buen tipo de módulo para que trabajen con él los principiantes.

1. Seleccione **Aceptar** para agregar el módulo seleccionado a la franja o al contenedor seleccionado de su página.

### <a name="remove-a-module"></a>Quitar un módulo

Para eliminar un módulo de una franja o un contenedor de una página, siga estos pasos.

1. En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) que se encuentra junto al módulo que se va a eliminar y, a continuación, seleccione el símbolo de papelera. Alternativamente, en el lienzo principal puede seleccionar el símbolo de la papelera en la barra de herramientas de un módulo seleccionado.
1. Cuando se le pida confirmar que desea quitar el módulo, seleccione **Aceptar**.

## <a name="move-a-module-to-a-new-position"></a>Mover un módulo a una nueva posición

Para mover un módulo a una nueva posición dentro de su página, use cualquiera de los siguientes métodos.

### <a name="move-a-module-using-the-outline-pane"></a>Mover un módulo usando el panel de esquema

Para mover un módulo usando el panel de contorno, siga estos pasos.

1. Seleccione y mantenga presionado el módulo que desea mover en el panel de contorno, luego arrastre el módulo a una nueva posición en el esquema. La línea azul en el contorno y en el lienzo indica dónde se puede colocar el módulo.
1. Suelte el módulo para colocarlo en la nueva posición.

### <a name="move-a-module-directly-within-the-canvas"></a>Mover un módulo directamente dentro del lienzo

Para mover un módulo directamente dentro del lienzo, siga estos pasos.

1. Seleccione el módulo que desea mover en el lienzo. 
1. Seleccione un símbolo de flecha hacia arriba o hacia abajo en la barra de herramientas del módulo y luego arrastre la flecha a una nueva posición en la página. La línea azul en el contorno y en el lienzo indica dónde se puede colocar el módulo. Si un módulo no se puede mover hacia arriba o hacia abajo, ese símbolo de flecha aparecerá atenuado. 
1. Suelte el módulo para colocarlo en la nueva posición.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Mover un módulo usando el menú de los puntos suspensivos

Para mover un módulo usando el menú de los puntos suspensivos, siga estos pasos.

1. Seleccione un módulo en el esquema o el lienzo.
1. Seleccione los puntos suspensivos (**...**) junto al nombre del módulo en el panel de contorno o en la barra de herramientas del módulo en el lienzo.
1. Si el módulo se puede mover hacia arriba o hacia abajo dentro del contenedor o la ranura, verá opciones para **Ascender** o **Descender**. Seleccione la opción de movimiento deseada para mover el módulo hacia arriba o hacia abajo en relación con los elementos del mismo nivel.

## <a name="configure-modules"></a>Configurar módulos

Los siguientes procedimientos describen cómo configurar contenido y módulos de contenedor.

### <a name="configure-a-content-module"></a>Configurar un módulo de contenido

Para configurar un módulo de contenido en una página, siga estos pasos.

1. En el panel de esquema de la izquierda, expanda el árbol y seleccione cualquier módulo de contenido (por ejemplo,**Bloque de contenido**). De forma alternativa, puede seleccionar el módulo en el lienzo principal.
1. En el panel de propiedades del módulo a la derecha, indique las propiedades de los controles de módulo deseados.
1. En la barra de comandos, seleccione **Guardar**. Esto también actualizará el lienzo de vista previa.

### <a name="edit-module-text-properties"></a>Editar las propiedades del texto del módulo

Las propiedades de texto del módulo que no son de solo lectura se pueden editar directamente en el lienzo.

Para editar las propiedades del texto del módulo, siga estos pasos.

1. Seleccione el control de texto en el lienzo, luego coloque el cursor donde desee editar el texto.
1. Especifique el contenido de texto.
1. Seleccione cualquier lugar fuera del contenido de texto para continuar editando otro contenido.

### <a name="inline-image-selection"></a>Selección de una imagen en línea

Las imágenes del módulo que no son de solo lectura se pueden cambiar directamente en el lienzo.

Para elegir una nueva imagen para un módulo de contenido, siga estos pasos.

1. En el lienzo, haga doble clic en la imagen. Esto abrirá la ventana del selector multimedia.
1. Busque y seleccione una nueva imagen que desee usar, y luego seleccione **Aceptar**. La nueva imagen ahora se representa en el lienzo.

### <a name="configure-a-container-module"></a>Configurar un módulo de contenedor

Para configurar un módulo de contenedor en una página, siga estos pasos.

1. Seleccione un módulo de contenedor en su página (por ejemplo, un módulo de contenido de fluido o carrusel).
1. En el panel de propiedades de la derecha, expanda los controles anidados seleccionando los encabezados y establezca los valores de control necesarios.
1. En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos que se encuentra junto al nombre del contenedor o de cualquier franja que se encuentre dentro del contenedor y, a continuación, seleccione **Agregar módulo**. A continuación, agregue módulos secundarios al contenedor seleccionado. Para obtener más información, consulte la sección [Trabajar con módulos](#add-a-module) descrita anteriormente en este tema.
1. Si existen varios módulos secundarios como elementos del mismo nivel en un contenedor principal, puede cambiar su orden de visualización en el contenedor principal. Seleccione el botón de puntos suspensivos para un módulo y utilice los botones de flecha arriba y flecha abajo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con plantillas](work-with-templates.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)

[Trabajar con fragmentos](work-with-fragments.md)

[Agregar un módulo de contenedor a una página](add-container-module.md)

[Trabajar con grupos de publicación](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]