---
title: Administración de costes descargados frente a transporte
description: Microsoft Dynamics 365 Supply Chain Management proporciona dos módulos diferentes para trabajar con el transporte, la gestión del transporte (TMS) y el costo de aterrizaje. Este tema resume la funcionalidad que los dos módulos tienen en común y destaca las diferencias entre ellos.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c7bc17cad246f4bdb9c2bc63cbc47d05731ad2ac
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021233"
---
# <a name="landed-cost-vs-transportation-management"></a>Administración de costes descargados frente a transporte

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management proporciona dos módulos diferentes para trabajar con el transporte: **gestión del transporte** (TMS) y **coste descargado**. Este tema resume la funcionalidad que los dos módulos tienen en común y destaca las diferencias entre ellos. Puede utilizar esta información para decidir qué módulo se adapta mejor a sus prácticas comerciales. Es posible que descubra que algunas prácticas comerciales funcionan mejor con TMS, mientras que otras funcionan mejor con el costo de aterrizaje. Luego, dependiendo de los requisitos de su negocio, puede optar por utilizar un módulo exclusivamente, o puede combinar los dos módulos.

Este tema no es una revisión completa de todas las características de ninguno de los módulos. En cambio, destaca la funcionalidad disponible en lo que respecta al transporte de mercancías desde un proveedor hasta el almacén de su empresa, donde se pueden consumir.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminología, datos de referencia y diferencias en los informes

### <a name="terminology-comparison"></a>Comparación de terminología

TMS y coste descargado usan términos diferentes para conceptos similares. La siguiente tabla resume estos términos y su uso en los dos módulos.

| Término de TMS | Término de coste descargado | Notas |
|----------|------------------|-------|
| **Cargar**<p>Una *carga* es una colección de envíos que se transportan simultáneamente en la misma unidad de transporte (como un camión o un barco). Las cargas pueden ser entrantes o salientes.</p> | **Viaje**<p>Normalmente, un *viaje* es un solo barco que viaja a lo largo de un solo *viaje*. Un viaje puede contener varios *contenedores de envío* y también puede incluir pedidos entrantes de diferentes entidades legales de su organización. Los viajes solo pueden ser entrantes.</p> | TMS también usa el término *número de viaje*, que se refiere a un campo de información donde puede ingresar un identificador. Sin embargo, ninguna funcionalidad está asociada con el campo TMS y no está relacionada con el *viaje* concepto en costo de aterrizaje. |
| **Ruta**<p>Una *ruta* es la ruta física de un transporte desde el origen hasta el destino.</p> | **Recorrido**<p>Un *recorrido* es la ruta física de un transporte desde el origen hasta el destino. Cada viaje debe asignarse a un viaje.</p> | |
| **Tramos de ruta**<p>Una ruta puede tener múltiples *segmentos de ruta*, cada uno de los cuales representa un paso del viaje. Una ruta puede incluir múltiples operadores o servicios, cada uno de los cuales se considera un segmento de ruta.</p> | **Escalas**<p>Cada recorrido puede tener múltiples *tramos*, cada uno de los cuales representa un paso del recorrido. Un tramo puede ser parte del transporte, el manejo de tareas u otra actividad.</p> | |
| **Contenedores**<p>Un *contenedor* puede ser cualquier tipo de paquete o embalaje que utilice TMS.</p> | **Contenedores de envío**<p>Un *contenedor de envío* es un contenedor de envío físico literal, como se conoce de los buques portacontenedores.</p> | |
| **Códigos de mercancías**<p>En TMS (y en otros lugares en Supply Chain Management), los *códigos de producto* identifican tipos de productos básicos. Pueden afectar las tarifas, el manejo de materiales peligrosos, etc.</p> | **Códigos de mercancías**<p>En el costo descargado, los *códigos de producto* se establecen a nivel de entidad jurídica. Se usan principlamente a efectos de notificación.</p> | El costo de entrega también puede usar los códigos de productos que se usan para TMS y otros lugares en Supply Chain Management. Sin embargo, los códigos de productos básicos de costo en tierra se utilizan solo por costo en tierra. |

