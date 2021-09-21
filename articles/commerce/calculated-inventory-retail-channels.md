---
title: Calcular la disponibilidad de inventario para canales comerciales
description: Este tema describe cómo una empresa puede usar Microsoft Dynamics 365 Commerce para ver la disponibilidad inmediata estimada de productos en los canales en línea y de la tienda.
author: hhainesms
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: d3cfd8c2f0b88a4e634cee0398283a51eddf60b2
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472180"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcular la disponibilidad de inventario para canales comerciales

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este tema describe cómo una empresa puede usar Microsoft Dynamics 365 Commerce para ver la disponibilidad inmediata estimada de productos en los canales en línea y de la tienda.

## <a name="accuracy-of-inventory-availability"></a>Precisión de la disponibilidad de inventario

Commerce utiliza múltiples servidores y bases de datos para garantizar la escalabilidad y el rendimiento. Por lo tanto, es importante que comprenda que los valores de inventario disponibles que se proporcionan a través de la aplicación de punto de venta (PDV), las interfaces de programación de aplicaciones (API) de disponibilidad de inventario de comercio electrónico y las páginas de inventario disponibles en la sede de Commerce podrían no ser 100 % precisas en tiempo real. Si las transacciones que se crean para productos en el canal en línea o en la tienda aún no se han sincronizado con la sede central, las páginas de inventario disponibles en la sede central podrían no mostrar un valor de inventario preciso en tiempo real para esos productos. Por el contrario, si configuró su empresa para que los usuarios de la sede central u otras aplicaciones integradas puedan vender, recibir, devolver o ajustar el inventario de una tienda o almacén en línea, es posible que el PDV o el canal en línea no tengan toda la información necesaria para mostrar valores disponibles en tiempo real precisos para los artículos.

Es fundamental que comprenda que todos los datos de disponibilidad disponibles que se proporcionan durante el día operativo se consideran un valor estimado. Por lo tanto, si intenta comparar la información de inventario disponible que la aplicación proporciona con el inventario físico real en los estantes, o si intenta comparar los valores disponibles que se muestran en el PDV con los datos disponibles que encuentra para el mismo almacén en la sede central, los valores pueden diferir. Se espera esta diferencia durante el día operativo y no debe considerarse un problema. Si desea auditar los datos y asegurarse de que los valores que se proporcionan en el PDV, las API y la sede central coinciden con las unidades físicas reales que encuentra en su tienda o estanterías de almacén, el mejor momento para hacerlo es después de que las operaciones del canal se hayan detenido para ese día y todas las transacciones se hayan sincronizado correctamente entre la sede central y los canales.

## <a name="channel-side-inventory-calculation"></a>Cálculo de inventario del lado del canal

El cálculo del inventario del lado del canal es un mecanismo que toma los datos de inventario del último canal conocidos en la sede de Commerce como línea de base y luego toma en cuenta los cambios de inventario adicionales que ocurrieron en el lado del canal que no están incluidos en esa línea de base para calcular un inventario disponible con estimación casi en tiempo real. 

Los siguientes cambios de inventario se consideran actualmente en la lógica de cálculo de inventario del lado del canal:

- Inventario vendido a través de pedidos de pago y recogida en la tienda
- Inventario vendido a través de pedidos de clientes en la tienda o canal en línea
- Inventario devuelto a la tienda
- Inventario cumplimentado (recoger, embalar, enviar) desde el almacén

Para utilizar el cálculo de inventario del lado del canal, debe habilitar la característica **Cálculo optimizado de la disponibilidad del producto**.

Si su entorno de Commerce tiene la versión de la **10.0.8 hasta la 10.0.11**, siga estos pasos.

1. En In Commerce Headquarters, Vaya a **Retail y Commerce** \> **Parámetros compartidos de Commerce**.
1. En la pestaña **Inventario**, en el campo **Disponibilidad de producto trabajo**, seleccione **Usar el proceso optimizado para el trabajo de disponibilidad del producto**.

Si su entorno de Commerce tiene la versión **10.0.12 o posterior**, siga estos pasos.

