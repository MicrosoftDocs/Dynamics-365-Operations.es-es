---
title: Gestionar viajes
description: En este tema se describe cómo trabajar con viajes. Un viaje típicamente representa una nave. Sin embargo, dependiendo de sus prácticas y procedimientos, puede representar un proveedor, una orden de compra o algún otro artículo que tenga sentido para su organización.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 50b6f306da1d32b1fd98da68bd997de1f1c23ffb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570955"
---
# <a name="manage-voyages"></a>Gestionar viajes

[!include [banner](../../includes/banner.md)]

Un viaje típicamente representa una nave. Sin embargo, dependiendo de sus prácticas y procedimientos, puede representar un proveedor, una orden de compra o algún otro artículo que tenga sentido para su organización.

La página **Todos los viajes** proporciona detalles del viaje, información de entrega y costos, e información sobre artículos, órdenes de compra y órdenes de transferencia. Para abrir la página **Todos los viajes**, vaya a **Coste de aterrizaje \> Viajes \> Todos los viajes**. Esta página muestra una lista de todos los viajes actuales. Puede utilizar los botones del Panel de acciones para crear, eliminar y trabajar con viajes. Seleccione cualquier viaje de la lista para ver sus detalles.

> [!NOTE]
> Los contenedores de envío y los folios están vinculados a un viaje. Las líneas de compra están vinculadas a un contenedor de envío. Si los contenedores de envío y los folios están desactivados, también se pueden vincular directamente a un viaje. Además, los costos que se ingresan aquí se distribuyen entre todas las líneas de compra adjuntas.

## <a name="action-pane"></a>Panel de acciones

El panel de acciones de la página **Viajes** proporciona botones que le permiten trabajar con un viaje seleccionado. Cada botón realiza una única acción. El Panel de acciones también incluye pestañas, cada una de las cuales, a su vez, proporciona un conjunto de botones relacionados. Excepto donde se indique, todos los botones y pestañas están disponibles en la vista de lista de la página **Todos los viajes** y en la vista detallada para un solo viaje seleccionado.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Botones que aparecen directamente en el panel de acciones

La tabla siguiente describe los botones disponibles directamente en el panel de acciones.

| Botón | Descripción |
|---|---|
| Crear nuevo | Crear un viaje. <!-- KFM: Link to scenario --> |
| Borrar | Eliminar el viaje actual. Solo los viajes que tienen un estado de viaje de *Confirmado* se pueden eliminar. Una vez que un viaje sale del puerto y procesa mercancías en tránsito, ya no se puede eliminar. |
| Editar de viajes | Abra la página **Editor de viajes**, donde puede agregar o eliminar líneas de compra para el viaje, crear nuevos contenedores y modificar los detalles del viaje en sí. |
| Costes de viaje | Abra la página **Costos del viaje**, donde puede ver y agregar los costos del viaje a todas las mercancías del viaje. Cuando los costos del viaje se agregan manualmente al viaje, se agregan automáticamente a la página **Consulta de costos** y se distribuye a cada bien de acuerdo con el método que se especifica en la página **Costos del viaje**. |

### <a name="buttons-on-the-voyage-tab"></a>Botones de la pestaña Viaje

La tabla siguiente describe los botones disponibles en la pestaña **Viaje** del panel de acciones. Esta pestaña está disponible solo cuando está trabajando en la vista de lista de la página **Todos los viajes**.

| Botón | Descripción |
|---|---|
| Contenedor de envío | Abra una página que muestra todos los contenedores de envío asociados con el viaje seleccionado. Puede haber un contenedor o varios contenedores. |
| Folio | Abra una página que muestra todos los folios asociados con el viaje seleccionado. Puede haber un folio o muchos folios. |

### <a name="buttons-on-the-manage-tab"></a>Botones de la pestaña Gestionar

La tabla siguiente describe las acciones disponibles en la pestaña **Gestionar** del panel de acciones.

