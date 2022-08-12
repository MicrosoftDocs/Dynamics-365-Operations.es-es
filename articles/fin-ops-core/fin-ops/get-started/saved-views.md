---
title: Vistas guardadas
description: Este artículo describe cómo usar las características guardadas de las vistas.
author: jasongre
ms.date: 04/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 14369b02f1d7553be5c732f3bdf768825267998b
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9125162"
---
# <a name="saved-views"></a>Vistas guardadas

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>Introducción

La personalización desempeña una característica importante al permitir que los usuarios y las organizaciones optimicen la experiencia del usuario para satisfacer sus necesidades. Para obtener más detalles acerca de la personalización, consulte [Personalizar la experiencia del usuario](personalize-user-experience.md).

La personalización tradicional permite a los usuarios tener solo un único conjunto de personalizaciones por página. La característica **Vistas guardadas** expande la personalización de varias maneras importantes:

- Las vistas permien a los usuarios tener varios conjuntos de personalización con nombre por formulario, que pueden intercambiar rápidamente según sea necesario. Esto permite que un usuario cree varias vistas optimizadas de una página, donde cada vista ha estado diseñada para que se adapte a las necesidades de realizar una tarea determinada empresarial. 
- Las vistas creadas para tipos de determinados de página también pueden incluir los filtros u ordenaciones añadidas por el usuario, que permite a los usuarios volver rápidamente a conjuntos de datos comunes filtrados. Consulte la sección [Qué páginas son compatibles con vistas](saved-views.md#what-pages-support-views) para obtener más detalles. 
- Las vistas se pueden publicar en los usuarios con roles específicos de seguridad y entidades jurídicas específicas. Por lo tanto, cualquier usuario que tenga un rol especificado y acceda a una entidad jurídica especificada puede acceder y usar esa vista, aunque dicho usuario no tenga permiso para personalizar. Esta capacidad de publicación permite a las organizaciones definir vistas corporativas estándar optimizadas para el negocio. Para obtener más información, consulte [Administrar personalizaciones en el nivel de organización con vistas](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- A diferencia de la personalización tradicional, las vistas no se guardan automáticamente cuando un usuario realiza personalizaciones o filtra una lista. Se requiere guardar de forma explícita para dar a los usuarios la flexibilidad de crear una vista antes o después de que se hayan realizado los cambios asociados con esa vista. Este requisito también garantiza que las definiciones de vista no se cambien involuntariamente por filtros o personalizaciones que no estén destinadas a un uso a largo plazo. Los elementos que el sistema almacena automáticamente como parte del uso típico de la página (por ejemplo, anchos de columna o el estado expandido o contraído de las secciones) se guardarán por vista.
- Las vistas se pueden agregar a espacios de trabajo como mosaicos, listas, o vínculos. Por lo tanto, un conjunto de datos filtrado puede emergerse en un área de trabajo, y los usuarios pueden asociar un conjunto de personalizaciones relevantes para dicho conjunto de datos con el icono o el vínculo.

## <a name="switching-between-views"></a>Cambiando entre vistas

Una vez que las vistas se hayan puesto a disposición para un entorno, en la parte superior de cualquier página que admita las vistas incluirá un control incurrido de selector de la parte superior del formulario que muestra el nombre de la vista actual.

Existen dos variantes de tamaño en selector de la vista: 

- **Selectores grandes de vista**: las páginas que cuentan con una lista prominente tendrán un selector de imagen mayor por varios motivos. Lo que es más importante, el selector de imagen mayor indica las páginas en la vista que pueden incluir los filtros y ordenaciones definidos por el usuario. Dado que los filtros y ordenaciones se incluyen en las vistas, el tamaño mayor de selector también se garantiza ya que los nombres de vista son normalmente la mejor descripción de los datos que se muestran en la pantalla y la expectativa es que los usuarios cambiarán entre las vistas más a menudo en estos tipos de la página. La agrupación en una cuadrícula también se puede guardar en vistas en una página con selectores de vistas grandes. 
- **Selectores de vista pequeños**: el resto de las páginas a pantalla completa (con excepción de los espacios de trabajo y el panel) tienen un selector de vista más pequeño que aparece junto a la leyenda de la página. Las vistas en estas páginas incluyen solo personalizaciones y los filtros no definido por el usuario.. En estas páginas, la leyenda de la página o título de registro es normalmente la información más importante en la parte superior de la página. El tamaño más pequeño del selector de vistas también refleja una frecuencia esperada inferior de conmutación de estas páginas. 
 
Si selecciona el nombre de vista, el selector de la vista se abre y muestra la lista de vistas disponibles para esta página

**Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, el selector de vistas muestra las vistas disponibles en dos secciones. La primera sección muestra las vistas que son específicas de la entidad jurídica actual y la segunda muestra las vistas que están disponibles para todas las entidades jurídicas. La primera sección es visible solo si hay vistas específicas de la entidad jurídica para la página.

- **Vista estándar**: la vista **estándar** es la vista de lista para usar la página sin personalizaciones aplicadas.
- **Vistas personales**: las vistas sin los candados representan las vistas personales. Éstas son las vistas que ha creado o que le ha asignado un administrador.
- **Vistas bloqueadas**: algunas vistas (por ejemplo la vista **Estándar** y las opiniones que se publiquen en su rol) tienen un símbolo de candado junto a ellas en el selector de la vista. Este símbolo indica que no se pueden editar las vistas. Sin embargo, los cambios que reflejan el uso de las páginas se guardan automáticamente. Estos cambios incluyen cambios en el ancho de una columna de cuadrícula y cambios en el estado expandido o contraído de una ficha desplegable. Sin embargo, si tiene privilegios de personalización, puede usar la acción **Guardar como** para crear una vista personal basada en una vista bloqueada.
- **Nuevas vistas**: las vistas publicadas que aún no se han abierto tienen un símbolo de chispa a la izquierda del nombre de vista.

Para cambiar a otra vista, abra el selector de la vista y seleccione la vista que desee cargar. 

## <a name="creating-and-modifying-views"></a>Crear y modificar vistas

A diferencia de la personalización tradicional, las vistas no se guardan automáticamente cuando un usuario personaliza la página o cuando un usuario aplica un filtro a una lista o la ordena. Se requiere una acción explícita para guardar estos cambios en una vista. Este requisito ofrece a los usuarios la flexibilidad de crear una vista antes o después de que se hayan realizado los cambios asociados con esa vista. También garantiza que las definiciones de vista no se cambien involuntariamente mediante filtros o personalizaciones únicos. Tenga en cuenta que los elementos de uso de página típicos (por ejemplo, anchos de columna o el estado expandido o contraído de las secciones) se guardan automáticamente en la vista actual, incluso para vistas bloqueadas.

Para garantizar que se conozca el estado actual de la vista, cuando comience a cambiar una vista personalizándola o filtrándola, un asterisco (\*) aparece junto al nombre de la vista actual. Este símbolo indica que está viendo una versión modificada y no guardada de esa vista.

Si desea guardar los cambios, siga estos pasos.

1. Seleccione el nombre de vista para abrir el selector de la vista.
2. Para modificar la vista existente, seleccione **Guardar**. Tenga en cuenta que esta acción no está disponible para vistas bloqueadas. 
3. Para crear una vista nueva:

    1. Seleccione **Guardar como**. 
    2. En el panel **Guardar vista como**, introduzca un nombre y, opcionalmente, una descripción para la vista.
    3. Si desea que esta vista sea su vista predeterminada, seleccione **Anclar como predeterminada**. Para obtener más información sobre las vistas predeterminadas, consulte la sección [Cambiar la vista predeterminada](#changing-the-default-view) que sigue. 
    4. **Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, puede seleccionar si desea que esta vista esté disponible para todas las entidades jurídicas o solo para un subconjunto de ellas.
    5. Seleccione **Guardar**.

## <a name="changing-the-default-view"></a>Cambiar la vista predeterminada

La vista predeterminada es la vista que el sistema intenta abrir cuando abra la página por primera vez. Debe establecer la vista predeterminada que espera usar más a menudo. 

> [!NOTE]
> - En la función **Vistas guardadas**, hay una vista predeterminada global única para todas las entidades jurídicas. Si cambia la vista predeterminada, esa vista se abrirá de manera predeterminada, independientemente de la entidad jurídica en la que se encuentre actualmente.
> - **Versión 10.0.21 o posterior:** Cuando la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, cada entidad jurídica puede tener su propia vista predeterminada por página.

Para cambiar la vista predeterminada de una página, siga estos pasos:

1. Cambie a la vista que usa como predeterminada. 
2. Seleccione el nombre de vista para abrir el selector de la vista. 
3. Seleccione **Más** y luego en **Anclar como predeterminada**.

Como alternativa, al crear una nueva vista (mediante la acción **Guardar como**), puede hacer que esa nueva vista sea la vista predeterminada mediante la opción **Anclar como predeterminada** antes de guardar la vista.

> [!WARNING]
> En algunos casos, la consulta asociada a la vista predeterminada no se ejecuta cuando abre por primera vez una página. Por ejemplo, si abre la página a través de un icono, la consulta del icono se ejecutará independientemente de que la consulta esté asociada a la vista predeterminada. Además, si abre una página cuya vista **Estándar** ya tiene una consulta definida, la consulta original se ejecutará en lugar de la consulta predeterminada de la vista. En este caso, recibirá un mensaje informativo cuando se cargue la vista. Si cambia de vista después de que se haya cargado la página, la consulta de vista debería poder ejecutarse como se esperaba. En la versión 10.0.10 y versiones posteriores, el mensaje informativo que recibe tendrá una acción incrustada que le permitirá cargar directamente la consulta de la vista predeterminada.

## <a name="managing-personal-views"></a>Gestión de vistas personales

El cuadro **Gestionar mis vistas** le da capacidades de mantenimiento básicas sobre sus vistas personales y el orden de vistas en el selector de la vista. Para abrir esta página, seleccione el nombre de vista para abrir el menú desplegable del selector de la vista, seleccione **Más** y, a continuación **Administrar mis vistas**.

**Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, la sección **Mis vistas** del cuadro de diálogo **Gestionar mis vistas** muestra las vistas disponibles para la página en secciones. Cualquier vista que sea específica de la entidad jurídica actual se muestra en su propia sección. La sección **Vistas globales** siempre se muestra, para que pueda administrar las vistas que están disponibles para la página en todas las entidades jurídicas. 

Para una lista de vistas disponibles para dicha página, el conjunto de acciones siguiente está disponible.

- **Cambiar la vista predeterminada**: use la acción **Anclar como predeterminada** para hacer que la vista actualmente seleccionada sea la vista predeterminada para esta página. Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, la sección **Vistas globales** le permite hacer que una vista sea la vista predeterminada para la entidad jurídica actual o para todas las entidades jurídicas.
- **Reordenar de sus vistas**: use las acciones **Trasladar hacia arriba** y **Trasladar hacia abajo** para reorganizar sus vistas en un orden determinado.
- **Renombrar una vista**: use la acción **Renombrar** para cambiar el nombre de la vista personal seleccionada actualmente. Esta acción se desactiva para las vistas bloqueadas. 
- **Eliminar una vista**: Use la acción **Eliminar** para eliminar de forma permanente la vista actualmente seleccionada desde la página. No es posible de recuperar una vista tras eliminarla.

Cualquier cambio realizado en este cuadro de diálogo tomará efecto después de activar el botón **Actualizar**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Administrar personalizaciones a nivel de organización con vistas

Para ayudar a comprender cómo las vistas guardadas ayudan a mejorar la gestión de personalizaciones en el nivel de organización, en esta sección se describen algunas diferencias en la administración de la personalización con y sin la característica de **Vistas guardadas**.

Sin vistas, los administradores aplicarían un conjunto de personalizaciones para una página a un usuario o a un grupo de usuarios usando la página de personalización. Si estos usuarios tuvieran derechos de personalización, las personalizaciones serían aplicadas a esa página. Sin embargo, no había capacidad para evitar que los usuarios personalizasen más la página, lo que significaba que la organización no podía garantizar que los usuarios tuvieran una interfaz de usuario coherente. Si ninguno de estos usuarios tenían derechos de personalización, las personalizaciones que les concedía un administrador no se cargaban. Además, si se contrataba a nuevos usuarios en una organización, los administradores debían cargar manualmente un conjunto de personalizaciones para el usuario. No había un mecanismo automático para especificar que un determinado conjunto de personalizaciones debían estar disponibles para los usuarios de ese rol.

La característica de **Vistas guardadas**, facilita mucho la gestión de organización de personalizaciones, principalmente debido a que las vistas se pueden publicar en grupos de usuarios. Una vez que se ha publicado una vista, cualquier usuario que tenga uno de los roles de seguridad definidos y tenga acceso a las entidades jurídicas especificadas podrá ver y usar la vista, aunque dicho usuario no tenga acceso a la personalización. Aunque cada usuario tenga una copia de la vista publicada en la que los artículos de uso de la página se apliquen automáticamente, ningún usuario puede guardar personalizaciones o actualizaciones de consulta en una la vista publicada. Es decir, las vistas publicadas están bloqueadas. Además, si a los usuarios nuevos se les asignan roles en entidades jurídicas donde se publican las vistas, verán automáticamente las vistas que están asociados a sus roles y entidades jurídicas. No se requiere ninguna acción adicional por la administración. Del mismo modo, si los usuarios cambian de roles en una organización o se les da acceso a otras entidades jurídicas, es posible que ya no puedan tener acceso a las vistas que se publicaron anteriormente a ellas. Una vez más no se requiere ninguna acción adicional por la administración.

Las actualizaciones de una vista publicada se pueden distribuir fácilmente a los usuarios republicando la vista a los roles de seguridad y las entidades jurídicas correspondientes.

Esta capacidad permite a las organizaciones definir las vistas corporativas estándar que se optimizan para su negocio, dirigidas a usuarios en roles de seguridad específicos.

## <a name="publishing-views"></a>Publicar vistas

Durante el proceso de publicación, las vistas se pueden asignar a uno o más roles de seguridad para una o más entidades jurídicas. Por lo tanto, cualquier usuario que tenga acceso a una entidad jurídica y al que se le asigne uno de estos roles puede acceder y usar las vistas. Sin embargo, el usuario no puede editar las vistas. De forma predeterminada, los administradores del sistema tienen acceso a la acción **Publicar** en el menú desplegable del selector de la vista. Sin embargo, otros usuarios de confianza en su organización también pueden obtener acceso para ver la publicación mediante el nuevo rol **Administrador de vistas guardadas**.

Para publicar una vista, siga estos pasos:

1. Cree y guarde una copia personal de la vista que desea publicar. 
2. Con esa vista cargada actualmente, seleccione el nombre de vista para abrir el menú desplegable del selector de la vista. 
3. Seleccione el botón **Más** y a continuación seleccione **Publicar**. El cuadro de diálogo de la publicación se abrirá.
4. Introduzca un nombre para la vista. El nombre que especifique es el nombre que los usuarios que reciben esta vista verán en los selectores de la vista. Los nombres de las vistas publicadas para una página deben ser únicos. No se permiten nombres duplicados, incluso si la lista de roles o entidades jurídicas a las que se aplican difieren.
5. **Actualización 10.0.17 o posterior:** Si la función de **(vista previa) Soporte de traducción para vistas de organización** está activada, puede agregar traducciones para el nombre de su vista en tantos idiomas como su organización lo requiera seleccionando el botón **Traducciones** junto al campo **Nombre**. El nombre de la vista se mostrará a los usuarios en su idioma actual. También puede establecer el idioma predeterminado para especificar la traducción que se mostrará a los usuarios que ejecutan idiomas para los que no se ha definido ninguna traducción.
5. Opcional: ingrese una descripción para la vista, de modo que los usuarios que reciben esta vista puedan comprender mejor su propósito. 
6. Determine si la vista debe publicarse como la vista predeterminada para los usuarios seleccionados. Cuando una vista se establece como vista predeterminada, los usuarios la verán la próxima vez que abran la página de destino. Se modificará la vista predeterminada global única de cada usuario objetivo. Sin embargo, los usuarios aún pueden cambiar su vista predeterminada después de que se haya publicado.

    > [!NOTE]
    > Tenga en cuenta el siguiente comportamiento al publicar una vista como vista predeterminada:
    >
    > - Si publica una vista como vista predeterminada para algunas o todas las entidades jurídicas, se produce el siguiente comportamiento:
    >
    >    - Si solo se ha activado la función base **Vistas guardadas**, la vista predeterminada global única se cambiará para cada usuario objetivo. 
    >    - **Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada y publica la vista en un subconjunto de entidades jurídicas, la vista predeterminada para esas entidades jurídicas se cambiará para cada usuario objetivo.
    >
    > - Si un usuario tiene roles donde se publican varias vistas como la vista predeterminada, la última vista que se publicó se usará como la vista predeterminada del usuario. 

8. Agregue los roles de seguridad que corresponden a los usuarios que son el objetivo de esta vista. 
9. Determine si desea publicar la vista en los roles secundarios de cada rol de seguridad seleccionado. Si lo hace, seleccione la casilla **Incluir roles secundarios** en la fila para los roles de seguridad apropiados. Tenga en cuenta que esta casilla de verificación no está disponible para roles que no tienen roles secundarios.
10. Agregue las entidades jurídicas para las que esta vista debe estar disponible. 

    > [!NOTE]
    > Tenga en cuenta el siguiente comportamiento si publica una vista en una entidad jurídica específica pero no la publica como vista predeterminada:
    >
    > - Si solo la función base **Vistas guardadas** está activada, el selector de vistas del usuario para la página muestra inicialmente la vista solo para las entidades jurídicas especificadas. Sin embargo, después de cargar la vista por primera vez, el selector de vistas de la página siempre la mostrará, independientemente de la entidad jurídica.
    > - **Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, el selector de vistas solo mostrará la vista para las entidades jurídicas especificadas.

11. Seleccione **Publicar**.

Tenga en cuenta que en algunos entornos esto podrá llevar tiempo (hasta una hora) antes de que los usuarios vean la vista publicada.

## <a name="modifying-a-published-view"></a>Modificar una vista publicada

Después de publicar una vista, es posible que desee cambiarla. Pese a que no puede realizar cambios en directo a una vista publicada, ya que estas vistas estarán bloqueadas para su edición para todos los usuarios (incluidos editores), puede volver a publicar una vista para actualizarla.

Si los cambios que desea realizar en una vista publicada afectan sólo a los parámetros de la publicación (el nombre y la descripción de la vista, o se publican los roles de seguridad la vista), haga lo siguiente:

1. Cambie a la vista publicada para los parámetros que desea actualizar. 
2. Seleccione **Volver a publicar** en el menú desplegable del selector de vista. Si está utilizando la versión 10.0.12 o versiones anteriores, debe seleccionar **Publicar** y después **Sí** para actualizar la vista existente.
3. Actualice el nombre, la descripción, y/o los roles de seguridad y entidades jurídicas para la vista. 
4. Seleccione **Publicar**. Si originalmente seleccionó esta vista publicada como la vista predeterminada, será la vista predeterminada para los usuarios nuevamente después de volver a publicarla. 

Si los cambios a la vista publicada implican modificar las personalizaciones o los filtros asociados a la vista, siga estos pasos.

1. Cargue la vista publicada que desea modificar. 
2. Realice los cambios necesarios en el borrador local.
3. Seleccione **Volver a publicar** en el menú desplegable del selector de vista.
4. Seleccione **Sí** para indicar que desea publicar la vista junto con sus cambios no guardados. 
5. Ajuste los parámetros de publicación que requieran ajustes y luego seleccione **Publicar**. 

## <a name="managing-published-views"></a>Administrar las vistas publicadas

Al igual que administrar las vistas personales, el cuadro **Administrar mis vistas** da a los usuarios con privilegios básicos de publicación la capacidad de mantener las vistas publicadas de esa página (además de sus propias vistas personales). Para abrir esta página, seleccione el nombre de vista para abrir el menú desplegable del selector de la vista, seleccione **Más** y, a continuación **Administrar mis vistas**.

Aunque todos los usuarios tengan una pestaña **Mis vistas** que muestra sus vistas personales, los usuarios con privilegios de publicación también tienen una pestaña **Vistas de la organización** que muestra todas las vistas publicadas y no publicadas de esa página. Dado que puede haber varios usuarios que publican las vistas, es importante poder administrar la lista completa de vistas publicadas, independientemente de si se era o no el usuario que publicó realmente la vista.

Para una lista de todas las vistas publicadas para dicha página, el conjunto de acciones siguiente está disponible. 

- **Volver a publicar**: use la acción **volver a publicar** para volver a publicar una vista después de haber cambiado los parámetros de publicación (nombre, descripción, roles de seguridad o entidades jurídicas).
- **Publicar**: utilice la acción **Publicar** para publicar una vista que no está publicada actualmente. 
- **Anular publicación**: utilice la acción **Anular publicación** para hacer que una vista esté inactiva. La vista seguirá estando disponible en el sistema, pero los usuarios no la verán en el selector de vista hasta que la vista se vuelva a publicar.
- **Guardar como personal**: utilice la acción **Guardar como personal** para crear una copia de borrador personal de la vista publicada. Esta capacidad puede ayudarle a comprender el contenido de una vista que no se le había publicado o que aún no se ha publicado. También puede usarlo para editar y luego volver a publicar una vista.
- **Eliminar**: use la acción **Eliminar** para eliminar de forma permanente una vista publicada o no publicada. Esta acción también elimina la vista para todos los usuarios en el sistema. La eliminación de vistas publicadas surtirá efecto después de que se seleccione el botón **Guardar**. Después de eliminar una vista, no se puede recuperar. 

## <a name="managing-views-globally"></a>Gestionar vistas globalmente

Aunque aparecen algunas capacidades de administración en cada página, como se indica en este artículo, **administradores del sistema** y **ver administradores guardados** puede administrar vistas de manera más holística para el sistema a través de la página **Personalización**. En particular, esta página tiene las siguientes secciones y capacidades: 

- **Vistas publicadas**: esta sección enumera todas las vistas que se han publicado para su organización. Desde aquí, puede volver a publicar una vista después de ajustar las características de seguridad o las entidades legales a las que se dirige la vista. También puede exportar, eliminar o cancelar la publicación de las vistas. Puede usar la acción **Guardar como personal** para crear una copia personal de la vista, de modo que pueda actualizar la vista u obtener una mejor comprensión de su contenido. 
- **Vistas no publicada**: esta sección enumera todas las vistas de la organización en su sistema que no están publicadas actualmente. Estas vistas suelen entrar en el sistema a través de la funcionalidad de importación. Puede publicar, exportar o eliminar estas vistas. La acción **Publicación rápida** que se agregó en la versión 10.0.12 permite que se publiquen varias vistas de esta sección en una sola acción, utilizando el rol de seguridad existente y las configuraciones de entidad legal. Puede usar la acción **Guardar como personal** para crear copias personales de estas vistas, de modo que pueda obtener una mejor comprensión de sus contenidos.
- **Vistas personales**: esta sección enumera todas las vistas que han creado los usuarios en el sistema. Desde aquí, puede publicar una vista personal en la organización, o copiar una o más de estas vistas a otros usuarios. También puede exportar o eliminar estas vistas como sea necesario.
- **Ajustes del usuario**: seleccione un usuario para ver o ajustar la capacidad del usuario para usar la personalización para todo el sistema o para páginas específicas que el usuario ha visitado. Puede ver e interactuar con las personalizaciones del usuario en el sistema. También puede eliminar todas las personalizaciones para ese usuario o restablecer las llamadas de funciones para el usuario. Si se restablecen las llamadas de características que introducían nuevas características y que el usuario descartó anteriormente, estas ventanas emergentes aparecerán de nuevo la próxima vez que el usuario se encuentre con aquellas características.
- **Configuración del sistema**: puede desactivar temporalmente la personalización para todos los usuarios del sistema. En este caso, no se aplican personalizaciones para cualquier usuario, y todas las páginas se restablecen a su estado predeterminado. Si vuelve a habilitar más tarde la personalización, todas las personalizaciones se volverán a aplicar. También puede desactivar permanentemente todas las personalizaciones para todos los usuarios del sistema. No es posible recuperar las personalizaciones que se han eliminado. Por lo tanto, antes de realizar esta tarea, asegúrese de exportar todas las personalizaciones que pueda querer más tarde.

Los usuarios con acceso a la página **Personalización** también pueden importar las vistas de la organización o de la plantilla con el botón **Importar vistas** del panel Acciones. Para las vistas de la organización, puede seleccionar **Publica inmediatamente** para que las vistas estén disponibles para los usuarios sin una publicación explícita adicional.

## <a name="known-issues"></a>Problemas conocidos

Para obtener una lista de los problemas conocidos con las vistas guardadas, consulte [Crear formularios que usan completamente las vistas guardadas](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>¿Cómo habilito las vistas guardadas en mi entorno?

> [!NOTE]
> La característica **Vistas guardadas** requiere que el sistema de personalización de aplicaciones de finanzas y operaciones esté habilitado. Si la personalización se desactiva para todo el entorno, las vistas se deshabilitarán incluso si sigue los pasos siguientes. 

Puede activar y desactivar la función **Vistas guardadas** a través de la gestión de funciones en cualquier entorno. Una vez activada, las vistas guardadas se habilitarán en todas las sesiones de usuario posteriores.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>¿Qué sucede a las personalizaciones existentes cuando se habilitan las vistas? 

Si se habilitan las vistas, las personalizaciones existente para un usuario y un formulario se guardan en una nueva vista denominada **Mi vista** que se establece automáticamente como vista predeterminada. Esto se hace para garantizar que existe una experiencia del usuario coherente antes y después de que se habilitan las vistas, excepto por el control de selector de la vista que aparece en los formularios.

### <a name="what-pages-support-views"></a>¿Qué páginas son compatibles con las vistas? 

Las vistas están disponibles en la mayoría pero no todas las páginas. Específicamente, las vistas se encuentran disponibles en todas las páginas de pantalla completa excepto los paneles de información y espacios de trabajo. Las páginas que no son a pantalla completa, que incluyen los cuadros de diálogo, los diálogos desplegables, las búsquedas, las vistas previas mejoradas, actualmente no admiten las vistas. El soporte para vistas de los tipos adicionales de la página, como espacios de trabajo y cuadros de diálogo, se puede considerar para una actualización futura.

### <a name="who-is-allowed-to-publish-views"></a>¿Quién tiene permiso para publicar vistas?

Sólo las administraciones y los usuarios del sistema a los que se ha asignado al rol **Administrador de las vistas guardadas** tienen derechos para publicar las vistas. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>¿Por qué no puedo guardar filtros con esta vista? 

Existen algunas razones por las que un filtro puede parecer no guardarse con una vista: 

- La página no puede admitir guardar filtros como parte de la definición de vista. Tenga en cuenta que sólo las páginas con los selectores grandes de la vista permiten que las personalizaciones y modificaciones a las consultas se guarden como vista. Consulte la sección **Cambiar vistas** para obtener más información. 
- La página en cuestión no puede admitir las vistas correctamente, mientras que puede omitir la consulta de vista completamente o puede funcionar en una tabla temporal cuyos datos no sean persistentes. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>¿Qué datos veré cuando visite una página?

Para las páginas con selectores de vista pequeña (solo se pueden guardar personalizaciones en la vista), verá los mismos datos que siempre tiene cuando visita la página. 

Para las páginas con selectores de vista grandes (las personalizaciones y consultas se pueden guardar en la vista), verá normalmente los datos vinculados a la consulta que se asociada con su vista predeterminada. Existen dos excepciones principales:

- Si navega a través de un mosaico a una página, la consulta del mosaico se ejecutará independientemente de la consulta asociada a la vista predeterminada. Si creó ese icono después de que se hubieran habilitado las vistas, al seleccionar un icono se abrirá la página con la vista asociada a ese icono.
- Si navega a una página cuyo punto de entrada incluye una consulta, la consulta original se ejecutará originalmente en lugar de la consulta predeterminada de la vista. Debería recibir una alerta cuando esto se produce mediante un mensaje informativo cuando se cargue la vista. También puede confirmar esto cambiando a esta vista después de que la página cargue, ya que eso debería permitir a la consulta de la vista ejecutarse de forma independiente.

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>¿Por qué una vista que se publicó para una entidad jurídica específica está visible en todas las entidades jurídicas?

Si publica una vista en una entidad jurídica específica pero no la publica como vista predeterminada, se produce el siguiente comportamiento:

- Si solo la función base **Vistas guardadas** está activada, el selector de vistas del usuario para la página muestra inicialmente la vista solo para las entidades jurídicas especificadas. Sin embargo, después de cargar la vista por primera vez, el selector de vistas de la página siempre la mostrará, independientemente de la entidad jurídica. Este comportamiento se produce porque los usuarios obtienen su propia copia personal de la vista publicada cuando se carga y las vistas personales son globales.
- **Versión 10.0.21 o posterior:** Si la función **Soporte de entidad jurídica mejorado para vistas guardadas** está activada, el selector de vistas solo mostrará la vista para las entidades jurídicas especificadas. Este comportamiento se produce porque la función permite que las vistas (incluidas las vistas personales) se vinculen a entidades jurídicas específicas.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

