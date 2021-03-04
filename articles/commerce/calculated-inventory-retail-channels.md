---
title: Calcular la disponibilidad de inventario para canales minoristas
description: Este tema describe las opciones disponibles para mostrar el inventario disponible para la tienda y los canales en línea.
author: hhainesms
manager: annbe
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: de4ee98198f441b8f42a8a55aa5ff1015f485234
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415522"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcular la disponibilidad de inventario para canales minoristas

[!include [banner](../includes/banner.md)]

Este tema describe cómo una empresa puede usar Microsoft Dynamics 365 Commerce para ver la disponibilidad disponible estimada de productos en los canales en línea y de la tienda.

## <a name="accuracy-of-calculation"></a>Precisión de cálculo

Commerce utiliza múltiples servidores y bases de datos para garantizar la escalabilidad y el rendimiento. Por lo tanto, es importante que comprenda que los valores de inventario disponibles que se proporcionan a través de la aplicación de punto de venta (PDV), las interfaces de programación de aplicaciones (API) de disponibilidad de inventario de e-Commerce y las páginas de inventario disponibles en la sede de Commerce podrían no ser 100% precisas en tiempo real. Si las transacciones que se crean para productos en el canal en línea o en la tienda aún no se han sincronizado con el servidor y la base de datos de la sede de Commerce, las páginas de inventario disponibles en la sede de Commerce podrían no mostrar un valor de inventario preciso en tiempo real para esos productos. Por el contrario, si configuró su empresa para que los usuarios en Commerce Headquarters u otras aplicaciones integradas puedan vender, recibir, devolver o ajustar el inventario de una tienda o almacén en línea, es posible que el PDV o el canal en línea no tengan toda la información necesaria para mostrar un valor disponible en tiempo real exacto para los artículos.

Este tema explica los procesos de sincronización de datos que se pueden ejecutar con frecuencia para ayudar a limitar la latencia de datos entre aplicaciones o canales. Sin embargo, es fundamental que comprenda que todos los datos de disponibilidad disponibles que se proporcionan durante el día operativo se consideran un valor estimado. Por lo tanto, si intenta comparar la información de inventario disponible que la aplicación proporciona con el inventario físico real en los estantes, o si intenta comparar los valores disponibles que se muestran en PDV con los datos disponibles que encuentra para el mismo almacén en la sede de Commerce, los valores pueden diferir. Se espera esta diferencia durante el día operativo y no debe considerarse un problema. Si desea auditar los datos y asegurarse de que los valores que se proporcionan en las API de disponibilidad de inventario y Commerce Headquarters coinciden con las unidades físicas reales que encuentra en su tienda o estanterías de almacén, el mejor momento para hacerlo es después de que las operaciones del canal se hayan detenido para ese día y todas las transacciones se han sincronizado correctamente entre Commerce Headquarters y el canal.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Use las API de búsqueda de inventario para las solicitudes de disponibilidad de inventario de comercio electrónico

Puede usar las siguientes API para mostrar la disponibilidad de inventario de un producto cuando sus clientes compran en un sitio de comercio electrónico.

- **GetEstimatedAvailability**: use esta API para obtener disponibilidad de inventario para el artículo en el almacén del canal de comercio electrónico o en todos los almacenes que están vinculados a la configuración del grupo de cumplimiento para el canal de comercio electrónico. Esta API también se puede utilizar para almacenes en un área o radio de búsqueda específica, según los datos de longitud y latitud.
- **GetEstimatedProductWarehouseAvailability** - Use esta API para solicitar inventario para un artículo de un almacén específico. Por ejemplo, puede usarlo para mostrar la disponibilidad de inventario en escenarios que involucran la recolección de pedidos.

> [!NOTE]
> Estas API reemplazan las API **GetProductAvailabilities** y **GetAvailableInventoryNearby** en Dynamics 365 Retail versión 10.0.7 y anterior.

Ambas API obtienen datos del servidor de Commerce y proporcionan una estimación del inventario disponible para una combinación específica de un producto o variante de producto y un almacén. Aunque otras API que están disponibles en el servidor de Commerce pueden ir directamente a la sede de Commerce para obtener cantidades disponibles de productos, no recomendamos que se usen en un entorno de comercio electrónico debido a posibles problemas de rendimiento y el impacto relacionado que estas solicitudes frecuentes pueden tener en sus servidores de la sede de Commerce. Además, si el inventario disponible se calcula a través del servidor de Commerce, es más probable que el cálculo incluya el inventario que se vendió en transacciones recientes de comercio electrónico que aún no se han sincronizado con Commerce Headquarters. Aunque Commerce Headquarters podría no tener información sobre estas transacciones, el servidor de Commerce y la base de datos de canales tienen los datos. Por lo tanto, los datos se tendrán en cuenta y pueden ayudar a proporcionar una estimación más precisa del inventario disponible de un producto.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Comience con la disponibilidad de inventario calculada de comercio electrónico