| Botón | Descripción |
|---|---|
| Documentos recibidos | Actualice el viaje para que la opción **Documentos recibidos** está configurada en *Sí*. Puede usar este botón para bloquear el artículo y / o la línea de compra para que no se pueda actualizar más. |
| En tránsito | Actualice el campo **Estado del viaje** al estado en tránsito que se establece en la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)**. No hay más lógica en este proceso. Un viaje también se puede actualizar automáticamente al estado en tránsito, según la configuración del [Centro de control de seguimiento](delivery-information-setup.md).
| Listo para la gestión de costes | Actualice el campo **Estado del viaje** al estado listo para gestión de costes que se establece en la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)**. Se puede calcular el costo de un viaje cuando se han procesado todas las facturas (facturas de stock y facturas de costo del viaje) y se han recibido las mercancías. Si no se han calculado los costes estimados asociados con un viaje, se produce un error cuando intenta procesar el costeo de un viaje. |
| Estimado | Elimine cualquier irregularidad en los costos después de que exista una factura para todas las órdenes de compra y los costos del viaje. Cuando selecciona este botón, el cuadro de diálogo **Actualización de viaje - Estimado**. Allí, puede seleccionar publicar en la fecha financiera estándar o especificar una fecha de publicación y luego ejecutar la acción. Puede volver a ejecutar la acción tantas veces como desee. También puede utilizar el cuadro de diálogo **Actualización de viaje - Estimado** para establecer una programación para ejecutar la acción como una tarea periódica (trabajo por lotes). Le recomendamos que ejecute la acción con regularidad configurándola como un trabajo por lotes. |
| Registrar lista de recepciones | Publique una lista de recibos para todas las líneas de órdenes de compra en el viaje. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de publicación de lista de recibos para cada empresa y se debe procesar en cada entidad jurídica. |
| Registrar recepción de productos | Publique un recibo de producto para todas las líneas de órdenes de compra en el viaje. El proceso de recepción de productos para las líneas de órdenes de compra que están asociadas con un viaje se utilizará solo si las mercancías **no** pasan por el procesamiento de mercancías en tránsito. Si las mercancías pasarán por el procesamiento de mercancías en tránsito, recibirá un error cuando intente registrar el recibo del producto para una línea de orden de compra. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de contabilización de notas de entrega para cada empresa. |
| Registrar factura | Publique una factura para todas las líneas de órdenes de compra en el viaje. Si las mercancías en el viaje pasarán por el procesamiento de mercancías en tránsito, las líneas de la orden de compra se facturarán antes de que se complete el proceso de recepción. Cuando se factura la orden de compra original, se crearán las órdenes de mercancías en tránsito asociadas con las líneas de la orden de compra original. A continuación, el almacén podrá recibir esos pedidos. Si se utilizan envíos de varias empresas, se abre un nuevo cuadro de diálogo de contabilización de facturas para cada empresa. |
| Pedido de transferencia de envío | Publique un viaje de orden de transferfencia para todas las líneas de órdenes de transferencia en el viaje. Cuando se selecciona este botón, solo las órdenes de transferencia estarán disponibles para su actualización. |
| Recibir pedido de transferencia | Publique un recibo de orden de transferfencia para todas las líneas de órdenes de transferencia en el viaje. |
| Recibir mercancía en tránsito | Reciba todas las líneas de pedido que se encuentren en tránsito en el viaje. Este botón es una de las tres opciones disponibles para recibir mercancías en tránsito en un viaje. (Las otras dos opciones son el botón **Crear diario de llegadas** que se describe más adelante en esta tabla, y la aplicación móvil Warehouse Management). Esta opción es la opción más simple y procesará las mercancías en tránsito desde el almacén de mercancías en tránsito hasta el almacén de destino final. Si desea tener más control sobre el proceso, utilice el diario de llegadas o un dispositivo móvil para procesar la recepción de mercancías. |
| Buscar costes automáticos | Encuentre los costos de viaje relevantes. Si estos costos ya se han encontrado o actualizado, recibirá el siguiente mensaje: "Existen líneas de costo no facturadas. ¿Desea sobrescribirlos? Se encontrarán todos los costos que no estaban asociados con el viaje en el momento de la creación. Los costos de viaje que se adjuntan a un viaje y que se hayan facturado no se sobrescribirán. |
| Crear diario de llegadas | <p>Abre el cuadro de diálogo **Crear diario de llegadas**, donde puede crear un diario de llegada que especifica una ubicación. El cuadro de diálogo proporciona las siguientes opciones:</p><ul><li>**Crear a partir de mercancías en tránsito** o **Crear desde orden de transferencia** - La etiqueta de esta opción cambia dependiendo de si está utilizando el proceso de mercancías en tránsito. Establézcalo en *Sí* para abrir una página de diario de llegadas que le permite procesar un diario de llegadas estándar para las mercancías en tránsito que están asociadas con el viaje. Si el artículo ya se recibió en el almacén de destino final, no se agregará a las líneas del diario de llegada.</li><li>**Inicializar cantidad** - Establezca esta opción en *Sí* para inicializar la cantidad que se recibirá, con base en la cantidad de mercancías que se especifica en la línea de viaje. Si la línea de viaje se ha recibido parcialmente, esta cantidad será la cantidad restante. Le recomendamos que establezca esta opción en *Sí*.</li><li>**Crear a partir de líneas de pedido** - Establezca esta opción en *Sí* para tomar el valor de las líneas de pedido.</li></ul><p>Este botón es una de las tres opciones disponibles para recibir mercancías en un viaje. (Las otras opciones son el botón **Recibir mercancías en tránsito** que se describió anteriormente en esta tabla y la aplicación móvil Warehouse Management).</p> |
| Acumular costes | Puede acumular costos cuando un tipo de costo tiene una cuenta contable especificada para el débito. Este botón se utiliza normalmente cuando el stock está en tránsito o cuando se han recibido y facturado mercancías. |
| Costes agregados | Mueva los costos del nivel del contenedor de envío al nivel del viaje. Puede utilizar este botón en un escenario de envío / servicios compartidos, donde varias entidades comparten un contenedor de envío o un espacio de cartón. Por ejemplo, el viaje tiene un contenedor de envío de 40 pies y un contenedor de envío de 20 pies, y la distribución se realiza por volumen. En este caso, los bienes / entidades que comparten o usan el espacio en el contenedor de envío de 20 pies podrían ser penalizados. Para distribuir equitativamente los costos, algunas organizaciones pueden querer transferir los costos al viaje y distribuirlos según el método de prorrateo a nivel del viaje. |
| Cambiar plantilla de recorrido | Abra un cuadro de diálogo donde pueda cambiar la plantilla del viaje. Después de cambiar la plantilla, se eliminarán los costos del viaje. Por lo tanto, es posible que deba seleccionar **Buscar costes automáticos** (consulte la descripción anterior en esta tabla) o agregue costos manualmente nuevamente. |

