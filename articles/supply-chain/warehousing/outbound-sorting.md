---
title: Ordenación de salida
description: Este tema proporciona información acerca de la ordenación de salida. Esta funcionalidad facilita el manejo de contenedores pequeños y ayuda a los empleados del almacén a planificar y organizar mejor la capacidad de los pallets en el camión.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 84c4ec83ed16762e6c3c1a22425cf60e5b3ae8da
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437273"
---
# <a name="outbound-sorting"></a>Ordenación de salida

[!include [banner](../includes/banner.md)]

Esta funcionalidad facilita el manejo de contenedores pequeños y ayuda a los empleados del almacén a planificar y organizar mejor la capacidad de los pallets en el camión. Cuando utiliza la ordenación de salida, puede ordenar los contenedores empaquetados en el pallet correcto después de que hayan estado en una estación de empaquetado. También puede crear una jerarquía de empaquetado.

Esta funcionalidad le permite crear pallets a partir de contenedores que se empaquetan a través de la funcionalidad de embalaje. El contenedor no se envía a la ubicación de envío final, ya que está en el flujo de embalaje original. Por el contrario, los empleados pueden cerrar el contenedor y moverlo a una ubicación de tipo de ordenación. Luego pueden ordenar los contenedores por posiciones, cada uno de los cuales tiene una matrícula (LP). Una vez que se han ordenado los contenedores, se puede crear un trabajo para enviar toda la matrícula al muelle de envío final o a las ubicaciones del escenario, según las directivas de ubicación o sus propios requisitos. Además, la acción de cerrar la posición de ordenación permite mover inmediatamente el inventario a la ubicación de envío final y seleccionarlo para el pedido.

## <a name="turn-on-the-outbound-sorting-feature"></a>Active la característica de ordenación de salida

Antes de poder usar la característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Ordenación de salida*

## <a name="setup"></a>Configurar

En este escenario, debe usar los datos de demostración **USMF** estándar y el almacén *62*. También debe completar la configuración que se describe en las siguientes subsecciones.

### <a name="set-up-a-wave-template"></a>Configurar una plantilla de oleada

Esta configuración procesa automáticamente la oleada y crear el trabajo cuando una línea se libera al almacén.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En la lista de plantillas, seleccione **Almacén 62**.
1. En la ficha desplegable **General**, asegúrese de que la opción **Procesar oleada para su liberación al almacén** está establecida en *Sí*.

### <a name="set-up-a-worker"></a>Configuración de un empleado

La estación de empaquetado se considera una ubicación. Los empleados del almacén que inician sesión en la estación de empaquetado solo ven y trabajan en envíos y contenedores que están planificados en ese lugar de empaquetado específico. Un usuario que inicia sesión en Microsoft Dynamics 365 debe configurarse como empleado en la gestión de almacenes. Si el nombre del usuario no aparece en la lista de usuarios del trabajo, utilice el siguiente procedimiento para agregarlo.

> [!NOTE]
> Estos pasos asumen que el usuario ya existe en el sistema y se ha asociado como empleado o trabajador en el módulo **Recursos humanos**.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. Seleccione **Nuevo**.
1. En el campo **Empleado**, seleccione el usuario de destino en la lista de empleados.
1. Seleccione **Seleccionar**.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Usuarios**, seleccione **Nuevo** para crear una cuenta de dispositivo móvil y establezca los siguientes valores para ella:

    - **Id. de usuario:** introduzca un id. exclusivo.
    - **Nombre de usuario:** introduzca un nombre para el Id.
    - **Almacén predeterminado:** *62*
    - **Nombre del menú:** *Principal*

1. En el panel Acciones, seleccione **Guardar**.
1. Aparece el cuadro de diálogo **Establecer contraseña** donde puede crear una contraseña sencilla que el usuario puede usar para iniciar sesión en la aplicación móvil. Establezca los valores siguientes:

    - **Contraseña:** introduzca una contraseña sencilla.
    - **Confirmar contraseña:** introduzca de nuevo la misma contraseña.

1. Seleccione **Establecer contraseña**.

    Una notificación en el Centro de acciones le informa de que la contraseña se ha establecido para el usuario creado.

### <a name="create-a-location-type"></a>Crear tipo de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Tipos de ubicación**.
1. En el panel de acciones, seleccione **Nuevo** para crear un tipo de ubicación y establecer los siguientes valores para él:

    - **Tipo de ubicación:** *ORDENAR*
    - **Descripción:** *Ordenar*