Antes de utilizar las dos API que se mencionaron anteriormente, debe habilitar la característica **Cálculo optimizado de disponibilidad de producto** a través del espacio de trabajo **Administración de características** en la sede de Commerce.

Antes de que las API puedan calcular la mejor estimación de disponibilidad de inventario para un artículo, debe procesarse una instantánea periódica de la disponibilidad de inventario de la sede de Commerce y enviarse a la base de datos de canales que utiliza la Unidad de Escala de Commerce de Comercio Electrónico. La instantánea representa la información que Commerce Headquarters tiene sobre la disponibilidad de inventario para una combinación específica de un producto o variante de producto y un almacén. Puede incluir ajustes de inventario o movimientos causados por recibos de inventario, o por envíos u otros procesos que se realizan en Commerce Headquarters y sobre los que el canal de comercio electrónico tiene información solo debido al proceso de sincronización.

La instantánea de la base de datos que el trabajo **Disponibilidad de producto** crea calcula solo las transacciones de inventario que se procesaron y publicaron en la sede de Commerce en el momento en que se tomó la instantánea. Si el inventario se vendió para un producto en el almacén de una tienda a través de una venta por pedido en efectivo o asíncrona de pedidos de clientes en la aplicación PDV, la sede de Commerce no tendrá inmediatamente información sobre la transacción de emisión de inventario relacionada para la venta. Tendrá información sobre el inventario que se vende para este tipo de ventas en la tienda solo después de que el trabajo P cargue la transacción relacionada de la base de datos de canales de la tienda en la sede de Commerce y el pedido de ventas relacionado se cree a través de la contabilización de estados de cuenta o los procesos de contabilización de alimentación por goteo. El proceso de creación del pedido en la sede de Commerce crea las transacciones de inventario relacionadas. Para las órdenes del canal de comercio electrónico, la sede de Commerce tiene información sobre las transacciones de inventario solo después de que las transacciones se envían a la sede de Commerce a través del trabajo P y se completa el proceso de sincronización de pedidos. Por lo tanto, es importante que comprenda que el valor de la instantánea de inventario que se proporciona en el trabajo **Disponibilidad de producto** es posible que no sea preciso al 100% en tiempo real debido al procesamiento constante de ventas que ocurre en los servidores distribuidos.

Para tomar una instantánea del inventario en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Retail y Commerce TI \> Productos e inventario \> Disponibilidad de producto**.
1. Seleccione **Aceptar** para ejecutar el trabajo **Disponibilidad de producto**. También puede programar este trabajo para que se ejecute en un lote.

Después de el trabajo **Disponibilidad de producto** ha terminado de ejecutarse, los datos que se capturaron deben enviarse a las bases de datos del canal de comercio electrónico, de modo que se pueda considerar la última instantánea del inventario de la sede de Commerce en el cálculo del inventario disponible estimado.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **1130** (**Disponibilidad de producto**) para sincronizar los datos de la instantánea que el trabajo **Disponibilidad de producto** ha creado desde la sede de Commerce a las bases de datos de su canal.

Cuando se solicita disponibilidad de inventario a la API **GetEstimatedAvailability** o **GetEstimatedProductWarehouseAvailability**, se ejecuta un cálculo para tratar de obtener la mejor estimación posible del inventario del producto. El cálculo hace referencia a todos los pedidos de clientes de comercio electrónico que se encuentran en la base de datos del canal, pero que no se incluyeron en los datos de instantánea que proporcionó el trabajo 1130. Esta lógica se realiza mediante el seguimiento de la última transacción de inventario procesada desde la sede de Commerce y comparándola con las transacciones en la base de datos del canal. Proporciona una línea de base para la lógica de cálculo del lado del canal, de modo que los movimientos de inventario adicionales que ocurrieron para las transacciones de ventas de pedidos de clientes en la base de datos del canal de comercio electrónico se pueden factorizar en el valor de inventario estimado que proporciona la API.

La lógica de cálculo del lado del canal devuelve un valor físicamente disponible estimado y un valor total disponible para el producto y el almacén solicitados. Los valores se pueden mostrar en su sitio de comercio electrónico si lo desea, o se pueden utilizar para activar otra lógica de negocios en su sitio de comercio electrónico. Por ejemplo, puede mostrar un mensaje de "agotado" en lugar de la cantidad disponible real que pasó la API.

