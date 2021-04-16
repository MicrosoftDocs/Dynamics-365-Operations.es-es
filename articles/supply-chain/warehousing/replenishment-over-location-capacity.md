---
title: Reabastecimiento según la capacidad de la ubicación
description: Este tema proporciona información sobre la característica Reabastecimiento según la capacidad de la ubicación. Esta característica permite crear todo el trabajo de reabastecimiento que se requerirá para el día y administra la disponibilidad de ese trabajo de reabastecimiento para garantizar que la ubicación de picking no se quede sin inventario ni supere la capacidad.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 309df56671bf258e1669ae6d5393de01e2b500f0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823248"
---
# <a name="replenishment-over-location-capacity"></a>Reabastecimiento según la capacidad de la ubicación

[!include [banner](../includes/banner.md)]

Algunos almacenes de gran volumen o con espacio limitado deben enviar más cantidad de un artículo en un día de lo que cabe en el lugar de picking. La característica *Reabastecimiento según la capacidad de la ubicación* permite crear todo el trabajo de reabastecimiento que se requerirá para el día y administra la disponibilidad de ese trabajo de reabastecimiento para garantizar que la ubicación de picking no se quede sin inventario ni supere la capacidad.

La característica permite que se cree más trabajo de reabastecimiento de lo que cabe en una ubicación, y bloquea el trabajo de reabastecimiento cuando la ubicación está llena. A medida que el inventario en la ubicación de picking desciende por debajo de un umbral configurable, se pone a disposición más trabajo de reabastecimiento.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Activar la característica Reabastecimiento según la capacidad de la ubicación

Para que esta característica esté disponible, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):

1. Bloqueo de trabajo en toda la organización
1. Reabastecimiento según la capacidad de la ubicación

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configure la función para el escenario de ejemplo

Esta sección proporciona pautas y un ejemplo que muestra cómo configurar la característica Control de calidad y preparar datos de muestra para el escenario de ejemplo que se proporciona más adelante en este tema.

### <a name="enable-sample-data"></a>Habilitar datos de muestra

Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

### <a name="location-profile"></a>Perfil de ubicación

Habilite la funcionalidad de reposición según la capacidad en el perfil de ubicación.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En el panel izquierdo, seleccione **PICK-06**.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **Reabastecimiento**, establezca los valores siguientes:

    - **Exceder la capacidad de ubicación**: *Sí*

        Cuando está habilitada, la capacidad máxima de la ubicación podrá superarse por el trabajo de reabastecimiento. Esto también habilita otros campos en la ficha desplegable **Reabastecimiento**.

    - **Tipo de umbral de disponibilidad de trabajo**: *Cantidad*

        Este campo define el método que se utiliza para determinar cuándo se debe liberar más trabajo. Puede despachar según la cantidad o un porcentaje:

        - *Porcentaje*: seleccione esta opción para usar el porcentaje de capacidad que se basa en los límites de existencias o en la volumetría. Al seleccionar esta opción, se habilita el campo **Porcentaje de desbordamiento** y deshabilita los dos campos relacionados con la cantidad, **Cantidad de desbordamiento** y **Unidad de desbordamiento**.

            Puede usar esta opción si las ubicaciones de picking usan volumetría.

            Si esta opción está seleccionada, configure el campo **Porcentaje de desbordamiento** en el porcentaje en el que se pondrá a disposición más trabajo de reposición.

        - *Cantidad*: seleccione esta opción para usar un valor de cantidad específico. Al seleccionar esta opción, se deshabilita el campo **Porcentaje de desbordamiento** y se habilita los dos campos relacionados con la cantidad, **Cantidad de desbordamiento** y **Unidad de desbordamiento**.

            Use esta opción cuando no esté utilizando los volúmenes para las ubicaciones que se están reabasteciendo, o cuando tenga cantidades consistentes en las que desea que se lleve más inventario a la ubicación.

           Si esta opción está seleccionada, configure los campos **Cantidad de desbordamiento** y **Unidad de desbordamiento** en la cantidad y la unidad en la que se pondrá a disposición más trabajo de reposición.

    - **Cantidad de desbordamiento:** *0,65*

        Este campo define la cantidad a la que se desborda la ubicación.

        El trabajo estará disponible siempre que la suma de la cantidad disponible en la ubicación y la cantidad de trabajo estén por debajo de este valor. Cualquier trabajo de reabastecimiento por encima de este valor se desbloqueará manualmente.

        Los límites de inventario de ubicación se consideran cuando se calcula la cantidad de trabajo.

    - **Unidad de desbordamiento**: *PL*

        Este campo define la unidad que está asociada con la cantidad de desbordamiento.

        En este caso, habrá más trabajo de reabastecimiento cuando la ubicación llegue a 0,65 pallets (PL).

    - **Porcentaje de desbordamiento**

        Este campo define el porcentaje al que se desborda la ubicación.

        El trabajo estará disponible siempre que la suma de la cantidad disponible en la ubicación y la cantidad de trabajo estén por debajo de este porcentaje. Cualquier porcentaje de cantidad de trabajo de reabastecimiento por encima de este valor se bloqueará y deberá desbloquearse manualmente.

        Los límites de inventario de ubicación se consideran cuando se calcula el porcentaje de trabajo. Si no se definen límites de inventario de ubicación, el porcentaje de cantidad de trabajo se calculará por volumen si las restricciones de volumen se definen en el perfil de ubicación.

