---
title: Acuerdos de gestión de devoluciones
description: En este tema se describe cómo crear Acuerdos de gestión de devoluciones. Las ofertas se utilizan para controlar diferentes métodos y bases para el cálculo de devoluciones y regalías. Incluyen reglas para inclusiones y exclusiones.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 7ba42df021eddccbae389321b38828c7a92e50c8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020516"
---
# <a name="rebate-management-deals"></a>Acuerdos de gestión de devoluciones

[!include [banner](../includes/banner.md)]

Los Acuerdos de gestión de devoluciones se utilizan para controlar diferentes métodos y bases para el cálculo de devoluciones y regalías. Incluyen reglas para inclusiones y exclusiones. Hay tres tipos de acuerdos de gestión de devoluciones: devoluciones de clientes, regalías de clientes y devoluciones de proveedores. Los tres tipos utilizan configuraciones similares. Este tema señala las diferencias donde existen.

## <a name="create-a-deal"></a>Crear un acuerdo

1. Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \> Todos los acuerdos de gestión de devoluciones**. En la página de la lista **Todos los acuerdos de gestión de devoluciones**, puede crear y trabajar con acuerdos de los tres tipos.

    También puede seguir uno de estos pasos. En cada caso, la página de lista que aparece proporciona las mismas configuraciones que la página de la lista **Todos los acuerdos de gestión de devoluciones**, pero está filtrada para mostrar acuerdos de un solo tipo.

    - Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \> Acuerdos de devoluciones para clientes** para crear solo acuerdos de devoluciones para clientes.
    - Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \> Acuerdos de regalías para clientes** para crear solo acuerdos de regalías para clientes.
    - Vaya a **Gestión de devoluciones \> Acuerdos de gestión de devoluciones \> Acuerdos de devoluciones para proveedores** para crear solo acuerdos de devoluciones para proveedores.

1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear acuerdo nuevo**, establezca los siguientes campos:

    - **Acuerdo de gestión de devoluciones** - Si tiene [configurada una secuencia numérica](rebate-management-parameters.md) en el caso de los acuerdos de devoluciones, este campo se establece automáticamente en un identificador exclusivo generado por el sistema. De lo contrario, introduzca un identificador único.
    - **Descripción**: escriba una descripción del acuerdo.
    - **Módulo**: seleccione el tipo de partner al que se aplica el trato (*Cliente* o *Distribuidor*). Dependiendo de la página desde la que comenzó, este campo puede configurarse automáticamente en función del tipo de oferta seleccionado. En este caso, el campo es de solo lectura.
    - **Tipo**: seleccione el tipo de acuerdo (*Devolución* o *Regalía*). Dependiendo de la página desde la que comenzó, este campo puede configurarse automáticamente en función del tipo de oferta seleccionado. En este caso, el campo es de solo lectura.
    - **Reconciliar por**: seleccione cómo se debe calcular y conciliar el acuerdo:

        - *Acuerdo*: se debe procesar una sola devolución para todas las devoluciones y deducciones en el acuerdo.
        - *Línea*: las devoluciones deben procesarse para cada línea de un acuerdo.

    - **Perfil de publicación**: selecciona el [perfil de publicación](rebate-management-posting.md) para utilizar en transacciones en las que se aplique el acuerdo. Este campo solo está disponible cuando el campo **Conciliar por** está establecido en *Acuerdo*. Si está configurado para *Línea*, asignará el perfil más tarde, para cada línea que agregue al acuerdo.
    - **Perfil de publicación de garantía**: seleccione el [perfil de publicación](rebate-management-posting.md) para utilizar en transacciones garantizadas. Los perfiles de publicación son necesarios para las transacciones garantizadas solo si la garantía se aplica a una regalía. De lo contrario, aunque un perfil de publicación no es obligatorio, si no se especifica ningún perfil de publicación, se mostrará un error cuando se publiquen las garantías. Este campo solo está disponible cuando el campo **Tipo** está establecido en *Regalía*. 
    - **Salida de devolución**: seleccione cómo se debe pagar la devolución o regalía:

        - *Financiero*: genera una nota de abono de texto sin formato o una nota de débito de proveedores, para que el dinero se pueda pagar o recibir más tarde. Tenga en cuenta que las disposiciones **pueden** utilizarse con devoluciones cuando se selecciona esta opción. Esta opción es la única opción disponible cuando el campo **Tipo** está establecido en *Regalía*.
        - *Artículo*: genere un pedido de ventas para artículos de acuerdo con la configuración del acuerdo. En este pedido de ventas, se asigna un precio de 0 (cero) a cada artículo. Tenga en cuenta que las provisiones **no pueden** utilizarse con devoluciones cuando se selecciona esta opción.

    - **Divisa de devolución**: seleccione la divisa que se utilizará cuando se pague la devolución, la deducción o la regalía.
    - **Notas del documento**: introduzca notas sobre el acuerdo, según sea necesario.
    - **Garantía acumulativa**: puede configurar esta opción en *Sí* solo si el campo **Tipo** está configurado en *Regalía*. Esta opción afecta el cálculo de los pagos de deducción garantizados. Este es un ejemplo:

        - La garantía del acuerdo es vender un valor que dará lugar a un pago de 10 000 $ por trimestre.
        - La organización que vende los bienes vende un valor que provoca un pago de deducción de 12 000 $ en el primer trimestre. El resultado es una regalía de 12 000 $ que se paga, menos la garantía de 10 000 $.
        - Si la opción **Garantía acumulativa** está establecida en *Sí*, los 2000 $ adicionales de regalías que se pagaron en el trimestre 1 se aplican al trimestre 2. Por lo tanto, el cliente tiene garantizados 8000 $ (la garantía de 10 000 $ menos el pago adicional de 2000 $).
        - En el segundo trimestre, registra las ventas que generan una regalía de 5000 $.
        - El sistema identifica un pago de 3000 $ (la garantía de 8000 $ menos los 5000 $ pagados en regalías).
        - Si la opción **Garantía acumulativa** está establecida en *No*, los 10 000 $ completos están garantizados cada trimestre. Esta garantía corresponde a un pago sugerido del pago de 5000 $ en el trimestre 2 (la garantía de 10 000 $ menos los 5000 $ pagados en regalías).

