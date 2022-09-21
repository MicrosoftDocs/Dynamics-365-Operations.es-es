---
title: Configurar directivas de consolidación de envíos
description: Este artículo explica cómo configurar directivas de consolidación de envíos predeterminadas y personalizadas.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427992"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurar directivas de consolidación de envíos

[!include [banner](../includes/banner.md)]

El proceso de consolidación de envíos que utiliza directivas de consolidación de envíos permite la consolidación automatizada de envíos durante la liberación automática y manual al almacén. Después de activar esta característica, debe configurar sus directivas iniciales. Si no se configuran directivas, cada línea de ventas generará un envío separado que tiene una sola línea de carga.

Los escenarios que se presentan en este artículo muestran cómo configurar directivas de consolidación de envío predeterminadas y personalizadas.

> [!WARNING]
> Si actualiza un sistema Microsoft Dynamics 365 Supply Chain Management en el que ha estado utilizando la función de consolidación de envíos heredada, la consolidación podría dejar de funcionar como espera, a menos que siga los consejos que se brindan aquí.
>
> En las instalaciones de Supply Chain Management donde la característica *Directivas de consolidación de envíos* está desactivada, usted habilita la consolidación de envíos usando la configuración **Consolidar el envío en el momento de la entrega al almacén** para cada almacén individual. Esta función es obligatoria a partir de la versión 10.0.29. Cuando está activada, la opción **Consolidar el envío en el momento de la entrega al almacén** se oculta y la funcionalidad se reemplaza por las *directivas de consolidación de envíos* que se describen en este artículo. Cada directiva establece reglas de consolidación e incluye una consulta para controlar dónde se aplica la directiva. Cuando active la función por primera vez, no se definirán políticas de consolidación de envíos en la página **Directivas de consolidación de envíos**. Cuando no se definen políticas, el sistema utiliza el comportamiento heredado. Por tanto, cada almacén existente sigue respetando su configuración de **Consolidar el envío en el momento de la entrega al almacén**, aunque esa configuración ahora está oculta. Sin embargo, después de crear al menos una política de consolidación de envíos, la configuración **Consolidar el envío en el momento de la entrega al almacén** ya no tiene ningún efecto y la funcionalidad de consolidación está totalmente controlada por las políticas.
>
> Después de definir al menos una política de consolidación de envíos, el sistema verificará las políticas de consolidación cada vez que se libere un pedido al almacén. El sistema procesa las pólizas usando la clasificación que se define por cada el valor **Secuencia de directiva** de cada directiva. Aplica la primera directiva donde la consulta coincide con el nuevo pedido. Si ninguna consulta coincide con el pedido, cada línea de pedido generará un envío separado que tiene una sola línea de carga. Por lo tanto, como alternativa, le recomendamos que cree una directiva predeterminada que se aplique a todos los almacenes y grupos por número de pedido. Otorgue a esta política alternativa el valor más alto de **Secuencia de directiva**, para que se procese en último lugar.
>
> Para reproducir el comportamiento heredado, debe crear una política que no agrupe por número de pedido y que tenga criterios de consulta que incluyan todos los almacenes relevantes.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Active la característica Directivas de consolidación de envíos

Para usar la característica *Directivas de consolidación de envíos*, debe activarla para su sistema. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Directivas de consolidación de envíos* en el espacio de trabamo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Configurar sus directivas de consolidación iniciales

Si está trabajando con un sistema nuevo o un sistema en el que acaba de activa la característica *Directivas de consolidación de envíos* por primera vez, siga estos pasos para configurar sus directivas iniciales de consolidación de envíos.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. En el panel Acciones, seleccione **Crear configuración predeterminada** para crear las siguientes directivas:

    - Una directiva llamada *Predeterminada* para el tipo de directiva *Ordenes de venta*.
    - Una directiva llamada *Predeterminada* para el tipo de directiva *Incidencia de transferencia*.
    - Una directiva llamada *CrossOrder* para el tipo de directiva *Incidencia de transferencia*. (Esta directiva se crea solo si tenía al menos un almacén donde la configuración **Consolidar el envío en el momento de la entrega al almacén** heredada estaba habilitada).
    - Una directiva llamada *CrossOrder* para el tipo de directiva *Ordenes de venta*. (Esta directiva se crea solo si tenía al menos un almacén donde la configuración **Consolidar el envío en el momento de la entrega al almacén** heredada estaba habilitada).

    > [!NOTE]
    > - Ambas directivas *CrossOrder* consideran el mismo conjunto de campos que la lógica anterior. Sin embargo, también consideran el campo del número de orden. (Ese campo se utiliza para consolidar líneas en envíos, en función de factores como el almacén, el modo de transporte de entrega y la dirección).
    > - Ambas directivas *Predeterminada* consideran el mismo conjunto de campos que la lógica anterior. Sin embargo, también consideran el campo del número de orden. (Ese campo se utiliza para consolidar líneas en envíos, en función de factores como número de pedido, el almacén, el modo de transporte de entrega y la dirección).

