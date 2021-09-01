---
title: Administrar folios
description: Este tema describe cómo trabajar con folios. Por lo general, un folio consta de los productos de un proveedor para una entidad o empresa por envío. Los productos en un folio pueden estar en un contenedor o pueden estar esparcidos entre múltiples contenedores.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 813065b32df8388ef2e86841267e499691b528e16d5bb9ef3072b3ce811ffaa0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713015"
---
# <a name="manage-folios"></a>Administrar folios

[!include [banner](../../includes/banner.md)]

Un folio suele estar determinado por las normas aduaneras. Puede constar de los productos de un proveedor para una entidad o empresa por envío. Los productos en un folio pueden estar en un contenedor o pueden estar esparcidos entre múltiples contenedores.

Para abrir la página **Todos los folios**, vaya a **Coste de aterrizaje \> Folios \> Todos los folios**. Esta página muestra una lista de todos los folios actuales. Puede utilizar los botones del Panel de acciones para crear, eliminar y trabajar con folios. Seleccione cualquier folio de la lista para ver sus detalles en la página **Folios**.

## <a name="action-pane"></a>Panel de acciones

El panel de acciones de las páginas **Todos los folios** y **Folios** proporciona botones que le permiten trabajar con un folio seleccionado. Cada botón realiza una única acción. El Panel de acciones también incluye pestañas, cada una de las cuales, a su vez, proporciona un conjunto de botones relacionados. Excepto donde se indique, todos los botones y pestañas que se describen en las siguientes subsecciones están disponibles en la vista de lista (es decir, en la página **Todos los folios**) y en la vista detallada (es decir, en la página **Folios**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Botones que aparecen directamente en el panel de acciones

La tabla siguiente describe los botones disponibles directamente en el panel de acciones.

| Botón | Descripción |
|---|---|
| Crear nuevo | Cree un folio. |
| Borrar | Elimine el folio abierto o seleccionado. |
| Costes de viaje | Abra la página **Costos del viaje**, donde puede ver y agregar los costos de nivel de folio a todas las mercancías del viaje. Cuando los costos de folio se agregan manualmente al viaje, se agregan automáticamente a la página de consulta de costos y se distribuye a cada bien de acuerdo con el método que se especifica en la página **Costos del viaje**. |

### <a name="buttons-on-the-manage-tab"></a>Botones de la pestaña Gestionar

La tabla siguiente describe los botones disponibles en la pestaña **Gestoinar** del panel de acciones.

| Botón | Descripción |
|---|---|
| Registrar lista de recepciones | Publique una lista de recibos para todas las líneas de órdenes de compra en el folio. Si se utilizan envíos de varias empresas, se abre un nuevo cuadro de diálogo de lista de recepción para cada empresa. |
| Registrar recepción de productos | Publique un recibo de producto para todas las líneas de órdenes de compra en el folio. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de recepción de producto para cada empresa. |
| Registrar factura | Publique una factura para todas las líneas de órdenes de compra en el folio. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de contabilización de facturas para cada empresa. |
| Pedido de transferencia de envío | Registrar una orden de transferencia para todas las líneas de la orden de transferencia que están relacionadas con el folio actual en el envío relacionado. |
| Recibir pedido de transferencia | Registrar una recepción de orden de transferencia para todas las líneas de la orden de transferencia que están relacionadas con el folio actual en el envío relacionado. |
| Recibir mercancía en tránsito | Reciba todas las líneas de pedido que se encuentren en tránsito en el folio. |
| Documentos recibidos | Actualice la configuración de la opción **Documentos recibidos** a *Sí*. Puede usar este botón para bloquear el artículo y / o la línea de compra para que no se pueda actualizar más. |
| Buscar costes automáticos | Encuentre los costos de viaje relevantes. Si estos costos ya se han encontrado o actualizado, recibirá el siguiente mensaje: "Existen líneas de costo no facturadas. ¿Desea sobrescribirlos? Tenga en cuenta que los costos de viaje que se adjuntan al folio y que se hayan facturado no se sobrescribirán. |
| Crear diario de llegadas | Genere un diario de llegadas para las organizaciones mediante el uso de funciones de almacén avanzadas. Puede seleccionar **Inicializar cantidad** (recomendado), y **Crear a partir de mercancías en tránsito** y/o **Crear a partir de órdenes de compra**. Las última opción depende de si se está utilizando el procesamiento de mercancías en tránsito. |
| Acumular costes | Acumule costos cuando un tipo de costo tiene una cuenta contable especificada para el débito. Este botón se utiliza normalmente cuando el stock está en tránsito o cuando se han recibido y facturado mercancías. |

### <a name="buttons-on-the-general-tab"></a>Botones de la pestaña General

La tabla siguiente describe los botones disponibles en la pestaña **General** del panel de acciones.

| Botón | Descripción |
|---|---|
| Lista de recepciones | Publique una lista de recibos para todas las líneas de órdenes de compra en el folio. Si se utilizan viajes de varias empresas, se abre un nuevo cuadro de diálogo de registro de lista de recepción para cada empresa. |
| Recepción de producto | Ver el registro de recibo del producto, si se usa. |
| Recepción de artículos | Vea el diario de llegada de artículos, si se utiliza. |
| Consulta de costes | Abra la página de consulta de costos para ver todos los costos de un viaje, incluido el contenedor de envío, el folio y la orden de compra. Puede ajustar la vista exacta de la página mediante la acción Ver. En la página de consulta de costos, puede ver cualquiera de las áreas, además del artículo y el código de tipo de costo. Al eliminar estos artículos, puede ajustar la página agrupando los costos. Esta capacidad puede resultar útil si utiliza tamaños y colores. Puede cambiar las dimensiones que se muestran en la página. La página **Costos** muestra solo códigos de tipo de costo donde el campo **Dr** de la pestaña **Registro** está configurado en *Artículo*. |

## <a name="header-view"></a>Visualización de encabezado

Para abrir la vista **Encabezado**, abra un folio y luego seleccione la pestaña **Encabezado** en la parte superior derecha del encabezado del folio.

### <a name="settings-on-the-general-fasttab"></a>Configuración en la ficha desplegable General

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **General** de la vista **Encabezamiento** de un folio.

| Campo | Descripción |
|---|---|
| Folio | Nombre del folio. Este nombre se genera automáticamente cuando se crea la publicación.|
| Viaje | El viaje asociado con el folio. |
| Agente de aduanas | Seleccione el agente de aduanas para el folio. Los agentes de aduanas se definen en el proveedor. Permiten determinar automáticamente los costes creados. |
| Hoja de ruta aérea/Conocimiento de embarque interno | Especifique la guía aérea de la casa o el conocimiento de embarque que se aplica al folio. |
| Empresa | La entidad jurídica (empresa) asociada al folio. |
| Número de control de carga | Este campo lo utilizan los departamentos de aduanas de algunos países o regiones. |
| Medida | Este campo permite especificar una medida en el módulo **Coste descargado**. Las medidas suelen ser utilizadas por organizaciones que no conocen el volumen o el peso individual de los productos, pero que requieren una distribución más precisa que la que proporciona la cantidad o cantidad. El transportista proporcionará el peso o la medida cúbica, y puede ponerlo al nivel de un artículo o de la orden de compra. Se puede actualizar automáticamente si se selecciona el parámetro, o se puede ingresar manualmente. |
| Unidad de medida | La unidad que se aplica a la medida especificada. |
| Número de cajas | El número de cajas en el folio. Este campo se puede actualizar automáticamente, dependiendo de la selección de parámetros. |
| Cuenta del proveedor | Seleccionar la cuenta del proveedor que está asociada al folio. La finalidad de este campo es meramente informativa. No afecta a ninguna funcionalidad. |
| Nombre | El nombre de la cuenta de proveedor seleccionada. |
| Comentarios | Escriba información adicional relacionada con el folio. |
| Descripción de los bienes | Seleccione una descripción de la mercancía para ayudar a identificar el folio. Para más información, consulte [Descripción de mercancías](shipping-information-setup.md#description-of-goods). |
| Fecha de valorización | Este campo está relacionado con la página de entrada de derechos. El módulo **Coste descargado** utilizará el tipo de cambio de aduana para la fecha que establezca aquí. El valor predeterminado es la fecha en la página de entrada de derechos. |
| Id. de aduanas | Especifique el identificador de aduanas. Los departamentos de aduanas de países o regiones proporcionan esta identificación. |
| Código de tarifa | Ingrese un código de tarifa para asociarlo con el folio. Por lo general, este código es requerido (y definido) por el país o la región al que realiza el envío. |

### <a name="settings-on-the-delivery-fasttab"></a>Configuración en la ficha desplegable Entrega

La siguiente tabla describe las configuraciones que están disponibles en la ficha desplegable **Entrega** de la vista **Encabezamiento** de un folio.

| Campo | Descripción |
|---|---|
| Fecha de folio | Seleccione una fecha para asociarlo al folio. El valor predeterminado es la fecha de creación del viaje. |
| Hora de llegada estimada en puerto de envío | La fecha estimada de llegada (ETA) al puerto de destino (puerto "a"). |
| Fecha de entrega estimada | Por lo general, la fecha en la que las mercancías deben llegar al almacén. Este campo no se utiliza cuando se calcula la fecha de entrega estimada. (En su lugar, se utiliza la fecha de entrega estimada del control de seguimiento). Para configurar este campo de modo que el valor coincida con la fecha de entrega estimada del control de seguimiento, utilice el [centro de control de seguimiento](delivery-information-setup.md#tracking-control-center). |
| Documentos originales recibidos | La fecha en la que se recibieron los documentos originales. |
| Con recomendación del agente | La fecha en la que se notificó al corredor. |
| Estado de desembarque original enviado | La fecha en la que se envió el conocimiento de embarque original. |
| Mercancías liberadas | La fecha en que se despacharon las mercancías. |
| Cita del cliente | La fecha de la cita del cliente. |
| Entregado en almacén | La fecha en la que se entregaron las mercancías al almacén. |
| Fecha de verificación | La fecha de verificación. |
| Instrucciones de entrega | La fecha en la que se recibieron las instrucciones de entrega. |
| Puerto de origen | El puerto desde el que parte el viaje. |
| Puerto de destino | El puerto donde llega el viaje. El contenedor de envío puede tener un puerto diferente, porque el barco puede detenerse en varios puertos. |

### <a name="settings-on-the-export-fasttab"></a>Configuración en la ficha desplegable Exportar

La siguiente tabla describe las configuraciones que están disponibles en la ficha desplegable **Exportar** de la vista **Encabezamiento** de un folio.

| Campo | Descripción |
|---|---|
| Exportador | El exportador se puede almacenar en el folio. En el comercio internacional, puede enviar una orden de compra a una empresa pero recibir los productos de otra empresa. La aduana requiere el seguimiento y la documentación. El nombre y la dirección del exportador se pueden almacenar aquí. |
| Nombre | Nombre del exportador seleccionado. |

## <a name="lines-view"></a>Vista de líneas

Para abrir la vista **Líneas**, abra un folio y luego seleccione la pestaña **Líneas** en la parte superior derecha del encabezado del folio.

### <a name="information-on-the-folio-fasttab"></a>Información en la ficha desplegable Folio

La ficha desplegable **Folio** en la vista **Líneas** muestra información sobre el folio. La mayor parte de esta información también aparece en la vista **Encabezamiento**, como se describió anteriormente en este tema.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Información y botones en la ficha desplegable Líneas

La ficha desplegable **Líneas** de la vista **Líneas** muestra detalles sobre cada línea de pedido de compra total o parcial que se incluye en el folio actual.

La tabla siguiente describe los botones disponibles en la barra de herramientas de la ficha desplegable **Líneas** de la vista **Líneas**.

| Botón | Descripción |
|---|---|
| Eliminar | Elimine la línea de orden de compra seleccionada del viaje. |
| Inventario \> Transacciones | Vea las transacciones de inventario para la línea de pedido de compra seleccionada. Tenga en cuenta que si utiliza mercancías en tránsito, también se muestran el pedido original y las órdenes de mercancías en tránsito. |
| Inventario \> Mostrar dimensiones | Abra un cuadro de diálogo donde puede seleccionar las dimensiones de inventario que aparecen para las transacciones que ve. |
| Actualización | Actualice la información relacionada con la cantidad, el peso o el volumen de la línea de la orden de compra seleccionada. |

### <a name="information-on-the-lines-details-fasttab"></a>Información sobre la ficha desplegable de detalles de líneas

La ficha desplegable **Detalles de líneas** de la vista **Líneas** muestra detalles sobre la línea de pedido de compra que está actualmente seleccionada en la ficha desplegable **Líneas**.
