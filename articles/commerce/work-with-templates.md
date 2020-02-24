---
title: Trabajar con plantillas
description: En este tema se describe cómo trabajar con plantillas en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/01/2019
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
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 815565dd203925fa0acca9336c4ddc56db8c4058
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002576"
---
# <a name="work-with-templates"></a>Trabajar con plantillas


[!include [banner](includes/banner.md)]

En este tema se describe cómo trabajar con plantillas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Como se trató en [Visión general de plantillas y diseños](templates-layouts-overview.md), las plantillas definen el conjunto de opciones que está disponible para los autores en sentido descendente. Las plantillas son útiles para el equipo de creación web de una empresa por varios motivos, y las plantillas bien estructuradas pueden ayudar con todos los objetivos siguientes:

- Simplificar la experiencia de creación para roles de editor de contenido diario.

    - Filtrar opciones de módulos de modo que solo se muestren los módulos relevantes para una sección de página específica. (Por ejemplo, una sección de marketing de una plantilla se puede configurar para filtrar módulos irrelevantes que nunca se deben usar en ese contexto, y que solo complicarán las tareas de creación de contenido si se muestran.)
    - Establecer la configuración del módulo predeterminado para ayudar a mejorar la eficacia de la creación.
    - Definir los fragmentos de página predeterminados para ayudar a mejorar la eficacia de la creación. (Por ejemplo, los fragmentos de encabezado y pie de página de una plantilla aparecerán automáticamente en cada página en sentido descendente).

- Mantener los sitios empresariales en marca definiendo un conjunto aprobado de opciones de configuración y organización del módulo.

    > [!TIP] 
    > Los sitios de comercio electrónico correctos proporcionan a los clientes patrones de diseño de experiencia de usuario familiares, repetibles y en marca. Mediante plantillas, ayuda a controlar la coherencia en todo el sitio.

- Mejore las puntuaciones de optimización de motor de búsqueda (SEO) garantizando metadatos y definiciones de página definidas mediante programación y repetibles.

> [!NOTE]
> Aunque las plantillas están diseñadas para controlar la coherencia en un sitio, se pueden configurar teóricamente de modo que no apliquen ninguna coherencia. Los administradores de sitio y marca pueden definir cualquier nivel de variabilidad para las páginas de su sitio. Por ejemplo, una plantilla se puede dejar completamente abierta, de modo que los autores de contenido puedan crear cualquier diseño de página que seleccionen. En este caso, no son aplicables ninguno de los beneficios de la lista precedente.

## <a name="modify-a-template"></a>Modificar una plantilla

Las plantillas se modifican mediante el editor de plantillas.

Para abrir el editor de plantillas, siga uno de estos pasos:

- En el panel de navegación del sitio, seleccione **Plantillas** y, a continuación, seleccione la plantilla que desea modificar.
- En el editor de páginas para una página existente, seleccione el nodo superior en el árbol de esquema de la izquierda. A continuación, en el panel de propiedades de la derecha, seleccione **Editar plantilla**.

La vista del árbol de esquema de la izquierda muestra las opciones de módulo y las estructuras disponibles para páginas y diseños secundarios. Al seleccionar un módulo en el árbol de esquema, puede ver las propiedades de plantilla para el módulo seleccionado en el panel de propiedades de la derecha. Algunas de estas propiedades son exclusivas de la edición de plantillas. La siguiente tabla describe estas propiedades.

| Nombre de la propiedad | Descripción |
|---|---|
| Ocurre lo mín. | Esta propiedad define el número mínimo de apariciones para el módulo seleccionado. Por ejemplo, si el valor se establece en **1**, el módulo se requiere para autores en sentido descendente, mientras que si el valor se establece en **0** (cero), el módulo es opcional. |
| Ocurre lo máx. | Esta propiedad define el número máximo de apariciones para el módulo seleccionado. Por ejemplo, si el valor se establece en **1**, el módulo se puede agregar solo una vez. |
| Módulos mínimos (contenedores) | Para los módulos que contienen otros módulos (es decir, para *módulos de contenedores*), esta propiedad define el número mínimo de módulos totales que se deben agregar como secundarios. Por ejemplo, para un módulo de carrusel, el valor se puede establecer en un número mayor que 1. |
| Módulos máximos (contenedores) | Para los módulos de contenedor, esta propiedad define el número máximo de módulos totales que se debe agregar como secundarios. Por ejemplo, para un módulo de carrusel, el valor se puede establecer en un número menor que 10. |
| Bloqueado | Un control booleano **Bloqueado** aparece junto a todas las propiedades básicas de módulo. Permite al autor de la plantilla bloquear una configuración de módulo en la plantilla. No se puede reemplazar una configuración de módulo que esté bloqueada por ninguna página o diseño secundarios. Se convierte en un valor de propiedad editable centralmente para todos los diseños y páginas que usan la plantilla. |

## <a name="create-a-new-template"></a>Crear una nueva plantilla

Para crear una nueva plantilla, siga estos pasos.

