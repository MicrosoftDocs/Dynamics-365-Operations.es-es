---
title: Asignar a contenedor/Asignar a tienda
description: En este tema se proporciona información sobre la funcionalidad Asignar a contenedor/Asignar a tienda. Esta funcionalidad le permite manejar escenarios en los que debe consolidar un producto en un área de almacenamiento provisional de preempaquetado, de acuerdo con criterios configurables. Ayuda a reducir el tiempo de selección porque permite seleccionar una única matrícula de entidad de almacén de destino y puede usar más posiciones de asignación que la selección de clústeres.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cf34a61d0b3f784b5a424473588d05bf8703635c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823296"
---
# <a name="put-to-wall---put-to-store"></a>Asignar a contenedor/Asignar a tienda

[!include [banner](../includes/banner.md)]

La funcionalidad *Asignar a contenedor/Asignar a tienda* le permite manejar escenarios en los que debe consolidar un producto en un área de almacenamiento provisional de preempaquetado, de acuerdo con criterios configurables. Dado que esta funcionalidad permite seleccionar una única matrícula de entidad de almacén de destino y puede usar más posiciones de asignación que la selección de clústeres, las empresas que envían a tiendas o manipulan artículos pequeños se beneficiarán de un menor tiempo de selección.

El flujo de trabajo para esta funcionalidad dirige el producto seleccionado a una ubicación de ordenación para su distribución a varios tipos de contenedores. Por lo general, cada ubicación de ordenación incluye varias posiciones de ordenación. Cada posición de ordenación se asigna de acuerdo con los criterios establecidos por el proceso empresarial. Los criterios típicos son el destino final, el envío o la carga. Una vez que llega un producto, se distribuye a cada posición de ordenación, en función de la cantidad asociada al pedido, al destino, al envío o la carga. Cuando un contenedor esté lleno o completo, se mueve a una ubicación de almacenamiento provisional o una ubicación de envío para su posterior manipulación, según el proceso empresarial.

Esta funcionalidad de almacenamiento también se conoce con otros nombres, como put-to-light y break opens.

## <a name="turn-on-the-outbound-sorting-feature"></a>Active la característica de ordenación de salida

Antes de poder usar la funcionalidad *Asignar a contenedor/Asignar a tienda*, la característica *Ordenación de salida* debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Ordenación de salida*

La característica *Ordenación de salida* se puede utilizar junto con la característica *Código de paso de oleada de toda la organización* si está activada. También debe activar esta característica si va a utilizar códigos predefinidos que está configurados en códigos de paso de oleada. En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Código de paso de oleada de toda la organización*

## <a name="setup"></a>Configurar

Para esta demostración, se utilizan datos estándar de Contoso y el almacén *62*. También se usan algunas adiciones que se indican más adelante.

### <a name="location-type"></a>Tipo de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Tipos de ubicación**.
1. En el panel de acciones, seleccione **Nuevo** para crear un tipo de ubicación para ordenar.
1. Establezca los valores siguientes:

    - **Tipo de ubicación:** *SORT*
    - **Descripción:** *Ordenar*

1. Seleccione **Guardar**.

### <a name="warehouse-management-parameters"></a>Parámetros de gestión de almacenes

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en la ficha desplegable **Tipos de ubicación**, en el campo **Tipo de ubicación de ordenación**, introduzca *SORT*.
1. Seleccione **Guardar**.

### <a name="location-profile"></a>Perfil de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En el panel de acciones, seleccione **Nuevo** para crear un perfil de ubicación para la ubicación de ordenación.
1. Establezca los siguientes valores en el encabezado:

    - **Id. de perfil de ubicación:** *Ordenar*
    - **Nombre:** *Ordenar*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Formato de ubicación:** *PACK*
    - **Tipo de ubicación:** *SORT*
    - **Usar seguimiento de matrículas de entidad de almacén:** *Sí*
    - **Permitir artículos combinados:** *Sí*
    - **Permitir estados de inventario combinados:** *Sí*