> [!IMPORTANT]
> Si está utilizando los datos de demostración para la entidad jurídica **USMF** y previamente se ha activado la característica *Posición de matrícula de entidad de almacén de almacén de ubicación*, debe desactivar la configuración **Habilitar el posicionamiento de matrícula de entidad de almacén** para el perfil de ubicación **A GRANEL-06** para completar los pasos móviles en el escenario de ejemplo.

### <a name="wave-step-code"></a>Código de paso de oleada

> [!NOTE]
> Para configurar un código de paso de oleada como se describe aquí, es posible que primero deba usar [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la característica que se llama *Código de paso de oleada de toda la organización*.

1. Vaya a **Administración de almacenes \> Configuración \> Oleadas \> Códigos de paso de oleada**.
1. Seleccione **Nuevo** y establezca los valores siguientes:

    - **Código de paso de oleada**: *Reabast.*
    - **Descripción de paso de oleada**: *Reabastecimiento*
    - **Tipo de paso de oleada**: *Reabastecimiento*

1. Seleccione **Guardar**.

### <a name="replenishment-template"></a>Plantilla de reabastecimiento

Las plantillas de reabastecimiento son un conjunto de reglas que controlan cuándo y cómo se reabastece un ubicación.

1. Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.
1. En el panel Acciones, seleccione **Editar**.
1. En la sección **Visión general**, seleccione la línea donde el campo **Reabastecer plantilla** se establece en *Solicitar reposición*.
1. Establezca los valores siguientes:

    - **Código de paso de oleada**: *Reabast.*
    - **Permitir demanda de oleadas para usar cantidades sin reservar:** *sí*

1. Seleccione **Guardar**.

### <a name="wave-template"></a>Plantilla de oleada

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel izquierdo, establezca el campo **Tipo de plantilla de oleada** en *Envío*.
1. Seleccione la plantilla **Envío 61** en la lista.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, establezca la opción **Automatizar liberación de trabajo de reabastecimiento** en *Sí*.

    Establezca esta opción en *Sí* para crear trabajo de reabastecimiento basado en demandas y libérelo automáticamente. Debe agregar el método de oleada de reabastecimiento en la plantilla de oleada, y crear una plantilla de reabastecimiento del tipo **Demanda de oleadas**. Configure una plantilla de reabastecimiento en la página **Plantillas de reabastecimiento**. Para configurar una plantilla de reabastecimiento, debe agregar el método de reposición a la plantilla de onda.

1. Sobre la ficha desplegable **Métodos**, en la columna **Métodos seleccionados**, busque la siguiente línea:

    - **Nombre del método**: *reabastecer*
    - **Nombre**: *Reabastecimiento*

1. Establezca el campo **Código de paso de oleada** para esta línea a *Reabast.*.
1. Seleccione **Guardar**.

## <a name="example-scenario"></a>Supuesto de ejemplo

Después de haber puesto a disposición todos los datos de ejemplo descritos anteriormente y configurarlos, puede trabajar en este escenario para probar la característica *Reabastecimiento según la capacidad de la ubicación*. Los valores que se muestran en este escenario suponen que está trabajando con los datos de demostración estándar, que seleccionó la entidad jurídica **USMF** y que preparó los registros de ejemplo que se describen anteriormente en este tema. Este escenario también sirve como ejemplo que muestra cómo se puede usar la característica en una configuración de producción.

### <a name="create-replenishment-work"></a>Crear trabajo de reabastecimiento

#### <a name="create-sales-order-1"></a>Crear pedido de ventas 1

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.
1. En el cuadro de diálogo, establezca los valores siguientes:

    - **Cuenta de cliente:** *US-007*
    - **Almacén**: *61*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *T0100*
    - **Cantidad:** *40*

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote**.
1. Cierre la página.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon. También se crea una oleada de reabastecimiento.

    También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".

#### <a name="create-sales-order-2"></a>Crear pedido de ventas 2

1. En la página **Todos los pedidos de ventas**, en el panel Acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.
1. En el cuadro de diálogo, establezca el valor siguiente:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *61*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *T0100*
    - **Cantidad:** *60*

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote**.
1. Cierre la página.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon. También se crea una oleada de reabastecimiento.

    También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".

#### <a name="create-sales-order-3"></a>Crear pedido de ventas 3

1. En la página **Todos los pedidos de ventas**, en el panel Acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.
1. En el cuadro de diálogo, establezca los valores siguientes:

    - **Cuenta de cliente:** *US-004*
    - **Almacén**: *61*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *T0100*
    - **Cantidad:** *30*

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote**.
1. Cierre la página.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon. También se crea una oleada de reabastecimiento.

    También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".

#### <a name="view-work-details"></a>Ver los detalles de trabajo

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. En la sección **Visión general**, filtre la columna **Almacén** para el almacén *61*.
1. Debería ver que se crearon siete identificadores de trabajo para los tres pedidos de venta de demanda.

    - Tres de los siete identificadores tiene un valor **Tipo de orden de trabajo** de *Reabastecimiento* y cuatro tienen un valor **Tipo de orden de trabajo** de *Pedidos de venta*.
    - Los tres identificadores de trabajo que tienen un valor **Tipo de orden de trabajo** de *Reabastecimiento* tienen las mismas ubicaciones de *Picking* y *Colocación* en la sección **Líneas**:

        - **Picking**: *02A01R5S1B*
        - **Colocación**: *06A01R2S1B*

    - Se crearon dos identificadores de trabajo para el pedido de cliente 1.

1. Anote los identificadores de trabajo para los pedidos de ventas.

Dependiendo de las cantidades disponibles, las cantidades de trabajo que se crean pueden variar ligeramente. Sin embargo, en general, los encabezados de trabajo que se crean deben coincidir con este ejemplo de escenario.

#### <a name="on-hand-inventory-license-plate-id"></a>Identificador de matrícula de inventario disponible

Más adelante en este escenario, usará la aplicación móvil Warehouse Management (o un emulador), donde debe identificar la placa de licencia para completar los escenarios de recolección y reabastecimiento.

Para encontrar los identificadores de matrícula de licencia que necesitará más adelante, siga estos pasos.

1. Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.
1. Seleccione le botón **Mostrar filtros** para abrir el panel de filtro.
1. Especifique los siguientes criterios de filtrado para obtener las placas para el escenario. Utilice el filtro *empieza con*.

    - **Código de artículo:** *T0100*
    - **Almacén**: *61*

1. Seleccionar **Aplicar**.
1. En el panel Acciones, seleccione **Dimensiones**.
1. En el cuadro de diálogo **Visualización de dimensiones**, en la sección **Dimensiones de almacenamiento**, seleccione todos los valores.
1. En la sección **Transacciones**, seleccione **Número de artículo** y **Cantidad \<\> 0**.
1. Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo.
1. La cuadrícula **Disponible** muestra los números de matrícula de entidad de almacén para el artículo *T0100* en cada ubicación. Tome nota de la matricula de entidad que se encuentra en cada ubicación, ya que necesitará esta información más adelante.
1. Cierre la página.

### <a name="process-steps"></a>Pasos del proceso

Realizará el reabastecimiento de la ubicación del almacén para los dos primeros identificadores de trabajo. El trabajo en el tercer trabajo de reabastecimiento se bloqueará hasta que el nivel de inventario en la ubicación de picking caiga por debajo del umbral.

#### <a name="replenishment"></a>Reabastecimiento

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario en el almacén *61*. (Escriba *61* como el identificador de usuario y *1* como la contraseña).
1. Vaya a **Inventario \> Reabastecimiento**.

    Se le solicitará que complete el primer trabajo de reabastecimiento. Se muestran el número de artículo, la cantidad y la ubicación de selección.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.
1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).

    El sistema genera un número de matrícula de entidad de almacén para la matrícula de entidad de almacén para el artículo seleccionado.