### <a name="buttons-on-the-general-tab"></a>Botones de la pestaña General

La tabla siguiente describe los botones disponibles en la pestaña **General** del panel de acciones.

| Botón | Descripción |
|---|---|
| Lista de recepciones | Abra una lista de recibos de producto para todas las líneas de órdenes de compra en el viaje. Si se utilizan viajes de varias empresas, se abre una nueva lista de recibos para cada empresa. Si no se han procesado listas de recepción de productos, este botón no está disponible. |
| Recepción de producto | Abra el registro de recepción de producto para las líneas de la orden de compra que están asociadas con el viaje, si se utiliza ese registro. Si no se han publicado recibos de productos, este botón no está disponible. El proceso de recepción de productos no se utilizará si utiliza el procesamiento de mercancías en tránsito. |
| Recepción de artículos | Abra el diario de llegada de artículos, si se utiliza. |
| Seguimiento | Abra la página **Seguimiento entrante**, donde puede actualizar la fecha de llegada prevista de las mercancías en un contenedor de envío y un viaje y, posteriormente, actualizar las fechas de entrega previstas de las líneas de la orden de compra. |
| Consulta de costes | <p>Abra la página **Consulta de costos**, que muestra todos los costos de un viaje.</p><p>Seleccione **Ver** en el panel de acciones para ajustar la vista. Puede ver cualquiera de los niveles, además del artículo y el código de tipo de costo.</p><p>Solo los códigos de tipo de costo que están directamente relacionados con las transacciones de inventario aparecen en la página **Consulta de costos**. Al eliminar los códigos de tipo de costo, puede ajustar la página agrupando los costos. Esta capacidad puede resultar útil si utiliza tamaños y colores.</p><p>La página **Consulta de costos** muestra solo códigos de tipo de costo donde el campo **Débito** está configurado en *Artículo*.</p> |
| Pedidos de mercancía en tránsito | Abra la página **Pedidos de mercancías en tránsito**, que muestra los registros de mercancías en tránsito para el viaje seleccionado únicamente. |

