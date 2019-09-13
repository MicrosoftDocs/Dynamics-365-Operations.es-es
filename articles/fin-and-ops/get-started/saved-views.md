---
title: Vistas guardadas
description: Este tema describe cómo usar las características guardadas de las vistas.
author: jasongre
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 43f25796e6271f14acfc72f931398ab63338a307
ms.sourcegitcommit: b068b17ef708a0b349db8df1542e4244bb983d13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2019
ms.locfileid: "1870842"
---
# <a name="saved-views"></a>Vistas guardadas

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introducción
La personalización desempeña una función importante al permitir que los usuarios y las organizaciones optimicen la experiencia del usuario en Microsoft Dynamics 365 for Finance and Operations para satisfacer sus necesidades. Para obtener más detalles acerca de la personalización, consulte [Personalizar la experiencia del usuario](personalize-user-experience.md).

Con la personalización tradicional, los usuarios sólo podían tener un único conjunto de personalizaciones por el formulario. Las vistas guardadas expanden la personalización de varias maneras importantes:

-    Las vistas permien a los usuarios tener varios conjuntos de personalización con nombre por formulario, que pueden intercambiar rápidamente según sea necesario. Esto permite que un usuario cree varias vistas optimizadas de una página, donde cada vista ha estado diseñada para que se adapte a las necesidades de realizar una tarea determinada empresarial. 