1. En el panel de navegación del sitio, seleccione **Plantillas** para abrir la vista del inspector de plantillas.
1. Seleccione **Nueva plantilla**.
1. En el cuadro de diálogo de creación de plantilla, especifique un nombre y una descripción para la plantilla. Los valores que escriba se mostrarán a los autores cuando creen páginas nuevas. Por lo tanto, especifique metadatos que serán útiles para autores de página. Por ejemplo, escriba **Usar esta plantilla para crear páginas de marketing generales** como la descripción. Estos metadatos se pueden editar posteriormente.
1. Seleccione **Aceptar** para crear la nueva plantilla y abrir el editor de plantillas. El editor de plantillas muestra un árbol de esquema a la izquierda y un panel de propiedades a la derecha.
1. En el árbol de esquema, expanda los nodos y seleccione la franja **Encabezado HTML**.
1. Si aún no hay módulos en esta franja, seleccione los puntos suspensivos (**...**) y **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Resumen de página determinada** y **Aceptar**.
1. En el árbol de esquema, seleccione el nuevo módulo y, a continuación, en el panel de propiedades, especifique la configuración predeterminada que se debe configurar automáticamente para todas las páginas secundarias de la plantilla. Si no desea ninguna configuración predeterminada, deje los valores en blanco.
1. En el árbol de esquema, seleccione el espacio **Cuerpo**, los puntos suspensivos y, a continuación, **Agregar módulo**.
1. Seleccione un módulo de contenedor de página (es posible que haya una opción) y, a continuación, seleccione **Aceptar**.

En el nuevo módulo de contenedor de página, verá un nuevo conjunto de franjas (**Encabezado**, **Principal**, etc.). Aquí, puede agregar y configurar las opciones de módulo que estarán disponibles para los autores cuando crean páginas de esta plantilla. De forma predeterminada, si no agrega módulos a una franja, todos los tipos de módulos disponibles se admiten para dicha franja.

La plantilla es válida ahora técnicamente, y se puede guardar, proteger y usar para crear nuevas páginas. Sin embargo, las tres secciones siguientes describen otras configuraciones predeterminadas que es posible que desee configurar primero.

## <a name="add-a-header-and-a-footer"></a>Agregar un encabezado o un pie de página

Si su sitio ya tiene un fragmento de encabezado, siga estos pasos para agregar un encabezado y un pie de página a una plantilla.

1. En el árbol de esquema, expanda la franja **Cuerpo** y su módulo de página secundaria.
1. Seleccione la franja **Encabezado**.
1. Seleccione el botón de puntos suspensivos para la franja **Encabezado** y, a continuación, seleccione **Agregar fragmento**.
1. Busque y seleccione el fragmento del encabezado del sitio y, a continuación, seleccione **Aceptar**.

Todas las páginas que usan la plantilla heredarán ahora automáticamente este fragmento de encabezado.

Si su sitio no tiene aún un fragmento de encabezado, consulte [Crear un fragmento](work-with-fragments.md#create-a-fragment) para obtener información acerca de cómo crearlo y, a continuación, completar el procedimiento anterior.

## <a name="change-the-template-theme"></a>Cambiar el tema de la plantilla

Para establecer el tema predeterminado para todas las páginas que usan una plantilla, siga estos pasos.

1. En el árbol de esquema de la izquierda, expanda la franja **Cuerpo**.
1. En la franja **Cuerpo**, seleccione el módulo de contenedor de página (por ejemplo, **Página predeterminada**).
1. En el panel de propiedades de la derecha, en el campo **Tema**, seleccione un tema.

De forma predeterminada, todas las páginas nuevas usarán ahora el tema seleccionado. Para evitar que las páginas reemplacen esta configuración en el nivel de página o diseño, establezca el control booleano **Bloqueado** en **Verdadero**.

## <a name="add-a-script-to-a-template"></a>Agregar un script a una plantilla

Puede agregar elementos de **&lt;script&gt;** HTML que contengan JavaScript a su plantilla. De esta manera, puede proporcionar comportamientos de script predeterminados al encabezado HTML, inicio del cuerpo y secciones finales del cuerpo de sus páginas.

Para agregar un script a una plantilla, siga estos pasos.

1. En el árbol de esquema de la izquierda, seleccione la franja donde desee agregar el elemento **&lt;script&gt;** (por ejemplo, el encabezado HTML, el inicio del cuerpo o el final del cuerpo).
1. Seleccione el botón de puntos suspensivos para la franja y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione un módulo de script (por ejemplo, **Script externo** o **Script en línea**).
1. En el panel de propiedades de la derecha, en el control de propiedad de script adecuado (por ejemplo, **Script en línea** o **Etiquetas de script**), especifique el script.
1. En el panel de propiedades, especifique cualquier otra configuración opcional que desee configurar.

> [!TIP]
> Si desea volver a usar cualquiera de sus módulos de script para otras plantillas, puede convertirlas en fragmentos. De esta manera, ayuda a hacer el proceso de creación más eficaz, y centralizada el proceso de actualización. Para obtener información acerca de cómo convertir un módulo de script en un fragmento, consulte [Guardar una configuración de módulo existente como fragmento](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Guardar, proteger, obtener una vista previa y publicar una plantilla

Para guardar y proteger una plantilla, siga estos pasos.

1. Seleccione **Guardar** en la parte superior del editor de plantillas. Los cambios guardados no afectan a las páginas en sentido descendente hasta que se protegen.
1. Seleccione **Proteger**. Sus cambios son ahora detectables para flujos de trabajo en sentido descendente.

Para obtener una vista previa de los cambios, abra una página existente que utilice la plantilla o cree una nueva página a partir de la plantilla.

Cuando haya obtenido una vista previa de los cambios para su plantilla, siga uno de estos pasos para publicar la plantilla en el sitio activo:

* Vaya a **Plantillas**, seleccione la plantilla y, a continuación, seleccione **Publicar**.
* En el editor de plantillas, seleccione **Publicar**.
* Publique una página que haga referencia a la plantilla sin publicar. La plantilla se publica automáticamente.

> [!WARNING]
> Cuando se publica una plantilla, o cualquier otro artículo del sistema de gestión de contenidos (CMS), es detectable en Internet. No publique documentos o activos hasta que esté listo para hacerlos público. Las versiones de documentos que se han guardado y protegido, pero que no se han publicado, solo son detectables para usuarios autenticados del sistema.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)
