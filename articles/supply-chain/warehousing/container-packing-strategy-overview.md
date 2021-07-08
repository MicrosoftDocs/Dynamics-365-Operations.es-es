---
title: Estrategias de embalaje de contenedores
description: Este tema describe las diferencias entre las estrategias de embalaje de contenedores y proporciona ejemplos.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292770"
---
# <a name="container-packing-strategies"></a>Estrategias de embalaje de contenedores

Una *estrategia de embalaje de contenedores* es una estrategia que puede utilizar para definir asignaciones de artículos entre contenedores. Este tema explica las diferencias entre las estrategias *Empaquetar en todos los contenedores abiertos* y *Empaquetar solo en el contenedor actual*.

- **Empaquetar en todos los contenedores abiertos** - El sistema debe verificar todos los contenedores abiertos que ya se hayan creado durante el ciclo de contenedorización, para asegurarse de que el artículo quepa en uno de ellos. Durante el embalaje, el sistema verifica cada artículo para determinar si cabe en alguno de los contenedores creados anteriormente. Si el artículo no cabe en un contenedor existente, el sistema crea un contenedor nuevo y continúa hasta que haya terminado de empaquetar todo el pedido.

    Por ejemplo, *n* artículos pedidos requieren contenedorización. En el peor de los casos, cada vez que el sistema procesa un artículo que no cabe en ningún contenedor existente, hará un total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) comprobaciones para evaluar si el artículo encaja en los contenedores existentes.

- **Embalar solo en el contenedor actual**: el sistema debe comprobar solo el contenedor creado más recientemente para asegurarse de que el artículo cabrá en él. Durante el embalaje, el sistema verifica cada artículo para determinar si cabe en el contenedor creado más recientemente. Si el artículo no cabe en ese contenedor, el sistema crea un contenedor nuevo y continúa hasta que haya terminado de empaquetar todo el pedido.

    Por ejemplo, *n* artículos pedidos requieren contenedorización. En el peor de los casos, el sistema hará un total de (*n* – 1) controles para evaluar si el artículo cabe en los contenedores.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Ejemplo de flujo para estrategias de empaque de contenedores

Debe configurar los siguientes elementos para la creación de contenedores.

| Artículo | Dimensiones físicas (ancho x profundidad x altura) | Importancia |
|---|---|---|
| Cable HDMI 6' | 1 × 1 × 1 | 1 |
| Cable HDMI 12' | 2 × 1 × 1 | 1 |
| Cable HDMI 18' | 3 × 1 × 1 | 2 |

También configura la siguiente caja que se utilizará para el embalaje.

| Contenedor | Dimensiones físicas (largo x ancho x altura) | Importancia | Volumen |
|---|---|---|---|
| Caja mediana | 6 × 3 × 2 | 10 | 100 |

Finalmente, configura un pedido que tiene los siguientes productos y cantidades.

| Línea de pedido de ventas | Cantidad |
|---|---|
| Cable HDMI 12' | 9 |
| Cable HDMI 18' | 8 |
| Cable HDMI 6' | 13 |

La siguiente tabla resume cómo funciona la contenedorización cuando usa la estrategia *Empaque en todos los contenedores abiertos* y cuando utilizas la estrategia *Empaquetar solo en el contenedor actual*.

| Embalar en todos los contenedores abiertos | Empacar en contenedor actual |
|---|---|
| <p>Cable HDMI 12':</p><ol><li>Crear un nuevo tipo de contenedor, CONT0001.</li><li>Ponga 9 ea en el recipiente CONT0001.</li></ol> | <p>Cable HDMI 12':</p><ol><li>Crear un nuevo tipo de contenedor, CONT0001.</li><li>Ponga 9 ea en el recipiente CONT0001.</li></ol> |
| <p>Cable HDMI 18':</p><ol><li>Compruebe si el artículo puede caber en el contenedor CONT0001.</li><li>Crear un nuevo tipo de contenedor, CONT0002.</li><li>Ponga 5 ea en el recipiente CONT0002.</li><li>Crear un nuevo tipo de contenedor, CONT0003.</li><li>Ponga 3 ea en el recipiente CONT0003.</li></ol> | <p>Cable HDMI 18':</p><ol><li>Compruebe si el artículo puede caber en el contenedor CONT0001.</li><li>Crear un nuevo tipo de contenedor, CONT0002.</li><li>Ponga 5 ea en el recipiente CONT0002.</li><li>Crear un nuevo tipo de contenedor, CONT0003.</li><li>Ponga 3 ea en el recipiente CONT0003.</li></ol> |
| <p>Cable HDMI 6':</p><ol><li>Compruebe si el artículo puede caber en el contenedor CONT0001.</li><li>Ponga 1 ea en el recipiente CONT0001.</li><li>Compruebe si el artículo puede caber en el contenedor CONT0002.</li><li>Compruebe si el artículo puede caber en el contenedor CONT0003.</li><li>Ponga 4 ea en el recipiente CONT0003.</li><li>Crear un nuevo tipo de contenedor, CONT0004.</li><li>Ponga 8 ea en el recipiente CONT0004.</li></ol> | <p>Cable HDMI 6':</p><ol><li>Compruebe si el artículo puede caber en el contenedor CONT0003.</li><li>Ponga 4 ea en el recipiente CONT0003.</li><li>Crear un nuevo tipo de contenedor, CONT0004.</li><li>Ponga 9 ea en el recipiente CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Escenario de ejemplo: empacar pedidos individuales por contenedor