1. Seleccione **Guardar**.

### <a name="locations"></a>Ubicaciones

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. Borre la casilla **Generar dígitos de control para la ubicación**.
1. En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:

    - **Almacén**: *62*
    - **Ubicación:** *Ordenar*
    - **Id. de perfil de ubicación:** *Ordenar*

1. Seleccione **Guardar**.

### <a name="packing-profiles"></a>Perfiles de embalaje

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.
1. En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:

    - **Id. de perfil de empaquetado:** *Ordenar*
    - **Descripción:** *Ordenar*
    - **Directiva de embalaje de contenedores:** Deje este campo en blanco.
    - **Modo del id. de contenedor:** *Automático*
    - **Tipo de contenedor:** *PALLET 48X48*
    - **Crear contenedor automáticamente al cerrar el contenedor:** Deje este campo en blanco.

1. Seleccione **Guardar**.

### <a name="wave-step-codes"></a>Códigos de paso de oleada

Si activó la característica *Código de paso de oleada de toda la organización*, configure el siguiente código.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Códigos de paso de oleada**.
1. En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:

    - **Código de paso de oleada:** *Ordenar*
    - **Descripción de paso de oleada:** *Ordenar*
    - **Tipo de paso de oleada:** *Plantilla de ordenación*

1. Seleccione **Guardar**.

### <a name="outbound-sorting-template"></a>Plantilla de ordenación de salida

La plantilla de ordenación controla si se crean las posiciones de ordenación, los criterios que se utilizan y otros atributos del proceso de ordenación.

1. Vaya a **Gestión de almacenes \> Configuración \> Embalado \> Plantillas de ordenación salientes**.
1. En el panel de acciones, seleccione **Nuevo** para crear una plantilla de ordenación.
1. En el encabezado de la nueva plantilla, establezca los siguientes valores:

    - **Id. de plantilla de ordenación de salida:** *Ordenación de oleadas*
    - **Descripción:** *Ordenación de oleadas*
    - **Tipo de plantilla de ordenación:** *Demanda de oleadas*

        Este campo define el proceso para el que se utiliza la plantilla de ordenación. Los siguientes valores están disponibles:

        - **Demanda de oleadas:** la plantilla de ordenación se utiliza para el proceso *Asignar a contenedor*. Este tipo de plantilla se usa para omitir la estación de embalaje y procesar el inventario directamente fuera de la oleada. Puede usar este tipo solo si el el proceso de la oleada de **ordenación** se incluye en la plantilla de la oleada.
        - **Contenedor:** la plantilla de ordenación se usa para el proceso *Construcción de pallets después del empaquetado*. Este tipo de plantilla se usa para procesar los contenedores que están cerrados en esa estación de embalaje y debe ordenados sobre pallets.

    - **Almacén**: *62*
    - **Ubicación:** *Ordenar*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Comprobación del orden:** *Escaneo de posición*.

        Este campo define la verificación que se requiere durante la ordenación. Los siguientes valores están disponibles:

        - None
        - Escaneo de matrícula de entidad de almacén
        - Escaneo de posición

    - **Crear trabajo en posición cerrada:** *Sí*

        Si la opción se establece en *Sí*, cuando la posición se cierre, se creará el trabajo para mover el inventario a la ubicación de envío final. Si se establece en *No*, el inventario se seleccionará inmediatamente para el pedido cuando se cierre la posición.

    - **Asignación de posición:** *Manual*

        Este campo define el tipo de asignación de posición. Los siguientes valores están disponibles:

        - **Manual**: el usuario debe indicar siempre en qué posición se debe ordenar el inventario.
        - **Automático:** el sistema automáticamente dirigirá el inventario a una posición cuando sea posible, en función de los descansos de la plantilla de ordenación.

    - **Asignar criterios de posición de ordenación:** *Usar solo una posición vacía*

        Este campo controla si el inventario que ya está presente en puestos clasificados se tiene en cuenta cuando se asigna un puesto para la demanda. Los siguientes valores están disponibles:

        - **Usar solo una posición vacía:** se tendrán en cuenta las posiciones que ya tienen inventario asociado a ellas.
        - **Asumir posición vacía:** cualquier inventario que ya esté en la posición no se tendrá en cuenta durante la asignación. Se utilizarán todas las posiciones disponibles.

    - **Código de paso de oleada:** *Ordenar*

        Si la característica *Código de paso de oleada de toda la organización* está activada, el código de paso de oleada *Ordenación* también debe configurarse en códigos de paso de oleada.

    - **Posición de ordenación de cierre automático:** *Sí*

        Si esta opción se establece en *Sí*, la posición de la ordenación se cerrará automáticamente cuando todo el trabajo que viene a la ubicación se haya completado.

    - **Número de posiciones de ordenación:** *3*

        Este campo define el número máximo de posiciones de ordenación que creará el sistema.

    - **Prefijo de posición de ordenación:** *SP*

        Este campo define el prefijo que el sistema asigna antes del número de posición.

    - **Posición de ordenación de empaquetado automático:** *Sí*

        Si esta opción se establece en *Sí*, el inventario en la posición de ordenación se envasará en un contenedor cuando se cierra la posición.

    - **Id. de perfil de empaquetado:** *Ordenar*

        Este campo define el perfil de embalaje que se usará cuando la posición de ordenación sea embalada en un contenedor.