1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-warehouse-management-parameters"></a>Configurar parámetros de gestión de almacenes

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en la ficha desplegable **Tipos de ubicación**, establezca el campo **Tipo de ubicación de ordenación** en *ORDENAR*.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-a-location-profile"></a>Configurar un perfil de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Id. de perfil de ubicación:** *Ordenación*
    - **Nombre:** *Ordenación*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Formato de ubicación:** *ASRB* (pasillo, estantería, balda y hueco)
    - **Tipo de ubicación:** *ORDENAR*
    - **Usar seguimiento de matrículas de entidad de almacén:** *Sí*
    - **Permitir artículos combinados:** *Sí* (Cuando configura esta opción en *Sí*, la opción **Permitir lotes de inventario mixtos** se configura automáticamente en *Sí* y no se puede cambiar de forma independiente).

1. Seleccione **Guardar**.

### <a name="set-up-a-location"></a>Configurar una ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. En el encabezado, borre la casilla **Generar dígitos de control para la ubicación**.
1. En el panel de acciones, seleccione **Nuevo** para crear una ubicación y establecer los siguientes valores para él:

    - **Almacén**: *62*
    - **Ubicación:** *SORT*
    - **Id. de perfil de ubicación:** *ORDENACIÓN*

1. Seleccione **Guardar**.

### <a name="set-up-an-outbound-sorting-template"></a>Configurar una plantilla de ordenación de salida

La plantilla de ordenación de salida determina si el trabajo se crea fuera de la ubicación de ordenación y si la ordenación se realiza de forma manual o automática.

En este escenario, creará una plantilla de ordenación de salida para crear pallets después de la estación de empaquetado.

1. Vaya a **Gestión de almacenes \> Configuración \> Embalado \> Plantillas de ordenación salientes**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el encabezado de la nueva plantilla, establezca los siguientes valores:

    - **Id. de plantilla de ordenación de salida:** *AutoWork*
    - **Descripción:** *Creación de AutoWork*
    - **Tipo de plantilla de ordenación de salida:** *Contenedor*
    - **Almacén**: *62*
    - **Ubicación:** *SORT*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Comprobación del orden:** *Escaneo de posición*.
    - **Crear trabajo en posición cerrada:** *Sí*

        Si la opción se establece en *Sí*, cuando la posición se cierre, se creará el trabajo para mover el inventario a la ubicación de envío final. Si se establece en *No*, el inventario se seleccionará inmediatamente para el pedido cuando se cierre la posición.

    - **Asignación de posición:** *Automática*

        Si este campo se establece en *Manual*, el usuario debe indicar siempre en qué posición se debe ordenar el inventario. Si este campo se establece en *Automático*, el sistema automáticamente dirigirá el inventario a una posición cuando sea posible, en función de los descansos de la plantilla de ordenación.

1. Seleccione **Guardar** para hacer que el botón **Editar consulta** esté disponible en el panel de acciones.
1. En el panel de acciones, seleccione **Editar consulta**.
1. En el cuadro editor de consultas, en la pestaña **Ordenación**, seleccione una línea que tenga los siguientes valores:

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Servicio de transportista*

        Al seleccionar este valor, puede que reciba el siguiente mensaje: "El campo Servicio de transportista no es un campo de índice. ¿Desea agregar una ordenación a esto?" Seleccione **Sí**.

    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar**.
1. Es posible que reciba el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?" Seleccione **Sí**.

    El botón **Descansos de la plantilla de ordenación de salida** del panel de acciones estará disponible.

1. En el panel de acciones, seleccione **Descansos de la plantilla de ordenación de salida**.
1. En el cuadro de diálogo **Criterios de ordenación de salida**, establezca los siguientes valores:

    - **Nombre de la tabla de referencia:** *Envíos*
    - **Nombre del campo de referencia:** *Servicio de transportista*
    - **Agrupar por campo**: seleccione esta casilla para agrupar los envíos por servicio de transportista.

1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.

### <a name="set-up-container-packing-policies"></a>Configurar políticas de embalaje de contenedores

1. Vaya a **Administración de almacenes \> Configurar \> Contenedores \> Perfiles de cierre de contenedor**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el encabezado de la nueva política, establezca los siguientes valores:

    - **Directiva de embalaje de contenedores:** *Ordenar*
    - **Descripción:** *Ordenar*