Esta sección presenta un escenario en el que el sistema está configurado para consolidar varios pedidos en un solo envío. Por lo tanto, la contenedorización se realizará a partir del pedido de venta para garantizar que cada pedido que contenga varios productos se empaque en su propio contenedor.

Esta funcionalidad le permite manejar escenarios en los que debe empaquetar solo un pedido de venta en cada contenedor, de modo que el centro de distribución pueda cruzar contenedores completos entre tiendas minoristas. Además de los escenarios minoristas (pedido por tienda minorista y envío a un centro de distribución para cross-docking), esta técnica también se usa comúnmente en cadenas de suministro ajustadas (pedido de venta por línea de producción justo a tiempo).

Este escenario muestra cómo puede disminuir el número de contenedores que se evalúan durante el embalaje mediante el uso de la estrategia *Empaquetar solo en el contenedor actual* de contenedorización.

### <a name="prerequisites"></a>Requisitos previos

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Active la función Consolidar envíos en su sistema

Este escenario usa la característica *Consolidar envíos*. Si esa función aún no está disponible en su sistema, debe activarla usando [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Este escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

### <a name="inspect-or-create-container-types"></a>Inspeccionar o crear tipos de contenedores

Para inspeccionar sus tipos de contenedores, o para crear nuevos tipos de contenedores si son necesarios, siga estos pasos.

1. Vaya a **Warehouse Management** \> **Configurar** \> **Contenedores** \> **Tipos de contenedor**.
1. Asegúrese de que cada uno de los siguientes tipos de contenedores esté disponible en sus datos de demostración. Edite o cree tipos de contenedores según sea necesario.

    - Tipo de contenedor 1:

        - **Código de tipo de contenedor:** *Caja grande*
        - **Descripción:** *Caja grande*
        - **Peso neto máximo:** *100*
        - **Volumen:** *400*
        - **Longitud:** *4*
        - **Anchura:** *10*
        - **Altura:** *10*

    - Tipo de contenedor 2:

        - **Código de tipo de contenedor:** *Caja mediana*
        - **Descripción:** *Caja mediana*
        - **Peso neto máximo:** *50*
        - **Volumen:** *200*
        - **Longitud:** *2*
        - **Anchura:** *10*
        - **Altura:** *10*

    - Tipo de contenedor 3:

        - **Código de tipo de contenedor:** *Caja pequeña*
        - **Descripción:** *Caja pequeña*
        - **Peso neto máximo:** *20*
        - **Volumen:** *100*
        - **Longitud:** *1*
        - **Anchura:** *10*
        - **Altura:** *10*

### <a name="inspect-or-create-container-groups"></a>Inspeccionar o crear grupos de contenedores

Para inspeccionar sus grupos de contenedores, o para crear nuevos grupos de contenedores si son necesarios, siga estos pasos.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Grupos de contenedores**.
1. Asegúrese de que los siguientes grupos de contenedores esté disponible en sus datos de demostración. Si no está disponible, seleccione **Nuevo** para crearlo.

    - **ID de grupo de contenedores:** *Cajas*
    - **Descripción:** *Tamaños de caja*

1. En la ficha desplegable **Detalles** del grupo de contenedores *Cajas*, asegúrese de que existan las siguientes líneas. Si no es así, seleccione **Nuevo** para agregarlos.

    - Línea 1:

        - **Número de secuencia:** *1*
        - **Tipo de contenedor:** *Caja grande*
        - **Porcentaje de utilización de contenedor:** *100*

    - Línea 2:

        - **Número de secuencia:** *2*
        - **Tipo de contenedor:** *Caja mediana*
        - **Porcentaje de utilización de contenedor:** *100*

    - Línea 3:

        - **Número de secuencia:** *3*
        - **Tipo de contenedor:** *Caja pequeña*
        - **Porcentaje de utilización de contenedor:** *100*

### <a name="create-a-new-container-build-template"></a>Cree una nueva plantilla de creación de contenedores

Para crear una nueva plantilla de creación de contenedores, siga estos pasos.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Contenedores** \> **Plantilla de creación de contenedores**.
1. Seleccione **Nuevo** para crear una plantilla de construcción de contenedor que tenga la siguiente configuración:

    - **Número de secuencia:** *1*
    - **ID de plantilla de contenedor:** *Caja*
    - **ID de grupo de contenedores:** *Cajas*
    - **Tipos de consultas base:** *Línea de asignación de ventas*
    - **Código de paso de oleada:** *234*
    - **Permitir selecciones divididas:** *Sí*
    - **Estrategia de embalaje de contenedores:** *Empaquetar solo en el contenedor actual*
    - **Embalaje por unidad directiva:** *No*

1. Mientras la fila de la nueva plantilla aún está seleccionada, seleccione **Editar consulta** en el panel de acciones.
1. Aparece un cuadro de diálogo de editor de consultas estándar. En la pestaña **Ordenación**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Transacciones laborales temporales*
    - **Tabla derivada:** *Transacciones laborales temporales*
    - **Campo:** *Número de pedido*
    - **Dirección de búsqueda:** *Ascendente*

    > [!IMPORTANT]
    > Para evitar pasar por encima de todos los demás recipientes abiertos y acelerar el proceso comprobando un recipiente a la vez, utilice la estrategia *Empaquetar solo en el contenedor actual* además de ordenar por número de orden. Esta combinación funcionará como un descanso en una plantilla de trabajo.

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Mientras la fila de la nueva plantilla aún está seleccionada, seleccione **Restricciones de mezcla de contenedores** en el panel de acciones.

    Ahora agregará una restricción que coloca los artículos de un solo pedido en un solo contenedor. Los artículos de cualquier otro pedido se colocarán en un contenedor separado.

1. Seleccione **Nuevo** para crear una restricción de mezcla que tenga la siguiente configuración:

    - **Tabla:** *Pedidos de ventas*
    - **Seleccionar campo:** *SalesId* (el campo aparecerá como *Órdenes de venta* en la cuadrícula).

1. Seleccione **Aceptar** para agregar la restricción.
1. Cierre la página.

### <a name="set-up-a-wave-template-for-containerization"></a>Configurar una plantilla de oleada para la creación de contenedores

Para configurar una plantilla de oleada, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel de lista, establezca el campo **Tipo de plantilla de oleada** en *Envío*.
1. Seleccione la plantilla **63 Containerización** en la lista.
1. En el panel Acciones, seleccione **Editar**.
1. Sobre la ficha desplegable **Métodos**, en la columna **Métodos seleccionados**, busque la siguiente línea:

    - **Nombre del método:** *contenedorización*
    - **Nombre**: *Creación de contenedores*

1. Establezca el campo **Código de paso de oleada** para la línea en *234*.

### <a name="set-up-a-work-template"></a>Configurar una plantilla de trabajo

Para configurar una plantilla de trabajo, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. Establezca el campo **Tipo de orden de trabajo** en *Pedidos de ventas*.
1. En la cuadrícula **Visión general**, busque y seleccione la plantilla de trabajo que debe usarse para embalar pedidos individuales por contenedor. Para este escenario, seleccione la plantilla **63 Recoger a contenedor**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. Aparece un cuadro de diálogo de editor de consultas estándar. En la pestaña **Ordenación**, agregue las líneas siguientes:

    - Línea 1:

        - **Tabla:** *Transacciones laborales temporales*
        - **Tabla derivada:** *Transacciones laborales temporales*
        - **Campo:** *Identificación del envío*
        - **Dirección de búsqueda:** *Ascendente*

    - Línea 2:

        - **Tabla:** *Transacciones laborales temporales*
        - **Tabla derivada:** *Transacciones laborales temporales*
        - **Campo:** *Número de pedido*
        - **Dirección de búsqueda:** *Ascendente*

    - Línea 3:

        - **Tabla:** *Transacciones laborales temporales*
        - **Tabla derivada:** *Transacciones laborales temporales*
        - **Campo:** *ID de contenedor*
        - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.
1. Recibirá el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?" Seleccione **Sí** para continuar.
1. Mientras que la plantilla **63 Recoger en contenedor** aún está seleccionada, seleccione **Descansos en el encabezado** en el Panel de acciones.

    Ahora aplicará la configuración para dividir el trabajo de modo que cada contenedor de la orden esté vinculado a una orden de trabajo.

1. Seleccione la casilla **Agrupar por este campo** para cada fila en la página **Descansos del encabezado de trabajo** (**Identificación del envío**, **Número de orden** e **ID de contenedor**).
1. Cierre la página.

### <a name="set-up-shipment-consolidation-policies"></a>Configurar directivas de consolidación de envíos

Siga estos pasos para configurar una directiva de consolidación de envíos.

1. Vaya a **Gestión de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. En el panel de lista, establezca el campo **Tipo de política** en *Pedidos de venta*.
1. Seleccione la política **Predeterminada** en la lista.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **Campos de consolidacion**, en la lista **Campos seleccionados**, seleccione la fila donde el campo **Nombre del campo** está establecido en *Número de pedido*.
1. Seleccione el botón **Quitar** ![Flecha izquierda](media/backward-button.png) para mover el campo a la lista **Campos restantes**.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-physical-dimensions-for-the-product"></a>Configurar las dimensiones físicas del producto

Para configurar las dimensiones físicas de los productos que se utilizarán en este escenario, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto cuyo campo **Número de artículo** está establecido en *A0001*.
1. En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.
1. En la página **Dimensiones físicas**, debería ver la siguiente línea en la cuadrícula:

    - **Unidad:** *piezas*
    - **Peso bruto:** *3,00*
    - **Anchura:** *2,00*
    - **Profundidad:** *2,00*
    - **Altura:** *4,00*
    - **Volumen:** *16,00*

1. Cierre la página.
1. Seleccione el producto cuyo campo **Número de artículo** está establecido en *A0002*.
1. En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.
1. En la página **Dimensiones físicas**, debería ver la siguiente línea en la cuadrícula:

    - **Unidad:** *piezas*
    - **Peso bruto:** *4,00*
    - **Anchura:** *3,00*
    - **Profundidad:** *1,00*
    - **Altura:** *3,00*
    - **Volumen:** *9,00*

### <a name="create-sales-order-1"></a>Crear pedido de ventas 1

Para crear un pedido de ventas, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Aparece un cuadro de diálogo para crear un nuevo pedido de cliente. Establezca los valores siguientes:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *63*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Líneas de pedido de ventas**, agregue las siguientes líneas de ventas:

    - Línea 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *2*

    - Línea 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *2*

1. Seleccione la primera línea y luego seleccione **Inventario \> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote**. A continuación, cierre la página.
1. Repita los dos pasos anteriores para la segunda línea.
1. Cierre la página.

### <a name="create-sales-order-2"></a>Crear pedido de ventas 2

Siga estos pasos para crear un segundo pedido de ventas.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Aparece un cuadro de diálogo para crear un nuevo pedido de cliente. Establezca los valores siguientes:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *63*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Líneas de pedido de ventas**, agregue las siguientes líneas de ventas:

    - Línea 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *4*

    - Línea 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *4*

1. Seleccione la primera línea y luego seleccione **Inventario \> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote**. A continuación, cierre la página.
1. Repita los dos pasos anteriores para la segunda línea.
1. Cierre la página.

### <a name="create-the-load"></a>Crear la carga

Siga estos pasos para crear una carga para cada conjunto de pedidos que creó para este escenario y luego despacharlo al almacén.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la pestaña **Líneas de venta**, busque y seleccione todas las líneas de pedido de los pedidos de venta que creó para este escenario.
1. En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**. Las líneas de pedido seleccionadas se agregan a una nueva carga.
1. En el cuadro de diálogo **Cargar asignación de plantilla**, en el campo **Cargar id. de plantilla**, seleccione una plantilla de carga, como *40' Container*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En la sección **Cargas**, busque y seleccione la carga que acaba de crear.
1. Seleccione **Lanzamiento \> Liberar al almacén**.
1. En el cuadro de diálogo **Despachar al almacén**, seleccione **Aceptar** para liberar la carga seleccionada al almacén.

### <a name="verify-the-shipments-and-containers"></a>Verificar los envíos y contenedores

El siguiente procedimiento le permite verificar los envíos que se han creado. Úselo para revisar el orden que creó para este escenario, para asegurarse de haber obtenido los resultados esperados.

1. Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.
1. Busque y seleccione el envío que se creó para la carga que acaba de liberar.
1. En el Panel acciones, en la pestaña **Transporte**, seleccione **Ver contenedores**.
1. Confirme que los artículos de los pedidos de venta se hayan colocado en contenedores en dos contenedores diferentes.

## <a name="additional-resources"></a>Recursos adicionales

- [Creación de contenedores](wave-containerization.md)
