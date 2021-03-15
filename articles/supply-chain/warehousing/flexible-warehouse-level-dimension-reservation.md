---
title: Política de reserva de dimensión de nivel de almacén flexible
description: Este tema describe la política de reserva de inventario que permite a las empresas que venden productos con seguimiento por lotes y ejecutan su logística como operaciones habilitadas para WMS reservar lotes específicos para pedidos de clientes, a pesar de que la jerarquía de reservas asociada con los productos no permite la reserva de lotes específicos.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bf50b0b8da2859caab4db2394f2d56f7b76793ca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004811"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Política de reserva de dimensión de nivel de almacén flexible

[!include [banner](../includes/banner.md)]

Cuando una jerarquía de reserva de inventario de tipo "Batch-below\[ubicación\]" está asociada con productos, las empresas que venden productos con seguimiento de lotes y ejecutan su logística como operaciones habilitadas para Microsoft Dynamics 365 Warehouse Management System (WMS) no pueden reservar lotes específicos de esos productos para pedidos de clientes.

De manera similar, las placas específicas no se pueden reservar para productos en pedidos de ventas cuando esos productos están asociados con la jerarquía de reserva predeterminada.

Este tema describe la política de reserva de inventario que permite a estas empresas reservar lotes específicos o matrículas de entidad, incluso cuando los productos están asociados con una jerarquía de reservas "Batch-below\[ubicación\]".

## <a name="inventory-reservation-hierarchy"></a>Jerarquía de reservas de inventario

Esta sección resume la jerarquía de reservas de inventario existente.

La jerarquía de reservas de inventario dicta que, en lo que respecta a las dimensiones de almacenamiento, la orden de demanda lleva las dimensiones obligatorias de sitio, almacén y estado del inventario, mientras que la lógica de almacén es responsable de asignar una ubicación a las cantidades solicitadas y reservar la ubicación. En otras palabras, en las interacciones entre el pedido de demanda y las operaciones de almacén, se espera que el pedido de demanda indique de dónde debe enviarse el pedido (es decir, qué sitio y almacén). El almacén se basa en su lógica para encontrar la cantidad requerida en las instalaciones del almacén.

Sin embargo, para reflejar el modelo operativo de la empresa, las dimensiones de seguimiento (números de serie y de lote) están sujetas a una mayor flexibilidad. Una jerarquía de reserva de inventario puede acomodar escenarios donde se aplican las siguientes condiciones:

- El negocio se basa en sus operaciones de almacén para gestionar la recolección de cantidades que tienen números de lote o de serie después de que las cantidades se hayan encontrado en el espacio de almacenamiento de almacenamiento. Este modelo a menudo se conoce como *Batch-below\[ubicación\]*. Por lo general, se usa cuando la identificación de un lote o número de serie de un producto no es importante para los clientes que colocan la demanda en la empresa vendedora.
- Si los números de lote o de serie son parte de la especificación de pedido de un cliente y se registran en el pedido de demanda, las operaciones de almacén que encuentran las cantidades en el almacén están restringidas por los números solicitados específicos y no se les permite cambiarlos. Este modelo a menudo se conoce como *Batch-above\[ubicación\]*.

En estos escenarios, el desafío es que solo se puede asignar una jerarquía de reserva de inventario a cada producto lanzado. Por lo tanto, para que el WMS maneje los artículos rastreados, una vez que la asignación de la jerarquía determina cuándo se debe reservar el lote o el número de serie (cuando se toma la orden de demanda o durante el trabajo de selección de almacén), este momento no se puede cambiar ad hoc.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Reserva flexible para artículos con seguimiento por lotes

### <a name="business-scenario"></a>Escenario empresarial

En este escenario, una compañía usa una estrategia de inventario donde se hace un seguimiento de los productos terminados por número de lote. Esta compañía también usa la carga de trabajo de WMS. Debido a que esta carga de trabajo tiene una lógica bien equipada para planificar y ejecutar operaciones de picking y envío de almacén para artículos habilitados por lotes, la mayoría de los artículos terminados están asociados con una jerarquía de reservas de inventario "Batch-below\[ubicación\]". La ventaja de este tipo de configuración operativa es que las decisiones (que son efectivamente decisiones de reserva) sobre qué lotes elegir y dónde colocarlas en el almacén se posponen hasta que comiencen las operaciones de selección del almacén. No se toman cuando se realiza el pedido del cliente.

Aunque la jerarquía de reservas "Batch-below\[ubicación\]" sirve bien a los objetivos comerciales de la compañía, muchos de los clientes establecidos de la compañía requieren el mismo lote que compraron previamente cuando reordenan productos. Por lo tanto, la compañía busca flexibilidad en la forma en que se manejan las reglas de reserva de lotes, de modo que, dependiendo de la demanda de los clientes por el mismo artículo, ocurran los siguientes comportamientos:

- Se puede registrar y reservar un número de lote cuando el procesador de ventas toma el pedido, y no se puede cambiar durante las operaciones de almacén ni otras demandas. Este comportamiento ayuda a garantizar que el número de lote que se solicitó se envíe al cliente.
- Si el número de lote no es importante para el cliente, las operaciones del almacén pueden determinar un número de lote durante el trabajo de recolección, después de que se haya realizado el registro y la reserva del pedido de ventas.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Permitir la reserva de un lote específico en el pedido de ventas

Para admitir la flexibilidad deseada en el comportamiento de reserva de lotes para artículos que están asociados con una jerarquía de reservas de inventario "Batch-below\[ubicación\]", los gerentes de inventario deben seleccionar la casilla **Permitir reserva bajo pedido** para el nivel de **Número de lote** en la página **Jerarquías de reservas de inventario**.

![Hacer que la jerarquía de reservas de inventario sea flexible](media/Flexible-inventory-reservation-hierarchy.png)

Cuando se selecciona en la jerarquía el nivel de **Número de lote**, todas las dimensiones por encima de ese nivel hasta el nivel **Ubicación** se seleccionarán automáticamente. (Por defecto, todas las dimensiones por encima del nivel de **Ubicación** están preseleccionadas). Este comportamiento refleja la lógica en la que todas las dimensiones en el rango entre el número de lote y la ubicación también se reservan automáticamente después de reservar un número de lote específico en la línea de pedido.

> [!NOTE]
> La casilla **Permitir reserva bajo pedido** se aplica solo a los niveles de jerarquía de reserva que están por debajo de la dimensión de ubicación del almacén.
>
> **Número de lote** y **Matrícula de entidad** es el único nivel en la jerarquía que está abierto para la política de reserva flexible. En otras palabras, no puede seleccionar la casilla **Permitir reserva bajo pedido** para el nivel **Ubicación** o **Número de serie**.
>
> Si su jerarquía de reservas incluye la dimensión del número de serie (que siempre debe estar por debajo del nivel de **Número de lote**) y si ha activado la reserva específica de lote para el número de lote, el sistema continuará manejando las operaciones de reserva y selección de número de serie, de acuerdo con las reglas que se aplican a la política de reserva "Serial-below\[ubicación\]".

