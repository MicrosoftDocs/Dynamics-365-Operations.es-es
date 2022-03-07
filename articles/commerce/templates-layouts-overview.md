---
title: Visión general de plantillas y diseños
description: Este tema abarca plantillas y diseños en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 39fae603a8ae34a7500ead1d2d1cecff6dc65f1e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804050"
---
# <a name="templates-and-layouts-overview"></a>Visión general de plantillas y diseños


[!include [banner](includes/banner.md)]

Las plantillas son un elemento fundamental del modelo de página de Microsoft Dynamics 365 Commerce. Si su objetivo es maximizar la eficacia y la coherencia para los flujos de trabajo de la creación de sitios, es importante que descubra cómo aprovechar las plantillas de su sitio web. Las primeras decisiones acerca de la estructura de la plantilla son importantes y pueden afectar significativamente al coste y a la agilidad para las actualizaciones de marca diarias, estaciones y en todo el sitio. Las plantillas bien estructuradas también tienen otras ventajas. Por ejemplo, ayudan a mejorar las puntuaciones de optimización de motor de búsqueda (SEO) en todos el sitio y minimizan los recuentos de errores.

Una buena forma de comenzar a trabajar con plantillas es comprender los beneficios funcionales de plantillas y diseños, las diferencias entre ellos y la jerarquía.

La ilustración siguiente muestra la jerarquía del modelo de páginas que se encuentra detrás de una página web representada.

![Diagrama del modelo de página](../commerce/media/page-model-diagram.png)

| Entidad        | Función básica |
|---------------|----------------|
| Plantilla      | Las plantillas definen las opciones de módulo y el scaffolding básico para un conjunto de diseños e instancias de páginas. |
| Diseño        | Los diseños definen la selección final y la organización de módulos para una página o un conjunto de páginas. |
| Instancia de página | Las instancias de página definen los datos y el contenido para páginas específicas. |

## <a name="templates"></a>Plantillas

Las plantillas se encuentran en la parte superior de la jerarquía del modelo de página de Dynamics 365 Commerce y representan un primer paso importante para la configuración del sitio. Conceptualmente, las plantillas ayudan a controlar la coherencia en una familia de páginas y diseños secundarios definiendo las opciones de creación y estructura base para los flujos de trabajo de creación de páginas y creación de diseños en sentido descendente. Las plantillas pueden ayudar a simplificar el proceso de creación de contenido a través de elementos predefinidos y administrados centralmente (como encabezados y pies de página) y flujos de creación guiados para ayudar a garantizar que las opciones de configuración de módulo siguen la marca.

### <a name="controlling-consistency"></a>Control de coherencia

Al diseñar una plantilla, la mayor decisión empresarial que debe tomar es cuánto control debe tener la plantilla sobre el proceso de creación de páginas. Una plantilla que deja todo abierto para un autor en sentido descendente es el tipo más sencillo de plantilla para crear, aunque puede tener graves consecuencias a largo plazo para el mantenimiento de las páginas que se crean a partir de ella. Una plantilla bien escrita ofrece orientación y una experiencia de creación agilizada, pero también ofrece a los autores la flexibilidad suficiente para poder completar su tarea. Todas estos aspectos dependen del nivel de control que se aplica por la plantilla.

Las plantillas pueden ayudar a los autores a ser más eficientes y a seguir la marcan de las siguientes maneras:

- Limite los módulos que se pueden usar en una página.
- Sugiera opciones predeterminadas de módulo y configuración.
- Tome explícitamente algunas decisiones de configuración y módulos que se controlan en el nivel de la plantilla. Este proceso también se conoce como *bloquear* un valor.

El siguiente ejemplo muestra la manera en que se puede configurar una plantilla básica (plantilla):

- Todos los diseños secundarios de la plantilla X deben tener un contenedor de encabezado, un contenedor de cuerpo y un contenedor de pie de página.
- En la plantilla X, la configuración del contenedor de encabezado se bloquea y se puede modificar únicamente en la propia plantilla X. Todas las páginas y diseños secundarios siempre tienen este encabezado.
- El contenedor de cuerpo requiere al menos un módulo y hasta un máximo de diez módulos. Esos módulos se definen por páginas y diseños en sentido descendente.
- Para el contenedor de cuerpo, hay disponibles módulos de elemento principal, características, carrusel y banner.
- Un contenedor de pie de página está configurado en la plantilla X, pero se puede sobrescribir por páginas y diseños en sentido descendente.

La plantilla de este ejemplo define una estructura sencilla y un conjunto de opciones para autores de contenido en sentido descendente. Observe que algunas partes de una página (en este caso, el encabezado) se han definido completamente y bloqueado en la plantilla, y no se pueden cambiar por los autores en sentido descendente. Se pueden definir otras piezas (en este caso, el cuerpo) por los autores en sentido descendente dentro de instrucciones específicas (en este caso, un número mínimo y un número máximo de módulos de tipos específicos). Y otras partes (en este caso, el pie de página) se definen en la plantilla, pero pueden reemplazarse por autores en sentido descendente.

Un importante paso inicial para los administradores de la marca y del sitio es determinar el equilibrio correcto entre restricción y flexibilidad para los autores de página y diseño secundarios. Cuando se usan plantillas, este equilibrio es completamente configurable. Afecta si los elementos de página están actualizados centralmente (bloqueados en la plantilla) o se dejan a niveles secundarios individuales que se encuentren más abajo en la jerarquía de la página.

Para empezar a usar plantillas, consulte [Trabajar con plantillas](work-with-templates.md).

## <a name="layouts"></a>Diseños

