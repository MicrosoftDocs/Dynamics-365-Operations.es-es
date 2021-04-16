---
title: Gestionar contenedores de envío
description: Este tema describe cómo trabajar con contenedores de envío. Los contenedores de envío se utilizan para agrupar mercancías que se agrupan físicamente. También se utilizan en los casos en que los costos deben compartirse solo entre esos bienes, generalmente porque están físicamente juntos.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9b42292194d40f6b0cc6203130bedc1fbb45eec8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833818"
---
# <a name="manage-shipping-containers"></a>Gestionar contenedores de envío

[!include [banner](../../includes/banner.md)]

Los contenedores de envío se utilizan para agrupar mercancías que se agrupan físicamente. También se utilizan en los casos en que los costos deben compartirse solo entre esos bienes, generalmente porque están físicamente juntos.

Para ver y procesar mercancías a través de la página del contenedor de envío, vaya a **Coste de aterrizaje \> Contenedores de envío \> Todos los contenedores de envío**. La página **Todos los contenedores de envío** muestra una lista de todos los contenedores de envío disponibles. Puede utilizar los botones del Panel de acciones para crear, eliminar y trabajar con contenedores de envío. Seleccione cualquier contenedor de envío de la lista para ver sus detalles en la página **Contenedores de envío**.

La parte superior de la página de detalles del contenedor de envío muestra el contenedor de envío y la información de costos. La sección **Líneas** muestra los folios, los artículos y las órdenes de compra u órdenes de transferencia que se adjuntan al contenedor.

## <a name="action-pane"></a>Panel de acciones

El panel de acciones en las páginas **Todos los contenedores de envío** y **Contenedores de envío** proporciona botones que le permiten trabajar con un contenedor de envío seleccionado. Cada botón realiza una única acción. El Panel de acciones también incluye pestañas, cada una de las cuales, a su vez, proporciona un conjunto de botones relacionados. Excepto donde se indique, todos los botones y pestañas que se describen en las siguientes subsecciones están disponibles en la vista de lista (es decir, en la página **Todos los contenedores de envío**) y en la vista detallada (es decir, en la página **Contenedores de envío**).

### <a name="buttons-on-the-manage-tab"></a>Botones de la pestaña Gestionar

La tabla siguiente describe los botones disponibles en la pestaña **Gestoinar** del panel de acciones.

| Botón | Descripciones |
|---|---|
| Registrar lista de recepciones | Publique una lista de recibos o vea las listas de recibos de productos para todas las líneas de órdenes de compra en el contenedor de envío. Si se utilizan envíos de varias empresas, se abre un nuevo cuadro de diálogo de lista de recepción para cada empresa. |
| Registrar recepción de productos | Publique un recibo de producto para todas las líneas de órdenes de compra en el contenedor de envío. |
| Registrar factura | Publique una factura para todas las líneas de órdenes de compra en el contenedor de envío. Si se utilizan envíos de varias empresas, se abre un nuevo cuadro de diálogo de contabilización de facturas para cada empresa. |
| Pedido de transferencia de envío | Publique un envío de orden de transferfencia para todas las líneas de órdenes de transferencia en el contenedor de envío. Solo aquellas líneas en el contenedor de envío que son un tipo de orden de transferencia aparecen en el cuadro de diálogo. |
| Recibir pedido de transferencia | Publique una recepción de orden de transferfencia para todas las líneas de órdenes de transferencia en el contenedor de envío. El cuadro de diálogo de recepción es la forma más sencilla de recibir mercancías en un contenedor de envío o en un viaje, y es una de las tres opciones disponibles. También puede recibir a través de diarios de llegada o procesamiento de dispositivos móviles. |
| Crear diario de llegadas | Puede generar un diario de llegadas para las organizaciones mediante el uso de funciones de almacén avanzadas. Las opciones son _Inicializar cantidad_ (recomendado), y _Crear a partir de mercancías en tránsito_ o _Crear a partir de órdenes de compra_. Las dos últimas opciones dependen de si se está utilizando el procesamiento de mercancías en tránsito. |
| Cambiar nombre | Abra un cuadro de diálogo donde puede cambiar el nombre de un contenedor de envío seleccionado. |
| Cambiar plantilla de recorrido | Cambiar la plantilla de recorrido. Después de cambiar la plantilla de viaje, es posible que deba seleccionar **Encuentra costes automáticos** o agregue costos manualmente nuevamente, porque los costos de envío serán eliminados. |
| Convertir en alquiler | Convierta un contenedor de envío seleccionado en un contenedor de envío de alquiler. |