1. En la ficha desplegable **Visión general**, establezca los valores siguientes:

    - **Almacén**: *62*
    - **Ubicación predeterminada para ordenación:** *ORDENAR*
    - **Unidad de peso:** *kg*
    - **Directiva de cierre del contenedor:** *Liberación automática*
    - **Directiva de lanzamiento de contenedores:** *Asignar contenedor a la posición de ordenación de salida*

1. Seleccione **Guardar**.

### <a name="set-up-packing-profiles"></a>Configurar perfiles de embalaje

Cree un nuevo perfil de embalaje que se usará junto con la funcionalidad de ordenación.

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.
1. En el panel de acciones, seleccione **Nuevo** para crear una línea y establecer los siguientes valores para él:

    - **Id. de perfil de empaquetado:** *Ordenar*
    - **Descripción:** *Ordenar*
    - **Directiva de embalaje de contenedores:** *Ordenar*
    - **Modo del id. de contenedor:** *Automático*
    - **Tipo de contenedor:** *Caja grande*
    - **Crear contenedor automáticamente al cerrar el contenedor:** Desactivado (= *No*)

1. Seleccione **Guardar**.

### <a name="set-up-work-classes"></a>Configurar de clases de trabajo

Configure una clase de trabajo que se usará junto con la ordenación.

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. En el panel de acciones, seleccione **Nuevo** para crear una clase de trabajo para la ordenación y establecer los siguientes valores para él:

    - **Id. de la clase de trabajo:** *Ordenar*
    - **Descripción:** *Ordenar*
    - **Tipo de orden de trabajo:** *Selección de inventario ordenado*

1. Seleccione **Guardar**.

### <a name="set-up-mobile-device-menu-items"></a>Configurar elementos de menú del dispositivo móvil

#### <a name="set-up-a-new-pallet-menu-item"></a>Configurar un nuevo elemento de menú de pallet

Cree un elemento de menú del dispositivo móvil para crear pallets durante la ordenación.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento del menú:** *Crear pallet*
    - **Título:** *Crear pallet*
    - **Modo:** *Indirecto*
    - **Usar trabajo existente:** *No*

1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Código de actividad:** *Ordenación de salida*

        Cuando este campo se establece en *Ordenación de salida*, aparece el campo **Id. de plantilla de ordenación de salida**.

    - **Usar guía de proceso:** *Sí*

        Cuando el campo **Código de actividad** se establece en *Ordenación de salida*, esta opción se establece automáticamente en *Sí*.

    - **Id. de plantilla de ordenación de salida:** *AutoWork*

1. Seleccione **Guardar**.

#### <a name="set-up-a-new-loading-menu-item"></a>Configurar un nuevo elemento de menú de carga

A continuación, cree un elemento de menú que permita a los usuarios mover los elementos de inventario ordenados a la ubicación de envío.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Nombre del elemento del menú:** *Cargar desde ordenación*
    - **Título:** *Cargar desde ordenación*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*

1. En la ficha desplegable **General**, establezca el campo **Dirigido por** en *Dirigido por el usuario*.
1. En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo** y luego establezca los valores siguientes:

    - **Id. de la clase de trabajo:** *ORDENAR*
    - **Tipo de orden de trabajo:** *Selección de inventario ordenado*

1. Seleccione **Guardar**.

### <a name="set-up-the-mobile-device-menu"></a>Configurar el menú de dispositivo móvil

Ahora debe agregar los nuevos elementos del menú al menú del dispositivo móvil.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. Seleccione el menú **Saliente**.
1. En el panel Acciones, seleccione **Editar**.
1. En la columna **Menús disponibles y elementos de menú**, busque y seleccione **Crear pallet**.
1. Seleccione el botón de flecha derecha para mover **Crear pallet** a la columna **Estructura del menú**.
1. Use los botones de flecha arriba y flecha abajo para poner el elemento del menú **Crear pallet** en la posición deseada del menú del dispositivo móvil.
1. Seleccione **Guardar**.
1. Repita este procedimiento para agregar el elemento del menú **Cargar desde ordenación** al menú **Salida**.

### <a name="set-up-location-directives"></a>Configurar directivas de ubicación