## <a name="lines-view"></a>Vista de líneas

Para abrir la vista **Líneas**, abra un viaje y luego seleccione la pestaña **Líneas** en la parte superior derecha del encabezado del viaje.

### <a name="information-on-the-voyage-header-fasttab"></a>Información sobre la ficha desplegable del encabezado de viaje

La ficha desplegable **Encabezado de viaje** de la vísta **Líneas** de un viaje contiene información básica que describe el viaje. Muchos de los campos que aparecen en esta ficha desplegable también aparecen en la vista **Encabezamiento**, como se describe más adelante en este tema.

### <a name="information-on-the-voyage-lines-fasttab"></a>Información sobre la ficha desplegable de líneas del viaje

La ficha desplegable **Líneas de viaje** de la vista **Líneas** de un viaje está relacionada con los detalles del viaje y la información de costos que se aplica al nivel del viaje. Aquí puede revisar los contenedores de envío, folios y artículos que se adjuntan al viaje. También se muestran el precio y la cantidad de los artículos del viaje. Puede ver cualquier contenedor de envío o folio que se enumere seleccionando el enlace correspondiente.

### <a name="information-on-the-line-details-fasttab"></a>Información sobre la ficha desplegable de detalles de línea

La ficha desplegable **Detalles de línea** de la vista **Líneas** de un viaje proporciona más información sobre la línea que está actualmente seleccionada en la ficha desplegable **Líneas de viaje**. Tenga en cuenta que esta ficha desplegable incluye detalles sobre la posición que ocupa cada línea en el contenedor y la cantidad declarada.

## <a name="header-view"></a>Visualización de encabezado

Para abrir la vista **Encabezado**, abra un viaje y luego seleccione la pestaña **Encabezado** en la parte superior derecha del encabezado del viaje.

### <a name="settings-on-the-general-fasttab"></a>Configuración en la ficha desplegable General

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **General** en la vista **Encabezamiento** de un viaje.

