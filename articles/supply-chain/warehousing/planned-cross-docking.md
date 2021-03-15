---
title: Tránsito directo planificado
description: Este tema describe la planificación avanzada del tránsito directo, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta. Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: fb598b3ac7dd72e8c500f0c2eaf07462009c67f7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970315"
---
# <a name="planned-cross-docking"></a>Tránsito directo planificado

[!include [banner](../includes/banner.md)]

Este tema describe la planificación avanzada del tránsito directo. El tránsito directo es un proceso de almacén, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta. Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.

El tránsito directo permite a los trabajadores omitir la recogida entrante y la selección saliente del inventario que ya está marcado para un pedido saliente. Por lo tanto, el número de veces que se toca el inventario se minimiza, siempre que sea posible. Además, debido a que hay menos interacción con el sistema, se incrementan los ahorros de tiempo y espacio en el piso del almacén.

Antes de que se pueda ejecutar el tránsito directo, el usuario debe configurar una nueva plantilla de tránsito directo, donde se especifique la fuente de suministro y otros conjuntos de requisitos para el tránsito directo. A medida que se crea la orden de salida, la línea debe marcarse contra una orden de entrada que contiene el mismo artículo.

En el momento de la recepción de la orden entrante, la configuración de tránsito directo identifica automáticamente la necesidad de tránsito directo y crea el trabajo de movimiento para la cantidad requerida, en función de la configuración de la directiva de ubicación.

> [!NOTE]
> Las transacciones de inventario son **no** sin registrar cuando se cancela el trabajo de tránsito directo, incluso si la configuración de esta capacidad está activada en los parámetros de gestión de Almacén.

## <a name="turn-on-the-planned-cross-docking-feature"></a>Active la función de tránsito directo planificado

Antes de que pueda usar la planificación avanzada de tránsito directo, debe activar la función en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Tránsito directo planificado*

## <a name="setup"></a>Configurar

### <a name="regenerate-load-posting-methods"></a>Regenerar métodos de registro de carga

El tránsito directo planificado se implementa como un método de registro de carga. Después de activar la función, debe volver a generar los métodos.

1. Vaya a **Administración de almacenes \> Configuración \> Métodos de registro de carga**.
1. En el panel acciones, seleccione **Regenerar métodos**.

    Cuando se completa la regeneración, debería ver un método que tiene un **Nombre del método** con el valor de *planCrossDocking*.

1. Cierre la página.

### <a name="create-a-cross-docking-template"></a>Cree una plantilla de tránsito directo

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Plantillas de tránsito directo**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear una plantilla.
1. Establezca los siguientes valores en el encabezado:

    - **Secuencia**: *1*

        Este campo define el orden en que se evalúan las plantillas.

    - **Identificación de plantilla de tránsito directo:** *51*
    - **Descripción:** *Almacén 51*
    - **Directiva de liberación de demanda:** *Antes del recibo de suministro*
    - **Almacén**: *51*

1. La configuración en la ficha desplegable **Planificación** controla cómo funciona la plantilla. Establezca los valores siguientes:

    - **Requisitos de demanda:** *Ninguno*

        Este campo define los requisitos del inventario de demanda. Si la demanda debe estar vinculada a la oferta antes del lanzamiento, seleccione *Calificación*. Si la demanda debe reservarse para el pedido antes del lanzamiento, seleccione *Reserva de pedidos*.

    - **Tipo de ubicación:** *Ubicaciones de envío*

        Este campo define si el trabajo de tránsito directo debe usar las ubicaciones de carga / preparación del envío, o si debe usar directivas de ubicación para encontrar sus propias ubicaciones de almacenamiento provisional / carga.

    - **Plantilla de trabajo**: deje este campo en blanco.

        Este campo define la plantilla de trabajo que debe usarse cuando se crea trabajo de tránsito directo.

    - **Revalidar con el recibo de suministro:** *No*

        Esta opción define si el suministro debe revalidarse durante la recepción. Si esta opción está establecida en *Sí*, se verifican tanto la ventana de tiempo máximo como el rango de días de vencimiento.

    - **Validar ventana de tiempo:** *Sí*

        Esta opción define si se debe evaluar la ventana de tiempo máximo cuando se selecciona una fuente de suministro. Si esta opción está establecida en *Sí*, los campos relacionados con las ventanas de tiempo máximo y mínimo están disponibles.

    - **Ventana de tiempo máxima:** *5*

        Este campo define el período máximo permitido entre la llegada del suministro y la salida de demanda.

    - **Unidad de ventana de tiempo máximo:** *Días*
    - **Ventana de tiempo mínima:** *0*

        Este campo define el período mínimo permitido entre la llegada del suministro y la salida de demanda.

    - **Unidad de ventana de tiempo mínimo:** *Días*
    - **Intervalo de días de caducidad:** *0*

        *Criterios de primera caducidad, primera salida (FEFO):* este campo define el número máximo de días entre la fecha de vencimiento del primer lote que está actualmente en el almacén y el lote que se está recibiendo.