1. En Commerce Headquarters, vaya a **Espacios de trabajo \> Administración de caracterísicas** y habilite la característica **Cálculo optimizado de disponibilidad de producto**.
1. Si sus canales en línea y de tienda utilizan los mismos almacenes de cumplimiento, también debe habilitar la característica **Lógica mejorada de cálculo de inventario del lado del canal de comercio electrónico**. De esa manera, la lógica de cálculo del lado del canal considerará las transacciones no contabilizadas que se crean en el canal de la tienda. (Esas transacciones pueden ser transacciones de efectivo y acarreo, pedidos de clientes y devoluciones).
1. Ejecute el trabajo **1070** (**Configuración del canal**) .

Si su entorno de Commerce se actualizó desde una versión anterior a la versión 10.0.8 de Commerce, después de habilitar la función **Cálculo optimizado de la disponibilidad del producto**, también debe ejecutar **Inicializar el programador de comercio** para que la función surta efecto. Para ejecutar la inicialziación, vaya a **Retail y Commerce** \> **Configuración de sede central** \> **Programador de Commerce**.

Para utilizar el cálculo de inventario del lado del canal, como requisito previo, una instantánea periódica de los datos de inventario de la sede creada por el trabajo **Disponibilidad de producto** debe enviarse a las bases de datos del canal. La instantánea representa la información que la sede central tiene sobre la disponibilidad de inventario para una combinación específica de un producto o variante de producto y un almacén. Incluye solo las transacciones de inventario que se procesaron y registraron en la sede central en el momento en que se tomó la instantánea, y es posible que no sea 100 % precisa en tiempo real, debido al constante procesamiento de ventas que se produce en los servidores distribuidos.

- Si el inventario se vendió para un producto en una tienda a través de una venta de pago y recogida o pedido asíncrono de cliente en la aplicación PDV, la sede central no tendrá inmediatamente información sobre la transacción de incidencia de inventario relacionada para la venta. La sede central tendrá información sobre el inventario que se vende para este tipo de ventas en la tienda solo después de que el trabajo P cargue la transacción relacionada de la base de datos de canales de la tienda en la sede central y los pedidos de ventas relacionados se creen a través de la contabilización de estados de cuenta o los procesos de registro de suministro contabilización de alimentación por pequeñas cantidades. El proceso de creación de los pedidos en la sede central crea las transacciones de inventario relacionadas. 
- Para los pedidos del canal de comercio electrónico, la sede central tiene información sobre las transacciones de inventario solo después de que las transacciones se envían a la sede central a través del trabajo P y se completa el proceso de sincronización de pedidos.

Para tomar una instantánea del inventario en la sede central, siga estos pasos.

1. Vaya a **Retail y Commerce \> Retail y Commerce TI \> Productos e inventario \> Disponibilidad de producto**.
1. Seleccione **Aceptar** para ejecutar el trabajo **Disponibilidad de producto**. También puede programar este trabajo para que se ejecute en lote.

Después de que el trabajo **Disponibilidad de producto** ha terminado de ejecutarse, los datos que se capturaron deben enviarse a las bases de datos del canal, de modo que se pueda considerar la última instantánea del inventario de la sede central en el cálculo del inventario disponible estimado.

Para sincronizar los datos de la instantánea de la sede a las bases de datos de su canal, siga estos pasos.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **1130** (**Disponibilidad de producto**) para sincronizar los datos de la instantánea que el trabajo **Disponibilidad de producto** ha creado desde la sede central con las bases de datos de su canal.

## <a name="inventory-availability-apis-for-e-commerce"></a>API de disponibilidad de inventario para comercio electrónico

Commerce proporciona las siguientes API para escenarios de comercio electrónico, para consultar la disponibilidad de inventario de un producto:

- **GetEstimatedAvailability**: utilice esta API para consultar el inventario de un producto o variante de producto en el almacén del canal en línea o en los almacenes que están vinculados al grupo de cumplimiento del canal en línea.
- **GetEstimatedProductWarehouseAvailability**: use esta API para consultar el inventario para un producto o variante de producto de un almacén específico.

> [!NOTE]
> Estas API reemplazan las API **GetProductAvailabilities** y **GetAvailableInventoryNearby** en la versión de Commerce 10.0.7 y anteriores.

