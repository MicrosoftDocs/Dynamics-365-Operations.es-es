---
title: Secuenciación del trabajo dirigida por el sistema
description: En este artículo se ofrece información sobre la secuencia del trabajo dirigida por el sistema. Esta funcionalidad le permite ordenar y filtrar las órdenes de trabajo que el sistema presenta a los usuarios para su ejecución. Resulta útil en escenarios donde se requieren criterios adicionales para realizar el proceso de picking del almacén.
author: Mirzaab
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 1dab8d8bdace046f0f061713600fd1eab69e7c12
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335477"
---
# <a name="system-directed-work-sequencing"></a>Secuenciación del trabajo dirigida por el sistema

[!include [banner](../includes/banner.md)]

La secuenciación del trabajo dirigida por el sistema le permite ordenar y filtrar las órdenes de trabajo que el sistema presenta a los usuarios para su ejecución. Resulta útil en escenarios donde se requieren criterios adicionales (como el tiempo de envío, la zona de picking, el perfil de ubicación o una combinación de varios criterios) para realizar el proceso de picking del almacén.

Esta funcionalidad amplía la funcionalidad actual de picking dirigido por el sistema al agregar una orden de consulta dirigida por el sistema, donde los usuarios pueden configurar una secuencia y una o más consultas que evaluarán todas las órdenes de trabajo que se crean. Solo se capturarán y presentarán las órdenes de trabajo que cumplan los criterios especificados en la configuración del elemento del menú del dispositivo móvil.

Por lo tanto, esta funcionalidad permite una mayor optimización de los procesos de picking del almacén, ya que identifica las órdenes de trabajo que coinciden con los criterios especificados, las asigna al elemento de menú correcto del dispositivo móvil y luego las presenta a un trabajador, en función de un conjunto de habilidades concretas, equipo de picking u otro requisito.

> [!NOTE]
> Si se necesitan diferentes criterios, se deben usar varios elementos del menú del dispositivo móvil.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Activar la característica Secuenciación del trabajo dirigida por el sistema en toda la organización

Antes de poder usar la secuenciación del trabajo dirigida por el sistema, la característica debe estar activada para su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica**: *Secuencia de trabajo dirigida al sistema de secuenciación de trabajo*