1. En la ficha desplegable **Fuentes de suministro**, especifique los tipos de suministro que son válidos para esta plantilla. Seleccione **Nuevo** y establezca los valores siguientes:

    - **Número de secuencia:** *1*
    - **Fuente de suministro:** *Orden de compra*

### <a name="create-a-work-class"></a>Crear una clase de trabajo

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.
1. En el Panel de acciones, seleccione **Nuevo** para crear una clase de trabajo.
1. Establezca los valores siguientes:

    - **Identificador de la clase de trabajo**: *CrossDock*
    - **Descripción:** *Tránsito directo*
    - **Tipo de orden de trabajo:** *Tránsito directo*

### <a name="create-a-work-template"></a>Crear una plantilla de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una línea a la pestaña **Resumen**.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** *1*
    - **Plantilla de trabajo:** *51 Cross Dock*
    - **Descripción de la plantilla de trabajo:** *51 Cross Dock*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Detalles de plantilla de trabajo**.
1. En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Tipo de trabajo**: *Recoger*
    - **Identificador de la clase de trabajo**: *CrossDock*

1. Seleccione **Nuevo** para agregar otra línea y establezca los siguientes valores en ella:

    - **Tipo de trabajo**: *Ubicar*
    - **Identificador de la clase de trabajo**: *CrossDock*

1. Seleccione **Guardar** y confirme que la casilla de verificación **Válido** está seleccionada para la plantilla *51 Cross Dock*.

> [!NOTE]
> Los identificadores de clase de trabajo para los tipos de trabajo *Recoger* y *Colocar* deben ser iguales.

### <a name="create-location-directives"></a>Crear directivas de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.
1. En el panel de acción, seleccione **Nuevo** y establezca los valores siguientes:

    - **Número de secuencia:** *1*
    - **Nombre:** *51 Cross Dock Colocar*
    - **Tipo de trabajo**: *Ubicar*
    - **Sitio**: *5*
    - **Almacén**: *51*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Cantidad inicial**: *1*
    - **Cantidad final**: *1000000*

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Nombre:** *Baydoor*
    - **Uso de ubicación fija:** *Ubicaciones fijas y no fijas*

1. Seleccione **Guardar** para tener disponible el botón **Editar consulta** en la barra de herramientas de **Acciones de directiva de ubicación**.
1. Seleccione **Editar consulta** para abrir el editor de consultas.
1. En la pestaña **Rango**, asegúrese de que las siguientes dos líneas estén configuradas:

    - Línea 1:

        - **Tabla**: *Ubicaciones*
        - **Tabla derivada:** *Ubicaciones*
        - **Campo:** *Almacén*
        - **Criterio:** *51*

    - Línea 2:

        - **Tabla**: *Ubicaciones*
        - **Tabla derivada:** *Ubicaciones*
        - **Campo:** *Ubicación*
        - **Criterio:** *Baydoor*

1. Seleccione **Aceptar** para cerrar el editor de consultas.

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En la lista de elementos de menú en el panel izquierdo, seleccione **Ubicación de compra**.
1. Seleccione **Editar**.
1. En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Identificador de la clase de trabajo**: *CrossDock*
    - **Tipo de orden de trabajo:** *Tránsito directo*

1. Seleccione **Guardar**.

## <a name="scenario"></a>Situación

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

Siga estos pasos para crear una orden de compra como fuente de suministro.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:

    - **Cuenta del proveedor:** *104*
    - **Almacén**: *51*

1. Seleccione **Aceptar** y anote el número de pedido.
1. Se agrega una nueva línea a la ficha desplegable **Líneas de orden de compra**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *5*

### <a name="create-a-sales-order"></a>Crear un pedido de ventas

Siga estos pasos para crear un pedido de ventas como fuente de demanda.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-002*
    - **Almacén**: *51*

1. Seleccione **Aceptar**.
1. Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *3*

### <a name="create-planned-cross-docking"></a>Crear tránsito directo planificado

Siga estos pasos para crear el tránsito directo planificado a partir del pedido de ventas.