1. Seleccione **Aceptar** para confirmar el valor.

    Se muestra el trabajo Colocar que indica al usuario que coloque la matrícula de entidad de almacén de destino en la ubicación de reabastecimiento. La ubicación *Colocar* debe ser **06A01R2S1B**.

1. Confirme los detalles de la colocación y seleccione **Aceptar**.

    Recibirá un mensaje de "Trabajo completado" y se mostrarán los detalles de la próxima tarea de selección de reabastecimiento: el número de artículo, la cantidad y la ubicación para elegir. La ubicación de picking será la misma que la primera ubicación de reabastecimiento. Por lo tanto, la matrícula de entidad de almacén tendrá el mismo identificador que se utilizó para la primera tarea de reabastecimiento.

1. Repita los pasos anteriores para completar el trabajo de reabastecimiento para la segunda tarea de trabajo. La cantidad y la matrícula de entidad de almacén de destino serán diferentes de la cantidad y la matrícula de entidad de almacén de destino para la primera tarea de trabajo.

Después de completar el segundo trabajo de reabastecimiento, recibirá un mensaje de "Trabajo completado". El dispositivo móvil también le informa de que no hay trabajo disponible, a pesar de que queda algo de trabajo de reabastecimiento. Este comportamiento se produce porque el trabajo de reabastecimiento tiene un estado de disponibilidad de *Retenido* y por lo tanto está marcado como **Bloqueado**.