### <a name="buttons-on-the-general-tab"></a>Botones de la pestaña General

La tabla siguiente describe los botones disponibles en la pestaña **General** del panel de acciones.

| Botón | Descripciones |
|---|---|
| Lista de recepciones | Publique una lista de recibos para todas las líneas de órdenes de compra en el contenedor de envío. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de registro de lista de recepción para cada empresa. |
| Recepción de producto | Ver el registro de recibo del producto, si se usa. El proceso de recepción de productos se utilizará solo si las mercancías no utilizan la función de mercancías en tránsito. |
| Recepción de artículos | Vea el diario de llegada de artículos para el contenedor de envío, si se utiliza ese diario. |
| Escalas | Los tramos se utilizan para identificar partes separadas de un viaje. Los plazos de entrega se pueden asociar con cada tramo para ayudar con el seguimiento del envío. Para más información, ver [Configuración de viaje de varios tramos](multi-leg-journey-setup.md). |
| Seguimiento | Ver o actualizar el seguimiento de envíos. |
| Pedidos de mercancía en tránsito | Puede abrir la página **Mercancías en tránsito** directamente desde el contenedor. Esa página muestra los registros de mercancías en tránsito para el contenedor de envío seleccionado únicamente. |

## <a name="header-view"></a>Visualización de encabezado

Para abrir la vista **Encabezamiento**, abra un contenedor de envío y luego seleccione la pestaña **Encabezamiento** en la parte superior derecha del encabezado del contenedor de envío.

### <a name="settings-on-the-general-fasttab"></a>Configuración en la ficha desplegable General

La siguiente tabla describe las configuraciones que están disponibles en la ficha desplegable **General** de la vista **Encabezamiento** de un contenedor de envío.

