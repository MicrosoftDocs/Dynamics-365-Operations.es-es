---
title: Procesamiento de mercancía en tránsito
description: En este tema se describe cómo trabajar con pedidos de mercancía en tránsito. Cuando se configura un pedido o un viaje para utilizar el procesamiento de mercancías en tránsito, las mercancías se pueden facturar antes de que se reciban en el almacén para su consumo.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ecf8caa7f31c560af2cbc929a37f3ca02bd0da44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021209"
---
# <a name="goods-in-transit-processing"></a>Procesamiento de mercancía en tránsito

[!include [banner](../../includes/banner.md)]

En este tema se describe cómo trabajar con pedidos de mercancía en tránsito. Este tipo de orden es utilizado solo por el módulo **Coste de aterrizaje**. Cuando se configura un pedido o un viaje para utilizar el procesamiento de mercancías en tránsito, no tiene que esperar hasta que los productos se reciban en el almacén para facturarlos. En cambio, las mercancías se facturan cuando salen del almacén del vendedor o del puerto de origen, y los costos financieros se reconocen cuando comienza el viaje. Esta funcionalidad le permite apropiarse correctamente del inventario, porque las mercancías a menudo se convierten en propiedad de su organización cuando salen del puerto de envío.

Cuando se utilizan pedidos de mercancías en tránsito, los artículos actualizados financieramente se reciben en un almacén provisional que se conoce como almacén de mercancías en tránsito. Luego, las mercancías permanecen en este almacén hasta que se pueden recibir en el almacén de destino final (es decir, el almacén que se define en la línea de compra). No se pueden eliminar manualmente.

Mientras los artículos estén en tránsito, no están disponibles en el inventario y no se pueden recoger del inventario para una entrega. Sin embargo, puede ver el inventario de mercancías en tránsito. También puede usar los productos para la planificación maestra. En este caso, use la fecha de entrega confirmada en la línea de la orden de compra como la fecha esperada cuando el inventario estará disponible para el consumo.

Las siguientes secciones describen la configuración necesaria para procesar el inventario y los viajes mediante el concepto y la funcionalidad de mercancías en tránsito.

## <a name="terms-of-delivery"></a>Condiciones de entrega

Cuando habilita el módulo **Coste de aterrizaje**, la entidad estándar de *condiciones de entrega* se ha mejorado para admitir la función de mercancías en tránsito.

Cuando la opción **Gestión de mercancías en tránsito** está configurada en *Sí* para los términos aplicables del registro de entrega, las mercancías se colocan en el almacén de mercancías en tránsito. Esta acción se activa solo si el recibo de inventario no se procesa antes de que se procese una factura. Cuando los términos de entrega de un pedido están configurados para utilizar mercancías en tránsito, los usuarios ya no pueden registrar una recepción de producto para el pedido de compra. Si lo intentan, se produce un error. El mensaje de error indica que deben utilizar la función de mercancías en tránsito para continuar.