1. Seleccione **Aceptar** para crear el acuerdo y cerrar el cuadro de diálogo.

Este procedimiento crea el nivel de encabezado del nuevo acuerdo. A continuación, agregará líneas al acuerdo.

## <a name="add-lines-to-a-deal"></a>Agregar líneas a un acuerdo

Una vez que haya creado un acuerdo como se describe en la sección anterior, puede abrirlo desde la página de lista. Entonces puede agregar líneas para identificar a los clientes o proveedores, artículos, marcos de tiempo, una base y métodos de cálculo para el acuerdo. Un acuerdo puede tener una o varias líneas. Si un acuerdo tiene varias líneas, generalmente son del mismo tipo o se les asocian los mismos parámetros. Hasta que agregue líneas a un acuerdo, el acuerdo en realidad no hará nada.

1. Abra la página de lista de acuerdos de devoluciones correspondiente, como se describe en la sección anterior.
1. Encuentre y abra el acuerdo con el que desee trabajar.
1. En la ficha desplegable **Gestión de devoluciones**, seleccione uno de los siguientes botones para agregar una línea de acuerdo a la cuadrícula:

    - **Agregar línea**: agrega una nueva línea de acuerdo en blanco.
    - **Copiar línea**: si una línea de acuerdo existente se parece a la línea de acuerdo que desea agregar, puede seleccionar este botón para copiar y agregar una copia de la misma. La nueva línea de acuerdo incluirá todas las configuraciones de los detalles relacionados con la gestión de devoluciones. Entonces podrá editar la configuración. Por ejemplo, normalmente actualizará la relación de artículo y el porcentaje de devolución.

1. En la nueva línea de acuerdo, establezca los siguientes campos:

    - **Número de gestión de devoluciones**: si tiene [configurada una secuencia numérica](rebate-management-parameters.md) para números de gestión de devoluciones, este campo se establece automáticamente en un identificador exclusivo generado por el sistema. De lo contrario, introduzca un identificador único.
    - **Tipo**: el tipo de acuerdo al que se aplica la línea (*Devolución* o *Regalía*). El valor se copia del encabezado y no se puede cambiar.
    - **Descripción**: escriba una descripción de la línea de acuerdo.
    - **Compañía**: seleccione la empresa (entidad jurídica) a la que se aplica la línea de acuerdo. Durante el procesamiento, los usuarios solo pueden procesar las líneas de negocio que están asignadas a la empresa que están utilizando actualmente. La página de la lista **Acuerdos de devoluciones para clientes** proporciona una vista de varias empresas, basada en el acceso de seguridad del usuario. Sin embargo, puede editar y procesar devoluciones solo para la empresa que está utilizando actualmente.
    - **Código de cuenta**: seleccione el ámbito de clientes o proveedores a los que se aplica la línea de trato:

        - *Tabla*: la línea de acuerdo se aplica a un cliente o proveedor específico.
        - *Grupo*: la línea de acuerdo se aplica a un grupo de clientes o proveedores. Para obtener más información acerca de cómo configurar grupos, consulte [Grupos de gestión de devoluciones](rebate-management-groups.md).
        - *Todos*: la línea de acuerdo se aplica a todos los clientes o proveedores.

    - **Relación de cuenta**: si seleccionó *Tabla* en el campo **Código de cuenta**, seleccione el cliente o proveedor al que se aplica el acuerdo. Si ha seleccionado *Grupo*, seleccione el grupo de clientes o proveedores. Si ha seleccionado *Todos*, este campo no está disponible.
    - **Código de artículo**: seleccione el ámbito de artículos los que se aplica la línea de trato:

        - *Tabla*: la línea de acuerdo se aplica a un artículo específico.
        - *Grupo*: la línea de acuerdo se aplica a un grupo de artículos. Para obtener más información acerca de cómo configurar grupos, consulte [Grupos de gestión de devoluciones](rebate-management-groups.md).
        - *Todos*: la línea de acuerdo se aplica a todos los artículos.

    - **Relación de artículo**: si seleccionó *Tabla* en el campo **Código de artículo**, seleccione el artículo al que se aplica la línea de acuerdo. Si ha seleccionado *Grupo*, seleccione el grupo de artículos. Si ha seleccionado *Todos*, este campo no está disponible.
    - **(Parámetros de gestión de inventario)**: en los campos restantes de la línea de oferta, especifique valores para los parámetros de gestión de inventario que se utilizarán para definir los artículos que se incluyen en el acuerdo (como el tamaño, el color, el estilo, el sitio y el almacén del artículo). Para agregar o eliminar las dimensiones, seleccione **Dimensiones de la pantalla** en el Panel de acciones.