| Campo | Descripción |
|---|---|
| Viaje | Introduzca el número de viaje o vuelo. |
| Referencia de reserva | Si su remitente o centro de envío proporciona un número de referencia para identificar el viaje (es decir, la referencia interna del remitente o del centro de envío), ingréselo aquí. |
| Embarcación | Especifique o seleccione el recipiente. Si la nave no aparece como un valor, puede ingresar la ID de la nave como texto libre. En ese caso, la tabla principal no se actualiza para que el ID de la nave se pueda seleccionar en este campo más adelante. |
| Id. de viaje externo | Ingrese la ID disponible públicamente para el viaje (como el número de vuelo). |
| Hoja de ruta aérea/Conocimiento de embarque maestro | Ingrese la guía aérea maestra o el número de conocimiento de embarque. Puede especificar este valor cuando realiza un envío aéreo. |
| Hoja de ruta aérea/Conocimiento de embarque interno | Especifique la guía aérea de la casa o el conocimiento de embarque para el contenedor de envío. |
| Alquiler | Seleccione esta casilla de verificación para indicar que el contenedor es un contenedor de alquiler que debe devolverse. |
| Descripción | Introduzca una descripción del viaje para que sea más fácil de reconocer. |
| Estado de viaje | El estado del viaje. Los valores incluyen *Creado*, *En tránsito*, *Documentos recibidos* y *Estimado*. Este campo no se calcula en base a la lógica. Se actualiza solo a través de la acción de publicación. El valor *Estimado* indica que se ha recibido una factura por las existencias y todos los costos del viaje. A menos que se reciba una factura, un viaje no puede alcanzar el estado *Estimado*. |
| Estado de pedido de compra | El estado más alto que se ha alcanzado entre todas las órdenes de compra asociadas con el viaje. |
| Documentos recibidos | Un valor que indica si su empresa ha recibido todos los documentos asociados con el viaje. Para cambiar el valor, seleccione **Documentos recibidos** en el grupo **Actualización de viaje** en la pestaña **Administrar** del Panel de acciones. |
| Empresa de transporte | Seleccione la empresa de envío para este viaje. Este campo se puede utilizar para determinar los costos automáticos. |
| Nombre | Nombre de la empresa seleccionada en el campo **Empresa de envío**. |
| Medida | Este campo permite especificar una medida en un coste automático. Las medidas suelen ser utilizadas por organizaciones que no conocen el volumen o el peso individual de los productos, pero que requieren una distribución más precisa que la que proporciona la cantidad o cantidad. El transportista proporcionará el peso o la medida cúbica, y puede ponerlo al nivel de un artículo o de la orden de compra. Se puede actualizar automáticamente si se selecciona el parámetro, o se puede ingresar manualmente. |
| Unidad de medida | La unidad de medida que se aplica al número en el campo **Medición**. |
| Número de pallets | Especifique el número de palés en la línea de viaje. Este campo se actualiza automáticamente si la opción **Actualizar automáticamente el número de cajas** está configurada en *Sí* en la pestaña **General** de la página **Parámetros de costo aterrizado**. |

### <a name="settings-on-the-delivery-fasttab"></a>Configuración en la ficha desplegable Entrega

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Entrega** en la vista **Encabezamiento** de un viaje.

| Campo | Descripción |
|---|---|
| Fecha y hora de creación | La fecha y hora de creación del registro de viaje. |
| Fecha ex fábrica | Este campo selecciona la fecha ex-fábrica más temprana entre las órdenes de compra que están vinculadas al viaje. La fecha de fábrica está disponible en el encabezado de la orden de compra y se actualiza mediante la función de control de seguimiento. |
| Fecha de envío | La fecha estimada en que el avión o la nave abandonan el punto de origen. |
| Fecha de salida | La fecha de salida suele ser la fecha en que el avión o la nave realmente salen del puerto de ultramar. La fecha de envío y la fecha de salida no tienen por qué coincidir. El campo **Fecha de salida** es solo para fines informativos. No se usa para estimar la fecha de entrega esperada. La función de control de seguimiento se utiliza para estimar la fecha de entrega esperada, y este campo se puede configurar para que la función de control de seguimiento lo rellene automáticamente. |
| Fecha en tienda | Este campo selecciona la fecha más temprana en la que estarán disponibles para la venta las mercancías de las órdenes de compra vinculadas al viaje. |
| Fecha de entrega estimada | La fecha de entrega estimada suele ser la fecha en la que las mercancías deben llegar al almacén. La finalidad de este campo es meramente informativa. No se utiliza para la planificación maestra de mercancías. La fecha de entrega prevista en la línea de la orden de compra se utiliza para la planificación maestra de mercancías en un viaje y se actualiza mediante la función de control de seguimiento. Este campo se puede configurar para que se rellene con la caracetrística de control de seguimiento. |
| Fecha de entrega real | La fecha de entrega más temprana, en función de las mercancías vinculadas al viaje. |
| Hora de llegada estimada en puerto de envío | Ingrese la fecha en la que espera que el viaje llegue al puerto de envío, según la información que le proporcionó su agente de envío. |
| Documentos originales recibidos | Introduzca la fecha en la que se recibieron los documentos originales. |
| Con recomendación del agente | Introduzca la fecha en la que se notificó al corredor. |
| Se envió el conocimiento de embarque original | Introduzca la fecha en la que se envió el conocimiento de embarque original. |
| Mercancías liberadas | Introduzca la fecha en que las mercancías salieron de la aduana. |
| Cita del cliente | Introduzca la fecha de la cita del cliente, que es la fecha en la que espera que el cliente tome posesión de los bienes. |
| Entregado en almacén | Introduzca la fecha en la que se entregaron las mercancías al almacén. |
| Fecha de verificación | Especifique la fecha de verificación. |
| Instrucciones de entrega | Introduzca la fecha en la que se recibieron las instrucciones de entrega. |
| Modo de entrega | Este campo proporciona información sobre el método que se utiliza para entregar el viaje y la selección de costos de los costos automáticos que están asociados con ese método de entrega. |
| Puerto de origen | El puerto de envío desde el que parte el viaje. |
| Puerto de destino | El puerto de embarque donde llega el viaje. Los contenedores de envío pueden tener diferentes puertos, porque el barco puede detenerse en varios puertos. Al verificar el puerto "hasta" en el nivel del contenedor de envío, proporciona detalles de puerto precisos para cada contenedor de envío en un viaje. El costo automático asociado con el flete se determina en función de la combinación del tipo de contenedor de envío, el puerto "hasta" y el puerto "desde". |
| Transitario local | La finalidad de este campo es meramente informativa. El reenviador local debe poder seleccionarse en la tabla de proveedores. |
| Fecha de transporte local | La fecha para la que se reservó el transporte local. Este campo puede ayudar al almacén a realizar su planificación. |
| Hora de transporte local | El intervalo de tiempo para el que se reservó el transporte local. Este campo puede ayudar al almacén a realizar su planificación. |
| Plantilla de recorrido | La plantilla de viaje que se especifica para el viaje. La plantilla de viaje se utiliza para ingresar al puerto "hasta" y "desde" el puerto del contenedor de envío y el viaje. Estos valores, a su vez, ayudan a identificar los costes automáticos asociados con el viaje. |