Para trabajar con la información de condiciones de entrega para mercancías en tránsito, vaya a **Adquisiciones y abastecimiento \> Configuración \> Distribución \> Condiciones de entrega**. La siguiente tabla describe los campos que el módulo **Coste de aterrizaje** suma a la página **Condiciones de entrega** para admitir la funcionalidad de mercancías en tránsito. Ambos campos están en la ficha desplegable **General**. Para obtener más información sobre los otros campos de esta página, consulte [Condiciones de entrega (formulario)](/dynamicsax-2012//terms-of-delivery-form).

| Campo | Descripción |
|---|---|
| Puerto de envío obligatorio | Establezca esta opción en *Sí* si un puerto de envío es obligatorio cuando se aplican los términos de entrega. |
| Administración de la mercancía en tránsito | Establezca esta opción en *Sí* para utilizar la gestión de mercancías en tránsito cuando se apliquen los términos de entrega. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Almacenes para mercancías en tránsito y entregas insuficientes

Cuando habilita el módulo **Coste de aterrizaje**, la entidad estándar de *almacenes* se ha mejorado para permitir que las órdenes de compra se facturen mientras las mercancías se encuentran en un almacén de mercancías en tránsito.

El costo de entrega agrega dos nuevos tipos de almacén: *mercancías en tránsito* y *entrega insuficiente*. Los almacenes de ambos tipos se pueden seleccionar como almacenes predeterminados. El procesamiento exitoso de pedidos de mercancías en tránsito requiere que tanto el almacén de mercancías en tránsito como el almacén de entrega insuficiente estén configurados en la página **Almacenes**. Luego, para cada almacén predeterminado que se utilizará con costo de entrega y mercancías en tránsito, se debe seleccionar el almacén de mercancías en tránsito y el almacén de entrega insuficiente para los almacenes disponibles de cada tipo.

El tipo de almacén de *mercancías en tránsito* se asociará con su almacén de mercancías en tránsito, y ese almacén se utilizará para procesar las mercancías en los pedidos de mercancías en tránsito antes de que se reciban en el almacén de destino final. En general, un almacén de mercancías en tránsito es suficiente para cada sitio si Sitio y Almacén son las únicas dimensiones de inventario que se utilizan para la gestión de inventario. Si también se utiliza la dimensión de inventario de ubicación, se debe configurar un almacén de mercancías en tránsito para cada combinación de un sitio y un almacén, de modo que también se pueda especificar la ubicación predeterminada.

Para trabajar con la configuración de mercancías en tránsito para sus almacenes, vaya a **Gestión del inventario \> Configuración \> Desglose de inventario \> Almacenes**. La siguiente tabla describe los campos que el módulo **Coste de aterrizaje** suma a la página **Almacenes** para admitir la funcionalidad de mercancías en tránsito. Ambos campos aparecen en la ficha desplegable **General**. Para obtener más información acerca de los otros campos de la página, vea [Almacenes (formulario)](/dynamicsax-2012//warehouses-form).

| Campo | Descripción |
|---|---|
| Almacén de mercancía en tránsito | Identifique el almacén de mercancías en tránsito relacionado con el almacén principal. |
| Almacén de entregas incompletas | Identifique el almacén con entrega insuficiente relacionado con el almacén principal. |

## <a name="posting-rules-for-landed-cost"></a>Reglas de publicación para el costo de entrega

El costo de entrega agrega dos nuevas reglas de publicación que puede configurar. Estas reglas de contabilización se utilizan para contabilizar financieramente los importes de la factura de la orden de compra directa para identificar la propiedad de las mercancías cuando salen del punto de origen. Este proceso reemplaza el concepto de *bienes recibidos no facturados*, porque las mercancías se facturan antes de su recepción. <!-- KFM: Add a link to the related scenario when available. -->

Para trabajar con perfiles de publicación, vaya a **Gestión del inventario \> Configuración \> Destino \> Destino**. En la pestaña **Orden de compra**, las siguientes nuevas reglas de publicación están disponibles:

- **Costo de destino, mercancías en tránsito** - Especificar las reglas de contabilización para la gestión de mercancías en tránsito.
- **Costo de destino, acumulación de cargo por costo** - Especifique las reglas de contabilización para la acumulación de cuentas de cargo.

## <a name="goods-in-transit-orders"></a>Pedidos de mercancía en tránsito

Puede revisar y administrar pedidos de mercancías en tránsito directamente en el módulo **Coste de aterrizaje**. Puede procesar pedidos de mercancías en tránsito directamente desde la página **Pedidos de mercancías en tránsito**. Alternativamente, puede ir al viaje asociado con los pedidos de mercancías en tránsito y procesar todo el viaje, el contenedor de envío o el folio. Cuando factura un viaje y crea órdenes de mercancías en tránsito, se crea una nueva orden de mercancías en tránsito para cada combinación de inventario y dimensiones de inventario que está asociada con la línea de orden de compra.

Para administrar mercancías en tránsito, el costo de entrega utiliza un procedimiento de dos pasos:

1. Se recibe un artículo cuando se procesa una factura de existencias y se le asigna un estado de *En tránsito*.
1. El pedido de mercancías en tránsito se procesa en la página **Pedidos de mercancías en tránsito** y luego se recibe en el almacén que se especifica en la orden de compra. En ese momento, el estado cambia a *Recibido*.

Para trabajar con pedidos de mercancías en tránsito, vaya a **Coste de aterrizaje \> Tareas periódicas \> Pedidos de mercancías en tránsito**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Recepción de stock del almacén de mercancías en tránsito

Puede recibir mercancías de un pedido de mercancías en tránsito de muchas formas, según la configuración de su sistema.

### <a name="in-transit-receiving"></a>Recepción en tránsito

Puede realizar la recepción en tránsito desde cualquiera de las siguientes páginas:

- En la página **Pedidos de mercancías en tránsito**, seleccione la línea y luego, en el Panel de acciones, seleccione **Recibir**.
- En la página **Todos los viajes**, seleccione o abra un viaje. Luego, en el Panel de acciones, en la pestaña **Administrar**, en el grupo **Mercancías en tránsito**, seleccione **Recibir mercancías en tránsito**.
- En la página **Todos los contenedores de envío**, seleccione o abra un contenedor de envío. Luego, en el Panel de acciones, en la pestaña **Administrar**, en el grupo **Mercancías en tránsito**, seleccione **Recibir mercancías en tránsito**.
- En la página **Todos los folios**, seleccione o abra un folio. Luego, en el Panel de acciones, en la pestaña **Administrar**, en el grupo **Mercancías en tránsito**, seleccione **Recibir mercancías en tránsito**.

> [!NOTE]
> La recepción en tránsito se usa generalmente en situaciones en las que no se usan ubicaciones y seguimiento de lotes / series.

### <a name="arrival-journal"></a>Diario de llegadas

También puede recibir mercancías creando un diario de llegadas. Puede crear un diario de llegadas directamente desde la página del viaje. Las mejores prácticas que ha establecido su organización determinan si el diario de llegadas se utiliza para recibir mercancías.

1. Abra el viaje, contenedor o folio.
1. En el Panel de acciones, en la ficha **Gestionar**, en el grupo **Funciones**, seleccione **Crear un diario de llegadas**.
1. En el cuadro de diálogo **Crear un diario de llegadas**, establezca los siguientes valores:
    - **Inicializar cantidad** - Establezca esta opción en *Sí* para establecer la cantidad a partir de la cantidad en tránsito. Si esta opción se establece en *No*, no se establece ninguna cantidad predeterminada de las líneas de mercancías en tránsito.
    - **Crear a partir de mercancías en tránsito** - Establezca esta opción en *Sí* para tomar cantidades de las líneas en tránsito seleccionadas para el viaje, contenedor o folio seleccionado.
    - **Crear a partir de líneas de pedido** - Establezca esta opción en *Sí* para establecer la cantidad predeterminada en el diario de llegadas de las líneas de la orden de compra. La cantidad predeterminada en el diario de llegadas se puede establecer de esta manera solo si la cantidad en la línea del pedido de compra coincide con la cantidad en el pedido de mercancías en tránsito.

1. Procese el diario de llegadas como se describe en [Registrar recibos de artículos con un diario de llegada de artículos](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> El diario de llegadas se utiliza generalmente en situaciones en las que se utilizan ubicaciones y seguimiento de lotes / series, pero no se utiliza la gestión del almacén.
>
> Las ubicaciones de recepción predeterminadas no deben especificarse en las líneas de pedido si se especificará una ubicación de almacenamiento en el diario de llegadas.

## <a name="warehouse-management"></a>Gestión de almacenes

Cuando habilita el módulo **Coste de aterrizaje**, varias páginas en el módulo **Gestion de almacenes** se modifican para que el procesamiento de pedidos (específicamente, procesamiento de mercancías en tránsito) se pueda realizar a través del módulo **Coste de aterrizaje**. Esta sección describe los campos y procesos que se agregan en el módulo **Gestion de almacenes**.

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

Los bienes se pueden recibir utilizando un dispositivo móvil, siempre que el menú del dispositivo móvil y el módulo **Gestion de almacenes** se ha configurado para recibir mercancías en un pedido de mercancías en tránsito. Esta sección describe la configuración asociada con la recepción de mercancías en tránsito.

Para configurar dispositivos móviles para el procesamiento de mercancías en tránsito, vaya a **Gestion de almacenes \> Configuración \> Dispositivo móvil \> Elementos del menú del dispositivo móvil**.

El costo de entrega agrega los siguientes procesos de creación de trabajo a los elementos del menú del dispositivo móvil para respaldar el procesamiento de mercancías en tránsito:

- Recepción de artículos de mercancía en tránsito
- Recepción y almacenamiento de artículos en tránsito

Los ajustes de configuración de estos procesos se asemejan a los ajustes de [procesos de creación de trabajos de recepción y almacenamiento de pedidos](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). Sin embargo, el proceso *Recepción y almacenamiento de artículos en tránsito* también agrega el siguiente campo.

- **Habilitar contenedor de envío completo** - Si esta opción está configurada en *Sí*, cuando se completa el trabajo de almacenamiento, la aplicación móvil Warehouse Management proporcionará una opción adicional que se denomina **Contenedor de envío completo**. Cuando se selecciona esa opción, se le pedirá al trabajador que confirme que el contenedor está completo. En ese momento, todos los recibos cortos se procesarán como una transacción inferior.

### <a name="location-directives"></a>Directivas de ubicación

El costo de entrega agrega un nuevo tipo de orden de trabajo que se denomina *Mercancías en tránsito* a la página **Directivas de ubicación**. Este tipo de orden de trabajo debe configurarse de la misma manera que los [tipos de orden de trabajo de órdenes de compra](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Plantillas de trabajo

El costo de entrega agrega un nuevo tipo de orden de trabajo que se denomina *Mercancías en tránsito* a la página **Plantillas de trabajo**. Este tipo de orden de trabajo debe configurarse de la misma manera que las [plantillas de trabajo de órdenes de compra](/dynamicsax-2012/appuser-itpro/create-a-work-template).