Las *directivas de ubicación* son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Ahora debe crear una regla para administrar el trabajo de ordenación.

#### <a name="set-up-a-single-sku-directive"></a>Configurar una directiva SKU única

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Secuencia**: *1*
    - **Nombre:** *Baydoor*

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes:

    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *6*
    - **Almacén**: *62*
    - **Varios SKU:** *No*

1. Seleccione **Guardar** para tener disponible la barra de herramientas en la ficha desplegable **Líneas**.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea. Acepte los valores predeterminados del resto de campos.

    - **Secuencia**: *1*
    - **De:** *0*
    - **A:** *1 000 000*

1. Seleccione **Guardar** para tener disponible la barra de herramientas de la ficha desplegable **Acciones directivas de ubicación**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea. Acepte los valores predeterminados del resto de campos.

    - **Secuencia**: *1*
    - **Nombre:** *Baydoor*

1. Seleccione **Guardar**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En el editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*. Seleccione el campo **Criterios** en esta fila para *Baydoor*.
1. Seleccione **Aceptar** para guardar los ajustes y cerrar el editor de consultas.

#### <a name="set-up-a-multiple-sku-directive"></a>Configurar varias directivas SKU

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.
1. En el panel de acciones, haga clic en **Nueva**.
1. Establezca los siguientes valores en el encabezado:

    - **Secuencia**: *2*
    - **Nombre:** *Baydoor Multi*

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes:

    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *6*
    - **Almacén**: *62*
    - **SKU múltiple:** *Sí*

1. Seleccione **Guardar** para tener disponible la barra de herramientas en la ficha desplegable **Líneas**.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea. Acepte los valores predeterminados del resto de campos.

    - **Secuencia**: *1*
    - **De:** *0*
    - **A:** *1 000 000*

1. Seleccione **Guardar** para tener disponible la barra de herramientas de la ficha desplegable **Acciones directivas de ubicación**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea. Acepte los valores predeterminados del resto de campos.

    - **Secuencia**: *1*
    - **Nombre:** *Baydoor Multi*

1. Seleccione **Guardar**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En el editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*. Seleccione el campo **Criterios** en esta fila para *Baydoor*.
1. Seleccione **Aceptar** para guardar los ajustes y cerrar el editor de consultas.

### <a name="set-up-work-templates"></a>Configurar plantillas de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.
1. En el panel de acciones, seleccione **Nuevo** para crear una plantilla de trabajo.
1. En la pestaña **Visión general**, establezca los valores siguientes:

    - **Secuencia**: *1*
    - **Plantilla de trabajo:** *Ordenar*
    - **Descripción de plantilla de trabajo:** *Ordenar*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Detalles de plantilla de trabajo**.
1. En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una línea y luego establecer los siguientes valores en ella:

    - **Tipo de trabajo**: *Recoger*
    - **Id. de la clase de trabajo:** *ORDENAR*

1. Seleccione de nuevo **Nuevo** para agregar una segunda línea y establezca los valores siguientes:

    - **Tipo de trabajo**: *Ubicar*
    - **Id. de la clase de trabajo:** *ORDENAR*

1. Seleccione **Guardar**.

## <a name="scenario"></a>Situación

Este escenario simula una situación en la que los contenedores empaquetados deben ordenarse automáticamente en diferentes posiciones (pallets) después de la estación de embalaje, dependiendo del servicio del transportista. Una vez que todos los artículos de la carga se hayan empaquetado y ordenado por dirección, los pallets se moverán a la compuerta.

### <a name="create-sales-orders-and-picking-work"></a>Crear pedidos de ventas y trabajos de selección

#### <a name="create-sales-order-1"></a>Crear pedido de ventas 1

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-005*
    - **Almacén**: *62*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

    Se abre el nuevo pedido de ventas.

1. Cambie a la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:

    - **Transportista de envío:** *Carga aérea*
    - **Servicio de transportista:** *Aire*

1. Cambie a la vista **Líneas**.
1. Si no se agrega automáticamente una línea nueva vacía a la cuadrícula en la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para agregar una.
1. En la nueva línea de pedido, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *2*

1. Con la nueva línea de pedido seleccionada en la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario** sobre la cuadrícula seleccione **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido. Anote los números del id. de la oleada y de id. del envío.