El estado *Retenido* se desencadenó porque el perfil de ubicación para la ubicación de picking a la que se asigna el trabajo tiene un valor de **Cantidad de desbordamiento** de *0,65 PL*. Las dos tareas de trabajo de reabastecimiento anteriores llenaron la ubicación casi hasta su límite de desbordamiento para el artículo *T0100*. (La conversión de unidades para el artículo es *1 PL = 100 ea*). Por lo tanto, el trabajo de reabastecimiento restante provocaría que la ubicación exceda su límite de desbordamiento.

Hasta que se seleccione suficiente inventario en la ubicación para colocarlo por debajo del umbral de liberación de trabajo en el elemento del menú del dispositivo móvil, este trabajo de reabastecimiento permanecerá bloqueado.

#### <a name="sales-order-pick"></a>Picking de pedido de ventas

Antes de que se pueda completar la tarea de reabastecimiento restante, la ubicación de picking debe agotarse del inventario a un nivel donde el trabajo de reabastecimiento restante se pueda desbloquear. Es decir, la suma de la cantidad de inventario disponible en la ubicación y la cantidad de reabastecimiento no puede exceder el valor **Cantidad de desbordamiento**. Cuando esta suma es menor que la cantidad de desbordamiento, el trabajo de reabastecimiento restante se desbloqueará.

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario en el almacén *61*. (Escriba *61* como el identificador de usuario y *1* como la contraseña).
1. Vaya a **Salida \> Selección de ventas**.
1. Especifique el primer identificador de trabajo para el pedido de cliente 1.

    Consulte los identificadores para los pedidos de ventas que anotó anteriormente, en la página **Detalles del trabajo**. El identificador de trabajo que estableció aquí generará trabajo de selección para una cantidad de 10 ea desde dos ubicaciones separadas.

1. Seleccione **Aceptar**.

    La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar para la primera ubicación.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.
1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).

    La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar para la siguiente ubicación.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.