1. Si el sistema genera una directiva *CrossOrder* para el tipo de directiva *Ordenes de venta*, selecciónela y luego, en el panel Acciones, seleccione **Editar consulta**. En el editor de consultas, puede ver en cuál de sus almacenes la configuración **Consolidar el envío en el momento de la entrega al almacén** estaba previamente habilitada para. Por lo tanto, esta política reproduce su configuración anterior para estos almacenes.
1. Personalice las nuevas políticas predeterminadas según sea necesario agregando o eliminando campos y/o editando las consultas. Puede también agregar tantas directivas nuevas como necesite. Para ver ejemplos que muestran cómo personalizar y configurar sus políticas, consulte el escenario de ejemplo más adelante en este artículo.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Escenario: configurar directivas de consolidación de envíos personalizadas

Este escenario proporciona un ejemplo que muestra cómo configurar políticas de consolidación de envío personalizadas y luego probarlas con datos de demostración. Las directivas personalizadas pueden admitir requisitos comerciales complejos donde la consolidación de envíos depende de varias condiciones. Para cada directiva de ejemplo que aparece más adelante en este escenario, se incluye una breve descripción del caso de negocio. Estas directivas de ejemplo deben configurarse en una secuencia que garantice una evaluación similar a una pirámide de las consultas. (En otras palabras, las directivas que tienen la mayoría de las condiciones deben ser evaluadas como de mayor prioridad).

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Este escenario hace referencia a valores y registros que se incluyen en los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar que se proporcionan para Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en *USMF* antes de empezar.

### <a name="prepare-master-data-for-this-scenario"></a>Preparar datos maestros para este escenario