La lógica de cálculo que utilizan las API de comercio electrónico del lado del canal para el valor de inventario estimado puede evaluar el inventario basándose solo en los pedidos de los clientes que se han creado en la base de datos del canal, pero que aún no se han sincronizado y publicado en Commerce Headquarters. Si la base de datos de su canal también contiene datos transaccionales para ventas recogidas por el cliente para almacenes específicos de la tienda, las ventas recogidas por el cliente no se tienen en cuenta en el cálculo de comercio electrónico del lado del canal para esos almacenes.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Configure la operación de búsqueda de inventario en el canal PDV

En Retail versión 10.0.9 y anteriores, la operación **Búsqueda de inventario** desde PDV utiliza una llamada de servicio en tiempo real a la sede de Commerce para obtener información de inventario para el producto seleccionado, tanto para la tienda actual del usuario como para cualquier otra tienda que esté configurada para el grupo de cumplimiento como parte de la configuración del canal para la tienda. En Commerce versión 10.0.10 y posterior, puede desactivar las llamadas de servicio en tiempo real a Commerce Headquarters. En cambio puede usar el cálculo del lado del canal en el servidor de Commerce para determinar el inventario disponible que está físicamente disponible para la tienda y cualquier otra ubicación que esté definida en el grupo de cumplimiento. Esta configuración de inventario calculada por canal también es útil para ubicaciones donde la conectividad a Internet no es fiable, ya que no tiene que estar en línea para obtener búsquedas de inventario desde la sede de Commerce.

Cuando el cálculo del lado del canal está configurado y administrado correctamente, puede proporcionar una estimación más fiable del inventario de la tienda actual, ya que utiliza los datos transaccionales que se encuentran en la base de datos del canal de Commerce, pero de los cuales Commerce Headquarters aún no tiene información. Por ejemplo, si utiliza la llamada de servicio en tiempo real existente para búsquedas de inventario en PDV, la sede de Commerce probablemente todavía no tendrá información sobre una venta de efectivo y transporte que acaba de ocurrir para un producto. Por lo tanto, el valor de inventario disponible que devuelve Commerce Headquarters para ese producto probablemente excederá el inventario disponible real de la tienda en una unidad. Sin embargo, si usa el cálculo del lado del canal, la venta de efectivo y transporte puede incluirse en el cálculo y deducirse del valor disponible que se muestra. Aunque los valores que proporcionan tanto el cálculo del lado del canal como la llamada de servicio en tiempo real son solo estimaciones del inventario disponible, el valor que proporciona el cálculo del lado del canal es mucho más probable que sea preciso para la tienda actual.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Comience con la disponibilidad de inventario calculada de en el lado del canal PDV

Para usar la lógica de cálculo del lado del canal y desactivar las llamadas de servicio en tiempo real para búsquedas de inventario desde la aplicación PDV, primero debe habilitar la característica **Cálculo optimizado de disponibilidad de producto** a través del espacio de trabajo **Administración de características** de la sede de Commerce. Además de habilitar la función, debe realizar cambios en el **Perfil de funcionalidad**.

Para cambiar el **Perfil de funcionalidad**, siga estos pasos:

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**.
1. Seleccione un perfil de funcionalidad.
1. En la ficha desplegable **Funciones**, en la sección **Inventariar cálculo de disponibilidad**, cambie el valor del campo **Inventariar el modo de cálculo de disponibilidad** de **Servicio en tiempo real** a **Canal**. Por defecto, todos los perfiles de funcionalidad utilizan llamadas de servicio en tiempo real. Por lo tanto, debe cambiar el valor de este campo si desea utilizar la lógica de cálculo del lado del canal. Todas las tiendas minoristas que estén vinculadas al perfil de funcionalidad seleccionado se verán afectadas por este cambio.

Luego debe sincronizar los cambios en el canal a través del proceso de programación de distribución realizando los siguientes pasos:

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute el trabajo **1070** (**Configuración del canal**) .

Una vez completada la configuración, la información que se proporciona sobre el inventario físicamente disponible ya no utiliza una llamada de servicio en tiempo real cuando un usuario en la aplicación PDV utiliza la operación **Búsqueda de inventario** (vistas estándar y matriciales). En cambio, los datos sobre el inventario físicamente disponible para la tienda actual y todas las tiendas en el grupo de cumplimiento se calculan en función de la última instantánea conocida que se entregó a la base de datos de canales desde Commerce Headquarters. El valor de la instantánea se refina aún más mediante el cálculo del lado del canal para ajustar el valor físicamente disponible, en función de las ventas adicionales o las transacciones de devolución que existen para el producto seleccionado en la base de datos del canal que no se incluyeron en la última instantánea sincronizada del trabajo 1130. Si la base de datos del canal no contiene datos transaccionales para ninguno de los almacenes o tiendas en el grupo de cumplimiento, no contiene transacciones adicionales que se puedan factorizar en un recalculo del valor. Por lo tanto, la mejor estimación del inventario disponible que se puede mostrar para esos almacenes o tiendas son los datos de la última instantánea conocida de la sede de Commerce.