1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).

    La página **Pedidos de venta: Colocar** le indica que guarde ambos trabajos de selección completados en la ubicación de almacenamiento provisional saliente.

1. Seleccione **Aceptar**.

    Recibe un mensaje "Trabajo completado".

1. Especifique el segundo identificador de trabajo para el pedido de cliente 1.

    Solo hay una tarea de selección para este identificador de trabajo.

1. Seleccione **Aceptar**.

    La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.

    La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema de las tareas de reabastecimiento. Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.

1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).
1. Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.
1. Seleccione **Aceptar**.

    Recibe un mensaje "Trabajo completado".

Se ha bloqueado la selección del pedido de ventas 2 porque la tarea de reabastecimiento a la que está vinculada no está completa. Actualmente, todavía hay una cantidad de 30 ea en la ubicación de picking, y la cantidad de reabastecimiento para el pedido de cliente 2 es 60 ea. La suma del inventario disponible y el inventario de reposición (90 ea) excede la cantidad de desbordamiento de 0,65 PL (o 65 ea). Antes de que se pueda completar el trabajo de reposición, se debe seleccionar el pedido de ventas 3.

1. Especifique el identificador de trabajo para el pedido de ventas 3.

    Solo hay una tarea de selección para este identificador de trabajo.

1. Seleccione **Aceptar**.

    La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.

    La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema de las tareas de reabastecimiento. Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.

1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).
1. Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.
1. Seleccione **Aceptar**.

    Recibe un mensaje "Trabajo completado".

Tan pronto como la suma de la cantidad disponible en la ubicación de picking y la cantidad de reabastecimiento esté por debajo del umbral, podrá procesar el trabajo de reabastecimiento restante.

Vuelva a la página **Detalles del trabajo** y observe que la disponibilidad del trabajo de reabastecimiento para la pieza final de reabastecimiento (para el pedido de cliente 2) es *Abierto*, porque ahora hay suficiente espacio en la ubicación para aceptar el reabastecimiento.

Ahora puede procesar este trabajo de reabastecimiento a través del dispositivo móvil.

1. Vaya a **Inventario \> Reabastecimiento**.

    Se le solicitará que complete el trabajo de reabastecimiento restante. Se muestran el número de artículo, la cantidad y la ubicación de selección.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.
1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).

    El sistema genera un número de matrícula de entidad de almacén para la matrícula de entidad de almacén para el artículo seleccionado.

1. Seleccione **Aceptar** para confirmar el valor.

    Se muestra el trabajo Colocar que indica al usuario que coloque la matrícula de entidad de almacén de destino en la ubicación de reabastecimiento. La ubicación *Colocar* debe ser **06A01R2S1B**.

1. Confirme los detalles de la colocación y seleccione **Aceptar**.

    Recibirá los mensajes "Trabajo completado" y "No hay trabajo disponible".

Ahora puede seleccionar el pedido de ventas 2. Se desbloqueó cuando se completó el trabajo de reabastecimiento vinculado al pedido de ventas.

1. Especifique el identificador de trabajo para el pedido de ventas 2.

    Solo hay una tarea de selección para este identificador de trabajo.

1. Seleccione **Aceptar**.

    La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.

1. En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.

    La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema desde la tareas de reabastecimiento. Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.

1. Seleccione el botón **Aceptar** (símbolo de marca de verificación).
1. Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.
1. Seleccione **Aceptar**.

    Recibe un mensaje "Trabajo completado".

## <a name="notes-and-tips"></a>Notas y consejos

- Esta funcionalidad funciona con todo tipo de reabastecimiento: demanda de oleadas, mínimo/máximo, demanda de carga y slotting.
- Puede anular manualmente la disponibilidad de trabajo de reabastecimiento para cada encabezado de trabajo desde la página **Detalles del trabajo** si quiere.
- Cuando el sistema establece la disponibilidad de trabajo de reabastecimiento, considera cualquier inventario que ya esté en la ubicación antes de que se complete cualquier trabajo.
- Cada pieza de trabajo de pedido de ventas está vinculada a un trabajo de reabastecimiento específico. No hay funcionalidad de disponibilidad de trabajo de ventas correspondiente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]