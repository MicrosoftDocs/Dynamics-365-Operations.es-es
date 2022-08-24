---
title: Agrupación de plantillas de oleada
description: La agrupación de plantillas de oleada permite que el sistema utilice configuraciones de plantilla de oleada para determinar, según los criterios que defina, cómo debe dividir las líneas liberadas y asignarlas a oleadas nuevas o existentes. Esta característica puede ser útil en almacenes en los que se crean oleadas según determinados criterios, pero donde los administradores prefieren crear oleadas automáticamente en lugar de hacerlo manualmente.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0f0419f1a109f043cb1af6a575704c24420639f1
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218926"
---
# <a name="wave-template-grouping"></a>Agrupación de plantillas de oleada

[!include [banner](../includes/banner.md)]

La agrupación de plantillas de oleada permite que el sistema utilice configuraciones de [plantilla de oleada](tasks/configure-wave-processing.md) para determinar, según los criterios que defina, cómo debe dividir las líneas liberadas y asignarlas a oleadas nuevas o existentes. Esta característica puede ser útil en almacenes en los que se crean oleadas según determinados criterios, pero donde los administradores prefieren crear oleadas automáticamente en lugar de hacerlo manualmente. Permite que el sistema agregue cada envío recién liberado a la primera oleada que encuentre que tenga valores de campo de agrupación coincidentes. Si no se encuentra ninguna coincidencia, el sistema crea una nueva oleada para el nuevo envío.

> [!IMPORTANT]
> La agrupación de plantillas de oleada no es compatible con los tipos de trabajo *picking de materia prima de producción* o *picking de kanban*. Esto se debe a que la agrupación de oleadas se basa en envíos y estos tipos de trabajo no utilizan envíos.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Activar la característica Agrupación de plantillas de oleada

Antes de poder usar la característica *Agrupación de plantillas de oleada*, esta debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica**: *Agrupación de plantillas de oleada*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Establecer una plantilla de oleada para usar una agrupación de plantillas de oleada

Para que la agrupación de plantillas de oleada esté disponible, siga estos pasos para configurar su [plantilla de oleada](tasks/configure-wave-processing.md).

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel izquierdo, seleccione la plantilla de oleada que desea configurar. Si se está preparando para trabajar en el escenario que aparece más adelante en este artículo utilizando datos de demostración, seleccione la plantilla **62 Envío predeterminado**.
1. Seleccione **Editar** para poner la página en modo de edición.
1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Automatizar la creación de oleadas:** *Sí*
    - **Asignar a oleadas abiertas:** *Sí*
    - **Procesar oleada para su liberación al almacén:** *No*

1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo de consulta.
1. En el cuadro de diálogo de consulta, en la pestaña **Ordenación**, revise los criterios de ordenación y asegúrese de que haya una regla que incluya el campo que desea usar para agrupar sus oleadas.

    Si se está preparando para trabajar en el escenario utilizando datos de demostración, agregue una fila que tenga los siguientes valores:

    - **Tabla:** *Envíos*
    - **Tabla derivada:** *Envíos*
    - **Campo:** *Servicio de transportista*

        > [!NOTE]
        > Después de seleccionar este valor, puede que reciba el siguiente mensaje: "El campo Servicio de transportista no es un campo de índice. ¿Desea agregar una ordenación a esto?" Seleccione **Sí** para agregar una ordenación.

    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para guardar sus cambios y cerrar el cuadro de diálogo de consulta.
1. En el panel de acciones, seleccione **Agrupación de plantillas de oleada**.
1. En la página **Agrupación de plantillas de oleada**, seleccione la casilla **Agrupar por** para cada fila que desee utilizar para agrupar sus líneas de pedido en oleadas, según sea necesario. Si se está preparando para trabajar en el escenario utilizando datos de demostración, seleccione la casilla **Agrupar por** para la fila *Servicio de transportista*.
1. Seleccione **Guardar**.
1. Cierre la página **Agrupación de plantillas de oleada**.
1. Seleccione **Guardar** para guardar la plantilla.

## <a name="scenario"></a>Situación

En esta sección se ofrece un script en el que puede trabajar para aprender qué hace esta característica y cómo trabajar con ella.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar este escenario como guía para usar la característica cuando trabaje en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.

### <a name="scenario-wave-template-grouping"></a>Escenario: Agrupación de plantillas de oleada

En este escenario se muestra cómo utilizar la agrupación de plantillas de oleada para crear automáticamente varias oleadas, según los criterios de agrupación que se definen en una plantilla de oleada. En este escenario, la plantilla de oleada se configura en el sistema para crear una oleada por servicio de transportista.

Antes de empezar, prepare su plantilla de oleada como se describe en la sección [Establecer una plantilla de oleada para usar una agrupación de plantillas de oleada](#set-up-template) que aparece anteriormente en este artículo. Si va a trabajar con datos de demostración para este escenario, asegúrese de utilizar los valores de datos de demostración que se sugieren en ese procedimiento. Esta configuración agrupará sus oleadas de acuerdo con el servicio de transportista que se establece para cada pedido de ventas.

#### <a name="create-sales-order-1"></a>Crear pedido de ventas 1

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-004*.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.
1. El nuevo pedido de ventas se abre en la vista **Líneas**. Anote el número del pedido de ventas.
1. Cambie a la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:

    - **Transportista de envío:** *Carga aérea*
    - **Servicio de transportista:** *Aire*

1. Vuelva a la vista **Líneas**.
1. En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *2*

1. Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido. Anote el número de id. de la oleada y los números de id. del envío.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Ver la oleada que se creó a partir del pedido de ventas 1

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione el id. de oleada que se creó a partir del pedido de ventas.
1. Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.
1. Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**.

#### <a name="create-sales-order-2"></a>Crear pedido de ventas 2

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-005*.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.
1. El nuevo pedido de ventas se abre en la vista **Líneas**. Anote el número del pedido de ventas.
1. Cambie a la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:

    - **Transportista de envío:** *Flower Moving*
    - **Servicio de transportista:** *Estándar*

1. Vuelva a la vista **Líneas**.
1. En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *1*

1. Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido. Anote el número de id. de la oleada y los números de id. del envío. Observe que el id. de oleada difiere del id. de oleada del primer pedido de ventas.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Ver la oleada que se creó a partir del pedido de ventas 2

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione el id. de oleada que se creó a partir del segundo pedido de ventas.
1. Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.
1. Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**.

Se creó una nueva oleada para este envío, ya que utiliza un servicio de transportista diferente al primer pedido de ventas.

#### <a name="create-sales-order-3"></a>Crear pedido de ventas 3

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-006*.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.
1. El nuevo pedido de ventas se abre en la vista **Líneas**. Anote el número del pedido de ventas.
1. Cambie a la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:

    - **Transportista de envío:** *Air Cargo*
    - **Servicio de transportista:** *Aire*

1. Vuelva a la vista **Líneas**.
1. En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *1*

1. Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.
1. Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido. Anote el número de id. de la oleada y los números de id. del envío. El envío se ha asignado a la oleada existente desde el primer pedido de ventas.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Ver la oleada para pedidos de ventas 1 y 3

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione el id. de oleada que se creó a partir del tercer pedido de ventas.
1. Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.
1. Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**, junto con el envío para el primer pedido de ventas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]