En cualquier momento, puede permitir una reserva específica de lote para la jerarquía de reservas "Batch-below\[ubicación\]" en su implementación. Este cambio no afectará ninguna reserva ni el trabajo de almacén abierto que se creó antes de que ocurriera el cambio. Sin embargo, la casilla de verificación **Permitir reserva bajo pedido** no se puede desactivar si las transacciones de inventario de tipo de problema **Pedido reservado**, **Cantidad física reservada** o **Cantidad pedida** existen para uno o más elementos que están asociados con esa jerarquía de reservas.

> [!NOTE]
> Si la jerarquía de reservas existente de un artículo no permite la especificación de lotes en el pedido, puede reasignarla a una jerarquía de reservas que sí permita la especificación de lotes, siempre que la estructura de nivel de jerarquía sea la misma en ambas jerarquías. Utilice la función **Cambiar jerarquía de reservas para artículos** para hacer la reasignación. Este cambio puede ser pertinente cuando desea evitar la reserva flexible de lotes para un subconjunto de artículos rastreados por lotes, pero permitirlo para el resto de la cartera de productos.

Independientemente de si ha seleccionado la casilla **Permitir reserva bajo pedido**, si no desea reservar un número de lote específico para el artículo en una línea de pedido, la lógica de operaciones de almacén predeterminada que es válida para una jerarquía de reservas "Batch-below\[ubicación\]" seguirá siendo aplicable.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Reservar un número de lote específico para un pedido del cliente

Después de que la jerarquía de reservas de inventario "Batch-below\[ubicación\]" de un artículo con seguimiento por lotes está configurada para permitir la reserva de números de lote específicos en pedidos de venta, los procesadores de pedidos de venta pueden tomar pedidos de clientes para el mismo artículo de una de las siguientes maneras, dependiendo de la solicitud del cliente:

- **Introducir los detalles del pedido sin especificar un número de lote**: este enfoque debe usarse cuando la especificación de lote del producto no es importante para el cliente. Todos los procesos existentes que están asociados con el manejo de un pedido de este tipo del sistema permanecen sin cambios. No se requieren consideraciones adicionales por parte de los usuarios.
- **Introducir los detalles del pedido y reservar un número de lote específico**: este enfoque debe usarse cuando el cliente solicita un lote específico. Por lo general, los clientes solicitarán un lote específico cuando reordenen un producto que compraron previamente. Este tipo de reserva específica de lote se conoce como *reserva comprometida con el pedido*.

El siguiente conjunto de reglas es válido cuando se procesan cantidades y se confirma un número de lote para un pedido específico:

- Para permitir la reserva de un número de lote específico para un artículo bajo la política de reserva "Batch-below\[ubicación\]", el sistema debe reservar todas las dimensiones a través de la ubicación. Este rango generalmente incluye la dimensión de la matrícula de entidad de almacén.
- Las directivas de ubicación no se utilizan cuando el trabajo de selección se crea para una línea de ventas que utiliza la reserva de lotes confirmada por pedido.
- Durante el procesamiento del trabajo en el almacén para lotes confirmados por pedido, ni el usuario ni el sistema pueden cambiar el número de lote. (Este procesamiento incluye el control de excepciones).

El siguiente ejemplo muestra el flujo de extremo a extremo.

## <a name="example-scenario-batch-number-allocation"></a>Escenario de ejemplo: asignación de número de lote

Para este ejemplo, los datos de prueba deben estar instalados y debe usar los datos de la compañía de prueba **USMF**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>Configurar una jerarquía de reservas de inventario para permitir la reserva específica de lote

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Inventario \> Jerarquía de reservas**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, escriba un nombre (por ejemplo, **BatchFlex**).
4. En el campo **Descripción**, ingrese una descripción (por ejemplo, **Lote flexible**).
5. En el campo **Seleccionado**, seleccione **Número de serie** y **Propietario**, y luego seleccione el botón de flecha izquierda para moverlos al campo **Disponible**.
6. Seleccione **Aceptar**.
7. En la fila para el nivel de dimensión **Número de lote**, seleccione la casilla **Permitir reserva bajo pedido**. Los niveles **Matrícula de entidad de almacén** y **Ubicación** se seleccionan automáticamente y no se pueden desactivar sus casillas de verificación.
8. Seleccione **Guardar**.

### <a name="create-a-new-released-product"></a>Crear un nuevo producto liberado

1. Establezca los tres parámetros de datos maestros del producto utilizando estos valores:

    - En el campo **Grupo de dimensiones de almacenamiento**, seleccione **Ware**.
    - En el campo **Grupo de dimensiones de seguimiento**, seleccione **Batch-Phy**.
    - En el campo **Jerarquía de reservas**, seleccione **BatchFlex**.

2. Cree dos números de lote, como **B11** y **B22**.
3. Agregue cantidades de artículos al stock disponible utilizando los siguientes valores.

    | Almacén | Número de lote | Ubicación | Matrícula de entidad de almacén | Cantidad |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Ninguno          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>Introducir detalles del pedido de ventas