### <a name="some-reference-data-isnt-shared"></a>Algunos datos de referencia no se comparten

TMS y Landed cost no comparten datos de referencia para entidades como configuración de costos, viajes y tramos. Si usa ambos módulos, debe volver a crear los datos de referencia no compartidos.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>Los informes de empresas vinculadas no funcionan con mercancías en tránsito

Los siguientes informes no funcionan junto con la función de mercancías en tránsito que proporciona el costo de aterrizaje:

- [Informe de totales de mercancía en tránsito de empresas vinculadas](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Informe de totales de mercancía en tránsito de empresas vinculadas](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Estos informes asumen que las mercancías se ponen en tránsito tan pronto como se emite un albarán de venta y que se incluyen en el inventario desde el tránsito al recibirlas. Sin embargo, las mercancías en tránsito no se procesan de esta manera. Por lo tanto, si utiliza las funciones de mercancías en tránsito y de empresas vinculadas juntas, los resultados de ambos informes serán incorrectos.

## <a name="using-the-two-modules-together"></a>Usando los dos módulos juntos

Puede utilizar TMS para operaciones entrantes y salientes. Aunque el costo de aterrizaje proporciona la mayor parte de la misma funcionalidad básica que TMS para las operaciones entrantes, también agrega algunas funcionalidades. Por lo tanto, es posible que desee considerar el uso de TMS para las operaciones de salida y el costo de aterrizaje para las operaciones de entrada.

En general, no recomendamos que utilice ambos módulos juntos para operaciones entrantes. Debe utilizar el módulo que mejor se adapte a sus requisitos. Si usa los dos módulos juntos, no debe compartir documentos fuente entre ellos. Por ejemplo, no utilice la misma orden de compra para una carga en TMS y un viaje en el costo de aterrizaje. En particular, debe asegurarse de no configurar el sistema para crear cargas entrantes automáticamente. Si los artículos de las órdenes de compra se incluyen en un viaje, no se pueden manipular como parte de una carga.

## <a name="goods-in-transit"></a>Mercancía en tránsito

Una de las características principales del costo de aterrizaje es su capacidad para procesar mercancías en tránsito. El procesamiento de mercancías en tránsito le permite asumir la propiedad financiera de los artículos enviados antes de que se reciban físicamente en el almacén de destino. El procesamiento de mercancías en tránsito suele ser necesario para el comercio internacional.

### <a name="tms-goods-in-transit-features"></a>Características de mercancía en tránsito de TMS

Actualmente, TMS no admite el procesamiento de mercancías en tránsito.

### <a name="landed-cost-goods-in-transit-features"></a>Características de bienes de desembarque en tránsito

El procesamiento de mercancías en tránsito es una característica principal del costo de aterrizaje y proporciona la siguiente funcionalidad:

- **Almacenes de mercancías en tránsito** - Se puede asociar un almacén de mercancías en tránsito con cada almacén en Supply Chain Management. Las mercancías se transfieren a las mercancías en los almacenes de tránsito después de facturar la orden de compra original. Los artículos que se reservan físicamente allí dejan de estar disponibles para el consumo hasta que se reciben en su almacén físico. Por lo tanto, puede asumir la propiedad financiera de los bienes facturando la orden de compra.
- **Cuenta del libro mayor de mercancías en tránsito** - El costo de entrega agrega una cuenta de registro del libro mayor general específica al perfil de registro de la orden de compra para manejar las mercancías en proceso de tránsito. Esta cuenta del libro mayor de mercancías en tránsito actúa como una cuenta del tipo "mercancías facturadas no recibidas". Cuando se factura la orden de compra original y se crean las mercancías en tránsito, el costo directo de la orden de compra se contabiliza en la cuenta del libro mayor general de mercancías en tránsito hasta que las mercancías se reciben en su ubicación física final.
- **Actualizaciones de control de seguimiento** - Los pedidos de mercancías en tránsito admiten la funcionalidad de control de seguimiento en el costo de entrega. El control de seguimiento le permite actualizar la fecha prevista de llegada de las mercancías mientras están en tránsito. Luego, el control de seguimiento actualiza el viaje y las líneas de orden de compra asociadas. La fecha de entrega prevista está disponible para la planificación maestra y la logística.
- **Activación de transacciones por encima / por debajo** - Si se produce una variación entre los bienes esperados en una línea de viaje y los bienes reales que se reciben en el almacén, el costo de destino lo resuelve creando transacciones por encima y / o por debajo. Luego, puede administrar estas transacciones, según la forma en que desee procesarlas, a través de una orden de compra o un diario de movimientos. Las transacciones por encima y por debajo proporcionan un enlace al viaje, la orden de compra original y el nuevo diario de movimiento u orden de compra para la variación.
- **Pedidos de mercancías en tránsito** - El costo de entrega introduce un nuevo documento de origen que se conoce como *pedido de mercancías en tránsito*. Una orden de mercancías en tránsito le permite facturar la orden de compra original para tomar posesión financiera de los artículos. Cuando se factura la orden de compra, se crea el nuevo documento de origen para cada línea de la orden de compra que tiene una combinación de dimensiones de inventario. Luego, las mercancías se mueven físicamente a un almacén de mercancías en tránsito, donde se reservan físicamente para las mercancías en tránsito y no se pueden consumir a menos que se reciban las mercancías en tránsito.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Cargos varios y costos de envío

Uno de los aspectos más importantes de la gestión de envíos y envíos de mercancías es el reconocimiento de los gastos generales asociados con los envíos. Estos costos generales no son los costos directos de inventario que están asociados con una orden de compra y un envío o viaje. En cambio, son costos adicionales que se introducen por la naturaleza del movimiento de las mercancías del proveedor a su organización. Estos costos pueden incluir costos de flete que están asociados con el envío de bienes de un lugar físico a otro, o costos de impuestos que están asociados con la importación de bienes de un proveedor extranjero.

El costo de destino maneja estos costos mediante la creación de un nuevo tipo de estructura de costos que se conoce como *costes automáticos*. TMS maneja estos costos mediante el uso de funciones de cargo diversas.

### <a name="tms-charge-and-cost-features"></a>Funciones de cargo y costo de TMS

TMS utiliza cargos varios para administrar los costos adicionales de las cargas que se asignan a las líneas del documento fuente relacionadas. Estos cargos varios se pueden establecer en el nivel de la línea de la orden de compra o del encabezado de la orden de compra.

En TMS, los cargos varios se pueden prorratear o dividir por el peso, el volumen o la cantidad del inventario. Los cargos se pueden dividir por flete o cargos adicionales. Se requerirá un mayor desarrollo para utilizar métodos de reparto adicionales en TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Cargos por costo de entrega y características de costo

El costo de entrega proporciona un conjunto de funciones de costo que manejan los costos adicionales asociados con el envío de mercancías. Estos costos se conocen como costes automáticos y se aplican en el momento de la facturación inicial del envío utilizando el monto del costo estimado. Cada tipo de coste se gestiona en su propia contabilización. Una vez que se registran las facturas reales de los costos generales, los costos estimados se actualizan automáticamente para reflejar los costos reales.

Además, los costos generales asociados con el envío de mercancías se pueden facturar durante el viaje desde el puerto de origen o en cualquier momento después de la recepción de las mercancías. Esta capacidad proporciona una mayor flexibilidad para el consumo de bienes.

La siguiente lista describe algunos conceptos para las características de cargo y costo en el costo de entrega:

- **Área de costo** - Los costos y cargos se pueden asignar a diferentes niveles, o *áreas de costo*, en un viaje. El costo se puede aplicar a nivel de viaje y desglosar a cada artículo del viaje. Además, los costos se pueden aplicar a nivel del contenedor, orden de compra, artículo u orden de transferencia. Cada cargo por costo se puede administrar por separado en las distintas áreas y se desglosa en un costo por artículo.
- **Métodos de reparto** - Varios métodos de reparto están disponibles en el costo de entrega. Los cargos por costos se pueden distribuir por cantidad, monto en dólares, valor, peso, volumen, medición o una medida volumétrica definida por el usuario.
- **Control de compensación / variación** - Los cargos de costo se configuran como su propio tipo de código de costo en el costo de entrega. Cada tipo de código de costo le permite definir una cuenta de compensación para los cargos de costos estimados, y también cuentas de variación del precio de acumulación y de compra para las variaciones en los costos estimados frente a los costos reales. Cuando los costos estimados se contabilizan inicialmente, hay un crédito en la cuenta de compensación. Una vez que se contabilizan las facturas reales, se contabilizan los cargos por costos reales y los costos estimados se cargan de la cuenta de compensación.

## <a name="matching-freight-bills-and-invoices"></a>Conciliación de albaranes de flete y facturas

### <a name="tms-bill-and-invoice-matching-features"></a>Facturas de TMS y funciones de conciliación de facturas

TMS puede hacer coincidir las facturas de flete que contienen costos y facturas estimados con el costo real del flete. Las facturas se pueden recibir de manera electrónica o en papel. La variación coincidente entre el costo estimado y el costo real no afecta la valoración del inventario.

Para más información, vea [Conciliar el flete en la gestión del transporte](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Facturas de coste descargado y funciones de conciliación de facturas

El costo de entrega puede hacer coincidir las facturas de flete con los costos estimados y puede facturar los costos reales a los costos estimados. En el momento de la facturación, los gastos de transporte están en un diario de facturas y los costos estimados se eliminan de la cuenta de compensación. Además, los cargos de costo reales se contabilizan contra el costo de los bienes vendidos para el artículo, junto con las variaciones entre los cargos estimados y los cargos reales. Este comportamiento permite flexibilidad en el proceso de facturación.

## <a name="tracking"></a>Seguimiento

Una característica importante tanto del TMS como del costo de aterrizaje es la capacidad de rastrear las mercancías e identificar dónde se encuentran en el viaje desde el punto de origen hasta el almacén de destino final. El seguimiento le permite seguir y actualizar dónde se encuentran las mercancías y cuándo se espera que lleguen al almacén para su consumo. Además del estado de las mercancías durante su viaje, el costo de aterrizaje proporciona fechas esperadas y reales para cada paso del viaje.

### <a name="tms-tracking-features"></a>Funciones de seguimiento de TMS

TMS proporciona funciones limitadas para rastrear cargas entrantes. Muestra fechas y permite construir una integración para encontrar la posición exacta (por ejemplo, en la página **Estado de transporte**).

Para cada segmento de ruta, puede ingresar horarios estimados y tiempos de llegada.

### <a name="landed-cost-tracking-features"></a>Funciones de seguimiento de costos de destino

El costo de aterrizaje puede proporcionar un control de seguimiento para cada viaje, desde el puerto de origen hasta el destino final. El control de seguimiento establece el estado del viaje. El estado indica si el viaje está navegando, en la aduana para inspección o en la entrega local de camino al almacén final. El estado se puede establecer en el nivel de la línea de la orden de compra, el contenedor y el encabezado del viaje. Por lo tanto, tiene un control más granular.

Además, una fecha esperada confirmada que se basa en tiempos de entrega especificados se asocia con cada paso de un viaje. Las fechas de entrega confirmadas y esperadas se agregan a la línea de la orden de compra y las mercancías en las órdenes de tránsito, y se pueden utilizar para la planificación maestra y la logística. Además de las fechas previstas, se pueden actualizar las fechas reales. Los siguientes pasos de un viaje se actualizarán en consecuencia.

## <a name="multi-leg-journeys"></a>Recorridos con varias escalas

El concepto de viaje identifica dónde se encuentran las mercancías en el proceso y controla el estado de las mercancías mientras están en tránsito. Los bienes pueden atravesar varios tramos de un viaje y puede asociar varios costos con un tramo específico. Los ejemplos incluyen un costo de flete en la navegación de un barco y los costos de transporte local en el transporte de mercancías desde el puerto hasta el destino.

### <a name="tms-multi-leg-journey-features"></a>Funciones de viaje de varios tramos de TMS

En TMS, las rutas se pueden dividir en segmentos de ruta para representar viajes de varios tramos. TMS puede asignar tarifas puntuales y cargos adicionales a segmentos de ruta individuales.

Para más información, vea [Planificar rutas de transporte de carga con múltiples paradas](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Características de viaje de varios tramos con costo de aterrizaje

El costo de aterrizaje proporciona un marco para mover mercancías desde el punto de origen hasta el destino a través de una serie de tramos, que son las paradas o pasos en un viaje. Los tramos se combinan para crear plantillas de viaje, que definen cómo se mueven las mercancías del proveedor a su organización.

En cada tramo de un viaje, puede definir aún más el estado de cada línea de orden de compra y los plazos de entrega asociados a ella. El tiempo de entrega combinado de todos los tramos se utiliza para identificar la fecha de entrega estimada. Sin embargo, se requiere procesamiento de mercancías en tránsito para que se apliquen los viajes de varios tramos. El viaje de mercancías en un viaje se gestiona en una tabla que es específica del costo de aterrizaje.

## <a name="receiving-by-container"></a>Recibiendo por contenedor

Puede ser importante gestionar cómo se dividen y almacenan las mercancías en un buque. En un barco, las mercancías se pueden guardar en un contenedor o en varios contenedores. Cuando se reciben mercancías, se reciben en contenedores, y los diferentes contenedores de un viaje pueden recibirse en diferentes momentos o en diferentes fechas.

Tanto el TMS como el Landed cost proporcionan funcionalidad para administrar la recepción de mercancías en un contenedor. TMS utiliza el concepto de cargas para administrar las mercancías, las órdenes de compra y las órdenes de transferencia que están asociadas con un contenedor de envío. TMS admite la recepción sobre la base de una estructura de embalaje que se recibe a través de un aviso de envío anticipado (ASN). El costo de aterrizaje utiliza el concepto de contenedores de envío para procesar las órdenes de compra y controlar los costos generales asociados con un contenedor en un barco.

### <a name="tms-receiving-by-container-features"></a>Características de recepción por contenedor en TMS

TMS admite ASN entrantes, todas las variantes de recepción a través de la aplicación móvil Warehouse Management y todos los métodos de recepción a través del cliente de Supply Chain Management.

### <a name="landed-cost-receiving-by-container-features"></a>Características de recepción por contenedor en el coste descargado

Para respaldar la recepción por contenedor, Landed Cost crea registros de contenedores de envío y asocia las órdenes de compra con un contenedor de envío específico mediante el uso de su ID de contenedor. Los costos generales se pueden aplicar a ese contenedor de envío y desglosarlos para que estén asociados con las órdenes de compra relevantes.

Los contenedores con costo de entrega se pueden recibir a través de un nuevo tipo de recibo que se conoce como *recibo de mercancías en tránsito*, a través de diarios de llegada, o mediante la recepción de dispositivos móviles. Cuando se utilizan diarios de llegada, las cantidades se pueden inicializar a partir de las mercancías en la orden de tránsito o las líneas de la orden de compra original en el contenedor. El costo de entrega proporciona dos tipos de trabajo para recibir a través de la aplicación móvil Warehouse Management.

El costo de entrega no proporciona un ASN para la recepción electrónica de mercancías. Además, no admite los flujos de aplicación móvil Warehouse Management que procesan la recepción de carga, la recepción de matrículas o la recepción de matrículas mixtas.

## <a name="rate-shopping-by-vendor"></a>Calificar las compras por proveedor

La compra de tarifas permite a una empresa seleccionar un proveedor de transporte en función del precio más bajo, la ruta más rápida o una combinación de ambas consideraciones.

### <a name="tms-rate-shopping-features"></a>Funciones de compra de tarifas de TMS

TMS le permite identificar proveedores y soluciones de enrutamiento para pedidos entrantes y salientes. Por ejemplo, puede identificar la ruta más rápida o la tarifa menos cara para un envío.

TMS proporciona optimización de carga y compras de tarifa completa a través del banco de trabajo de ruta de tarifas, opciones de calificación flexibles a través del motor de calificación, un motor de calificación API para integración con partes externas y soporte para peso volumétrico.

Para más información, vea [Motores de gestión del transporte](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Funciones de compra con tarifa de costo aterrizado

El costo de destino proporciona solo un soporte limitado para la compra de tarifas por parte del proveedor. Aunque puede ingresar los valores del transportista, el costo de entrega no los compara entre varios proveedores.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Registro de entrada / salida del conductor con programación de citas

Las funciones de registro de entrada y salida del conductor permiten que el sistema controle las llegadas y evite la congestión en los muelles de carga.

### <a name="tms-driver-check-incheck-out-features"></a>Características de registro de entrada y de salida del conductor para TMS

TMS permite crear *citas*. Una cita representa eventos que se producen en un muelle para recibir un pedido de compra, enviar un pedido de ventas o procesar una carga de entrada o salida en una fecha y hora específicas. Las citas garantizan que los muelles estén disponibles para cargar y descargar mercancías, y ayudan a prevenir situaciones en las que varios transportistas llegan a un lugar al mismo tiempo.

El sistema permite que los conductores se registren en una puerta de muelle específica.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Características de registro de entrada y salida del conductor para coste descargado

El costo descargado puede almacenar estimaciones para la fecha y hora en que se entregará un contenedor.

## <a name="transfer-orders-and-additional-costs"></a>Órdenes de transferencia y costos adicionales

A menudo, las empresas deben poder transferir mercancías entre almacenes. Cuando se produce este tipo de transferencia, los costos están asociados y es posible que desee reconocer esos costos. En el costo de aterrizaje, las órdenes de transferencia se pueden agregar a un viaje o nave para rastrear el movimiento de mercancías de un almacén o sitio a otro, estimar el tiempo de entrega y la fecha de entrega esperada y agregar costos generales a la transferencia de mercancías.

### <a name="tms-transfer-order-cost-features"></a>Características de costo de la orden de transferencia TMS

TMS admite la creación de cargos de flete que están conectados a transferencias. Aunque estos cargos se pueden ver en la orden de transferencia, el costo de entrega no se agrega al costo del artículo. La conciliación del flete se respalda mediante la creación de una factura de flete que se basa en estos cargos. Luego, esta factura de flete se compara con una factura de flete de proveedor.

### <a name="landed-cost-transfer-order-cost-features"></a>Características de costo de la orden de transferencia de costo de entrega

El costo de aterrizaje le permite agregar órdenes de transferencia a un barco o viaje. De esta manera, puede agregar costos de envío al viaje como liquidaciones de inventario en el momento de la recepción de la orden de transferencia. Los costos generales pueden facturarse por los costos reales y rastrearse contra un viaje para actualizar el costo de los bienes vendidos. Aunque las órdenes de transferencia no utilizan mercancías en proceso de tránsito en el despacho estándar, se pueden agregar a los viajes. El costo de entrega se agrega al costo total de cada artículo.