1. En el panel de acciones, seleccione **Editar consulta** para especificar los criterios que se utilizan para esta plantilla de ordenación.
1. En el cuadro de diálogo de consulta, en la pestaña **Ordenación**, seleccione **Nuevo** para agregar una línea y luego establezca los siguientes valores:

    - **Tabla:** *Detalles de carga*
    - **Tabla derivada:** *Detalles de carga*
    - **Campo:** *Identificación del envío*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar**.
1. Es posible que reciba el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?" Seleccione **Sí**.

    El botón **Descansos de la plantilla de ordenación de salida** del panel de acciones estará disponible.

1. En el panel de acciones, seleccione **Descansos de la plantilla de ordenación de salida**.
1. Seleccione la casilla **Agrupar por campo** para agrupar por id. de envío.

    Esta configuración creará una posición de ordenación por envío que es un contenedor en la oleada.

1. Seleccione **Aceptar**.

### <a name="wave-process-methods"></a>Métodos de procesamiento de oleada

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. En el panel acciones, seleccione **Regenerar métodos**.

    El método de **ordenación** se agrega a la lista de métodos disponibles, y se selecciona el tipo de plantilla de oleada *Envío* para ello.

### <a name="wave-templates"></a>Plantillas de oleada

Edite la plantilla de oleada que se utiliza para la ordenación de la demanda de oleadas.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el campo **Tipo de plantilla de oleada**, seleccione *Envío*.
1. Seleccione la plantilla **62 Envío predeterminado** existente.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, haga los siguientes cambios:

    - Establezca la opción **Procesar oleada para su despacho al almacén** en *No*.
    - Establezca la opción **Asignar a oleadas abiertas** en *Sí*.

1. En la ficha desplegable **Métodos**, configure el método de **ordenación**:

    1. En la cuadrícula **Métodos restantes**, seleccione **ordenación**.
    2. Seleccione el botón de flecha derecha para mover la **ordenación** a la cuadrícula **Métodos seleccionados**.
    3. En la cuadrícula **Métodos seleccionados**, seleccione **ordenación**.
    4. Establezca el campo **Código de paso de oleada** en *Ordenación*.

1. Seleccione **Guardar**.

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento de menú:** *Ordenar*
    - **Título:** *Ordenar*
    - **Modo:** *Indirecto*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Código de actividad:** *Ordenación de salida*
    - **Usar guía de proceso:** *Sí* (valor predeterminado)
    - **Id. de plantilla de ordenación de salida:** *Ordenación de oleadas*