| Campo | Descripción |
|---|---|
| Contenedor de envío | El nombre del contenedor de envío. |
| Viaje | El viaje asociado con el contenedor de envío. |
| Tipo de contenedor de envío | Ingrese el tipo de contenedor de envío. Este campo debe estar configurado. Puede usarlo para determinar el costo del flete, por ejemplo, seleccionando el costo automático asociado con el tipo de contenedor de envío. |
| Embarcación | Especifique o seleccione el recipiente. Si la nave no aparece como un valor, puede ingresar la ID de la nave como texto libre. En ese caso, la tabla principal no se actualiza para que el ID de la nave se pueda seleccionar en este campo más adelante. Para obtener más información, consulte [Recipientes](shipping-information-setup.md#vessels). |
| Tipo de unidad | Los tipos de unidades se utilizan como un medio adicional para agrupar e identificar contenedores de envío. Se muestran y seleccionan en la página del contenedor de envío. Para obtener más información, consulte [Configurar tipos de unidad](shipping-container-setup.md#unit-types). |
| Tipo de refrigeración | Los tipos de refrigeración se utilizan como un medio adicional para agrupar e identificar contenedores de envío, normalmente contenedores refrigerados. Se muestran y seleccionan en la página del contenedor de envío. Para obtener más información, consulte [Configurar tipos de refrigeración](shipping-container-setup.md#refrigeration-types). |
| Medida | Este campo permite especificar una medida en el módulo **Coste descargado**. Las medidas suelen ser utilizadas por organizaciones que no conocen el volumen o el peso individual de los productos, pero que requieren una distribución más precisa que la que proporciona la cantidad o cantidad. El transportista proporcionará el peso en kilogramos o la medida cúbica, y puede ponerlo al nivel de un artículo o de la orden de compra. Se puede actualizar automáticamente si se selecciona el parámetro, o se puede ingresar manualmente. |
| Unidad de medida | La unidad de medida que se aplica al número en el campo **Medición**. |
| Peso real | Puede registrar el peso real de la caja o contenedor. Este valor se puede utilizar para verificar el peso máximo permitido en la configuración de un contenedor de envío. |
| Número de cajas | El número de cajas se actualiza automáticamente si se selecciona el parámetro. |
| Descripción de los bienes | Se puede seleccionar una descripción de las mercancías en el contenedor de envío o en el encabezado del folio. Se utiliza para ayudar a identificar un viaje, un contenedor de envío o un folio de mercancías. Para más información, consulte [Descripción de mercancías](shipping-information-setup.md#description-of-goods). |
| Hoja de ruta aérea/Conocimiento de embarque interno | Puede especificar la guía aérea de la casa o el conocimiento de embarque para el contenedor de envío. |
| Comentarios | Información adicional relacionada con el contenedor de envío. |
| Retornable | Un valor que indica si el contenedor de envío se puede devolver después del viaje. |
| Estado de viaje | El estado del recorrido asociado al contenedor de envío. |
| Estado de pedido de compra | El estado de la orden de compra asociada al contenedor de envío. |

### <a name="settings-on-the-delivery-fasttab"></a>Configuración en la ficha desplegable Entrega

La siguiente tabla describe las configuraciones que están disponibles en la ficha desplegable **Entrega** de la vista **Encabezamiento** de un contenedor de envío.

| Campo | Descripción |
|---|---|
| Fecha y hora de creación | La fecha y hora de creación del contenedor. |
| Fecha ex fábrica | Esta fecha generalmente se proporciona a la fábrica/proveedor para indicar cuándo espera que los productos salgan de sus instalaciones. Cuando trabaja con una fábrica en Asia, a menudo se requiere esta fecha en lugar de la fecha en la que espera recibir los productos. (Por el contrario, para una entrega local, se requiere la fecha en la que espera la mercancía). Este campo se puede completar desde las líneas de la orden de compra en la lista de contenedores de envío. También puede introducirlo manualmente aquí. |
| Fecha de envío | Esta fecha se puede imprimir en el documento de la orden de compra. Por lo general, informa a la fábrica / proveedor sobre la fecha en la que las mercancías deben entregarse en el puerto. La finalidad de este campo es meramente informativa. No se usa para estimar la fecha de entrega esperada de las mercancías en el contenedor de envío. Este campo se puede configurar para que se actualice automáticamente cuando se actualice la página de control de seguimiento. |
| Fecha en tienda | La fecha más temprana en la que estarán disponibles para la venta las mercancías de las órdenes de compra vinculadas al viaje.|
| Fecha de entrega estimada | Por lo general, la fecha en la que las mercancías deben llegar al almacén. La finalidad de este campo es meramente informativa. No se utiliza para calcular la planificación maestra en las líneas de la orden de compra en el contenedor de envío. La fecha de entrega prevista en las líneas de la orden de compra se actualiza mediante el control de seguimiento. Este campo se puede configurar para que se actualice cuando se actualice la página de control de seguimiento. |
| Fecha de salida | Por lo general, la fecha en que el avión o la nave realmente sale del puerto de ultramar. |
| Hora de llegada estimada en puerto de envío | La fecha estimada de llegada al puerto de destino ("al" puerto). |
| Documentos originales recibidos | Opcional: actualice la fecha en la que se recibieron los documentos originales. |
| Con recomendación del agente | Opcional: actualice la fecha en la que se notificó al corredor. |
| Se envió el conocimiento de embarque original | Opcional: actualice la fecha en la que se envió el conocimiento de embarque original. |
| Mercancías liberadas | Opcional: actualice la fecha en la que se liberaron los productos. |
| Cita del cliente | Opcional: actualice la fecha de la cita del cliente. |
| Entregado en almacén | Opcional: actualice la fecha en la que se entregaron las mercancías al almacén. |
| Fecha de verificación | Opcional: actualice la fecha de verificación. |
| Instrucciones de entrega | Opcional: actualice la fecha de las instrucciones de entrega. |
| Puerto de origen | El puerto desde el que se enviarán los artículos. |
| Puerto de destino | El puerto al que se enviarán los artículos. |
| Transitario local | La finalidad de este campo es meramente informativa. El reenviador local debe poder seleccionarse en la tabla de proveedores. |
| Fecha de transporte local | Ingrese la fecha para la que se reservó el transporte local. Este campo puede ayudar al almacén a realizar su planificación. |
| Hora de transporte local | Escriba el intervalo de tiempo. Este campo puede ayudar al almacén a realizar su planificación. |
| Plantilla de recorrido | La plantilla de viaje que se especifica para el viaje. La plantilla de viaje proporciona los detalles de los puertos "hacia" y "desde", y los plazos de entrega asociados con el control de seguimiento del contenedor de envío. |

### <a name="settings-on-the-other-fasttab"></a>Configuración en la otra ficha desplegable

La siguiente tabla describe las configuraciones que están disponibles en la ficha desplegable **Otro** de la vista **Encabezamiento** de un contenedor de envío.

| Campo | Descripción |
|---|---|
| Alquiler | Un valor que indica si el contenedor de envío es un contenedor de envío de alquiler. Los costos de alquiler pueden estar asociados con los contenedores de alquiler. |
| Convertido en alquiler | Un valor que indica si el contenedor de envío se convirtió en contenedor de envío de alquiler. Los costos de alquiler pueden estar asociados con los contenedores de alquiler. |
| Viaje original | Si el contenedor de envío se trasladó a un nuevo viaje, el viaje original. |
| Utilizado | Utilice esto para registrar si se ha utilizado un contenedor de envío de alquiler. Su finalidad es meramente informativa. |
| Fecha de carga esperada | La fecha en la que se espera que el contenedor de envío se cargue con mercancías. |
| Nuestro número de serie | Ingrese el número de serie que su empresa utiliza internamente para el contenedor de envío. |
| Número de serie de la empresa de transporte | Ingrese el número de serie que la compañía de envío o el agente proporcionó para el contenedor de envío. |
| Fecha de aplicación de certificado de examen | La fecha en la que se solicitó un examen para el contenedor de envío. |
| Fecha de recepción del certificado de examen | Fecha en la que se recibió el certificado de examen. |
| Fecha de vencimiento de certificado de examen | Fecha en la que expirará el certificado de examen. |
| Número de certificado de examen | El número de certificado del certificado que se emitió después de que se realizó un examen. |

## <a name="lines-view"></a>Vista de líneas

Para abrir la vista **Líneas**, abra un contenedor de envío y luego seleccione la pestaña **Líneas** en la parte superior derecha del encabezado del contenedor de envío.

### <a name="information-on-the-shipping-container-fasttab"></a>Información sobre la ficha desplegable Contenedor de envío

La ficha desplegable **Contenedor de envío** en la vista **Líneas** muestra información sobre la publicación. La mayor parte de esta información también aparece en la vista **Encabezamiento**, como se describió anteriormente en este tema.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Información y botones en la ficha desplegable Líneas

La ficha desplegable **Líneas** de la vista **Líneas** muestra detalles sobre cada línea de pedido de compra total o parcial que se incluye en el contenedor de envío actual.

La tabla siguiente describe los botones disponibles en la barra de herramientas de la ficha desplegable **Líneas** de la vista **Líneas**.

| Botón | Descripción |
|---|---|
| Eliminar | Elimine la línea de orden de compra seleccionada del viaje. |
| Inventario \> Transacciones | Vea las transacciones de inventario para la línea de pedido de compra seleccionada. Tenga en cuenta que si utiliza mercancías en tránsito, también se muestran el pedido original y las órdenes de mercancías en tránsito. |
| Inventario \> Mostrar dimensiones | Abra un cuadro de diálogo donde puede seleccionar las dimensiones de inventario que aparecen para las transacciones que ve. |
| Actualización | Actualice la información relacionada con la cantidad, el peso o el volumen de la línea de la orden de compra seleccionada. |

### <a name="information-on-the-lines-details-fasttab"></a>Información sobre la ficha desplegable de detalles de líneas

La ficha desplegable **Detalles de líneas** de la vista **Líneas** muestra detalles sobre la línea de pedido de compra que está actualmente seleccionada en la ficha desplegable **Líneas**.