Los diseños se encuentran en el siguiente nivel de la jerarquía del modelo de página, debajo de las plantillas. Mientras que una plantilla define todos los módulos que se permiten para una página, un diseño es una selección y organización explícitas de módulos. Las páginas se encuentran en el siguiente nivel de la jerarquía del modelo de página, debajo de los diseños. Definen el contenido localizado para los módulos seleccionados en el diseño.

El siguiente ejemplo se basa en el ejemplo de plantilla de la sección anterior y muestra cómo puede estar configurado un diseño básico:

- La plantilla principal del diseño requiere que el contenedor de cuerpo tenga entre uno y diez módulos. Esos módulos solo se pueden módulos de elemento principal, características, carrusel y banner. Por lo tanto, el diseño puede definir la siguiente selección y organización de módulos:

    - El primer módulo del contenedor de cuerpo es un módulo de banner y va seguido de un módulo de elemento principal y dos módulos de características.
    - El primer módulo de características se alinea a la izquierda y el segundo módulo de características se alinea a la derecha.

- Aunque un pie de página predeterminado se hereda de la plantilla principal, el autor de la plantilla dejó el pie de página desbloqueado. Por lo tanto, el diseño puede reemplazarlo definiendo otro fragmento de pie de página.

El diseño de este ejemplo define la organización final de módulos para páginas secundarias. Como una plantilla, un diseño puede definir las propiedades de módulo bloqueadas o predeterminadas que se heredarán siempre por las páginas secundarias (por ejemplo, la alineación de los módulos de características). Los datos o contenido real para cada módulo del diseño se definen a continuación más abajo en la jerarquía, en cada instancia de página secundaria. Una distinción importante aquí es los diseños que no contienen directamente el contenido localizable, mientras que sí lo contienen sus páginas secundarias. La función principal del diseño es definir la organización final y la configuración predeterminada de los módulos para sus páginas secundarias.

Esta jerarquía es eficaz por dos motivos. En primer lugar, los diseños que comparten la misma plantilla primaria se tratan como compatibles para los escenarios de cambio de diseño. Por lo tanto, el diseño de cualquier página se puede cambiar por otro diseño de la misma jerarquía de plantilla sin requerir que se vuelva a crear el contenido de nivel de página. Puede aprovechar esta capacidad de realizar actualizaciones de diseño de temporada, experimentar o hacer un rediseño de sitio permanente. En segundo lugar, los diseños constituyen otro modo de modificar centralmente elementos compartidos para un grupo de páginas sin requerir actualizaciones de las páginas individuales. Por ejemplo, si una categoría de producto tiene 1000 páginas que comparten el mismo diseño, los módulos se pueden reordenar en el diseño y este cambio se reflejará inmediatamente en todas las 1000 páginas secundarias.

Al comprender esta jerarquía, puede entregar una estructura de sitio ágil y eficaz que ayude a ahorrar en coste, sea escalable y genere mejores resultados mientras que el sitio evoluciona con el tiempo.

### <a name="preset-and-custom-layouts"></a>Configurar diseños preestablecidos y personalizados

Los diseños de su sitio pueden ser *preestablecidos* o *personalizados*:

- Los **diseños preestablecidos** permiten un flujo de trabajo de creación de página donde todos los módulos están seleccionados y organizados, y solo se requiere la entrada de datos. Este método puede ayudar a ahorrar tiempo en el caso de que se deban crear varias páginas con los mismos requisitos de diseño. Los diseños preestablecidos tienen una relación de uno a varios con sus páginas secundarias. Por lo tanto, se puede usar un solo diseño preestablecido para controlar centralmente la organización del módulo para cientos o miles de páginas secundarias.
- Los **diseños personalizados** son esencialmente diseños de un solo uso que no se incrustan en una página. No se exponen como opción cuando se crean nuevas páginas o en escenarios de cambio de diseño. La ventaja de este enfoque es que un autor puede probar creando una página que utilice un diseño personalizado. A continuación, si el autor desea volver a usar el diseño para otras páginas, se puede convertir fácilmente en un diseño preestablecido. El nuevo diseño preestablecido se expone a continuación como una opción en flujos de trabajo de creación de páginas y en escenarios de cambio de diseño para páginas desde la misma jerarquía de plantillas. A la inversa, los diseños preestablecidos se pueden ramificar en diseños personalizados. De esta manera, un autor puede sacar una página del diseño preestablecido y crear un nuevo diseño personalizado de un solo uso. (Este nuevo diseño personalizado aún está enlazado por restricciones de la plantilla primaria.)

El diseño preestablecido y los diseños personalizados se editan en las diferentes partes del conjunto de herramientas de creación. Dado que los diseños personalizados no tienen dependencia de otras páginas, se editan directamente en el editor de páginas. En este caso, la existencia de un diseño es principalmente transparente para el usuario y solo se expone en propiedades de nivel de página y a través de las acciones para opciones de diseño. Sin embargo, ya que los cambios realizados a los diseños preestablecidos pueden afectar a muchas páginas secundarias, deben editarse en el editor de diseño, donde las acciones de publicación consideran el impacto completo en sentido descendente en las páginas secundarias.

En las siguientes ilustraciones se muestran escenarios para diseños preestablecidos y personalizados.

![Escenarios de diseño preestablecidos y personalizados](../commerce/media/template-figure1.png)

Para empezar a usar diseños preestablecidos, consulte [Trabajar con diseños predefinidos](work-with-layouts.md).

## <a name="additional-resources"></a>Recursos adicionales

[Trabajar con plantillas](work-with-templates.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)

[Trabajar con grupos de publicación](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]