Las pantallas **Cumplimiento de la orden** de PDV también aprovechan el cálculo del lado del canal para mostrar el inventario disponible de artículos cuando se selecciona una línea de cumplimiento de pedido y un usuario ve el panel **Detalles** para el inventario disponible para el artículo seleccionado.

## <a name="optimize-your-inventory-data"></a>Optimice sus datos de inventario

Para garantizar la mejor estimación posible del inventario, es fundamental que utilice los siguientes trabajos por lotes de Commerce y los ejecute con frecuencia:

- **Trabajo P** - El trabajo P se encuentra en la página **Horarios de distribución** y debe ejecutarse con frecuencia. Este trabajo lleva los pedidos de comercio electrónico, los pedidos de clientes asíncronos que PDV creó y los pedidos de efectivo y transporte que los PDV crearon desde las bases de datos del canal a la sede de Commerce, para que puedan procesarse aún más. Hasta que estos datos se sincronicen desde el canal a la sede de Commerce, la sede de Commerce no tiene información sobre los ajustes de inventario de los productos en los almacenes que resultan de esas transacciones.
- **Sincronizar pedidos** - Este trabajo procesa los datos transaccionales sin procesar en Commerce Headquarters que proporciona el trabajo P y convierte el comercio electrónico y las transacciones asíncronas de pedidos de clientes en pedidos de ventas en Commerce Headquarters. Hasta que se procese este trabajo y se creen los pedidos de ventas, no se crearán transacciones de inventario. Por lo tanto, el inventario disponible en la sede de Commerce no considerará las transacciones.
- **Calcular declaraciones transaccionales en lote** - Para las transacciones de efectivo y transporte que se crean en la tienda, el proceso de contabilización de alimentación por goteo garantiza que el inventario relacionado con las ventas se actualice de manera eficiente. Para obtener el procesamiento más eficiente de las transacciones de inventario para los pedidos de efectivo y transporte, asegúrese de configurar su sistema para usar [publicación de alimentación por goteo](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Publicar extractos transaccionales en lote** - Este trabajo también es necesario para la publicación de alimentación por goteo. Sigue el trabajo **Calcular declaraciones transaccionales en lote**. Este trabajo publica sistemáticamente los extractos calculados, de modo que los pedidos de ventas para ventas en efectivo se llevan a cabo en la sede de Commerce y la sede de Commerce refleja con mayor precisión el inventario de su tienda.
- **Disponibilidad de producto** - Este trabajo crea la instantánea del inventario de Commerce Headquarters.
- **1130 (disponibilidad del producto)** - Este trabajo se encuentra en la página **Programación de distribución** y debe ejecutarse inmediatamente después del trabajo **Disponibilidad de producto**. Este trabajo transporta los datos de la instantánea del inventario desde la sede de Commerce a las bases de datos del canal.

Se recomienda que no ejecute esos trabajos por lotes con demasiada frecuencia (cada pocos minutos). Las ejecuciones frecuentes sobrecargarán la sede (HQ) de Commerce y pueden afectar al rendimiento. En general, es recomendable ejecutar la disponibilidad de productos y 1130 trabajos por hora, y programar trabajos P, sincronizar pedidos y trabajos relacionados con la publicación de alimentación por goteo con la misma o mayor frecuencia.

> [!NOTE]
> Por razones de rendimiento, cuando los cálculos de disponibilidad de inventario del lado del canal se utilizan para realizar una solicitud de disponibilidad de inventario utilizando las API de comercio electrónico o la nueva lógica de inventario del lado del canal PDV, el cálculo utiliza una memoria caché para determinar si ha pasado suficiente tiempo para justificar la ejecución de la lógica de cálculo de nuevo. La caché predeterminada está fijada en 60 segundos. Por ejemplo, activó el cálculo del lado del canal para su tienda y vio el inventario disponible de un producto en la página **Búsqueda de inventario**. Si luego se vende una unidad del producto, la página **Búsqueda de inventario** no mostrará el inventario reducido hasta que se haya borrado el caché. Después de que los usuarios publiquen transacciones en PDV, deben esperar 60 segundos antes de verificar que se haya reducido el inventario disponible.

Si su situación empresarial requiere un menor tiempo de caché, póngase en contacto con su representante de soporte de productos para obtener ayuda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]