## <a name="setup"></a>Configurar

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para resolver el escenario utilizando los valores que se presentan en este artículo, debe trabajar en un sistema donde se instalen [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF**. El escenario utiliza el almacén *51* de los datos de demostración.

> [!IMPORTANT]
> Antes de liberar los pedidos al almacén, asegúrese de que las ubicaciones de picking tengan suficiente inventario para todos los artículos de los pedidos.
>
> Los datos predeterminados de USMF deberían admitir este escenario. Si no va a usar datos de demostración, revise la configuración de **Directiva de ubicación** para descubrir qué ubicaciones de picking se utilizan para el picking de pedidos de ventas. Si debe ajustar el inventario, puede crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo.

### <a name="set-up-a-mobile-device-menu-item"></a>Configurar un elemento de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En la lista de elementos de menú del dispositivo móvil, seleccione **Picking de ventas - Sistema**. El elemento de menú requerido ya debería existir. 
1. Confirme los siguientes ajustes:

    - En la ficha desplegable **General**, el campo **Dirigido por** debe establecerse en *Sistema dirigido*.
    - La ficha rápida **Clases de trabajo** debería mostrar la siguiente configuración.

        | Identificador de la clase de trabajo | Tipo de pedido de trabajo |
        |---|---|
        | Sales | Pedidos de ventas |
        | Picking de pedidos de ventas | Pedidos de ventas |

1. En el panel de acciones, seleccione **Consultas de secuencias de trabajo dirigidas por el sistema**.
1. Seleccione **Editar**.
1. Elimine la línea existente y luego confirme la acción seleccionando **Sí**.
1. En el panel de acciones, haga clic en **Nuevo** para crear una línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** *1*
    - **Campo de descripción:** *Cantidad de trabajo inferior a 20 y descendente*

1. Seleccione **Guardar**.
1. En el panel de acciones, seleccione **Editar consulta**.
1. En la pestaña **Combinaciones**, expanda la jerarquía de combinación para mostrar la tabla **Lineas de trabajo**.
1. Seleccione la combinación de tabla **Lineas de trabajo**.
1. Seleccione **Agregar unión de tabla**.
1. En la lista que aparece, busque y seleccione la fila que tiene la siguiente configuración:

    - **Modo de combinación:** *n:1*
    - **Relación:** *Ubicaciones (ubicación)*

1. Seleccione **Seleccionar**.

    Las ubicaciones se agregan a la combinación de tabla.

1. En la pestaña **Ordenación**, seleccione **Agregar** para agregar una línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Cantidad de trabajo* (En el cuadro de mensaje que aparece, seleccione **Sí** para agregar una ordenación a este campo).
    - **Dirección de búsqueda:** *Descendente*

1. Seleccione la ficha **Intervalo**.

    Si solo se deben incluir criterios de trabajo concretos en la secuenciación, puede especificarlos en la pestaña **Intervalo**. En este ejemplo, desea incluir solo el trabajo donde la cantidad es inferior a 20 ea (la unidad de medida más baja).

    Tenga en cuenta que algunas líneas ya están incluidas. Esas líneas no deben eliminarse.

1. Seleccione **Agregar** para agregar una línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Cantidad de trabajo de inventario*
    - **Criterios:** *\<20* (menos de 20)

1. Seleccione **Agregar** para agregar otra línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla:** *Lineas de trabajo*
    - **Tabla derivada:** *Líneas de trabajo*
    - **Campo:** *Tipo de trabajo*
    - **Criterios:** *Seleccionar*

1. Seleccione **Agregar** para agregar otra línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo**: *ID de perfil de ubicación*
    - **Criterios:** *!ALMACENAR*

        > [!IMPORTANT]
        > Asegúrese de incluir el signo de exclamación (*!*) delante de *ALMACENAR*.

1. Seleccione **Aceptar** para guardar y cerrar la consulta.
1. Seleccione **Guardar**.
1. Cierre la página para volver a la página **Elementos de menú del dispositivo móvil**.

> [!NOTE]
> Esta configuración define los criterios que se utilizarán para alimentar el trabajo elegible al elemento del menú del dispositivo móvil. Si agrega más líneas de criterios a la consulta, el sistema usará primero la línea de consulta que tenga el número de secuencia más bajo. Es decir, primero se presentará al usuario todo el trabajo elegible para la secuencia número 1 y después todo el trabajo para la secuencia número 2. Por lo tanto, si un rango y ordenación concretos deben usarse juntos, deben especificarse en la misma consulta de secuencia de trabajo dirigida por el sistema.
>
> Esta configuración capturará cualquier trabajo que tenga al menos una línea donde la cantidad sea inferior a 20 ea. Por lo tanto, si el trabajo tiene una línea donde la cantidad es exactamente 20 ea o más de 20 ea, será válido siempre que también tenga al menos una línea donde la cantidad sea menor que 20 ea.

### <a name="location-directives"></a>Directivas de ubicación

Si va a utilizar datos de Contoso predeterminados, la consulta de la acción de directiva de ubicación no requerirá cambios. No obstante, para asegurarse de que las directivas de ubicación capturarán los artículos en los pedidos de ventas cuando aplique la característica en un entorno que no sea de Contoso, cree una nueva directiva de ubicación. Para verificar la configuración en el entorno de demostración, siga estos pasos.

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Directivas de ubicación**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.
1. Seleccione la directiva de ubicación que se denomina *51 Seleccionar*.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione la línea para la acción **Seleccionar**.
1. Seleccione **Editar consulta** encima de la cuadrícula.
1. Revise la consulta **Intervalo**.

    1. Encuentre la línea donde el campo **Campo** se establece en *Ubicación*.
    2. Asegúrese de que el campo **Criterios** está en blanco (es decir, no hay restricciones).

## <a name="scenario"></a>Situación

### <a name="create-sales-order-picking-work"></a>Crear trabajo de picking de pedido de ventas

Antes de ejecutar el picking dirigido por el sistema, debe crearse un trabajo de salida. Para este escenario, creará cuatro pedidos de ventas que se basan en las consultas de secuencia de trabajo dirigidas por el sistema especificadas.

Reservará cantidades de inventario para cada pedido de ventas. Por tanto, el inventario reservado no se puede sacar del almacén para otros pedidos excepto que se cancele la reserva de inventario o parte de esta.

A continuación, liberará cada pedido de ventas al almacén para crear el trabajo de salida.

#### <a name="sales-order-1"></a>Pedido de ventas 1

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 1.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - En la sección **Cliente**, establezca el campo **Cuenta de cliente** en *US-004*.
    - En la sección **General**, establezca el campo **Almacén** en *51*.

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Anote el número del pedido de ventas.
1. Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:

    - **Código de artículo:** *M9200*
    - **Cantidad:** *20*

1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar el inventario.
1. Cierre la página **Reserva**.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén** para crear un trabajo para el almacén.

    Recibirá mensajes informativos que muestran el trabajo, el id. de oleada y los id. de envío que se crean para el pedido de ventas.

#### <a name="sales-order-2"></a>Pedido de ventas 2

1. En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 2.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-007*
    - **Almacén**: *51*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Anote el número del pedido de ventas.
1. Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:

    - **Código de artículo:** *M9200*
    - **Cantidad:** *5*

1. Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *M9201*
    - **Cantidad:** *1*

1. Reserve inventario para ambas líneas.
1. Libere el pedido al almacén.

#### <a name="sales-order-3"></a>Pedido de ventas 3

1. En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 3.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-009*
    - **Almacén**: *51*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Anote el número del pedido de ventas.
1. Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:

    - **Código de artículo:** *M9200*
    - **Cantidad:** *7*

1. Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *M9202*
    - **Cantidad:** *8*

1. Reserve inventario para ambas líneas.
1. Libere el pedido al almacén.

#### <a name="sales-order-4"></a>Pedido de ventas 4

1. En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 4.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-010*
    - **Almacén**: *51*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Anote el número del pedido de ventas.
1. Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:

    - **Código de artículo:** *M9200*
    - **Cantidad:** *25*

1. Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:

    - **Código de artículo:** *M9202*
    - **Cantidad:** *10*

1. Reserve inventario para ambas líneas.
1. Libere el pedido al almacén.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Obtener id. de trabajo para el trabajo que se creó

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. Filtre el campo **Almacén** para que solo se muestre el trabajo para el almacén *51*.
1. Deben haberse creado cuatro id. de trabajo. Anote el id. de trabajo de cada pedido de ventas.

    | Id. de pedido de ventas | Id. de trabajo | Cantidad de trabajo |
    |---|---|---|
    | Pedido de ventas 1 | Id. de trabajo 1 | 20 ea |
    | Pedido de ventas 2 | Id. de trabajo 2 | 6 ea (suma de ambas líneas) |
    | Pedido de ventas 3 | Id. de trabajo 3 | 15 ea (suma de ambas líneas) |
    | Pedido de ventas 4 | Id. de trabajo 4 | 35 ea (suma de ambas líneas) |

Antes de ejecutar el flujo en el dispositivo móvil, asegúrese de que solo el trabajo que acaba de crear esté en estado *Abierto* para el almacén *51* y el tipo de pedido de trabajo *Pedido de ventas*. De lo contrario, los resultados de la prueba pueden variar, porque el picking dirigido por el sistema incluirá todo el trabajo elegible.

1. Vaya **Gestión de almacenes \> Trabajo \> Salida \> Trabajo de ventas abierto**.
1. En la cuadrícula **Trabajo de ventas abierto**, filtre el campo **Almacén** para que solo se muestre el trabajo para el almacén *51*.
1. Confirme que solo se muestran los cuatro id. de trabajo que creó anteriormente.
1. Cierre la página **Trabajo**.

### <a name="mobile-device-flow-execution"></a>Ejecución de flujo del dispositivo móvil

Según la configuración, el sistema alimentará el trabajo del usuario que se ordena de la cantidad de línea de trabajo más alta a la más baja. La cantidad en cada línea será inferior a 20 ea.

Recuerde que esta configuración capturará cualquier trabajo que tenga al menos una línea donde la cantidad sea inferior a 20 ea. Por lo tanto, si el trabajo tiene otra línea donde la cantidad es exactamente 20 ea o más de 20 ea, también será válida.

#### <a name="mobile-app"></a>Aplicación móvil

1. Inicie sesión en la aplicación de almacén como un usuario en el almacén *51*.
1. Vaya a **Salida \> Picking de ventas - Sistema**.

    Se presenta el paso de selección para el id. de trabajo *4*. Este id. de trabajo se presenta primero debido a la configuración de la orden de consulta dirigida por el sistema, donde especificó que el trabajo debe secuenciarse según una cantidad de línea de trabajo descendente.

1. Complete la selección requerida y colóquela para cerrar el id. de trabajo.

    A continuación, se presenta el id. de trabajo *3*. Una de sus líneas de trabajo es la siguiente en la secuencia, según la cantidad de línea de trabajo.

1. Complete la selección y colóquela para cerrar el id. de trabajo.

    A continuación, se presenta el id. de trabajo *2*. La línea de selección de este trabajo es la siguiente en la secuencia.

1. Complete la selección y colóquela para cerrar el id. de trabajo.

    No se le debe presentar más trabajo. El id. de trabajo *1* no es elegible para este elemento de menú del dispositivo móvil, ya que la consulta especifica que los encabezados de trabajo se consideran solo si la cantidad en las líneas de trabajo es inferior a 20 ea.

## <a name="tips"></a>Sugerencias

Las consultas de secuencia de trabajo dirigidas por el sistema son *inclusivas*. Es importante que recuerde este hecho para algunas configuraciones. Por ejemplo, desea que un determinado elemento de menú procese solo el trabajo donde la unidad de trabajo es *ea* y especifica esa restricción en la pestaña **Intervalo** de la consulta. En este caso, todo trabajo en el que al menos una línea de trabajo tenga la unidad de trabajo establecida en *ea* será alimentado al trabajo. Por lo tanto, este trabajo también puede incluir el trabajo en el que las líneas de trabajo tengan una unidad de trabajo distinta de *ea* (como *caja* o *pallet*). La consulta excluirá solo el trabajo en el que ninguna línea de trabajo tenga la unidad de trabajo establecida en *ea*.

Por lo tanto, en el ejemplo de este escenario, la consulta también capturó el id. de trabajo *4*. Cuando se creó, se agregaron dos líneas: una para 25 ea y otra para 10 ea. El trabajo se siguió presentando al usuario, porque al menos una línea de trabajo tiene una cantidad inferior a 20 ea.

Dependiendo del escenario, puede evitar este comportamiento utilizando interrupciones de trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]