#### <a name="sales-order-2"></a>Pedido de ventas 2

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-006*
    - **Almacén**: *62*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**. En esta línea de pedido, establezca los siguientes valores:

    - **Artículo**: *A0001*
    - **Cantidad:** *1*

1. Sobre la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, configure el campo **Modo de entrega** en *Flowe-STD*.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Agregar línea** y luego establezca los valores siguientes en la segunda línea.

    - **Artículo**: *A0002*
    - **Cantidad:** *1*

1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, cambie el valor de **Modo de entrega** a *Air C-Air*.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione la primera línea. A continuación, en el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione la segunda línea. A continuación, en el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido. Observe que se han creado dos números de Id. de oleada y dos números de Id. de envío, uno para cada modo de entrega para las líneas de pedido de ventas.

#### <a name="get-the-work-ids-from-the-work-details"></a>Obtenga los Id. de trabajo de los detalles del trabajo

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. La página muestra los Id. de trabajo que se han creado a partir de pedidos de ventas. Utilice los Id. de oleada y los Id. de envío de los pedidos de ventas que creó para encontrar el Id. de trabajo de cada oleada y envío. Tome nota de esos Id. de trabajo, ya que los necesitará en los próximos pasos. Observe que se han creado dos Id. de trabajo para el segundo pedido de ventas. Si se seleccionan diferentes artículos de diferentes ubicaciones, se generan Id. con palabras separadas.

### <a name="pick-items-for-the-sales-orders"></a>Seleccionar artículos para los pedidos de ventas

Complete el trabajo creado utilizando el dispositivo móvil para mover los elementos a la estación de embalaje.

1. En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Selección de ventas**.
1. En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 1.
1. Seleccione **Aceptar**.
1. En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino que se creó para el pedido de ventas 1. Observe que aparecen la ubicación de picking (*bulk-001*), articulo (*A0001*) y cantidad (*2 piezas*).
1. Seleccione **Aceptar**.
1. Revise la información en la página **Órdenes de venta: Colocar**. El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.
1. Seleccione **Aceptar**.

    En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado", que indica que el id. de trabajo del pedido de ventas 1 se ha completado.

    Ahora seleccionará el pedido de ventas 2.

1. En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 2, donde la línea 1 tiene el artículo *A0001*.
1. Seleccione **Aceptar**.
1. En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino. Observe que aparecen la ubicación de picking (*bulk-001*), articulo (*A0001*) y cantidad (*1 piezas*).
1. Seleccione **Aceptar**.
1. Revise la información en la página **Órdenes de venta: Colocar**. El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.
1. Seleccione **Aceptar**.

    En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado". Este mensaje indica que el id. de trabajo de la línea 1 del pedido de ventas 2 se ha completado.

1. En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 2, donde la línea 2 tiene el artículo *A0002*.
1. Seleccione **Aceptar**.
1. En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino. Observe que aparecen la ubicación de picking (*bulk-002*), articulo (*A0001*) y cantidad (*1 piezas*).
1. Seleccione **Aceptar**.
1. Revise la información en la página **Órdenes de venta: Colocar**. El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.
1. Seleccione **Aceptar**.

    En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado". Este mensaje indica que el id. de trabajo de la línea 2 del pedido de ventas 2 se ha completado.

### <a name="pack-sales-orders-into-containers"></a>Embalaje de pedidos de venta en contenedores

#### <a name="pack-sales-order-1-into-containers"></a>Embalaje de pedido de venta 1 en contenedores

1. Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Paquete**.

    Aparece el cuadro de diálogo **Seleccionar estación de embalaje**. De manera predeterminada, el campo **Trabajador** debe establecerse con el nombre del trabajador que configuró anteriormente.

1. Establezca los siguientes valores para ver y trabajar en envíos y contenedores que están planificados en la ubicación de embalaje específica:

    - **Sitio**: *6*
    - **Almacén**: *62*
    - **Ubicación:** *Paquete*
    - **Id. de perfil de empaquetado:** *Ordenar*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En la página **Paquete**, en el campo **Matrícula o envío**, introduzca la matrícula de destino para el pedido de venta 1. Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.