1. Seleccione **Guardar**.

### <a name="mobile-device-menu"></a>Menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En la lista de menús, seleccione **Saliente**.
1. En el panel Acciones, seleccione **Editar**.
1. En la cuadrícula **Menús disponibles y elementos de menú**, busque y seleccione el elemento de menú **Ordenar** que acaba de crear.
1. Seleccione el botón de flecha derecha para mover **Ordenar** a la cuadrícula **Estructura del menú**. De esta manera, agrega el elemento de menú al menú **Saliente**.
1. Seleccione **Guardar**.

### <a name="location-directives"></a>Directivas de ubicación

Debe crear directivas de ubicación para guiar el trabajo que se crea después de que se complete la ordenación.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Selección de inventario ordenado*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Secuencia**: *1*
    - **Nombre:** *Asignar a Baydoor*

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes:

    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *6*
    - **Almacén**: *62*
    - **Código de directiva:** deje en blanco este campo.
    - **Varios SKU:** *No*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes. Acepte los valores predeterminados del resto de campos.

    - **Número de secuencia:** *1*
    - **Cantidad inicial**: *0*
    - **Cantidad final**: *1000000*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes. Acepte los valores predeterminados del resto de campos.

    - **Número de secuencia:** *1*
    - **Nombre:** *Baydoor*

1. Seleccione **Guardar** para tener disponible el botón **Editar consulta** en la ficha desplegable **Acciones de directiva de ubicación**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En el cuadro de diálogo de consulta, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*. Seleccione el campo **Criterios** en esta fila para *Baydoor*.
1. Seleccione **Aceptar** para confirmar la edición.

### <a name="work-classes"></a>Clases de trabajo

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Id. de la clase de trabajo:** *Ordenación*
    - **Descripción:** *Ordenación*
    - **Tipo de orden de trabajo:** *Selección de inventario ordenado*

1. Seleccione **Guardar**.

### <a name="work-templates"></a>Plantillas de trabajo

1. Vaya a **Gestión de almacenes \> Trabajo \> Plantillas de trabajo**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.
1. En la cuadrícula, seleccione la plantilla de trabajo **62 Selección para empaquetar**.
1. En el panel de acciones, seleccione **Saltos de encabezado de trabajo**.
1. En el panel Acciones, seleccione **Editar**.
1. En la línea donde el campo **Nombre del campo** esté establecido en *Id. del envío*, desactive la casilla **Agrupar por este campo**.
1. Seleccione **Guardar** y luego cierre el cuadro de diálogo **Saltos de encabezado de trabajo**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Selección de inventario ordenado*.
1. Seleccione **Nuevo** para crear una plantilla de trabajo.
1. En la sección **Visión general**, establezca los siguientes valores. Acepte los valores predeterminados del resto de campos.

    - **Plantilla de trabajo:** *Selección ordenada*
    - **Descripción de la plantilla de trabajo:** *Selección ordenada*

1. Seleccione **Guardar** para tener disponible la sección **Detalles de plantilla de trabajo**.
1. En la sección **Detalles de plantilla de trabajo**, creará dos líneas. Seleccione **Nuevo** y establezca los valores siguientes para la línea 1:

    - **Tipo de trabajo**: *Recoger*
    - **Obligatorio:** Seleccionado (= *Sí*)
    - **Id. de la clase de trabajo:** *Ordenación*

1. Seleccione **Nuevo** una vez más y establezca los valores siguientes para la línea 2:

    - **Tipo de trabajo**: *Ubicar*
    - **Obligatorio:** Seleccionado (= *Sí*)
    - **Id. de la clase de trabajo:** *Ordenación*