1. Vaya a **Ventas y marketing** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.
2. Seleccione **Nuevo**.
3. En el encabezado del pedido de venta, en el campo **Cuenta de cliente**, ingrese **US-003**.
4. Agregue una línea para el nuevo artículo y escriba **10** como cantidad. Asegúrese de que el campo **Almacén** se haya definido como **24**.
5. En la ficha desplegable **Líneas de pedido de venta**, seleccione **Inventario** y, luego, en el grupo **Mantener**, seleccione **Reserva de lotes**. La página **Reserva de lotes** muestra una lista de los lotes disponibles para la reserva para la línea de pedido. En este ejemplo, muestra una cantidad de **20** para el número de lote **B11** y una cantidad de **10** para el número de lote **B22**. Tenga en cuenta que no se puede acceder a la página **Reserva de lotes** desde una línea si el elemento en esa línea está asociado con la jerarquía de reservas "Batch-below\[ubicación\]" a menos que esté configurado para permitir reservas específicas de lote.

    > [!NOTE]
    > Para reservar un lote específico para un pedido de venta, debe utilizar la página **Reserva de lotes**.
    >
    > Si introduce el número de lote directamente en la línea de pedido de venta, el sistema se comportará como si ingresara un valor de lote específico para un artículo que está sujeto a la política de reserva "Batch-below\[ubicación\]". Cuando guarde la línea, recibirá un mensaje de advertencia. Si confirma que el número de lote debe especificarse directamente en la línea de pedido, la línea no será manejada por la lógica de administración de almacén regular.
    >
    > Si reserva la cantidad en la página **Reserva**, no se reservará ningún lote específico y la ejecución de las operaciones de almacén para la línea seguirá las reglas que se aplican en la política de reserva "Batch-below\[ubicación\]".

    En general, esta página funciona y se interactúa de la misma manera que funciona y se interactúa con los elementos que tienen una jerarquía de reservas asociada del tipo "Batch-above\[ubicación\]". Sin embargo, se aplican las siguientes excepciones:

    - La ficha desplegable **Números de lote comprometidos con la línea de origen** muestra los números de lote que están reservados para la línea de pedido. Los valores del lote en la cuadrícula se mostrarán durante todo el ciclo de cumplimiento de la línea de pedido, incluidas las etapas de procesamiento del almacén. Por el contrario, en la ficha desplegable **Visión general**, la reserva de línea de pedido regular (es decir, la reserva que se realiza para las dimensiones por encima del nivel **Ubicación**) se muestra en la cuadrícula hasta el punto en que se crea el trabajo de almacén. La entidad de trabajo se hace cargo de la reserva de línea y la reserva de línea ya no aparece en la página. La ficha desplegable **Números de lote comprometidos con la línea de origen** ayuda a garantizar que el procesador de pedidos de ventas pueda ver los números de lote que se comprometieron con el pedido del cliente en cualquier momento durante su ciclo de vida, hasta la facturación.
    - Además de reservar un lote específico, un usuario puede seleccionar manualmente la ubicación y la placa específica del lote en lugar de permitir que el sistema las seleccione automáticamente. Esta capacidad está relacionada con el diseño del mecanismo de reserva de lotes confirmado por pedido. Como se mencionó anteriormente, cuando se reserva un número de lote para un artículo bajo la política de reserva "Batch-below\[ubicación\]", el sistema debe reservar todas las dimensiones a través de la ubicación. Por lo tanto, el trabajo en el almacén tendrá las mismas dimensiones de almacenamiento que fueron reservadas por los usuarios que trabajaron con los pedidos, y puede que no siempre represente la ubicación de almacenamiento del artículo que sea conveniente, o incluso posible, para las operaciones de picking. Si los procesadores de pedidos conocen las restricciones del almacén, pueden querer seleccionar manualmente las ubicaciones específicas y las placas de matrícula cuando reservan un lote. En este caso, el usuario debe usar la funcionalidad de **Mostrar dimensiones** en el encabezado de la página y debe agregar la ubicación y la matrícula en la cuadrícula en la ficha desplegable **Visión general**.