1. En el panel de acciones, seleccione **Nuevo contenedor**.
1. Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**. Anote el id. de contenedor.
1. En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:

    - **Cantidad:** *1*
    - **Identificador:** Articulo *A0001*

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.
1. Seleccione **Aceptar**. El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.
1. Cree un segundo contenedor para agregar el segundo artículo de la matrícula para el pedido de ventas 1 a un nuevo contenedor.
1. En el panel de acciones, seleccione **Nuevo contenedor**.
1. Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**. Anote el id. de contenedor.
1. En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:

    - **Cantidad:** *1*
    - **Identificador:** Articulo *A0001*

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.
1. Seleccione **Aceptar**. El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.

#### <a name="pack-sales-order-2-into-containers"></a>Embalaje de pedido de venta 2 en contenedores

1. En la página **Paquete**, en el campo **Matrícula o envío**, introduzca la matrícula de destino para la línea 1 del pedido de venta 2. Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.
1. En el panel de acciones, seleccione **Nuevo contenedor**.
1. Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**. Anote el id. de contenedor.
1. En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:

    - **Cantidad:** *1*
    - **Identificador:** Articulo *A0001*

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.
1. Seleccione **Aceptar**. El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.
1. En el campo **Matrícula o envío**, introduzca la matrícula de destino para la línea 2 del pedido de venta 2. Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.
1. En el panel de acciones, seleccione **Nuevo contenedor**.
1. Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**. Anote el id. de contenedor.
1. En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:

    - **Cantidad:** *1*
    - **Campo identificador:** Artículo *A0002*

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.
1. Seleccione **Aceptar**. El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.

Para ver los detalles del contenedor, vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Contenedores** y busque los Id. de contenedores que se crearon durante el embalaje.

### <a name="sort-the-containers"></a>Ordenar los contenedores

> [!IMPORTANT]
> Cuando acceda al elemento de menú **Crear pallet** en la aplicación móvil para hacer la ordenación de salida, verá un botón que está etiquetado como **Completo**. *No use el botón **Completo** para ordenar o cerrar la posición.*
>
> El botón **Completo** se proporciona de manera predeterminada y no se puede deshabilitar ni eliminar de la página. No se usa para la característica *Ordenación de salida*.

#### <a name="sort-the-first-container"></a>Ordenar el primer contenedor

1. En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Crear pallet**.
1. En el campo **Matrícula de entidad de almacén/Con**, introduzca el primer Id. de contenedor asociado con el pedido de ventas 1.
1. Seleccione **Aceptar**.
1. Como actualmente no existen posiciones de ordenación, debe especificar una. En el campo **Id. de posición de ordenación**, escriba *SP01*.
1. Como actualmente no hay matrículas asociadas a la posición de ordenación *SP01*, debe especificar una. En el campo **Matrícula**, introduzca *PLP01*.
1. Seleccione **Aceptar**.
1. Como la validación de posición de ordenación está activada, debe introducir nuevamente el id. de posición de ordenación. En el campo **Id. de posición de ordenación**, escriba *SP01*.
1. Seleccione **Aceptar**.

    Recibe un mensaje "Trabajo completado".

> [!TIP]
> Para ver la posición de ordenación y la matrícula que contiene, vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.
>
> La pagina **Asignaciones de posición de ordenación de salida** muestra todas las posiciones de ordenación que están activas actualmente. Los campos **Ordenar posición de transacciones** muestran la matrícula asociada con cada posición de ordenación y los contenedores que están en la posición de ordenación. Observe que actualmente existe una posición de ordenación y que la ficha desplegable **Criterios de posición de ordenación** muestra un criterio de **Envío - Servicio de transportista - Air**.

#### <a name="sort-the-remaining-containers"></a>Ordenar los contenedores restantes

1. En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Crear pallet**.
1. En el campo **Matrícula de entidad de almacén/Con**, introduzca el segundo Id. de contenedor asociado con el pedido de ventas 1.
1. Seleccione **Aceptar**. Como la plantilla de ordenación está configurada para ordenar automáticamente, y ya existe una posición de ordenación que tiene criterios coincidentes, se le dirige automáticamente a la posición de ordenación correcta.
1. Seleccione **Aceptar**.
1. Confirme el Id. de posición de ordenación para indicar que el inventario está en el lugar correcto. En el campo **Id. de posición de ordenación**, escriba *SP01*.
1. Seleccione **Aceptar**.

    El trabajo se completa en el segundo contenedor del pedido de venta 1. Ahora ordenará los contenedores restantes del pedido de venta 2.