Ambas API utilizan internamente la lógica de cálculo del lado del canal y devuelven estimaciones de cantidades **físicamente disponibles**, la cantidad **total disponible**, la **unidad de medida (UoM)** y el **nivel del inventario** para el producto solicitado y el almacén. Los valores devuelltos se pueden mostrar en su sitio de comercio electrónico si lo desea, o se pueden utilizar para desencadenar otra lógica de negocios en su sitio de comercio electrónico. Por ejemplo, puede evitar la compra de productos con un nivel de inventario "agotado".

Aunque otras API que están disponibles en Commerce pueden ir directamente a la sede central para obtener cantidades disponibles de productos, no recomendamos que se usen en un entorno de comercio electrónico debido a posibles problemas de rendimiento y el impacto relacionado que estas solicitudes frecuentes pueden tener en sus servidores de la sede central. Además, con el cálculo del lado del canal, las dos API mencionadas anteriormente pueden proporcionar una estimación más precisa de la disponibilidad de un producto al tener en cuenta las transacciones creadas en los canales que aún no conoce la sede central.

Para definir cómo se debe devolver la cantidad de producto en la salida de la API, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce**.
1. Seleccione la pestaña **Inventario** y luego, en la ficha desplegable **API de disponibilidad de inventario para comercio electrónico**, configure el valor de la opción **Cantidad en salida de API**.
1. Ejecute el trabajo **1070** (**Configuración de canal**) para sincronizar la última opción en los canales.

La opción **Cantidad en salida de API** ofrece tres opciones:

- **Devolver la cantidad de inventario**: la cantidad física disponible y la cantidad total disponible de un producto solicitado se devuelven en la salida de la API.
- **Devolver la cantidad de inventario restando el búfer de inventario**: la cantidad devuelta en la salida de la API se ajusta restando el valor del búfer de inventario. Para obtener más información sobre el búfer de inventario, consulte [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).
- **No devolver la cantidad de inventario**: solo se devuelve el nivel de inventario en la salida de la API. Para obtener más información sobre los niveles de inventario, consulte [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).

Puede usar el parámetro de API `QuantityUnitTypeValue` para especificar el tipo de unidad en el que le gustaría que las API devuelvan la cantidad. Este parámetro es compatible con las opciones **unidad de inventario** (predeterminada)**, unidad de compra** y **unidad de venta**. La cantidad devuelta se redondea a la precisión definida de la unidad de medida (UOM) correspondiente en la sede.

La API **GetEstimatedAvailability** ofrece los siguientes parámetros de entrada para admitir diferentes escenarios de consulta:

- `DefaultWarehouseOnly`: utilice este parámetro para consultar el inventario de un producto en el almacén predeterminado del canal en línea. 
- `FilterByChannelFulfillmentGroup` y `SearchArea`: utilice estos dos parámetros para consultar el inventario de un producto desde todas las ubicaciones de recogida dentro de un área de búsqueda específica, según `longitude`, `latitude` y `radius`. 
- `FilterByChannelFulfillmentGroup` y `DeliveryModeTypeFilterValue`: utilice estos dos parámetros para consultar el inventario de un producto de almacenes específicos que están vinculados al grupo de cumplimiento de un canal en línea y están configurados para admitir ciertos modos de entrega. El parámetro `DeliveryModeTypeFilterValue` admite las opciones **todo** (predeterminado), **envío** y **recogida**. Por ejemplo, en un escenario en el que un pedido en línea se puede cumplimentar desde varios almacenes de envío, puede usar estos dos parámetros para consultar la disponibilidad de inventario de un producto en todos esos almacenes de envío. En este caso, la API devuelve la cantidad disponible del producto y el nivel de inventario en cada uno de los almacenes de envío, más una cantidad agregada y un nivel de inventario agregado de todos los almacenes de envío en el ámbito de la consulta.
 