6. En la página **Reserva de lotes**, seleccione la línea para el lote **B11** y luego seleccione **Reservar línea**. No existe una lógica designada para asignar ubicaciones y placas durante la reserva automática. Puede introducir manualmente la cantidad en el campo **Reserva**. Tenga en cuenta que, en la ficha desplegable **Números de lote comprometidos con la línea de origen**, el lote **B11** se muestra como **Comprometido**.

    ![Confirmación de un número de lote específico en una línea de pedido de venta en la página de reserva de lote](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > La reserva de la cantidad en una línea de pedido de ventas se puede realizar en varios lotes. Del mismo modo, la reserva del mismo lote se puede realizar en múltiples ubicaciones y placas de matrícula (si las placas están habilitadas para las ubicaciones).
    >
    > La reserva de un lote específico para la cantidad en una línea de pedido de ventas también puede ser parcial. Por ejemplo, la cantidad total de 100 unidades se puede reservar para que un lote específico se comprometa a 20 unidades, mientras que 80 unidades se reservan en los niveles de sitio y almacén para cualquier lote disponible. En este caso, el WMS se encargará de las operaciones de selección utilizando dos líneas de trabajo separadas.

7. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**. Seleccione su artículo y luego seleccione **Administrar inventario** \> **Ver** \> **Transacciones**.

    ![Reserva confirmada por pedido como un tipo de transacción de inventario](media/Inventory-transactions-for-order-committed-reservation.png)

8. Revise las transacciones de inventario del artículo que están relacionadas con la reserva de línea de pedido de ventas.

    - Una transacción donde el campo **Referencia** se establece en **Pedido de venta** y el campo **Problema** se establece en **Cantidad física reservada** representa la reserva de línea de pedido para las dimensiones de inventario por encima del nivel **Ubicación**. De acuerdo con la jerarquía de reserva de inventario del artículo, esas dimensiones son sitio, almacén y estado del inventario.
    - Una transacción donde el campo **Referencia** se establece en **Reserva comprometida con el pedido** y el campo **Problema** se establece en **Cantidad física reservada** representa la reserva de línea de pedido del lote específico y todas las dimensiones de inventario situadas por encima. De acuerdo con la jerarquía de reserva de inventario del artículo, esas dimensiones son número de lote y ubicación. En este ejemplo, la ubicación es **Bulk-001**.

9. En el encabezado del pedido de ventas, seleccione **Almacén** \> **Acciones** \> **Liberar al almacén**. La línea de pedido ahora se somete a oleada y se crean una carga y un trabajo.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>Revisar y procesar el trabajo de almacén que tiene números de lote confirmados por pedido

1. En la ficha desplegable **Líneas de pedido de venta**, seleccione **Almacén** \> **Detalles del trabajo**.

    El trabajo que maneja la operación de picking para cantidades de lote que se comprometen con la línea de pedido de ventas tiene las siguientes características:

    - Para crear trabajo, el sistema usa plantillas de trabajo pero no directivas de ubicación. Todas las configuraciones estándar que se definen para las plantillas de trabajo, como un número máximo de líneas de selección o una unidad de medida específica, se aplicarán para determinar cuándo se debe crear un nuevo trabajo. Sin embargo, las reglas asociadas con las directivas de ubicación para identificar ubicaciones de selección no se tienen en cuenta, ya que la reserva confirmada por pedido ya especifica todas las dimensiones del inventario. Esas dimensiones de inventario incluyen las dimensiones en el nivel de almacenamiento del almacén. Por lo tanto, el trabajo hereda esas dimensiones sin tener que consultar las directivas de ubicación.
    - El número de lote no se muestra en la línea de selección (como es el caso de la línea de trabajo que se crea para un artículo que tiene asociada una jerarquía de reservas "Batch-above\[ubicación\]"). En cambio, el número de lote "desde" y todas las demás dimensiones de almacenamiento se muestran en la transacción de inventario de trabajo de la línea de trabajo a la que se hace referencia desde las transacciones de inventario asociadas.

        ![Transacción de inventario de almacén para el trabajo que se origina en la reserva comprometida con el pedido](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Después de crear el trabajo, se elimina la transacción de inventario del artículo donde el campo **Referencia** se establece en **Reserva comprometida con el pedido**. La transacción de inventario donde el campo **Referencia** se establece en **Trabajo** mantiene la reserva física en todas las dimensiones de inventario de la cantidad.

        Las operaciones de almacén pueden proceder a manejar la ejecución del trabajo de la manera habitual. Sin embargo, las instrucciones en el dispositivo móvil le indicarán al trabajador que elija un número de lote específico. En entornos de almacén donde las ubicaciones están controladas por matrículas, después de que un trabajador llega a una ubicación que almacena el mismo lote en varias placas, puede elegir cualquier placa que no esté reservada (por ejemplo, por otro pedido reserva comprometida o trabajo que se origina en una reserva de ese tipo).

        Si resulta poco práctico elegir desde la ubicación que se especifica en la línea de trabajo, los operadores del almacén pueden utilizar una de las siguientes acciones para redirigir la selección del lote específico desde una ubicación más conveniente:

        - La acción estándar **Anular ubicación** en un dispositivo móvil (siempre que esté habilitada la configuración **Permitir anulación de ubicación de selección** para el trabajador del almacén).
        - La acción **Cambiar ubicación** en la página **Detalles de la lista de trabajo**. 

2. En el dispositivo móvil, terminar la selección y colocar el trabajo.

    Ahora se selecciona la cantidad **10** del número de lote **B11** para la línea del pedido de venta y se coloca en la ubicación **Baydoor**. En este punto, está listo para ser cargado en el camión y enviado a la dirección del cliente.

## <a name="flexible-license-plate-reservation"></a>Reserva de matrícula de entidad de almacén flexible

### <a name="business-scenario"></a>Escenario empresarial

En este escenario, una empresa utiliza la gestión de almacenes y el procesamiento del trabajo, y administra la planificación de la carga a nivel de pallets o contenedores individuales fuera de la Supply Chain Management antes de crear el trabajo. Estos contenedores están representados por placas en las dimensiones del inventario. Por lo tanto, para este enfoque, las placas específicas deben asignarse previamente a las líneas de pedido de ventas antes de realizar el trabajo de selección. La empresa está buscando flexibilidad en la forma en que se administran las reglas de reserva de matrículas, para que ocurran los siguientes comportamientos:

- Se puede registrar y reservar una matrícula de entidad de almacén cuando el procesador de ventas toma el pedido, y no se tomar por otras demandas. Este comportamiento ayuda a garantizar que la matrícula de la entidad se planificó se envíe al cliente.
- Si la matrícula de licencia no está asignada a una línea de pedido de ventas, el personal del almacén puede seleccionar una matrícula de entidad de almacén durante el trabajo de selección, después de que se haya completado el registro y la reserva del pedido de ventas.

### <a name="turn-on-flexible-license-plate-reservation"></a>Activar la reserva de matrícula de entidad de almacén flexible

Antes de que pueda usar la reserva de matrícula de entidad de almacén flexible, se deben activar dos características en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas características y activarlas si es necesario. Debe activar las funciones en el siguiente orden:

1. **Nombre de la característica**: *Reserva de dimensión de nivel de almacén flexible*
1. **Nombre de la característica**: *Reserva flexible de matrícula de entidad de almacén de pedido confirmado*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>Reservar una matrícula de entidad de almacén específica en el pedido de ventas

Para habilitar la reserva de matrículas de entidad en un pedido, debe seleccionar la casilla **Permitir reserva bajo pedido** para el nivel **Matrícula de entidad** en la página **Jerarquías de reserva de inventario** para la jerarquía asociada con el elemento relevante.

![Página de jerarquías de reserva de inventario para una jerarquía de reserva de matrículas de entidad flexible](media/Flexible-LP-reservation-hierarchy.png)

Puede habilitar la reserva de matrículas en el pedido en cualquier punto de su implementación. Este cambio no afectará ninguna reserva o al trabajo de almacén abierto que se creó antes de que ocurriera el cambio. Sin embargo, no puede anular la selección de la casilla de verificación **Permitir reserva bajo pedido** si existen transacciones de inventario de salida con un estado de problema de *En pedido*, *Pedido reservado* o *Cantidad física reservada* para uno o más elementos que están asociados con esa jerarquía de reservas.

Incluso si la casilla **Permitir reserva bajo pedido** está seleccionada para **Matrícula de entidad**, todavía es posible *no* reservar una matrícula de entidad de almacén específica en el pedido. En este caso, se aplica la lógica de operaciones de almacén predeterminada que es válida para la jerarquía de reservas.

Para reservar una matrícula de entidad de almacén específica, debe usar un proceso [Open Data Protocol (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). En la aplicación, puede hacer esta reserva directamente desde un pedido de ventas utilizando la opción **Reservas confirmadas por pedido por matrícula de entidad de almacén** del comando **Abrir en Excel**. En los datos de la entidad que se abren en el complemento de Excel, debe especificar los siguientes datos relacionados con la reserva y luego seleccionar **Publicar** para enviar los datos nuevamente a Supply Chain Management:

- Referencia (solo el valor *Órdenes de venta* es compatible).
- Número de pedido (el valor puede derivarse del lote).
- Id. de lote interno
- Matrícula de entidad de almacén
- Cantidad

Si debe reservar una matrícula de entidad de almacén específica para un artículo rastreado por lotes, use la página **Reserva de lotes**, como se describe en la sección [Especificar los detalles del pedido de ventas](#sales-order-details).

Cuando la línea de pedido de ventas que utiliza una reserva de matrícula de entidad de almacén confirmada por pedido se procesa por operaciones de almacén, no se utilizan las directivas de ubicación.

Si un elemento de trabajo de almacén consta de líneas que equivalen a un pallet completo y tienen cantidades confirmadas por la matrícula de entidad de almacén, puede optimizar el proceso de selección utilizando un elemento de menú del dispositivo móvil donde la opción **Gestionar por matrícula de entidad de almacén** esté establecida en *Sí*. Un trabajador del almacén puede escanear una placa para completar una selección en lugar de tener que escanear los artículos del trabajo uno por uno.

![Elemento del menú del dispositivo móvil en el que la opción Gestionar por matrícula de entidad de almacén está establecida en Sí](media/Handle-by-LP-menu-item.png)

Dado que la funcionalidad **Gestionar por matrícula de entidad de almacén** no admite trabajos que cubran múltiples pallets, es mejor tener un elemento de trabajo separado para diferentes matrículas de entidad. Para usar este enfoque, agregue el campo **Id. de matrícula de entidad de almacén confirmada por pedido** como un salto de encabezado de trabajo en la página **Plantilla de trabajo**.

> [!NOTE]
> Para el proceso de creación de trabajo de pedido comprometido, se asignará un valor de "dimensión de inventario de pedido comprometido" a las líneas de trabajo de picking y no será posible ver el valor de la placa de matrícula directamente. Solo el proceso *Dirigido por el usuario* es compatible al configurar un elemento de menú de dispositivo móvil.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>Escenario de ejemplo: configurar y procesar una reserva de matrícula de entidad de almacén confirmada por pedido

Este escenario muestra cómo configurar y procesar una reserva de matrícula de entidad de almacén confirmada por pedido.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Este escenario hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Supply Chain Management. Si quiere trabajar en el escenario utilizando los valores que se presentan en este tema, asegúrese de trabajar en un entorno donde se instalen datos de demostración estándar. Además, también debe establecer la entidad jurídica en **USMF** antes de empezar.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>Crear una jerarquía de reserva de inventario que permita la reserva de matrículas

1. Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Jerarquía de reservas**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre**, escriba un valor (por ejemplo, *FlexibleLP*).
1. En el campo **Descripción**, indique un valor (por ejemplo, *Reserva de Flexible LP*).
1. En la lista **Seleccionado**, seleccione **Número de lote**, **Número de serie** y **Propietario**.
1. Seleccione el botón **Quitar** ![flecha hacia atrás](media/backward-button.png) para mover los registros seleccionados a la lista **Disponible**.
1. Seleccione **Aceptar**.
1. En la fila para el nivel de dimensión **Matrícula de entidad**, seleccione la casilla **Permitir reserva bajo pedido**. El nivel **Ubicación** se seleccionan automáticamente y no se pueden desactivar la casilla de verificación para este.
1. Seleccione **Guardar**.

### <a name="create-two-released-products"></a>Crear dos productos liberado

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Nuevo producto liberado**, establezca los valores siguientes:

    - **Número del producto**: *Artículo1*
    - **Número de artículo**: *Artículo1*
    - **Grupo de modelos de artículo**: *FIFO*
    - **Grupo de artículos**: *Audio*
    - **Grupo de dimensiones de almacenamiento:** *Almacén*
    - **Grupo de dimensiones de seguimiento:** *Ninguno*
    - **Jerarquía de reserva**: *FlexibleLP*

1. Seleccione **Aceptar** para crear el producto y cerrar el cuadro de diálogo.
1. El nuevo producto está abierto. En la ficha desplegable **Almacén**, establezca el campo **Identificador de grupo de secuencia de unidad** en *ea*.
1. Repita los pasos anteriores para crear un segundo producto que tenga la misma configuración, pero establezca los campos **Número de producto** y **Número de artículo** en *Artículo2*.
1. En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Ver**, seleccione **Inventario disponible**. Luego seleccione **Ajuste de la cantidad**.
1. Ajuste el inventario disponible de los nuevos artículos como se especifica en la siguiente tabla.

    | Artículo  | Almacén | Ubicación | Matrícula de entidad de almacén | Cantidad |
    |-------|-----------|----------|---------------|----------|
    | Artículo1 | 24        | FL-010   | LP01          | 10       |
    | Artículo1 | 24        | FL-011   | LP02          | 10       |
    | Artículo2 | 24        | FL-010   | LP01          | 5        |
    | Artículo2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > Debe crear las dos placas y utilizar ubicaciones que permitan elementos mixtos, como *FL-010* y *FL-011*.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>Crear un pedido de venta y reservar una matrícula de entidad de almacén específica

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *24*

1. Seleccione **Aceptar** para crear el cuadro de diálogo **Crear pedido de ventas** y abrir el nuevo pedido de ventas.
1. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:

    - **Número de artículo**: *Artículo1*
    - **Cantidad:** *10*

1. Agregue un segundo pedido de venta que tenga la siguiente configuración:

    - **Número de artículo**: *Artículo2*
    - **Cantidad:** *5*

1. Seleccione **Guardar**.
1. En la ficha desplegable **Detalles de línea**, en la pestaña **Configuración**, tome nota del valor del **Id. del lote** para cada línea. Estos valores serán necesarios durante la reserva de matrículas de entidad específicas.

    > [!NOTE]
    > Para reservar una placa específica, debe utilizar la entidad de datos **Reservas confirmadas por pedido por matrícula de entidad de almacén**. Para reservar una matrícula de entidad de almacén específica en una matrícula de entidad de almacén, también puede usar la página **Reserva de lotes**, como se describe en la sección [Especificar los detalles del pedido de ventas](#sales-order-details).
    >
    > Si especifica la placa directamente en la línea del pedido de venta y la confirma al sistema, el procesamiento de gestión de almacén no se utilizará para la línea.

1. Seleccione **Abrir en Microsoft Office**, **Reservas confirmadas por pedido por matrícula de licencia** y descargue el archivo.
1. Abra el archivo descargado en Excel, y seleccione **Habilitar edición** para habilitar el complemento de Excel que desee ejecutar.
1. Si ejecuta el complemento de Excel por primera vez, seleccione **Confiar en este complemento**.
1. Si se le pide que inicie sesión, seleccione **Iniciar sesión** y, a continuación, inicie sesión con las mismas credenciales empleadas para Supply Chain Management.
1. Para reservar un artículo en una matrícula de entidad de almacén específica, en el complemento Excel, seleccione **Nuevo** para agregar una línea de reserva y luego establecer los siguientes valores:

    - **Id. del lote**: especifique el valor del **Id. del lote** que encontró para la línea de pedido de ventas para *Artículo1*.
    - **Matrícula de entidad**: *LP02*
    - **ReservedInventoryQuantity**: *10*

1. Seleccione **Nuevo** para agregar otra línea de reserva y establezca los siguientes valores en ella:

    - **Id. del lote**: especifique el valor del **Id. del lote** que encontró para la línea de pedido de ventas para *Artículo2*.
    - **Matrícula de entidad**: *LP02*
    - **ReservedInventoryQuantity**: *5*

1. En el complemento de Excel, seleccione **Publicar** para enviar los datos de vuelta a Supply Chain Management.

    > [!NOTE]
    > La línea de reserva aparecerá en el sistema solo si la publicación se completa sin errores.

1. Vaya a Supply Chain Management. 
1. Para revisar la reserva del artículo, en la ficha desplegable **Líneas de pedido de venta**, en el menú **Inventario**, seleccione **Mantener \> Reserva**. Tenga en cuenta que, para la línea de pedido de ventas para *Artículo1*, inventario de *10* está reservado y para la línea de pedido de ventas para *Artículo2*, inventario de *5* está reservado.
1. Para revisar las transacciones de inventario relacionadas con la reserva de línea de pedido de ventas, en la ficha desplegable **Líneas de pedido de venta**, en el menú **Inventario**, seleccione **Ver \> Transacciones**. Observe que hay dos transacciones relacionadas con la reserva: una donde el campo **Referencia** se establece en *Pedido de venta* y otro donde el campo **Referencia** se establece en *Reserva confirmada por pedido*.

    > [!NOTE]
    > Una transacción donde el campo **Referencia** se establece en *Pedido de venta* representa la reserva de la línea de pedido para las dimensiones de inventario sobre el nivel de **Ubicación** (sitio, almacén y estado de inventario). Una transacción donde el campo **Referencia** se establece en *Reserva confirmada por pedido* representa la reserva de línea de pedido para la matrícula de entidad de almacén y ubicación específicas.

1. Para despachar el pedido de ventas, en el panel de acciones, en la pestaña **Almacén**, seleccione el grupo **Acciones** y **Despachar al almacén**.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>Revisar y procesar el trabajo del almacén con las matrículas de entidad de pedido asignadas

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, seleccione **Detalles del trabajo**.

    Al igual que cuando se realiza la reserva para un lote específico, el sistema no utiliza las directivas de ubicación cuando crea el trabajo para el pedido de venta que utiliza la reserva de matrícula de entidad de almacén. Debido a que la reserva confirmada por pedido especifica todas las dimensiones del inventario, incluida la ubicación, las directivas de ubicación no tienen que usarse, porque esas dimensiones del inventario tan solo se especifican en el trabajo. Se muestran en la sección **De dimensiones de inventario** en la página **Transacciones de inventario de trabajo**.

    > [!NOTE]
    > Después de crear el trabajo, se elimina la transacción de inventario del artículo donde el campo **Referencia** se establece en *Reserva comprometida con el pedido*. La transacción de inventario donde el campo **Referencia** se establece en *Trabajo* mantiene la reserva física en todas las dimensiones de inventario de la cantidad.

1. En el dispositivo móvil, termine de seleccionar y colocar el trabajo utilizando un elemento de menú donde la casilla **Gestiona por matrícula de entidad de almacén** está seleccionada.

    > [!NOTE]
    > La funcionalidad **Gestionar por matrícula de licencia** le ayuda a procesar toda la matrícula. Si debe procesar parte de la matrícula de licencia, no puede usar esta funcionalidad.
    >
    > Recomendamos que tenga un trabajo separado generado para cada matrícula de licencia. Para lograr este resultado, use la característica **Saltos de encabezado de trabajo** característica en la página **Plantilla de trabajo**.

    La matrícula de licencia *LP02* se selecciona para las líneas de pedido de ventas y se coloca en la ubicación *Baydoor*. En este punto, está listo para ser cargado en el camión y enviado al cliente.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>Control de excepciones del trabajo de almacén que tiene números de lote confirmados por pedido

El trabajo de almacén para seleccionar los números de lote comprometidos con el pedido está sujeto a las mismas acciones y control de excepciones de almacén estándar que el trabajo normal. En general, el trabajo abierto o la línea de trabajo se pueden cancelar, se pueden interrumpir porque la ubicación de un usuario está llena, se puede seleccionar con picking corto y se puede actualizar debido a un movimiento. Del mismo modo, la cantidad de trabajo seleccionada que ya se ha completado se puede reducir, o bien se puede revertir el trabajo.

La siguiente regla clave se aplica a todas estas acciones de manejo de excepciones: el número de lote que se reservó para el cliente nunca se puede reemplazar con un número de lote diferente, pero sus dimensiones de almacenamiento (ubicación y placa de matrícula) se pueden cambiar mediante una actualización manual por el usuario o una actualización automática por parte del sistema. La actualización automática se basa en la misma asignación aleatoria de dimensiones de almacenamiento que se aplicaba cuando un lote específico se reservaba automáticamente pero no se especificaban dimensiones de almacenamiento.

### <a name="example-scenario"></a>Supuesto de ejemplo

Un ejemplo de este escenario es una situación en la que el trabajo completado anteriormente no se selecciona utilizando la función **Reducir cantidad seleccionada**. Este ejemplo supone que ya ha completado los pasos que se describen en [Escenario de ejemplo: asignación de número de lote](#Example-batch-allocation). Continúa de ese ejemplo.

1. Vaya a **Gestión de almacenes** \> **Cargas** \> **Cargas activas**.
2. Seleccione la carga que se creó en relación con el envío de su pedido de ventas.
3. En la ficha desplegable **Cargar líneas de pedido**, seleccione **Reducir cantidad seleccionada**.
4. En la página **Reducir cantidad seleccionada**, en el campo **Mover a la ubicación**, seleccione **FL-001**.
5. En el campo **Mover a matrícula de entidad de almacén**, seleccione **LP33**.
6. En la cuadrícula, en el campo **Cantidad de inventario para anular selección**, introduzca **10**.
7. Seleccione **Aceptar**.

Aquí están los resultados de la acción de anulación de selección:

- El estado del trabajo previamente cerrado se establece en **Cancelado**.
- Se crea un nuevo trabajo de tipo **Movimiento de inventario** para la cantidad no seleccionada de **10** para el número de lote **B11**. Este trabajo representa el movimiento de la ubicación **Baydoor** a la matrícula **LP33** en la ubicación **FL-001**. El estado se establece en **Cerrado**.
- El sistema vuelve a reservar el número de lote que se ordenó originalmente y asigna la ubicación y los id. de las matrículas de entidad de almacén. (Este proceso es equivalente a ejecutar la función **Reservar línea** para la línea de pedido de un número de lote dado). Como resultado, el lote **B11** se muestra como comprometido en la ficha desplegable **Números de lote comprometidos con la línea de origen** de la página **Reserva de lotes** y el campo **Reserva** contiene una cantidad de **10** para el número de lote **B11**. Además, el campo **Ubicación** se establece en **FL-001** y el campo **Matrícula de entidad de almacén** se establece en **LP11**. (Puede agregar estos campos a la cuadrícula si no están visibles).

Las siguientes tablas proporcionan una descripción general que muestra cómo el sistema maneja la reserva de lotes confirmada por pedido para acciones específicas de almacén. Para interpretar el contenido de las tablas, suponga que cada acción de almacén se ejecuta en el contexto del trabajo de almacén existente que se origina en una reserva de lote confirmada por pedido, o que la ejecución de cada acción de almacén afecta el trabajo de ese tipo.

> [!NOTE]
> En estas tablas, la columna "Cantidad de lote está disponible" indica si hay una cantidad de lote disponible además de la cantidad que ya está reservada para las reservas actuales confirmadas por pedido o ya está reservada por el trabajo de almacén que se origina a partir de reservas de ese tipo.

#### <a name="override-the-pick-location-on-the-open-work"></a>Reemplazar la ubicación de selección en el trabajo abierto

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>La opción <strong>Permitir anulación de ubicación de picking</strong> está habilitada en el trabajador.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Anular ubicación</strong> en la aplicación de almacén al comenzar a seleccionar trabajo.</li>
<li>Seleccione <strong>Sugerir</strong>.</li>
<li>Confirme la nueva ubicación que se sugiere según la disponibilidad de la cantidad de lote.</li>
</ol>
</td>
<td>En el trabajo actual, se producen las siguientes acciones:
<ul>
<li>La ubicación en la línea de selección se actualiza a la nueva ubicación. (Si la ubicación está controlada por una placa de matrícula, se asigna una placa de matrícula aleatoria a la transacción del inventario de trabajo, y el trabajador puede elegir de cualquier placa que tenga una cantidad disponible).</li>
<li>Si la cantidad se encuentra en más de una placa en la nueva ubicación, la línea de selección original se divide en varias líneas para que coincida con cada placa.</li>
</ul>
</td>
<td>No aplicable</td>
</tr>
<tr>
<td>Nº</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Anular ubicación</strong> en la aplicación de almacén al comenzar a seleccionar trabajo.</li>
<li>Introduzca manualmente una ubicación.</li>
</ol>
</td>
<td>La acción <strong>Anular ubicación</strong> no es posible. Falla y se produce un error.</td>
<td>No aplicable</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Botón completo: divide una línea de trabajo debido a un desbordamiento en la ubicación del usuario

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td>La opción <strong>Permitir la división del trabajo</strong> está habilitada en el elemento de menú del dispositivo móvil.</td>
<td>No aplicable</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Completo</strong> en la aplicación de almacén al procesar la selección de trabajo.</li>
<li>En el campo <strong>Cant. picking</strong>, introduzca una cantidad parcial de la selección requerida para indicar la capacidad total.</li>
</ol>
</td>
<td>
<ul>
<li>En el trabajo actual, la cantidad se actualiza con la cantidad restante que debe seleccionarse.</li>
<li>Se crea y cierra un nuevo trabajo para la cantidad seleccionada.</li>
</ul></td>
<td>No aplicable</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>Reducir la cantidad seleccionada de trabajo completado (de una carga)

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>No aplicable</td>
<td>Sí</td>
<td>
<ol>
<li>Abra la página <strong>Reducir cantidad seleccionada</strong> en la línea de carga.</li>
<li>Especifique la cantidad completa cuya selección se debe anular.</li>
<li>Seleccione una ubicación/matrícula como destino del movimiento.</li>
</ol>
</td>
<td>
<ul> 
<li>El trabajo asociado con la línea de carga se cancela.</li>
<li>Se crea y se cierra el nuevo trabajo de movimiento de inventario.</li>
</ul>
</td>
<td>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>Vea la fila anterior.</td>
<td>La cantidad se vuelve a reservar para el mismo lote y para la misma ubicación y matrícula (si la ubicación está controlada por la matrícula) que se ingresaron durante la eliminación.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Mover un artículo dentro de un almacén.

> [!NOTE]
> Esta acción de almacén es aplicable solo al movimiento del tipo **Proceso de creación de trabajo**, no al movimiento por plantilla.

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>La opción <strong>Permitir movimiento de inventario con trabajo asociado</strong> está habilitada en el trabajador.</td>
<td>Sí</td>
<td>
<ol>
<li>Inicie un movimiento en la aplicación de almacén.</li>
<li>Especifique las ubicaciones de origen y destino.</li>
</ol></td>
<td>
<ul>
<li>En todo el trabajo existente que se ve afectado por el movimiento, la ubicación de selección se actualiza con la nueva ubicación de destino.</li>
<li>Se crea y se cierra el nuevo trabajo de movimiento de inventario.</li>
</ul>
</td>
<td>Todas las reservas existentes que se ven afectadas por el movimiento de cantidad desde la ubicación dada se vuelven a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>Vea la fila anterior.</td>
<td>Todas las reservas existentes que se ven afectadas por el movimiento de cantidad desde la ubicación dada se vuelven a reservar para el mismo lote y para la nueva ubicación y matrícula de destino (si la ubicación está controlada por la matrícula).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>Revertir la cantidad seleccionada de trabajo completado (de una carga u oleada)

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>No aplicable</td>
<td>Sí</td>
<td>
<ol>
<li>Abra la página <strong>Invertir el trabajo</strong>.</li>
<li>En la página solicitada, seleccione la opción <strong>Dejar los artículos en la ubicación actual</strong>.</li>
</ol>
</td>
<td>Todo el trabajo asociado con la carga se cancela.</td>
<td>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>Vea la fila anterior.</td>
<td>La cantidad se vuelve a reservar para el mismo lote, y para la ubicación y la placa donde se dejó la cantidad al revertirla.</td>
</tr>
<tr>
<td>Sí</td>
<td>
<ol>
<li>Abra la página <strong>Invertir el trabajo</strong>.</li>
<li>En la página solicitada, seleccione la opción <strong>Asignar artículos a esta ubicación</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>El trabajo actual se cancela.</li>
<li>Se crea y se cierra el nuevo trabajo de movimiento de inventario.</li>
</ul>
</td>
<td>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>Vea la fila anterior.</td>
<td>La cantidad se vuelve a reservar para el mismo lote y para la ubicación y la matrícula a las que estaba asignada la cantidad al revertirla.</td>
</tr>
<tr>
<td>Sí/No</td>
<td>
<ol>
<li>Abra la página <strong>Invertir el trabajo</strong>.</li>
<li>En la página solicitada, seleccione la opción <strong>Mover artículos a esta ubicación</strong>.</li>
</ol>
</td>
<td>No se admite la reversión.</td>
<td>No aplicable</td>
</tr>
<tr>
<td>Sí/No</td>
<td>
<ol>
<li>Abra la página <strong>Invertir el trabajo</strong>.</li>
<li>En la página solicitada, seleccione la opción <strong>Mover artículos según las directivas de ubicación</strong>.</li>
</ol>
</td>
<td>No se admite la reversión. </td>
<td>No aplicable</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Realizar la selección corta de una cantidad: registre la cantidad como físicamente no encontrada en la ubicación/matrícula mientras realiza el trabajo de selección

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Ninguna</strong>, <strong>Ajustar inventario</strong> = <strong>Sí</strong> y <strong>Eliminar reservas</strong> = <strong>No</strong>.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Seleccionar cantidad</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, introduzca <strong>Sin reasignación</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>El trabajo actual está cerrado y la cantidad seleccionada es 0 (cero).</li>
<li>Se crea una transacción de inventario de tipo <strong>Recuento</strong> y con el tipo de problema <strong>Vendido</strong> para representar el ajuste.</li>
</ul>
</td>
<td>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>
<ul>
<li>La acción de selección corta falla y se genera un error.</li>
<li>El trabajo actual permanece abierto.</li>
</ul>
</td>
<td>No aplicable</td>
</tr>
<tr>
<td rowspan='2'>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Ninguna</strong>, <strong>Ajustar inventario</strong> = <strong>Sí</strong> y <strong>Eliminar reservas</strong> = <strong>Sí</strong>.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Seleccionar cantidad</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, introduzca <strong>Sin reasignación</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>El trabajo actual está cerrado y la cantidad seleccionada es 0 (cero).</li>
<li>Se crea una transacción de inventario de tipo <strong>Recuento</strong> y con el tipo de problema <strong>Vendido</strong> para representar el ajuste.</li>
</ul>
</td>
<td>Todas las reservas existentes que se ven afectadas por el ajuste de la cantidad en la ubicación con selección corta se vuelven a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>Vea la fila anterior.</td>
<td>Todas las reservas existentes que se ven afectadas por el ajuste de la cantidad en la ubicación con selección corta se eliminan.</td>
</tr>
<tr>
<td>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Manual</strong>, <strong>Ajustar inventario</strong> = <strong>Sí</strong> y <strong>Eliminar reservas</strong> = <strong>No/Sí</strong>. Además, la opción <strong>Permitir reasignación manual de artículos</strong> está habilitada en el trabajador.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Cantidad de selección corta</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, seleccione <strong>Selección corta con reasignación manual</strong>.</li>
<li>Seleccione la ubicación/matrícula en la lista.</li>
</ol>
</td>
<td>
<ul>
<li>En el trabajo actual, se producen las siguientes acciones:
<ul>
<li>La línea de selección se cierra y la cantidad seleccionada es 0 (cero).</li>
<li>La línea de venta se cancela.</li>
<li>Se crea una línea de selección nueva. Utiliza la ubicación/matrícula que seleccionó el usuario.</li>
<li>Se crea una línea de colocación nueva.</li>
</ul>
</li>
<li>Se crea una transacción de inventario de tipo <strong>Recuento</strong> y con el tipo de problema <strong>Vendido</strong> para representar el ajuste.</li>
</ul>
</td>
<td>No aplicable</td>
</tr>
<tr>
<td>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Manual</strong>, <strong>Ajustar inventario</strong> = <strong>Sí</strong> y <strong>Eliminar reservas</strong> = <strong>No</strong>. Además, la opción <strong>Permitir reasignación manual de artículos</strong> está habilitada en el trabajador.</td>
<td>Nº</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Cantidad de selección corta</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, seleccione <strong>Selección corta con reasignación manual</strong>.</li>
</ol>
</td>
<td>La acción de selección corta falla y se genera un error.</td>
<td>No aplicable</td>
</tr>
<tr>
<td>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Manual</strong>, <strong>Ajustar inventario</strong> = <strong>Sí</strong> y <strong>Eliminar reservas</strong> = <strong>Sí</strong>. Además, la opción <strong>Permitir reasignación manual de artículos</strong> está habilitada en el trabajador.</td>
<td>Nº</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Cantidad de selección corta</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, seleccione <strong>Selección corta con reasignación manual</strong>.</li>
<li>Seleccione la ubicación/matrícula en la lista.</li>
</ol>
</td>
<td>
<ul>
<li>En el trabajo actual, se producen las siguientes acciones:
<ul>
<li>La línea de selección se cierra y la cantidad seleccionada es 0 (cero).</li>
<li>La línea de venta se cancela.</li>
</ul>
</li>
<li>Se crea una transacción de inventario de tipo <strong>Recuento</strong> y con el tipo de problema <strong>Vendido</strong> para representar el ajuste.</li>
</ul>
</td>
<td>Todas las reservas existentes que se ven afectadas por el ajuste de la cantidad en la ubicación/matrícula con selección corta se eliminan.</td>
</tr>
<tr>
<td>Se ha configurado una excepción de trabajo del tipo <strong>Selección corta</strong> donde <strong>Reasignación de artículos</strong> = <strong>Automática</strong>, <strong>Ajustar inventario</strong> = <strong>Sí/No</strong> y <strong>Eliminar reservas</strong> = <strong>Sí/No</strong>.</td>
<td>No aplicable</td>
<td>
<ol>
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacén al ejecutar la selección de trabajo.</li>
<li>En el campo <strong>Cantidad de selección corta</strong>, especifique <strong>0</strong> (cero).</li>
<li>En el campo <strong>Razón</strong>, seleccione <strong>Selección corta con reasignación automática</strong>.</li>
</ol>
</td>
<td>La selección corta que implica reasignación automática no es compatible.</td>
<td>La selección corta que implica reasignación automática no es compatible.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>Cambiar el estado de inventario

> [!NOTE]
> Esta acción de almacén se puede realizar desde múltiples puntos de entrada. El ejemplo que se muestra aquí usa la acción **Cambio de estado de inventario** en la página **Disponible por ubicación**.

<table>
<thead>
<tr>
<th>Parámetro de configuración clave</th>
<th>Cantidad de lote disponible</th>
<th>Pasos clave del usuario</th>
<th>Trabajo de almacén</th>
<th>Reserva de lote confirmada por pedido</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>En la pestaña <strong>Almacén</strong>, en el registro <strong>Almacén</strong>, el campo <strong>Eliminar reservas y marcas</strong> se establece en <strong>Reservas</strong> o <strong>Marcas y reservas</strong>.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione una ubicación específica.</li>
<li>Seleccione una línea que tenga un artículo, una ubicación y una matrícula específicos (si la ubicación está controlada por matrícula).</li>
<li>Seleccione <strong>Cambio de estado de inventario</strong>.</li>
<li>Establezca el campo <strong>Estado de inventario</strong> en <strong>Bloqueo</strong>.</li>
</ol>
</td>
<td>No se permiten cambios en el estado del inventario para cantidades reservadas para el trabajo.</td>
<td>
<ul>
<li>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</li>
<li>Dos transacciones de inventario de tipo <strong>Cambio de estado de inventario</strong> se crean para representar el cambio en la dimensión de estado del inventario.</li>
<li>Se crea una transacción de inventario de tipo <strong>Bloqueo de inventario</strong> y tipo de problema <strong>Cantidad física reservada</strong> para representar la reserva de la cantidad bloqueada.</li>
</ul>
</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>No se permiten cambios en el estado del inventario para cantidades reservadas para el trabajo.</td>
<td>
<ul>
<li>Se elimina la reserva.</li>
<li>Dos transacciones de inventario de tipo <strong>Cambio de estado de inventario</strong> se crean para representar el cambio en la dimensión de estado del inventario.</li>
<li>Se crea una transacción de inventario de tipo <strong>Bloqueo de inventario</strong> y tipo de problema <strong>Cantidad física reservada</strong> para representar la reserva de la cantidad bloqueada.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>En la pestaña <strong>Almacén</strong>, en el registro <strong>Almacén</strong>, el campo <strong>Eliminar reservas y marcas</strong> se establece en <strong>Ninguna</strong>.</td>
<td>Sí</td>
<td>
<ol>
<li>Seleccione una ubicación específica.</li>
<li>Seleccione una línea que tenga un artículo, una ubicación y una matrícula específicos (si la ubicación está controlada por matrícula).</li>
<li>Seleccione <strong>Cambio de estado de inventario</strong>.</li>
<li>Establezca el campo <strong>Estado de inventario</strong> en <strong>Bloqueo</strong>.</li>
</ol>
</td>
<td>No se permiten cambios en el estado del inventario para cantidades reservadas para el trabajo.</td>
<td>La cantidad se vuelve a reservar para el mismo lote. El sistema asigna aleatoriamente una ubicación y una placa de matrícula (si la ubicación está controlada por la placa de matrícula) donde la cantidad está disponible.</td>
</tr>
<tr>
<td>No</td>
<td>Vea la fila anterior.</td>
<td>No se permiten cambios en el estado del inventario para cantidades reservadas para el trabajo.</td>
<td>No se permiten cambios en el estado del inventario.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Limitaciones

- La funcionalidad flexible de reserva de dimensión a nivel de almacén no admite las siguientes características:

    - Gestión del peso capturado
    - Inventario negativo físico
    - Reserva contra suministro solicitado
    - Órdenes de transferencia y selección de materia prima.

- La regla de consolidación de contenedores para el embalaje por unidad directiva tiene limitaciones. Para las reservas confirmadas por pedido, le recomendamos que no use plantillas de compilación de contenedores donde el campo **Unidad de directiva de empaque** esté habilitado. En el diseño actual, las directivas de ubicación no se utilizan cuando se crea el trabajo de almacén. Por lo tanto, solo la unidad más baja en el grupo de secuencia de unidades (la unidad de inventario) se aplica durante el paso de oleada de contenedorización.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]