1. Seleccione **Guardar**.

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario simula una situación en la que el almacén almacena artículos pequeños en ubicaciones y debe empaquetarlos en cajas antes de enviarlos, y donde la funcionalidad de la estación de empaquetado no es realmente adecuada. Para aumentar la velocidad de selección, los trabajadores seleccionan pedidos para varios clientes y diferentes direcciones al mismo tiempo. Una vez que se ha completado la selección, los trabajadores llegan a la ubicación de ordenación, donde los artículos seleccionados se pueden ordenar en la casilla correcta, según los criterios requeridos. En este ejemplo, el id. del envío se utilizará para determinar la casilla correcta, porque cada envío tiene una dirección diferente. Después de que todos los artículos de la carga se empaqueten y ordenen por envío, las cajas se moverán al área de almacenamiento provisional y finalmente se cargarán en un camión.

Antes de comenzar el escenario, asegúrese de que toda la funcionalidad estándar del almacén esté configurada correctamente para su almacén. El almacén estándar *62* de Contoso se utiliza para este propósito. No se han cambiado las configuraciones estándar, aparte de lo que se describe en la configuración.

### <a name="create-demand"></a>Crear demanda

Antes de que se pueda demostrar la funcionalidad, debe crear cierta demanda. Para este escenario, creará tres pedidos de ventas para tres clientes diferentes a fin de simular distintas direcciones de entrega. De esta manera, creará tres envíos independientes.

Antes de crear pedidos de ventas y envíos, asegúrese de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en los pedidos. Revise la configuración de la directiva de ubicación para confirmar las ubicaciones de selección que se utilizan para la selección de pedidos de ventas. Si debe ajustar el inventario, puede crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo. A continuación, reserve el inventario.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas para el pedido 1.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cliente:** *US-001*
    - **Almacén**: *62*

1. Seleccione **Aceptar**.
1. Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**. Establezca los valores siguientes:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *5*

1. Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *10*

1. Repita los siguientes pasos para cada línea de ventas en el pedido para reservar inventario para este:

    1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.
    1. En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.
    1. Seleccione **Guardar**.

1. Seleccione **Nuevo** para crear un pedido de ventas para el pedido 2.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cliente:** *US-004*
    - **Almacén**: *62*

1. Seleccione **Aceptar**.
1. Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**. Establezca los valores siguientes:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *7*

1. Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *3*

1. Repita los siguientes pasos para cada línea de ventas en el pedido para reservar inventario para este:

    1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.
    1. En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.
    1. Seleccione **Guardar**.

1. Seleccione **Nuevo** para crear un pedido de ventas para el pedido 3.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cliente:** *US-007*
    - **Almacén**: *62*

1. Seleccione **Aceptar**.
1. Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**. Establezca los valores siguientes:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *8*

1. Siga estos pasos para reservar el inventario para la línea de ventas:

    1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.
    1. En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.
    1. Seleccione **Guardar**.

Complete el siguiente procedimiento para liberar cada pedido de ventas al almacén. Se crearán tres envíos diferentes. A continuación, agregará los tres envíos a una nueva oleada.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En la cuadrícula, seleccione el primer pedido de ventas que creó.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Recibirá un mensaje informativo que muestra el id. de oleada y el id. de envío que se crearon.

1. Repita los pasos anteriores para liberar los pedidos de ventas 2 y 3 al almacén. Observe que el mensaje informativo que recibe indica que se ha agregado un envío a la oleada que se creó cuando liberó el pedido de ventas 1.
1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione el id. de oleada que se creó a partir de la liberación de los pedidos de ventas para abrir la página **Oleadas**. Esta página muestra los detalles de la oleada. La ficha desplegable **Líneas de oleada** muestra los envíos que se crearon.

    Ahora debe crear un trabajo para llevar artículos de las ubicaciones de selección a la ubicación de ordenación.