-    Las vistas creadas para tipos de determinados de página también pueden incluir los filtros u ordenaciones añadidas por el usuario, que permite a los usuarios volver rápidamente a conjuntos de datos comunes filtrados. Consulte la sección [Qué páginas son compatibles con vistas](saved-views.md#what-pages-support-views) para obtener más detalles. 

-    Las vistas se pueden publicar a roles de seguridad, lo que significa que los usuarios con dicho rol podrá tener acceso y usar a esa vista, independientemente de la capacidad del usuario de personalizar. Esta capacidad permite a las organizaciones definir las vistas corporativas estándar que se optimizan para su negocio. Consulte la sección [Administrar personalizaciones a nivel de organización con vistas](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) para obtener más información.

-    A diferencia de la personalización tradicional, las vistas no se guardan automáticamente cuando un usuario realiza personalizaciones explícitas o filtra una lista. El guardado explícito es necesario para proporcionar flexibilidad para crear una vista antes o después de que los cambios asociados a esa vista se han realizado y garantizar que las definiciones de vista no son modificadas por error por los filtros o las personalizaciones que no están destinados para su uso a largo plazo.  

## <a name="switching-between-views"></a>Cambiando entre vistas
Una vez que las vistas se hayan habilitado para un entorno, cualquier página que admita las vistas incluirá un control incurrido de selector de la parte superior del formulario que muestra el nombre de la vista actual.  

Existen dos variantes de tamaño en selector de la vista: 

-   **Selectores grandes de vista**: las páginas que cuentan con una lista prominente tendrán un selector de imagen mayor por varios motivos. Lo que es más importante, el selector de imagen mayor indica las páginas en la vista que pueden incluir los filtros definidos por el usuario. Dado que los filtros se incluyen en las vistas, el tamaño mayor de selector también se garantiza ya que los nombres de vista son normalmente la mejor descripción de los datos que se muestran en la pantalla y la expectativa es que los usuarios cambiarán entre las vistas más a menudo en estos tipos de la página.  
 
-   **Selectores de vista pequeños**: el resto de los formularios a toda página (con excepción de los espacios de trabajo y el panel) tienen un selector de vista más pequeño que aparece junto a la leyenda de la página. Las vistas en estas páginas incluyen solo personalizaciones (y los filtros no definido por el usuario). En estas páginas, la leyenda del formulario o título de registro es normalmente la información más importante en la parte superior del formulario. El tamaño más pequeño también refleja una frecuencia esperada inferior de conmutación de estas páginas. 
 
Si hace clic en el nombre de vista, el selector de la vista se abre y muestra la lista de vistas disponibles para esta página

-    **Vista clásica**: la vista clásica es la vista de lista para usar la página sin personalizaciones explícitas aplicadas.  
-    **Vistas personales**: las vistas sin los candados representan las vistas personales. Éstas son las vistas que ha creado o que le ha asignado un administrador.  
-    **Vistas bloqueadas**: algunas vistas (como la vista clásica y las vistas publicadas para su rol) tiene un candado junto a ellas en el selector de la vista, indicando que no podrá editarlas. Sin embargo, las personalizaciones implícitas que reflejan el uso de la página se guardan automáticamente, por ejemplo cambiar el ancho de una columna de la cuadrícula o ampliar o contraer una ficha desplegable. Puede, no obstante, crear una vista personal basada en una vista bloquea mediante la acción **Guardar una copia**, si tiene privilegios de personalización.
-    **Nuevas vistas**: las vistas publicadas que aún no se han abierto se delinean con una chispa a la izquierda del nombre de vista.  

Para cambiar a otra vista, abra el selector de la vista y seleccione la vista que desee cargar. 

## <a name="creating-and-modifying-views"></a>Crear y modificar vistas
A diferencia de la personalización tradicional, las vistas no se guardan automáticamente cuando un usuario realiza personalizaciones explícitas (o filtra una lista). Se requiere una acción explícita para guardar estos cambios en una vista. Esto proporciona al usuario flexibilidad para crear una vista antes o después de que los cambios asociados a esa vista se han realizado y garantizar que las definiciones de vista no son modificadas por error por los filtros o personalizaciones de un uso. Tenga en cuenta que las personalizaciones implícitas (por ejemplo cambiar el ancho de una columna de la cuadrícula o ampliar o contraer una ficha desplegable) se guardan automáticamente en la vista actual, incluso para las vistas bloqueadas. 

Para garantizar que se conozca el estado actual de la vista, al empezar a realizar cambios en una vista realizando una personalización o un filtrado explícito, aparecerá un asterisco junto al nombre de vista actual que indica que está mirando una versión no guardada y modificada de esa vista.

Si desea guardar los cambios, siga estos pasos.
1.  Seleccione el nombre de vista para abrir el selector de la vista.
2.  Para modificar la vista existente:
     1. Seleccione **Guardar**. Tenga en cuenta que esta acción no se permitirá para las visiones bloqueadas. 
3.  Para crear una vista nueva:
     1.    Seleccione **Guardar una copia**. 
     2.    Especifique un nombre de vista y una descripción (opcional).
     3.    Seleccione **Guardar**.

## <a name="changing-the-default-view"></a>Cambiar la vista predeterminada
La vista predeterminada es la vista que el sistema intentará abrir cuando navegue a la página por primera vez. Debe establecer esto a la vista que espera usar más a menudo.  

Para cambiar la vista predeterminada de una página, siga estos pasos: 
1.  Cambie a la vista que usa como predeterminada. 
2.  Seleccione el nombre de vista para abrir el selector de la vista. 
3.  Seleccione **Más** y luego en **Anclar como predeterminada**.  

Como alternativa, al crear una nueva vista (mediante la acción **Guardar una copia**), puede crear una nueva vista predeterminada estableciendo la opción **Anclar como predeterminada** antes de guardar la vista.  

Tenga en cuenta que en algunos casos, la consulta asociada a la vista predeterminada no se ejecuta cuando navega por primera vez a una página. Por ejemplo, si navega a través de un mosaico a una página, la consulta del mosaico se ejecutará independientemente de la consulta asociada a la vista predeterminada. Además, si navega a una página cuya vista clásica ya tiene una consulta definida, la consulta se ejecutará originalmente en lugar de la consulta predeterminada de la vista. Cuando esto sucede, un mensaje informativo le alertará cuando la vista se cargue. Intercambiar las vistas después de que la página haya cargado debe permitir que la consulta de la vista se ejecute como se espera.

## <a name="managing-personal-views"></a>Gestión de vistas personales 
El cuadro **Gestionar mis vistas** le da capacidades de mantenimiento básicas sobre sus vistas personales y el orden de vistas en el selector de la vista. Para abrir esta página, haga clic en el nombre de vista para abrir el menú desplegable del selector de la vista, seleccione **Más**y, a continuación **Gestionar mis vistas**.  

Para una lista de vistas disponibles para dicha página, el conjunto de acciones siguiente está disponible.  
-    **Cambiar la vista predeterminada**: use la acción **Anclar como predeterminada** para hacer que la vista actualmente destacada sea la vista predeterminada para esta página.  
-    **Reordenar de sus vistas**: use las acciones **Trasladar hacia arriba** y **Trasladar hacia abajo** para reorganizar sus vistas en un orden determinado.  
-    **Renombrar una vista**: use la acción **Renombrar** para cambiar el nombre de la vista personal destacada actualmente. Esta acción se desactiva para las visiones bloqueadas. 
-    **Eliminar una vista**: Use la acción **Eliminar** para eliminar de forma permanente la vista actualmente destacada desde la página. No es posible de recuperar una vista tras eliminarla.  

Cualquier cambio realizado en este cuadro de diálogo tomará efecto después de activar el botón **Guardar**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Administrar personalizaciones a nivel de organización con vistas
Para entender las mejoras en administrar personalizaciones a nivel de organización, veamos primero cómo la administración de personalización trabajadas antes de las vistas.  

Sin vistas, los administradores aplicarían un conjunto de personalizaciones para una página a un usuario o a un grupo de usuarios usando la página de personalización. Si estos usuarios tuvieran derechos de personalización, las personalizaciones serían aplicadas a esa página. Sin embargo, no había capacidad para evitar que los usuarios personalizasen más la página, lo que significaba que la organización no podía garantizar que los usuarios tuvieran una interfaz de usuario coherente. Si ninguno de estos usuarios tenían derechos de personalización, las personalizaciones que les concedía un administrador no se cargaban. Además, si se contrataba a nuevos usuarios en una organización, los administradores debían cargar manualmente un conjunto de personalizaciones para el usuario. No había un mecanismo automático para especificar que un determinado conjunto de personalizaciones debían estar disponibles para los usuarios de ese rol.

Con la función de vistas guardadas, la gestión de organización de personalizaciones es mucho más sencilla, principalmente debido a la capacidad de publicar las vistas a roles de seguridad. Una vez una vista se publica, cualquier usuario con dicho rol podrá tener acceso y usar a esa vista, independientemente de la capacidad del usuario de personalizar. Aunque cada usuario tiene una copia de la vista publicada en la que el uso de la página (personalizaciones implícitas) se aplicará automáticamente, ningún usuario puede guardar personalizaciones o actualizaciones explícitas a la consulta para la vista publicada (significa que las vistas publicadas están bloqueadas). Además, si nuevos usuarios reciben un rol para el que se publicó la vista, automáticamente verán las vistas asociadas con sus roles sin que el administrador tenga que actuar. De forma similar, si un usuario cambia de rol en una organización, las vistas asociadas al antiguo rol ya no estarán accesibles, de nuevo sin ninguna acción del administrador. Las actualizaciones de una vista publicada se pueden distribuir fácilmente a los usuarios republicando la vista a los roles de seguridad correspondientes.

Esta capacidad permite a las organizaciones definir las vistas corporativas estándar que se optimizan para su negocio, dirigidas a usuarios en roles de seguridad específicos.  

## <a name="publishing-views"></a>Publicar vistas
Durante el proceso de la publicación, las vistas se pueden asignar a uno o más roles de seguridad, lo que significa que los usuarios con dicho rol podrá tener acceso y usar a esa vista, aunque no pueden editarla. Actualmente, solo los administradores del sistema tienen derechos para la acción **Publicar** en el menú desplegable del selector de vista, pero un nuevo rol de seguridad estará disponible en una actualización futura para dar derechos de publicación a otros usuarios de confianza.  

Para publicar una vista, siga estos pasos: 
1.  Cree y guarde una copia personal de la vista que desea publicar. 
2.  Con esa vista cargada actualmente, seleccione el nombre de vista para abrir el menú desplegable del selector de la vista. 
3.  Seleccione el botón **Más** y a continuación seleccione **Publicar**. El cuadro de diálogo de la publicación se abrirá.  
4.  Proporcione un nombre de vista y una descripción (opcional). Este es el nombre que los usuarios que reciben esta vista verán en los selectores de la vista. Tenga en cuenta que no se permiten los nombres duplicados para las vistas publicadas para una página, incluso si la lista de roles a las que se aplican difieren.  
5.  Agregue cualquier rol de seguridad que se corresponda con los usuarios que obtendrán esta vista.  
6.  Seleccione **Publicar**.

Tenga en cuenta que en algunos entornos esto podrá llevar tiempo (hasta una hora) antes de que los usuarios vean la vista publicada.

## <a name="modifying-a-published-view"></a>Modificar una vista publicada
Tras publicar una vista, puede descubrir que desea efectuar cambios en una vista publicada. Aunque no podrá realizar cambios en vivo a una vista publicada, ya que estas vistas estarán bloqueadas para su edición para todos los usuarios (incluidos editores), puede volver a publicar una vista para crear actualizaciones.  

Si los cambios que desea realizar en una vista publicada afectan sólo a los parámetros de la publicación (el nombre y la descripción de la vista, o se publican los roles de seguridad la vista), haga lo siguiente: 
1.  Cambie a la vista publicada para los parámetros que desea actualizar. 
2.  Seleccione **Publicar** en el menú desplegable del selector de vista. 
3.  Seleccione **Sí** si desea actualizar la vista existente (o **No** si desea publicar esto con otro nombre.)
4.  Actualice el nombre, la descripción, y/o los roles de seguridad de la vista. 
5.  Seleccione **Publicar**. 
6.  Si ha actualizado el nombre de la vista publicada, también deberá eliminar la vista publicada con el nombre anterior (consulte la sección **Administrar las visiones publicadas** para obtener más detalles.) 

Si los cambios a la vista publicada implican modificar las personalizaciones o los filtros asociados a la vista, siga estos pasos: 
1.  Cambie a la vista publicada que desea modificar. 
2.  Guarde una copia de la vista publicada para crear un borrador local de la vista publicada. 
3.  Modificar el borrador local con los cambios necesarios.
4.  Publicar la vista con el nombre original. 

## <a name="managing-published-views"></a>Administrar las visiones publicadas
Como administrar las vistas personales, el cuadro **Administrar mis vistas** da a los usuarios con privilegios básicos de publicación la capacidad de mantener las vistas publicadas de esa página (además de sus propias vistas personales). Para abrir esta página, seleccione el nombre de vista para abrir el menú desplegable del selector de la vista, seleccione **Más**y, a continuación **Administrar mis vistas**.

Aunque todos los usuarios ven una pestaña **Mis vistas** mostrando sus vistas personales, los usuarios con privilegios de publicación también ven una pestaña **Publicadas** que muestra todas las visiones publicadas de la página. Dado que puede haber varios usuarios que publican las vistas, es importante poder administrar la lista completa de vistas publicadas, independientemente de si se era el usuario que publicó realmente la vista.

Para una lista de todas las vistas publicadas para dicha página, el conjunto de acciones siguiente está disponible. 

-    **Publicar**: use la acción **Publicar** para volver a publicar una vista con parámetros de publicación modificados (nombre, descripción, roles de seguridad).  
-    **Eliminar**: use la acción **Eliminar** para eliminar de forma permanente una vista publicada. Esta acción elimina la vista para todos los usuarios en el sistema.  
 
Cualquier cambio realizado en este cuadro de diálogo tomará efecto después de seleccionar el botón **Guardar**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>¿Cómo habilito las vistas guardadas en mi entorno? 
Para habilitar las vistas guardadas mientras la característica se encuentra en vista previa, realice los siguientes pasos: 

1.  **Habilite el tramo**: ejecute la instrucción SQL siguiente: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Restablecer IIS** para vaciar la memoria caché estática de la distribución de paquetes piloto. 

3.  **Encontrar la característica**: vaya al espacio de trabajo **Administración de características**. Si **Vistas guardadas** no aparece en la lista, seleccione **Buscar actualizaciones**.   

4.  **Habilitar la característica**: encuentre la característica **Vistas guardadas** en la lista de características y seleccione **Habilitar ahora** en el panel de detalles.

Todas las sesiones de usuario posteriores comenzarán con las vistas guardadas habilitadas.  

Tenga en cuenta que si la personalización se desactiva para el entorno, las vistas se deshabilitarán incluso si sigue los pasos anteriores. Esto se debe a que la característica de las vistas se crea sobre el subsistema de personalización.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>¿Qué sucede a las personalizaciones existentes cuando se habilitan las vistas? 
Si se habilitan las vistas, las personalizaciones existente para un usuario y un formulario se guardan en una nueva vista denominada **Mi vista** que se establece automáticamente como vista predeterminada. Esto se hace para garantizar que existe una experiencia del usuario coherente antes y después de que se habilitan las vistas, excepto por el control de selector de la vista que aparece en los formularios.  

### <a name="what-pages-support-views"></a>¿Qué páginas son compatibles con las vistas? 
Las visiones están disponibles en la mayoría pero no todas las páginas de Finance and Operations. Específicamente, las vistas se encuentran disponibles en todas las páginas de pantalla completa excepto los paneles de información y espacios de trabajo. Las páginas que no son a pantalla completa, que incluyen los cuadros de diálogo, los diálogos desplegables, búsquedas, vistas previas mejoradas, actualmente no admiten las vistas. El soporte para vistas de los tipos adicionales de la página, como espacios de trabajo y cuadros de diálogo, se puede considerar para una actualización futura.   

### <a name="who-is-allowed-to-publish-views"></a>¿Quién tiene permiso para publicar vistas?
Los administradores del sistema son actualmente los únicos usuarios con derechos de publicar las vistas.  Se planea un nuevo rol de seguridad en una actualización futura que proporcionaría a los clientes más flexibilidad sobre quién puede publicar.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>¿Por qué no puedo guardar filtros con esta vista? 
Existen algunas razones por las que un filtro puede parecer no guardarse con una vista: 

- La página no puede admitir guardar filtros como parte de la definición de vista. Tenga en cuenta que sólo las páginas con los selectores grandes de la vista permiten que las personalizaciones y modificaciones a las consultas se guarden como vista. Para más información consulte la sección "Cambiar vistas". 

- Si la vista es la vista predeterminada y la ruta de navegación de la página incluye una consulta, la consulta de la vista puede que no se aplique inicialmente. Las dos casos principales para esto son: 
     - Si navega a través de un mosaico a una página, la consulta del mosaico se ejecutará independientemente de la consulta asociada a la vista predeterminada. 
     - Si navega a una página cuyo punto de entrada incluye una consulta, la consulta original se ejecutará originalmente en lugar de la consulta predeterminada de la vista. 
     
  Cuando esto sucede, un mensaje informativo debería alertarle cuando la vista se cargue. También puede confirmar esto cambiando a esta vista después de que la página cargue, ya que eso debería permitir a la consulta de la vista ejecutarse de forma independiente.  

- La página en cuestión no puede admitir las vistas correctamente, mientras que puede omitir la consulta de vista completamente o puede funcionar en una tabla temporal cuyos datos no sean persistentes. 