1. En el campo **Matrícula de entidad de almacén/Con**, introduzca el Id. del contenedor del contenedor del pedido de venta 2 que contiene el artículo *A0001*. Como el servicio de transportista es diferente, se le solicita que introduzca una nueva posición de ordenación y asigne una matrícula a esa posición. Usar posición de ordenación *SP02* y la matrícula *PLP02*.
1. Seleccione **Aceptar**.
1. Confirme la posición de ordenación introduciendo *SP02* en el campo **Id. de posición de ordenación**.
1. Seleccione **Aceptar**.

    El trabajo se completa en el contenedor.

1. En el campo **Matrícula de entidad de almacén/Con**, introduzca el Id. del contenedor restante del pedido de venta 2 que contiene el artículo *A0002*. Como el servicio de transportista es el mismo que el servicio de transportista del pedido de venta 1, el sistema muestra la posición de ordenación existente que tiene criterios coincidentes.
1. Seleccione **Aceptar**.
1. Confirme la posición de ordenación introduciendo *SP01* en el campo **Id. de posición de ordenación**.
1. Seleccione **Aceptar**.

    El trabajo se completa en el contenedor.

### <a name="close-the-outbound-sorting-positions"></a>Cerrar las posiciones de ordenación de salida

Cuando se haya ordenado todo el inventario, la posición debe cerrarse para poder crear el trabajo. El trabajo de selección de inventario ordenado se creará para llevar el inventario a compuerta.

#### <a name="close-a-position-from-the-mobile-device"></a>Cerrar una posición desde el dispositivo móvil

1. En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Crear pallet**.
1. En el campo **Matrícula de entidad de almacén/Con**, introduzca un Id. de contenedor que se haya ordenado a la posición de ordenación *SP01*.
1. Seleccione **Aceptar**.
1. Recibirá el siguiente mensaje: "El contenedor ya está ordenado en la posición SP01. ¿Desea cerrar la posición?" Seleccione **Cerrar**.

    El trabajo se completó.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Cerrar una posición de las asignaciones de posición de ordenación de salida

1. Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.
1. En la columna izquierda, seleccione **SP02**. Esta fila de posición de ordenación de salida es la que cerrará.
1. En el panel de acciones, seleccione **Cerrar posición**. El registro de posición de ordenación está cerrado y ya no se muestra.

    > [!TIP]
    > Para mostrar todos los registros de posición cerradlos, seleccione la casilla de verificación **Mostrar cerrados**.

### <a name="sorted-inventory-picking"></a>Picking de inventario ordenado

Debe completar el trabajo de selección de inventario ordenado. Cuando se complete, el inventario se seleccionará para el pedido de ventas. En ese punto, se aplican todos los demás procesos de almacén.

1. En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Cargar desde ordenación**.
1. Introduzca el id. de matrícula de destino de la primera posición de ordenación, *SP01*. Establezca el campo **Id.** en *PLP01*.
1. Seleccione **Aceptar**.
1. La página **Selección de inventario ordenado: selección** muestra el trabajo de selección que debe realizarse. Seleccione la ubicación *ORDENAR* y la matrícula de destino *PLP01*, que tiene varios artículos y una cantidad de *3*.
1. Seleccione **Aceptar**.
1. La página **Selección de inventario ordenado: colocación** muestra el trabajo de colocación que debe realizarse. Realice la colocación en la ubicación *Baydoor* y la matrícula de destino *PLP01*, que tiene varios artículos y una cantidad de *3*.
1. Seleccione **Aceptar**.

    El trabajo se completó.

1. Introduzca el id. de matrícula de destino de la segunda posición de ordenación, *SP02*. Establezca el campo **Id.** en *PLP02*.
1. Seleccione **Aceptar**.
1. La página **Selección de inventario ordenado: selección** muestra el trabajo de selección que debe realizarse. Seleccione la ubicación *ORDENAR* y la matrícula de destino *PLP02*, que tiene varios artículos y una cantidad de *1*.
1. Seleccione **Aceptar**.
1. La página **Selección de inventario ordenado: colocación** muestra el trabajo de colocación que debe realizarse. Realice la colocación en la ubicación *Baydoor* y la matrícula de destino *PLP02*, que tiene varios artículos y una cantidad de *1*.
1. Seleccione **Aceptar**.

    El trabajo se completó.

A partir de ese punto, se aplican todos los demás procesos de almacén.