1. En el panel de acciones, seleccione **Proceso**.

    Durante el procesamiento de oleadas, el método de ordenación utilizará la plantilla de ordenación para asignar el inventario a las posiciones de ordenación. Cuando se completa el procesamiento de oleadas, recibe un mensaje informativo que indica que se ha registrado la oleada y se ha creado el trabajo.

1. En el panel de acciones, en la pestaña **Oleada**, en el grupo **Información relacionada**, seleccione **Trabajo** para ver el trabajo que se creó. Anote el id. de trabajo.
1. Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.
1. En la columna izquierda, puede ver la posición de ordenación de salida que se creó para cada envío.
1. En la ficha desplegable **Criterios de posición de ordenación**, puede ver el id. del envío para esa posición.

Se ha creado un id. de trabajo para llevar el inventario de las ubicaciones de selección a la ubicación de ordenación. Para completar el trabajo, necesitará el id. de trabajo que se creó durante el procesamiento de oleadas.

### <a name="sales-order-picking-to-the-sorting-location"></a>Selección del pedido de ventas en la ubicación de ordenación

1. Inicie sesión en la aplicación móvil como un trabajador en el almacén *62*.
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Selección de ventas**.
1. Selecciona el campo **Id.** y luego introduzca el id. de trabajo del procesamiento de oleadas.
1. Confirme su entrada.

    A continuación, se le pide que introduzca una matrícula de entidad de almacén de destino. Observe que la línea 1 del pedido de cliente 1 es lo que debe seleccionarse y agregarse a la matrícula de entidad de almacén de destino. Se muestran el número de artículo, la cantidad, la descripción del artículo y la ubicación de selección.

1. En el campo **Matrícula de destino**, introduzca una matrícula de entidad de almacén.

    Seleccionará todas las líneas que se crearon a partir de la oleada procesada en la misma matrícula de entidad de almacén de destino.

1. Confirme su entrada.

    La aplicación móvil ahora presenta una serie de páginas **Selección** que le dirigen a la ubicación de selección, y al artículo y la cantidad que debe seleccionarse. Después de agregar el artículo seleccionado a la matrícula de entidad de almacén, confirmará el trabajo de selección. La última página será el trabajo para colocar los artículos seleccionados en la ubicación de ordenación.

1. Confirme el primer trabajo de selección.
1. Se muestra el siguiente trabajo de selección. Confirme la selección.
1. Siga confirmando el trabajo de selección restante.
1. El último paso es completar el trabajo de colocación. Confirme la ubicación en la ubicación de ordenación.

    Recibe un mensaje "Trabajo completado".

1. Salga de **Selección de ventas** en la aplicación móvil.

### <a name="sortingput-to-wall"></a>Ordenación/Asignar a contenedor

Ahora que todo el inventario se ha colocado en la ubicación de ordenación, debe ordenarse en la posición de ordenación correcta.

1. Inicie sesión en la aplicación móvil.
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Ordenar** para empezar a ordenar los artículos.
1. En el campo **Matrícula/CON**, introduzca la matrícula de entidad de almacén de destino del trabajo de pedido de ventas seleccionado.
1. Confirme su entrada.
1. Introduzca el número de artículo para ordenarlo primero.
1. El sistema determina la primera posición de ordenación que se debe mostrar. Confirme la posición de ordenación.
1. Se le pedirá que asigne una matrícula de entidad de almacén a la posición de ordenación. Seleccione el campo **Matrícula**, introduzca una matrícula de entidad de almacén y luego confirme su entrada.

    Debido a que la posición de ordenación está relacionada con el id. de envío, ordenará los artículos seleccionados en una matrícula de entidad de almacén específica para el envío saliente y el pedido de ventas.

    La siguiente página muestra el id. del artículo, la cantidad, el id. de posición de ordenación y los id. de matrícula de entidad de almacén "desde" (selección) y "hasta" (ordenación). La información de esta página le indica que ordene el artículo y las cantidades especificadas de la matrícula de entidad de almacén de selección en la matrícula de entidad de almacén de ordenación.