1. En el panel Acciones, seleccione **Guardar**.
1. Si desea limitar aún más el conjunto de elementos a los que se aplica una línea de acuerdo, seleccione la línea y, a continuación, en la ficha desplegable **Gestión de devoluciones**, seleccione **Filtrar** para abrir una ventana de diálogo de **Consulta** estándar.
1. Para cada línea de acuerdo que agregue, configure los detalles del cálculo y otros detalles en la ficha desplegable **Detalles de la gestión de devoluciones**, como se describe en la siguiente sección.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Agregar detalles de administración de devoluciones a una línea de acuerdo

Para cada línea de su acuerdo, debe configurar los detalles en la ficha desplegable **Detalles de la gestión de devoluciones**. Primero seleccione la línea de acuerdo en la ficha desplegable **Gestión de devoluciones**. Después establezca los valores para esa línea de acuerdo utilizando las distintas pestañas en la ficha desplegable **Detalles de la gestión de devoluciones**. En las siguientes subsecciones, se describe cómo usar cada pestaña.

### <a name="settings-on-the-general-tab"></a>Configuración en la pestaña General

La pestaña **General** en la ficha desplegable **Detalles de la gestión de devoluciones** le permite configurar el método de cálculo y la base para la línea de acuerdo seleccionada. Esta configuración controla si se requiere una compra mínima, los perfiles de publicación que están asociados con la línea de trato y los detalles del cálculo. En la tabla siguiente se describen los campos disponibles.