1. En la página **Detalles del pedido de ventas** para el pedido de ventas que acaba de crear, en el Panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.

    La acción de liberación al almacén crea una línea de envío y carga para la línea de pedido de ventas e intenta asignar inventario.
    
    Recibirá un mensaje informativo. También recibirá el siguiente mensaje de advertencia: "No se creó ningún trabajo para la oleada XXXX. Consulte el registro del historial de creación de trabajo para obtener más detalles". Se espera este comportamiento, porque no hay inventario en el almacén.

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, seleccione **Detalles del envío**.

    Aparecerá la página **Detalles del envío** y muestra el envío que se creó para el pedido de ventas.

1. En la ficha desplegable **Líneas de carga**, observe que el campo **Cantidad prevista de tránsito directo** se establece en *3*. Debido a que no había inventario disponible en el almacén, pero una fuente de suministro válida llegará dentro de la ventana de tiempo definida en la plantilla de tránsito directo, se creó la cantidad de tránsito directo.
1. En la ficha desplegable **Líneas de carga**, seleccione **Tránsito directo planeado** para ver los detalles del tránsito directo que se creó.

## <a name="process-the-cross-docking"></a>Procesar el tránsito directo

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Pedido de compra recibido en la aplicación móvil del almacén

El sistema recibirá la cantidad de 5 del pedido de compra en la ubicación de recepción y creará dos partes de trabajo.

La primera identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Tránsito directo* y está vinculado al pedido de ventas. Tiene una cantidad de 3 y se dirige a la ubicación de envío final para que pueda enviarse de inmediato.

La segunda identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Pedidos de compra* y está vinculado al pedido de compra. Tiene la cantidad restante de 2 que no se cruzó y se dirige al almacenamiento.

1. Inicie sesión en el dispositivo móvil como un usuario en el almacén *51*.
1. Vaya **Entrante \> Recibir compra**.
1. En el campo **PONUM**, introduzca su número de orden de compra.
1. En el campo **Cantidad**, especifique *5*.
1. Seleccione **Aceptar**.
1. En la página siguiente, establezca el campo **Artículo** a *A0001*.
1. Seleccione **Aceptar**.
1. En la página siguiente, confirme los valores **PONUM**, **Artículo** y **Cantidad** seleccionando **Aceptar**.

    Recibe un mensaje "Trabajo completado".

1. Seleccione **Cancelar** para salir.

### <a name="put-away-to-cross-docking-and-bulk"></a>Ubicación a tránsito directo y a granel

Actualmente, ambas identificaciones de trabajo tienen la misma matrícula de entidad objetivo. Para completar los siguientes pasos, debe obtener la identificación del trabajo y la identificación de la matrícula de identidad. Puede obtener esta información de los detalles de trabajo para la línea de orden de compra y la línea de pedido de ventas. Alternativamente, puede ir a **Gestión de almacenes \> Trabajo \> Detalles del trabajo** y filtrar para el trabajo donde el valor de **Almacén** es *51*.

1. En el dispositivo móvil, vaya a **Entrante \> Ubicación de compra** e introduzca la matricula de identidad de destino del trabajo.
1. En campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino de los detalles del trabajo.

    La página de selección de tránsito directo muestra la ubicación de selección (*RECV*), matrícula de entidad objetivo (*matrícula de entidad*), artículo (*A0001*) y cantidad (*3*).

1. Seleccione **Aceptar**.
1. En el campo **LP objetivo**, introduzca una matrícula de entidad de destino para la identificación de la matrícula que debe colocarse (tránsito directo) en la ubicación de envío. Puede seleccionar cualquier identificación de matrícula de su elección.
1. Seleccione **Aceptar**.
1. En la página siguiente, en campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino.
1. Seleccione **Aceptar**.
1. Confirme el trabajo para elegir la cantidad restante de 2 y luego seleccione **Aceptar**.
1. En la página siguiente, seleccione **Hecho** para finalizar el proceso de selección y comenzar el proceso de almacenamiento.

    La aplicación móvil le presenta la ubicación y la matrícula de entidad para colocar el artículo.

1. Confirme el almacenamiento a granel **Colocar** seleccionando **Aceptar**.
1. En la página siguiente, confirme el tránsito directo **Colocar** seleccionando **Aceptar**.

    Recibe un mensaje "Trabajo completado".

1. Seleccione **Cancelar** para salir.

La siguiente ilustración muestra cómo puede aparecer el trabajo de tránsito directo completado en Microsoft Dynamics 365 Supply Chain Management.

![Trabajo de tránsito directo completado](media/PlannedCrossDockingWork.png "Trabajo de tránsito directo completado")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]