1. Confirme la posición de ordenación.
1. Ordene los artículos en la primera posición de ordenación. Cuando haya terminado, el sistema le dirige a la siguiente posición de ordenación.
1. Repita este proceso para todas las líneas seleccionadas en la orden de trabajo. También debe usar este proceso cuando haya varias líneas de selección que tengan el mismo número de artículo.

    A medida que repita este proceso para todos los artículos, el sistema evalúa los criterios del siguiente artículo escaneado (línea de trabajo) y determina en qué posición de ordenación debe colocarse. Se le dirige automáticamente para que coloque el artículo en la posición de ordenación correcta. Según de la configuración de la confirmación, también se le pide que confirme esta acción introduciendo el número de posición o el id. de matrícula de entidad de almacén.

    > [!NOTE]
    > Si la ordenación automática está activada, la anulación manual no está disponible.

1. Cuando haya terminado, en Microsoft Dynamics 365 Supply Chain Management, abra la página **Asignaciones de posición de ordenación de salida** para revisar el estado de las posiciones.

    - Si las posiciones se cierran automáticamente, seleccione **Mostrar cerrado** para mostrar las posiciones cerradas.
    - Observe que se muestran las transacciones de posición de ordenación. Se muestran el artículo y la cantidad que se procesaron a través de la posición.

    Cuando configura la plantilla de ordenación de salida, establece la opción **Posición de ordenación de cierre automático** en *Sí*. Por lo tanto, la posición se cierra automáticamente una vez que se le asigna el último inventario esperado. Las posiciones de ordenación están en estado **Cerrado** y se ha creado un trabajo para mover el inventario ordenado a una ubicación *Baydoor*.

1. Complete el trabajo de selección de inventario ordenado para mover el inventario a la ubicación de envío. Cuando el inventario esté listo, envíelo y confírmelo.

> [!NOTE]
> Para que el trabajo de selección de inventario ordenado se procese correctamente, un elemento de menú del dispositivo móvil con un id. de clase de trabajo donde el campo **Tipo de orden de trabajo** está establecido en *Selección de inventario ordenado* debe usarse para el movimiento y el proceso de carga.

### <a name="manually-close-a-position-optional"></a>Cerrar manualmente una posición (opcional)

Si las posiciones de ordenación deben cerrarse manualmente, la opción **Posición de ordenación de cierre automático** para la plantilla de ordenación de salida debe establecerse en *No*, y el cierre debe hacerse antes de que el inventario se pueda mover al área de la compuerta. Las posiciones se pueden cerrar de varias maneras:

- Mediante la aplicación móvil Warehouse Management:

    - El usuario puede escanear uno de los artículos que ya están en la posición y luego seleccionar **Cerrar** para cerrar la posición.
    - Si el usuario escanea un contenedor que ya se ha ordenado, se muestra un mensaje de error. Sin embargo, el usuario puede seguir cerrando la posición.

- Desde la página **Asignaciones de posición de ordenación de salida** de Microsoft Dynamics 365 Supply Chain Management:

    - El usuario puede seleccionar el registro de posición de ordenación de salida y luego seleccionar **Cerrar posición** en el panel de acciones.

## <a name="tips"></a>Sugerencias

- Los artículos no se pueden mover entre posiciones después de haber sido asignados a una. El sistema evalúa cuántos de cada artículo deben ir a una posición concreta.
- Se puede configurar una plantilla de ordenación para crear contenedores automáticamente cuando las posiciones estén cerradas. Este enfoque creará una estructura de id. de contenedor estándar que se basa en el perfil de embalaje especificado.

> [!IMPORTANT]
> Una vez que se haya creado un trabajo de movimiento desde la ubicación de ordenación, no debe cancelar el trabajo. De lo contrario, la posición y los contenedores que contiene se eliminarán del sistema y no estarán disponibles para su posterior procesamiento. El inventario también se eliminará.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]