Antes de poder realizar los ejercicios en este escenario, debe preparar los datos maestros necesarios para realizar el filtrado, como se describe en las subsecciones siguientes. (Estos requisitos previos también se aplican a los escenarios enumerados en la sección [Escenarios de ejemplo de cómo usar las directivas de consolidación de envíos](#example-scenarios)).

#### <a name="create-two-new-product-filter-codes"></a>Crear dos nuevos códigos de filtro de producto

1. Vaya a **Gestión de almacenes \> Configurar \> Filtros de producto \> Filtros de producto** y agregue dos filtros de producto:

    - Filtro de productos 1:

        - **Código de filtro:** *Inflamable*
        - **Título del filtro:** *Código 4*

    - Filtro de productos 2:

        - **Código de filtro:** *Explosivo*
        - **Título del filtro:** *Código 4*

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abra el producto con número de artículo *M9200*. (El producto que seleccione debe estar habilitado para procesos de almacén avanzado \[WMS\] y este producto está habilitado previamente para procesos WMS en los datos de demostración **USMF**).
1. En la ficha desplegable **Almacén**, establezca el campo **Código 4** en *Inflamable*.
1. Cierre la página.
1. Abra el producto con número de artículo *M9201*. (Este producto también está habilitado previamente para procesos WMS en los datos de demostración **USMF**).
1. En la ficha desplegable **Almacén**, establezca el campo **Código 4** en *Explosivo*.
1. Cierre la página.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Crear un nuevo modo de transporte de entrega

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Modo**.
1. Cree un modo de transporte que se utilizará en consultas de consolidación y asígnele el nombre *Vías aéreas*.
1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.
1. Cree un transportista con la siguiente configuración:

    - **Transportista de envío:** *Vías aéreas*
    - **Nombre:** *Vías aéreas*
    - **Modo:** *Vías aéreas*

1. En la ficha desplegable **Servicios** del nuevo operador, agregue una fila que tenga la siguiente configuración:

    - **Servicio de transportista:** *Aire*
    - **Método de transporte:** *Aire*

1. En el panel Acciones, seleccione **Guardar**.

    > [!NOTE]
    > Cuando guarde el nuevo transportista, el campo **Modo de entrega** para la nueva fila en la cuadrícula **Servicios** se establece automáticamente en *Airwa-Air*. Cuando usa el modo de entrega *Airwa-Air* para un pedido de ventas, el modo de transporte *Vías aéreas* se utilizará para los envíos relacionados.

#### <a name="create-an-order-pool"></a>Crear un grupo de pedidos

1. Vaya a **Ventas y marketing \> Configuración \> Pedidos de ventas \> Grupos de pedidos**.
1. Cree un grupo de pedidos que se utilizará para la consulta de consolidación. Este grupo de pedidos debe tener la siguiente configuración:

    - **Grupo:** Introduzca un número entero que no haya sido utilizado por ningún otro grupo.
    - **Nombre:** *ShipCons*

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. Abra el cliente que tiene el número de cuenta *US-003*.
1. En el ficha desplegable **Valores predeterminados de pedidos de ventas**, establezca el campo **Grupo de pedidos de ventas** en el grupo de órdenes que acaba de crear.
1. Cierre la página y luego repita los pasos 4 y 5 para el cliente que tiene el número de cuenta *US-004*.

### <a name="create-example-policy-1"></a>Crear directiva de ejemplo 1

En este ejemplo, creará una directiva *Cliente + Modo* que se puede usar para el siguiente caso de negocio:

- La directiva consultará una cuenta de cliente específica (*US-001*) y un modo específico de entrega (*Airwa-Air*).
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza por id. de pedido. (En otras palabras, habrá envíos separados por pedido, almacén, etc.).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *CustomerMode*
    - **Descripción de directiva:** *Cuenta de cliente y modo de entrega*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion**, en la lista **Campos restantes**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, en la cuadrícula, busque la fila donde el campo **Campo** está establecido en *Cuenta de cliente* y establezca el campo **Criterio** para esa fila en *US-001*.
1. Seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Líneas de pedido*
    - **Tabla derivada:** *Líneas de pedido*
    - **Campo:** *Modo de entrega*
    - **Criterio:** *Airwa-Air*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, las líneas de pedido para el cliente *US-001* que usan el modo de entrega *Airwa-Air* no se consolidarán en todos los pedidos. Esta directiva está destinada a usarse primero en una secuencia, en los casos en que los envíos para todos los demás modos de entrega se consoliden para este cliente.

### <a name="create-example-policy-2"></a>Crear directiva de ejemplo 2

En este ejemplo, creará una directiva *Mercancías peligrosas* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un código de filtro específico (*peligroso*) y un modo específico de entrega (*Airwa-Air*).
- La consolidación con envíos abiertos está activada.
- La consolidación se realiza en todos los pedidos. (En otras palabras, habrá envíos separados por cuenta, almacén, etc., pero solo dentro del grupo de artículos que se especifica en la consulta).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Tipo de artículo*
    - **Descripción de directiva:** *Consolidar el mismo tipo de artículo en todos los pedidos*

1. Configure la opción **Consolidar con envíos abiertos** en *Sí*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion**, en la lista **Campos restantes**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Uniones**, expanda y seleccione **Tablas \> Detalles de carga** en el árbol.
1. Seleccione **Agregar unión de tabla**.
1. En la cuadrícula de relaciones que aparece, busque y seleccione la fila donde el campo **Relación** está establecido en *Número de artículo de almacén (número de artículo)* y luego elija **Seleccionar**. 
1. En la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Número de artículo del almacén*
    - **Tabla derivada:** *Número de artículo del almacén*
    - **Campo:** *Código 4*
    - **Criterio:** *Inflamable*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los artículos tienen un código de filtro específico (es decir, el código de filtro donde el campo **Código 4** está establecido en *Inflamable*) se consolidarán con otros artículos del mismo tipo en todos los pedidos. Si hay un envío abierto para la misma cuenta, almacén y grupo de artículos, se le adjuntarán las nuevas líneas.

### <a name="create-example-policy-3"></a>Crear directiva de ejemplo 3

En este ejemplo, creará una directiva *Requisitos del cliente* que se puede usar para el siguiente caso de negocio:

- La directiva consultará una cuenta de cliente específica.
- La consolidación con envíos abiertos está activada.
- La consolidación se realiza en todos los pedidos, pero se basa en las solicitudes de los clientes. (En otras palabras, los pedidos múltiples se agruparán en envíos, según el mismo número de solicitud del cliente y el mismo almacén).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *CustomerOrderNo*
    - **Descripción de directiva:** *Consolidar líneas basadas en el pedido del cliente*

1. Configure la opción **Consolidar con envíos abiertos** en *Sí*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion**, en la lista **Campos restantes**, seleccione la fila donde el campo **Nombre de campo** está establecido en *Solicitud de cliente*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En la lista **Campos restantes**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** está establecido en *Cuenta de cliente* y establezca el campo **Criterio** para esa fila en *US-001*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los pedidos de ventas tienen el mismo número de solicitud del cliente se consolidarán en un solo envío, independientemente del número de pedido de ventas. (El número de solicitud del cliente se utiliza como número de \[pedido de compra\]) del cliente. Si hay un envío abierto para la misma cuenta, almacén y solicitud del cliente, se le agregarán las nuevas líneas. Esta directiva se puede usar si el cliente envía líneas de pedido adicionales que tienen el mismo número de pedido varias veces durante un día y desea que todas las líneas se agrupen en un solo envío. (En otras palabras, habrá un conocimiento de embarque y un albarán).

### <a name="create-example-policy-4"></a>Crear directiva de ejemplo 4

En este ejemplo, creará una directiva *Clientes que permiten consolidación* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un grupo de pedidos específico para identificar a los clientes que aceptan envíos consolidados.
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza en todos los pedidos utilizando los campos seleccionados por defecto en la directiva CrossOrder (para replicar la casilla anterior **Consolidar envío en el despacho al alamacén**).

- Puede anular la regla en un pedido de ventas seleccionando un grupo de pedidos diferente.

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Grupo de pedidos*
    - **Descripción de directiva:** *Consolidar en todos los pedidos según el grupo de pedidos*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion**, en la lista **Campos restantes**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Pedidos de ventas*
    - **Tabla derivada:** *Pedidos de ventas*
    - **Campo:** *Grupo*
    - **Criterio:** *ShipCons*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los pedidos de ventas pertenecen al mismo grupo de pedidos se consolidarán en un solo envío a través de los pedidos de ventas para la misma cuenta, almacén y modo de entrega de transporte. En lugar del grupo de pedidos, puede usar cualquier otro campo para distinguir un grupo de clientes y usar el encabezado del pedido de ventas de forma predeterminada. Puede utilizar este enfoque si el cliente, no el almacén, está impulsando la necesidad de consolidación. (En la lógica de consolidación anterior, el almacén impulsó la necesidad de consolidación).

### <a name="create-example-policy-5"></a>Crear directiva de ejemplo 5

En este ejemplo, creará una directiva *Almacenes que permiten consolidación* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un grupo de pedidos específico para identificar almacenes que pueden consolidar envíos.
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza en todos los pedidos utilizando los campos seleccionados por defecto en la directiva CrossOrder (para replicar la casilla anterior **Consolidar envío en el despacho al alamacén**).

Por lo general, este caso de negocios se puede abordar mediante las directivas predeterminadas que creó en el [Configurar sus directivas de consolidación iniciales](#initial-policies). Sin embargo, también puede crear directivas similares manualmente siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Peido cruzado*
    - **Descripción de directiva:** *Consolidación de pedidos cruzados para almacenes específicos*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion**, en el campo **Campos restantes**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Agregar** ![Flecha derecha.](media/forward-button.png) Para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** está establecido en *Almacén* y establezca el campo **Criterio** para esa fila en *61, 63*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

### <a name="set-the-order"></a>Configurar el pedido

Ahora que ha creado todas sus directivas, debe establecer el orden en que se aplicarán. Para utilizar un enfoque tipo pirámide, donde las directivas que tienen la mayoría de las condiciones se evalúan como de mayor prioridad, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. Seleccione cada directiva que aparezca en la columna de la izquierda y luego use los botones **Hacer subir** y **Hacer bajar** del panel Acciones para organizar las directivas en el siguiente orden:

    1. CustomerMode
    1. Tipo de artículo
    1. CustomerOrderNo
    1. Grupo de pedidos
    1. Pedido cruzado
    1. Predeterminada

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Escenarios de ejemplo de cómo usar las directivas de consolidación de envíos

Los siguientes escenarios ilustran cómo podría utilizar las directivas de consolidación de envíos que creó al leer este artículo. Cada escenario le lleva por unproceso de consolidación de envíos que utiliza directivas de consolidación de envíos durante el deespacho automátizado o manual al almacén:

- Escenario 1: [Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas](../warehousing/consolidate-shipments-automatic.md)
- Escenario 2: [Consolidar envíos cuando la directiva de consolidación de envíos se anula desde la página Despachar al almacén](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Escenario 3: [Consolidar los envíos utilizando Despachar al almacén desde área de trabajo de planificación de la carga](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Escenario 4: [Consolidar los envíos utilizando el área de trabajo de consolidación de envíos](../warehousing/consolidate-shipments-manual-workbench.md)
- Escenario 5: [Consolidar los envíos manualmente utilizando la página Consolidar envíos](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Recursos adicionales

- [Vista general de directivas de consolidación de envíos](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