Los módulos de cuadro de compra, selector de tienda, lista de deseos, carrito e icono de carrito de Commerce utilizan las API y los parámetros mencionados anteriormente para mostrar mensajes de nivel de inventario en el sitio de comercio electrónico. El creador de sitios de Commerce proporciona varias configuraciones de inventario para controlar la comercialización y el comportamiento de compra. Para obtener más información, consulte [Aplicar configuración de inventario](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Búsqueda de inventario de PDV con cálculo del lado del canal

En la versión 10.0.9 y anteriores de Commerce, la operación **Búsqueda de inventario** en PDV utiliza una llamada de servicio en tiempo real a la sede central para obtener información de inventario para el producto seleccionado, tanto para la tienda actual del usuario como para cualquier otra tienda que esté configurada para el grupo de cumplimiento como parte de la configuración del canal para la tienda. En la versión 10.0.10 de Commerce y posteriores, puede desactivar las llamadas de servicio en tiempo real a la sede central y, en su lugar, utilizar el cálculo del lado del canal en el servidor de Commerce para determinar el inventario disponible que está disponible físicamente para la tienda y cualquier otra ubicación definida en el grupo de cumplimentación. Esta configuración de inventario calculada por canal también es útil para ubicaciones donde la conectividad a Internet no es fiable, ya que no tiene que estar en línea para obtener búsquedas de inventario desde la sede central.

Cuando el cálculo del lado del canal está configurado y administrado correctamente, puede proporcionar una estimación más fiable del inventario de la tienda actual, ya que utiliza los datos transaccionales que se encuentran en la base de datos del canal de Commerce, pero de los cuales la sede central pudiera no tener información aún. Por ejemplo, si utiliza la llamada de servicio en tiempo real existente para búsquedas de inventario en PDV, la sede central probablemente todavía no tendrá información sobre una venta de pago y recogida que acaba de ocurrir para un producto. Por lo tanto, el valor de inventario disponible que devuelve la sede central para ese producto probablemente excederá el inventario disponible real de la tienda en una unidad. Sin embargo, si usa el cálculo del lado del canal, la venta de efectivo y transporte puede incluirse en el cálculo y deducirse del valor disponible que se muestra. Aunque los valores que proporcionan tanto el cálculo del lado del canal como la llamada de servicio en tiempo real son solo estimaciones del inventario disponible, el valor que proporciona el cálculo del lado del canal es mucho más probable que sea preciso para la tienda actual.

Para configurar la operación **Búsqueda de inventario** de PDV en Commerce Headquarters para usar la lógica de cálculo del lado del canal y desactivar la llamada de servicio en tiempo real, primero debe habilitar la característica **Cálculo optimizado de disponibilidad de producto** a través del espacio de trabajo **Administración de características** de Commerce Headquarters y luego seguir estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**.
1. Seleccione un perfil de funcionalidad.
1. En la ficha desplegable **Funciones**, en la sección **Cálculo de disponibilidad de inventario**, cambie el valor de **Modo de cálculo de disponibilidad de inventario** de **Servicio en tiempo real** a **Canal**. Por defecto, todos los perfiles de funcionalidad utilizan llamadas de servicio en tiempo real. Debe cambiar el valor de este campo si desea utilizar la lógica de cálculo del lado del canal. Todas las tiendas minoristas que estén vinculadas al perfil de funcionalidad seleccionado se verán afectadas por este cambio.

Luego debe sincronizar los cambios en los canales a través del proceso de programación de distribución en la sede central siguiendo estos pasos.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **1070** (**Configuración del canal**) .

Una vez completada la configuración, la información que se proporciona sobre el inventario físicamente disponible ya no utiliza una llamada de servicio en tiempo real cuando un usuario en la aplicación PDV utiliza la operación **Búsqueda de inventario** (vistas estándar y matriciales). En cambio, los datos sobre el inventario físicamente disponible para la tienda actual y todas las tiendas en el grupo de cumplimiento se calculan en función de la última instantánea conocida que se entregó a la base de datos de canales desde Commerce Headquarters. El valor de la instantánea se refina aún más mediante el cálculo del lado del canal para ajustar el valor físicamente disponible, en función de las ventas adicionales o las transacciones de devolución que existen para el producto seleccionado en la base de datos del canal que no se incluyeron en la última instantánea sincronizada del trabajo 1130. Si la base de datos del canal no contiene datos transaccionales para ninguno de los almacenes o tiendas en el grupo de cumplimiento, no contiene transacciones adicionales que se puedan factorizar en un recalculo del valor. Por lo tanto, la mejor estimación del inventario disponible que se puede mostrar para esos almacenes o tiendas son los datos de la última instantánea conocida de la sede de Commerce.

Las pantallas **Cumplimiento de la orden** de PDV también aprovechan el cálculo del lado del canal para mostrar el inventario disponible de artículos cuando se selecciona una línea de cumplimiento de pedido y un usuario ve el panel **Detalles** para el inventario disponible para el artículo seleccionado.

## <a name="optimize-your-inventory-data"></a>Optimice sus datos de inventario

Para garantizar la mejor estimación posible del inventario, es fundamental que utilice los siguientes trabajos por lotes de Commerce y los ejecute con frecuencia:

- **Trabajo P** - El trabajo P se encuentra en la página **Horarios de distribución** y debe ejecutarse con frecuencia. Este trabajo lleva los pedidos de comercio electrónico, los pedidos de clientes asíncronos que PDV creó y los pedidos de efectivo y transporte que los PDV crearon desde las bases de datos del canal a la sede de Commerce, para que puedan procesarse aún más. Hasta que estos datos se sincronicen desde el canal a la sede de Commerce, la sede de Commerce no tiene información sobre los ajustes de inventario de los productos en los almacenes que resultan de esas transacciones.
- **Sincronizar pedidos** - Este trabajo procesa los datos transaccionales sin procesar en Commerce Headquarters que proporciona el trabajo P y convierte el comercio electrónico y las transacciones asíncronas de pedidos de clientes en pedidos de ventas en Commerce Headquarters. Hasta que se procese este trabajo y se creen los pedidos de ventas, no se crearán transacciones de inventario. Por lo tanto, el inventario disponible en la sede de Commerce no considerará las transacciones.
- **Calcular declaraciones transaccionales en lote** - Para las transacciones de efectivo y transporte que se crean en la tienda, el proceso de contabilización de alimentación por goteo garantiza que el inventario relacionado con las ventas se actualice de manera eficiente. Para obtener el procesamiento más eficiente de las transacciones de inventario para los pedidos de efectivo y transporte, asegúrese de configurar su sistema para usar [publicación de alimentación por goteo](./trickle-feed.md).
- **Publicar extractos transaccionales en lote** - Este trabajo también es necesario para la publicación de alimentación por goteo. Sigue el trabajo **Calcular declaraciones transaccionales en lote**. Este trabajo publica sistemáticamente los extractos calculados, de modo que los pedidos de ventas para ventas en efectivo se llevan a cabo en la sede de Commerce y la sede de Commerce refleja con mayor precisión el inventario de su tienda.
- **Disponibilidad de producto** - Este trabajo crea la instantánea del inventario de Commerce Headquarters.
- **1130 (disponibilidad del producto)** - Este trabajo se encuentra en la página **Programación de distribución** y debe ejecutarse inmediatamente después del trabajo **Disponibilidad de producto**. Este trabajo transporta los datos de la instantánea del inventario desde la sede de Commerce a las bases de datos del canal.

> [!NOTE]
> - Es práctica recomendada ejecutar los trabajos **Disponibilidad de productos** y **1130** cada hora, programar trabajos P, sincronizar pedidos y trabajos relacionados con el registro de suministro en pequeñas cantidades con la misma o mayor frecuencia.
> - Por razones de rendimiento, cuando los cálculos de disponibilidad de inventario del lado del canal se utilizan para realizar una solicitud de disponibilidad de inventario utilizando las API de comercio electrónico o la lógica de inventario del lado del canal PDV, el cálculo utiliza una memoria caché para determinar si ha pasado suficiente tiempo para justificar la ejecución de la lógica de cálculo de nuevo. La caché predeterminada está fijada en 60 segundos. Por ejemplo, activó el cálculo del lado del canal para su tienda y vio el inventario disponible de un producto en la página **Búsqueda de inventario**. Si luego se vende una unidad del producto, la página **Búsqueda de inventario** no mostrará el inventario reducido hasta que se haya borrado el caché. Después de que los usuarios publiquen transacciones en PDV, deben esperar 60 segundos antes de verificar que se haya reducido el inventario disponible.

Si su situación empresarial requiere un menor tiempo de caché, póngase en contacto con su representante de soporte de productos para obtener asistencia.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
