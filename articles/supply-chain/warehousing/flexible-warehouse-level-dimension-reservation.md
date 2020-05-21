---
title: Política de reserva de dimensión de nivel de almacén flexible
description: Este tema describe la política de reserva de inventario que permite a las empresas que venden productos con seguimiento por lotes y ejecutan su logística como operaciones habilitadas para WMS reservar lotes específicos para pedidos de clientes, a pesar de que la jerarquía de reservas asociada con los productos no permite la reserva de lotes específicos.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 6c462a87494c434a6047542d448a85b3bce9f769
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346477"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Política de reserva de dimensión de nivel de almacén flexible

[!include [banner](../includes/banner.md)]

Cuando una jerarquía de reserva de inventario de tipo "Batch-below\[ubicación\]" está asociada con productos, las empresas que venden productos con seguimiento de lotes y ejecutan su logística como operaciones habilitadas para Microsoft Dynamics 365 Warehouse Management System (WMS) no pueden reservar lotes específicos de esos productos para pedidos de clientes. Este tema describe la política de reserva de inventario que permite a estas empresas reservar lotes específicos, incluso cuando los productos están asociados con una jerarquía de reservas "Batch-below\[ubicación\]".

## <a name="inventory-reservation-hierarchy"></a>Jerarquía de reservas de inventario

Esta sección resume la jerarquía de reservas de inventario existente. Se centra en la forma en que se manejan los artículos seguidos por lotes y seguidos en serie.

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
> **Número de lote** es el único nivel en la jerarquía que está abierto para la política de reserva flexible. En otras palabras, no puede seleccionar la casilla **Permitir reserva bajo pedido** para el nivel **Ubicación**, **Matrícula de entidad de almacén** o **Número de serie**.
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

## <a name="example-scenario"></a>Supuesto de ejemplo

Para este ejemplo, los datos de prueba deben estar instalados y debe usar los datos de la compañía de prueba **USMF**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a>Configurar una jerarquía de reservas de inventario para permitir la reserva específica de lote

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

### <a name="enter-sales-order-details"></a>Introducir detalles del pedido de ventas

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

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a>Control de excepciones del trabajo de almacén que tiene números de lote confirmados por pedido

El trabajo de almacén para seleccionar los números de lote comprometidos con el pedido está sujeto a las mismas acciones y control de excepciones de almacén estándar que el trabajo normal. En general, el trabajo abierto o la línea de trabajo se pueden cancelar, se pueden interrumpir porque la ubicación de un usuario está llena, se puede seleccionar con picking corto y se puede actualizar debido a un movimiento. Del mismo modo, la cantidad de trabajo seleccionada que ya se ha completado se puede reducir, o bien se puede revertir el trabajo.

La siguiente regla clave se aplica a todas estas acciones de manejo de excepciones: el número de lote que se reservó para el cliente nunca se puede reemplazar con un número de lote diferente, pero sus dimensiones de almacenamiento (ubicación y placa de matrícula) se pueden cambiar mediante una actualización manual por el usuario o una actualización automática por parte del sistema. La actualización automática se basa en la misma asignación aleatoria de dimensiones de almacenamiento que se aplicaba cuando un lote específico se reservaba automáticamente pero no se especificaban dimensiones de almacenamiento.

### <a name="example-scenario"></a>Supuesto de ejemplo

Un ejemplo de este escenario es una situación en la que el trabajo completado anteriormente no se selecciona utilizando la función **Reducir cantidad seleccionada**. Este ejemplo continúa el ejemplo anterior de este tema.

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
<li>Seleccione el elemento de menú <strong>Anular ubicación</strong> en la aplicación de almacenamiento al comenzar a seleccionar trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Anular ubicación</strong> en la aplicación de almacenamiento al comenzar a seleccionar trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Completo</strong> en la aplicación de almacenamiento al procesar la selección de trabajo.</li>
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
<li>Inicie un movimiento en la aplicación de almacenamiento.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
<li>Seleccione el elemento de menú <strong>Elección corta</strong> en la aplicación de almacenamiento al ejecutar la selección de trabajo.</li>
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