### <a name="settings-on-the-other-fasttab"></a>Configuración en la otra ficha desplegable

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Otro** en la vista **Encabezamiento** de un viaje.

| Campo | Descripción |
|---|---|
| Comentarios | Escriba otra información relacionada con el viaje. |
| Fecha de valorización | Seleccione la fecha ex-fábrica más temprana para las órdenes de compra que están vinculadas al viaje. |
| Viaje pendiente | Puede usar esto para indicar si su envío o viaje ya ha salido. Su finalidad es meramente informativa.  |
| Cambiar el nombre de los contenedores de envío | Para viajes que tienen más de un contenedor, la cantidad de contenedores que aún no se han recibido. |

## <a name="voyage-update-periodic-tasks"></a>Tareas periódicas de actualización de viaje

El módulo **Coste de aterrizaje** incluye varias tareas periódicas relacionadas con el viaje que pueden actualizar de forma masiva varios aspectos de los viajes. Para ejecutar o programar estas tareas periódicas, vaya a **Coste de aterrizaje \> Tareas periódicas \> Actualizaciones de viaje** y luego seleccione uno de los siguientes tipos de tareas:

- **Documentos recibidos** - Esta tarea le permite configurar **Documentos recibidos** como *Sí* para varios viajes al mismo tiempo. Utilice la configuraicón de **Filtro** para definir el conjunto de viajes que desea actualizar.
- **En tránsito** - Esta tarea le permite configurar el campo **Estado del viaje** con el estado en tránsito que se establece en la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)** para varios viajes al mismo tiempo. Utilice la configuraicón de **Filtro** para definir el conjunto de viajes que desea actualizar.
- **Listo para gestión de costes** - Esta tarea le permite configurar el campo **Estado del viaje** con el estado listo para gestión de costes que se establece en la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)** para varios viajes al mismo tiempo. Por lo general, configurará esta tarea para que se ejecute en un horario regular.
- **Estimado** - Esta tarea le permite configurar el campo **Estado del viaje** con el estado de costeo que se establece en la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)** para varios viajes al mismo tiempo, siempre que se hayan calculado los costos pero aún no se hayan actualizado en el viaje. Por lo general, configurará esta tarea para que se ejecute en un horario regular.