| Campo | Descripción |
|---|---|
| Método de cálculo | Seleccione el método que se utilizará cuando la línea de acuerdo seleccionada se combine con otras líneas de acuerdo (*Escalonado*, *Acumulativo*, *Recurrente*, o *Total*). El valor de este campo puede afectar drásticamente el resultado de sus cálculos de devolución. Para obtener una descripción completa de cada método y ejemplos que muestran cómo afecta el cálculo de la devolución, consulte la sección [Métodos de cálculo para líneas de acuerdo](#calc-methods) más adelante en este tema. |
| Base | Seleccione si el reembolso se aplica en función de la cantidad (es decir, el número total de unidades que se compran o venden) o el valor (es decir, el precio total de los bienes que se compran o venden). |
| Tipo de transacción | <p>Seleccione el punto del proceso en el que debe producirse el cálculo:</p><ul><li>*Pedido* - Utilice la cantidad o el valor pedidos como base para el cálculo.</li><li>*Entregado* - Utilice la cantidad o el valor entregados como base para el cálculo.</li><li>*Facturado* - Utilice la cantidad o el valor facturados como base para el cálculo.</li></ul> |
| Unidad | Si seleccionó *Cantidad* en el campo **Base**, seleccione la unidad en la que se debe especificar la cantidad. |
| Importe mínimo | Introduzca la cantidad mínima que debe pagarse por período. Puede introducir un valor negativo para permitir cantidades de devolución negativas si las notas de crédito exceden las ventas del período. |
| Principio de reducción de devolución | Seleccione el [principio de reducción de devolución](rebate-reduction-principle.md) que se aplica a la línea de acuerdo. |
| Número de variante | Si la línea de acuerdo se aplica a un artículo que tiene variantes, seleccione la variante a la que se aplica la línea de acuerdo. |
| Base de devolución de proveedor | <p>Este campo se muestra solo para devoluciones de proveedores (es decir, ofertas donde el campo **Módulo** está configurado en *Proveedor*). Seleccione la base para el reembolso del proveedor:</p><ul><li>*Pedido de compra* - La devolución que recibe el proveedor se basa en la cantidad o valor en la orden de compra.</li><li>*Pedido de ventas* - El proveedor recibe un descuento solo después de que se hayan vendido las mercancías. La devolución se basa en la cantidad o el valor del pedido de ventas.</li></ul> |
| Base de precio | <p>Este campo se muestra solo para devoluciones de proveedores (acuerdos donde el campo **Módulo** está configurado en *Proveedor*). Si seleccionó *Pedido de ventas* en el campo **Base de devolución del proveedor**, seleccione la base de precio aplicable:</p><ul><li><p>*FIFO* - La tarea periódica **Calcular el precio de compra FIFO** se debe ejecutar una para calcular la devolución. (Para ejecutar la tarea, vaya a **Gestión de devoluciones \> Tareas periódicas \> Calcular el precio de compra FIFO**). Se utilizará una regla de primero en entrar, primero en salir (FIFO) para calcular el valor de las existencias que se venden. Este valor luego se utilizará para calcular las devoluciones del proveedor. Este es un ejemplo:</p><ul><li>**Existencias vendidas:** 1000 unidades a 3 $ cada una = 3000 $</li><li>**Precio de compra actual, basado en FIFO:** 2 $</li><li>**Cálculo de trabajo:** *Unidades vendidas* × *Precio de compra actual* = 1000 × 2 $ = 2000 $</li></ul></li><li><p>*Último precio de compra* - El valor de la última transacción de compra se utilizará para calcular las devoluciones del proveedor. Este es un ejemplo:</p><ul><li>**Existencias vendidas:** 1000 unidades a 3 $ cada una = 3000 $</li><li>**Ultimo precio de compra:** 2 $</li><li>**Cálculo de trabajo:** *Unidades vendidas* × *Último precio de compra* = 1000 × 2 $ = 2000 $</li></ul></li><li><p>*Precio de compra medio* - El valor medio ponderado de los últimos *X* meses se utilizará para calcular las devoluciones del proveedor. Si selecciona esta opción, debe ingresar el número de meses en el campo **Número de meses** (que está disponible solo cuando el campo **Base de precio** está configurado en *Precio de compra medio*). Este es un ejemplo:</p><ul><li>**Existencias vendidas:** 1000 unidades a 3 $ cada una = 3000 $</li><li>**Precio medio de compra:** 2 $</li><li>**Cálculo de trabajo:** *Unidades vendidas* × *Precio de compra medio* = 1000 × 2 $ = 2000 $</li></ul></li><li><p>*Precio de venta* - El precio de venta se utilizará para calcular las devoluciones del proveedor. Este es un ejemplo:</p><ul><li>**Existencias vendidas:** 1000 unidades a 3 $ cada una = 3000 $</li><li>**Precio medio de compra:** 2 $</li><li>**Cálculo de trabajo:** *Unidades vendidas* × *Precio de venta* = 1000 × 3 $ = 3000 $</li></ul></li></ul> |
| Número de meses | Este campo se muestra solo para devoluciones de proveedores (acuerdos donde el campo **Módulo** está configurado en *Proveedor*). Si seleccionó *Precio de compra medio* en el campo **Base de precio**, introduzca el número de meses que se debe utilizar. |
| Perfil de contabilización | Seleccione el [perfil de publicación](rebate-management-posting.md) que se aplica a la línea de acuerdo seleccionada. Este perfil se usa solo cuando el campo **Reconciliar por** en el encabezado de la oferta está configurado en *Línea*. Si el campo **Reconciliar por** está configurado en *Acuerdo*, siempre se utiliza el perfil de contabilización que se establece en el encabezado del acuerdo. Si no hay perfil de contabilización en la línea del acuerdo, el perfil de contabilización que se establece es el usado en el encabezado del acuerdo. |
| Perfil de contabilización para la garantía | Este campo funciona como el campo **Perfil de contabilización**, pero se aplica solo a las regalías. |
| Tipo de pago | El tipo de pago para el perfil de contabilización seleccionado para el acuerdo. |
| Impuestos incluidos | Seleccione si la transacción incluye impuestos. La inclusividad fiscal es relevante solo cuando el campo **Base** está configurado en *Valor*. El importe de la factura se utilizará como importe con impuestos incluidos. Si el cálculo de la devolución se basa en un porcentaje, el sistema multiplicará el porcentaje de la devolución por la cantidad con impuestos incluidos. Tenga en cuenta que el cálculo utiliza el valor del impuesto sobre las ventas de la línea de oferta. |
| Incluir notas de abono | <p>Establezca esta opción en *Sí* para incluir notas de crédito en el cálculo de la devolución.</p><p>Si configura esta opción en *Sí*, el efecto varía, dependiendo del valor del campo **Tipo de transacción**:</p><ul><li>Si el campo **Tipo de transacción** está configurado en *Factura*, el cálculo tendrá en cuenta las notas de crédito. Esta configuración es la configuración habitual.</li><li>Si el campo **Tipo de transacción** está configurado en *Pedido*, el cálculo tendrá en cuenta tanto los pedidos de venta que tengan valores negativos como los pedidos devueltos abiertos.</li></ul> |
| Importe descontado | Establezca esta opción en *Sí* para basar el cálculo en el monto descontado del artículo o artículos en los casos en que se otorgan descuentos en la línea de oferta. |
| Solo facturas pagadas | Establezca esta opción en *Sí* si el cálculo debe considerar solo facturas totalmente pagadas. (En otras palabras, las devoluciones no se calcularán para facturas pagadas parcialmente). Esta opción está disponible solo cuando el campo **Tipo de transacción** está configurado en *Factura*. |
| Incluir facturas de servicios | Establezca esta opción en *Sí* para incluir facturas de servicios en el cálculo. Las facturas de servicios se pueden incluir solo para las líneas de oferta donde **Código del artículo** el campo está configurado en *Todo*. |
| Incluir descuento de liquidación | Establezca esta opción en *Sí* para reducir el descuento por el primer descuento de liquidación. Se asume que la organización tomará el primer descuento de liquidación. Establezca esta opción en *No* para permitir que el descuento de liquidación se utilice más tarde. |
| Notas de documentos | Introduzca notas que deben usarse como texto de transacción en las líneas del diario de transacciones de devolución. |

### <a name="settings-on-the-dates-tab"></a>Configuración en la pestaña Fechas

Los ajustes en la pestaña **Fechas** en la ficha desplegtable **Detalles de la gestión de devoluciones** definen la frecuencia y el tiempo de los cálculos que se especifican en la pestaña **General**. Ellos determinan cómo ocurren los cálculos en el momento del procesamiento.

Esta pestaña le permite especificar el rango de fechas para las que la línea de oferta seleccionada es válida y la frecuencia de cálculo. También puede especificar si la garantía debe publicarse y cuándo.

Puede utilizar los botones de la barra de herramientas para agregar líneas de fecha a la cuadrícula o eliminarlas. Si existen varias líneas de fecha, los intervalos de fechas válidos no deben superponerse. De lo contrario, recibirá un mensaje de error cuando intente guardar el acuerdo.

En la tabla siguiente se describen los campos disponibles para cada línea de fecha.

| Campo | Descripción |
|---|---|
| Fecha de inicio | Introduzca la primera fecha a la que se aplica la línea de fecha. Si las fechas "desde" y "hasta" se especifican en el encabezado de la oferta, se utilizan como valores predeterminados para cada nueva línea de fecha. |
| Fecha de finalización | Introduzca la última fecha a la que se aplica la línea de fecha. Si las fechas "desde" y "hasta" se especifican en el encabezado de la oferta, se utilizan como valores predeterminados para cada nueva línea de fecha. |
| Por | Especifique la frecuencia con la que se debe calcular la línea de acuerdo. Introduzca un número entero aquí y luego seleccione una unidad en el campo **Acumular por**. Por ejemplo, para calcular cada dos semanas, establezca el campo **Por** a *2* y el campo **Acumular por** a *Semanas*. |
| Acumular por | Seleccione la unidad que se aplica al ajuste **Por**. Seleccione *Duración* para calcular durante toda la vida útil de la línea de negociación. Seleccione *Periodo personalizado* para seleccionar un período definido en la contabilidad general. En este caso, también debe configurar el campo **Tipo de período**. |
| Tipo de período | Este campo solo está disponible cuando el campo **Acumular por** está establecido en *Período personalizado*. Los valores que están disponibles para la selección provienen de los tipos de período que se definen en la contabilidad general. |
| Primer día de la semana | Especifique cómo se identifican las semanas para el período. Este campo solo está disponible cuando el campo **Acumular por** está establecido en *Semanas*. |
| Notificación por | Especifique la frecuencia con la que se pueden reclamar las devoluciones por la línea de acuerdo. Introduzca un número entero aquí y luego seleccione una unidad en el campo **Notificar por**. |
| Notificar por | Seleccione la unidad que se aplica al ajuste **Notificar por**. Seleccione *Duración* para permitir reclamaciones solo una vez durante toda la vida útil de la línea de negociación. Seleccione *Periodo personalizado* para seleccionar un período definido en la contabilidad general. En este caso, también debe configurar el campo **Período de notificación**. |
| Tipo de período de notificación | Este campo solo está disponible cuando el campo **Notificar por** está establecido en *Período personalizado*. Los valores que están disponibles para la selección provienen de los tipos de período que se definen en la contabilidad general. |
| Proceso de registro | Seleccione esta casilla de verificación si la línea de notificación debe procesarse en el momento de la publicación. Esta opción solo está disponible para las líneas de acuerdo en las que el campo **Tipo de transacción** en la pestaña **General** está configurado en *Entregado* o *Factura*. Para provisiones, la provisión se contabilizará cuando se genere el albarán o factura. |
| Garantía por | Este campo solo se aplica a los acuerdos de regalías. Especifique la frecuencia con la que se debe calcular la garantía de la regalía durante el período definido por la configuración **Acumular por**. Introduzca un número entero aquí y luego seleccione un período de pago en el campo **Pago garantizado**. |
| Garantía pagada | <p>Este campo solo se aplica a los acuerdos de regalías. Funciona junto con el campo **Garantía por** para definir la frecuencia del cálculo de la garantía. Seleccione uno de los siguientes valores:</p><ul><li><p>*Comienzo del período* - La garantía se paga al inicio del período del contrato que se define para la línea de fecha. La garantía total se procesa primero. Solo se contabiliza como regalía el valor de las regalías que superen la cantidad garantizada. Este es un ejemplo:</p><ul><li>**Garantía mínima:** 10 000 $ durante dos meses.</li><li>**Mes 1:** se publicaron 10 000 $ como garantía y 0 $ en regalías.</li><li>**Mes 2:** se publicaron 2000 $ como regalías y 0 $ en garantías.</li><li>**Cálculo de trabajo:** *Garantía restante* - *Regalías contabilizadas* = 0 $ - 2000 $ = - 2000 $.</li></ul><p>Debido a que se requiere un pago de regalías de 2 000 $, se crea un diario para 2 000 $.</p><p>**Nota:** la garantía debe calcularse y contabilizarse junto con la provisión de deducciones para el primer período.</p></li><li><p>*Fin del período* - La garantía no se paga hasta el final del acuerdo de deducciones, según se define en la línea de fecha. Este es un ejemplo:</p><ul><li>**Garantía mínima:** 10 000 $ durante dos meses.</li><li>**Mes 1:** 5000 $ se publicaron como regalías y se creó un diario.</li><li>**Mes 2:** 7000 $ se publicaron como regalías y se creó un diario.</li><li>**Cálculo de trabajo:** debido a que las regalías exceden el monto de la garantía, los $0 se incluyen en la garantía.</li></ul><p>**Nota:** la garantía debe calcularse y contabilizarse solo junto con la provisión de deducciones y descuentos para el período final.</p></li></ul> |
| Mínimo de garantía | Este campo solo se aplica a los acuerdos de regalías. Ingrese la cantidad del mínimo de la garantía para una regalía, en la moneda que se define en el encabezado del acuerdo. |

### <a name="settings-on-the-lines-tab"></a>Configuración en la pestaña Líneas

La pestaña **Líneas** en la ficha desplegable **Detalles de la gestión de devoluciones** le permite definir el de cálculo de líneas para la línea de acuerdo seleccionada. Cada línea de cálculo establece un umbral de cantidad o valor y una cantidad o artículos de compensación relacionados. El campo **Base** en **General** especifica si cada línea de cálculo se basa en una cantidad o un valor.

Puede utilizar los botones de la barra de herramientas para agregar líneas de cálculo a la cuadrícula o eliminarlas. Puede tener cualquier número de líneas de cálculo. Sin embargo, si existen varias líneas de cálculo, los rangos de cantidad o valor "hasta" y "desde" no deben superponerse.

En la tabla siguiente se describen los campos disponibles para cada línea de cálculo.

| Campo | Descripción |
|---|---|
| De cantidad / valor | Introduzca la cantidad mínima o el valor al que se aplica la línea de cálculo. |
| A cantidad / valor | Introduzca la cantidad máxima o el valor al que se aplica la línea de cálculo. |
| Método de gestión de devoluciones | <p>Este campo está disponible solo para ofertas en las que el campo **Rebaja de salida** en el encabezado está configurado en *Financiero*. Seleccionar el método que se desea utilizar para calcular la devolución:</p><ul><li>*Fijo*: se utiliza una cantidad de precio fijo para la línea.</li><li>*Por ciento*: se utiliza un porcentaje del importe de la venta.</li><li>*Tasa*: se utiliza un precio fijo por pedido.</li></ul><p>**Importante:** recomendamos encarecidamente que utilice el mismo método para cada línea de cálculo en la pestaña **Líneas**. Si se requiere un nuevo método, cree una nueva línea de trato. Recuerde que puede utilizar el botón **Copiar línea** en la ficha desplegable **Gestión de devoluciones** para crear una nueva línea de oferta a partir de una línea de oferta existente.</p><p>**Nota:** si el campo **Rebaja de salida** está configurado en *Artículo*, este campo siempre se establece en *Fijo*. Para obtener más información sobre cómo especificar los elementos, consulte el texto que sigue a esta tabla. |
| Cantidad de gestión de devoluciones | Este campo está disponible solo para ofertas en las que la **Rebaja de salida** en el encabezado está configurada en *Financiero*. Introduzca la cantidad que debe usarse para calcular el reembolso, según el método que seleccionó en el campo **Método de gestión de devoluciones**. |

Como se mencionó en la tabla anterior, para las transacciones en las que el campo **Devolución de salida** en el encabezado está configurado en *Artículo*, debe especificar los elementos que se proporcionarán para cada línea de cálculo en la pestaña **Líneas**. Para especificar los elementos, siga estos pasos.

1. En la pestaña **Líneas**, cree la línea de cálculo requerida si no existe y selecciónela.
1. Si el acuerdo no se ha guardado desde que creó la línea de cálculo, seleccione **Guardar** en el Panel de acciones.
1. En la pestaña **Líneas**, seleccione **Artículos**.
1. En la página **Artículos**, utilice los botones del Panel de acciones para agregar elementos a la cuadrícula o eliminar elementos, según sea necesario. Para cada fila, establezca los siguientes campos:

    - **Número de artículo**: seleccione el artículo que se le proporcionará.
    - **(Otras dimensiones)**: si debe usar más dimensiones para definir el artículo (por ejemplo, configuración del artículo, tamaño, color, estilo, sitio o almacén), especifíquelas. Para agregar o eliminar las dimensiones disponibles, seleccione **Dimensiones de la pantalla** en el Panel de acciones.
    - **Cantidad**: introduzca la cantidad que se proporcionará después de que se alcance el umbral para la línea de cálculo seleccionada.
    - **Unidad**: seleccione la unidad en que se específica el valor **Cantidad**.
    - **Múltiple**: este campo funciona junto al campo **Cantidad**. Por ejemplo, en una línea de artículo, establezca el campo **Cantidad** a *2* y el campo **Múltiple** a *100*. Si luego tiene una cantidad total de pedido de venta de 150, dos de los artículos serán gratuitos (dos por cada 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Configuración en la pestaña la ficha Dimensiones de inventario

La pestaña **Dimensiones de inventario** en la ficha desplegable **Detalles de la gestión de devoluciones** muestra todos los valores de dimensión disponibles para el producto que se especifica para la línea de oferta seleccionada. Incluye dimensiones que no se muestran en la ficha desplegable **Gestión de devoluciones**. Puede editar valores solo para aquellas dimensiones que se aplican al producto seleccionado.

Puede agregar más dimensiones a la cuadrícula en la ficha desplegable **Gestión de devoluciones** seleccionando **Dimensiones de la pantalla** en el Panel de acciones.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Métodos de cálculo para líneas de acuerdo

Cada vez que configure detalles para una de sus líneas de acuerdo, como se describe en la sección anterior, debe seleccionar el método de cálculo para esa línea. Esta sección explica cada método de cálculo y proporciona ejemplos que muestran cómo cada método calcula la devolución total para pedidos y líneas de acuerdo. En estos ejemplos, los pedidos y las líneas de acuerdo son idénticos. Solo los métodos de cálculo difieren.

### <a name="stepped-calculation-method"></a>Método de cálculo escalonado

El método de cálculo escalonado calcula paso a paso, donde cada línea de oferta contribuye de forma incremental al reembolso hasta que se alcanza la cantidad o el valor de las ventas. Los pasos pueden basarse en la cantidad o el valor de los bienes que se venden, dependiendo de la configuración del campo **Base** campo en la pestaña **General** de la ficha desplegable **Detalles de la gestión de reembolsos**.

Por ejemplo, se configura una línea de trato para que el **Método de cálculo** está configurado en *Escalonado* y el campo **Base** está configurado en *Valor*. Incluye líneas de cálculo que proporcionan los siguientes descuentos:

- **Línea A:** 10 por ciento hasta 1000 $
- **Línea B:** 25 por ciento hasta 2500 $

Si el valor de los bienes comprados o vendidos es 2000 $, el descuento resultante de 350 $ se calcula de la siguiente manera:

- **Devolución (A):** *Umbral (A)* × *Porcentaje (A)* = 1000 $ × 10 por ciento = $100
- **Devolución (B):** (*Valor vendido* - *Umbral (A)*) × *Porcentaje (B)* = (2000 $ - 1000 $) × 25 por ciento = 250 $
- **Devolución total:** *Devolución (A)* + *Devolución (B)* = 100 $ + 250 $ = 350 $

Si el campo **Base** el campo está configurado en *Cantidad* en vez de *Valor*, el método de cálculo escalonado funciona de manera similar. El primer paso se utiliza para la cantidad identificada hasta que se alcanza el segundo paso. El segundo paso se utiliza entonces para toda la cantidad sobre el primer paso, hasta que se llega al tercer paso. Este proceso continúa luego a través de todos los pasos posteriores.

### <a name="cumulative-calculation-method"></a>Método de cálculo acumulativo

El método de cálculo acumulativo utiliza solo una línea de cálculo para calcular la devolución. Si hay varias líneas de cálculo disponibles para la línea de trato, la línea de cálculo de valor más alto o de cantidad más alta que se alcanza se usa para la cantidad o valor total. Al igual que los otros métodos de cálculo, el método acumulativo utiliza la configuración del campo **Base** en la pestaña **General** de la ficha desplegable **Detalles de la gestión de devoluciones** para determinar si la cantidad de ventas o el valor de ventas se utilizan para calcular los reembolsos.

Por ejemplo, se configura una línea de trato para que el **Método de cálculo** está configurado en *Acumulativo* y el campo **Base** está configurado en *Valor*. Incluye líneas de cálculo que proporcionan los siguientes descuentos:

- **Línea A:** 10 por ciento hasta 1000 $
- **Línea B:** 25 por ciento hasta 2500 $

Si el valor de los bienes comprados o vendidos es 2000 $, el cálculo usa solo la línea B. La devolución resultante de 500 $ se calcula de la siguiente forma:

- **Devolución total:** *Valor vendido* × *Devolución (B)* = 2000 $ × 25 por ciento = 500 $

### <a name="rolling-calculation-method"></a>Método de cálculo continuo

El método de cálculo continuo calcula todas las líneas de cálculo posibles para el trato. Si hay varias líneas de cálculo y se alcanza más de una, se utilizarán todas las líneas de cálculo que se alcancen, pero los umbrales superiores se aplican a cada porcentaje. Al igual que los otros métodos de cálculo, el método continuo utiliza la configuración del campo **Base** en la pestaña **General** de la ficha desplegable **Detalles de la gestión de devoluciones** para determinar si la cantidad de ventas o el valor de ventas se utilizan para calcular los reembolsos.

Por ejemplo, se configura una línea de trato para que el **Método de cálculo** está configurado en *Continuo* y el campo **Base** está configurado en *Valor*. Incluye líneas de cálculo que proporcionan los siguientes descuentos:

- **Línea A:** 10 por ciento hasta 1000 $
- **Línea B:** 25 por ciento hasta 2500 $

Si el valor de los bienes comprados o vendidos es 2000 $, el descuento resultante de 600 $ se calcula de la siguiente manera:

- **Devolución (A):** *Umbral (A)* × *Porcentaje (A)* = 1000 $ × 10 por ciento = $100
- **Reembolso (B):** *Valor vendido* × *Porcentaje (B)* = 2000 $ × 25 por ciento = 500 $
- **Devolución total:** *Devolución (A)* + *Devolución (B)* = 100 $ + 500 $ = 600 $

### <a name="total-calculation-method"></a>Método de cálculo total

El método de cálculo total utiliza todas las líneas de cálculo para calcular la devolución. Aplica la cantidad total para calcular la devolución para cada línea de cálculo que se alcanza, y cada línea de cálculo aplica su porcentaje a la cantidad total. Al igual que los otros métodos de cálculo, el método total utiliza la configuración del campo **Base** en la pestaña **General** de la ficha desplegable **Detalles de la gestión de devoluciones** para determinar si la cantidad de ventas o el valor de ventas se utilizan para calcular los reembolsos.

Por ejemplo, se configura una línea de trato para que el **Método de cálculo** está configurado en *Total* y el campo **Base** está configurado en *Valor*. Incluye líneas de cálculo que proporcionan los siguientes descuentos:

- **Línea A:** 10 por ciento hasta 1000 $
- **Línea B:** 25 por ciento hasta 2500 $

Si el valor de los bienes comprados o vendidos es 2000 $, el descuento resultante de 700 $ se calcula de la siguiente manera:

- **Reembolso (A):** *Valor vendido* × *Porcentaje (A)* = 2000 $ × 10 por ciento = 200 $
- **Reembolso (B):** *Valor vendido* × *Porcentaje (B)* = 2000 $ × 25 por ciento = 500 $
- **Devolución total:** *Devolución (A)* + *Devolución (B)* = 200 $ + 500 $ = 700 $
