---
title: Pedidos de clientes en el punto de venta (PDV)
description: Este artículo proporciona información sobre los pedidos de clientes en el punto de venta (PDV). Los pedidos de cliente también se conocen como pedidos especiales. El artículo incluye una discusión de parámetros y flujos de transacción relacionados.
author: josaw1
ms.date: 08/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260594"
- intro-internal
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6051e0a18823b354dd9940aac70a086a0f317002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850391"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Pedidos de clientes en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

Este artículo proporciona información sobre cómo crear y administrar pedidos de clientes en la aplicación de punto de venta (PDV). Los pedidos de los clientes se pueden utilizar para capturar las ventas en las que los compradores desean recoger productos en una fecha posterior, recoger productos de una ubicación diferente o que se les envían artículos. 

En un mundo de comercio onmicanal, muchos minoristas ofrecen la opción de pedidos de cliente, o pedidos especiales, para cumplir diferentes requisitos de producto y de cumplimiento. Aquí hay algunas situaciones habituales:

- Un cliente desea que los productos se entreguen en una dirección específica en una fecha específica.
- Un cliente desea elegir productos de una tienda o de una ubicación diferente de la tienda o de la ubicación donde el cliente compró los productos.
- Un cliente dentro de la ubicación de una tienda quiere pedir productos hoy y recogerlos en la misma ubicación de la tienda en una fecha posterior.

Los minoristas pueden utilizar pedidos de cliente para minimizar las ventas perdidas que, de no ser así, la falta de existencias podría provocar; la mercancía se puede entregar o recoger en una hora o un lugar distintos.

## <a name="set-up-customer-orders"></a>Configurar pedidos de cliente
Antes de intentar usar la funcionalidad de pedidos de clientes en PDV, asegúrese de completar todas las configuraciones requeridas en la central de Commerce.

### <a name="configure-modes-of-delivery"></a>Configurar modos de entrega

Para utilizar los pedidos de los clientes, debe configurar los modos de entrega que puede utilizar el canal de la tienda. Debe definir al menos un modo de entrega que se puede utilizar cuando las líneas de pedido se envían a un cliente desde una tienda. Debe también definir al menos un modo de entrega para la recogida que se puede utilizar cuando las se recogen desde la tienda. Los modos de entrega se definen en la página **Modos de entrega** en la central de Commerce. Para obtener más información sobre cómo configurar el modo de entrega para los canales de Commerce, consulte [Definir modos de entrega](./configure-call-center-delivery.md#define-delivery-modes).

![Página Modos de entrega.](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Configurar grupos de cumplimiento

Es posible que algunas tiendas o almacenes no puedan cumplir con los pedidos de los clientes. Al configurar grupos de cumplimiento, una organización puede especificar qué tiendas y ubicaciones de almacén se muestran como opciones para los usuarios que crean pedidos de clientes en PDV. Los grupos de cumplimiento se configuran en la página **Grupos de cumplimiento**. Las organizaciones pueden crear tantos grupos de cumplimiento como necesiten. Una vez definido un grupo de cumplimiento, vincúlelo a una tienda seleccionando **Asignación de grupo de cumplimiento** desde la pestaña **Configuración** del panel de acciones de la página **Tiendas**.

En la versión 10.0.12 de Commerce y posteriores, las organizaciones pueden definir si las combinaciones de almacén o almacén y tienda que se definen en los grupos de cumplimiento se pueden utilizar para el envío, la recogida o tanto para el envío como para la recogida. Esto permite una mayor flexibilidad para que la empresa determine qué almacenes se pueden seleccionar al crear un pedido de cliente para los artículos a enviar frente a qué tiendas se pueden seleccionar al crear un pedido de cliente para los artículos a recoger. Para utilizar estas opciones de configuración, debe activar la característica **Posibilidad de especificar ubicaciones como "Envío" o "Recogida" habilitadas en el grupo de cumplimiento**. Si un almacén que está vinculado a un grupo de cumplimiento no es una tienda, solo se puede configurar como ubicación de envío. No se puede utilizar cuando los pedidos de recogida están configurados en PDV.

![Página de grupos de cumplimiento.](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Configurar opciones de canal

Cuando trabaja con pedidos de clientes en PDV, debe considerar algunas de las configuraciones del canal de la tienda. Estos ajustes se encuentran en la página **Tiendas** en la central de Commerce.

- **Almacén**: este campo indica el almacén que se utilizará al disminuir el inventario de efectivo y llevar y los pedidos de recogida del cliente vinculados a esta tienda. Como práctica recomendada, recomendamos el uso de almacenes únicos para cada canal de tienda, a fin de evitar problemas de lógica empresarial conflictivos entre las tiendas.
- **Almacén de envío**: este campo indica el almacén que se utilizará al disminuir el inventario de inventario para pedidos de clientes que se enviarán desde la tienda seleccionada. Si la característica **Posibilidad de especificar ubicaciones como "Envío" o "Recogida" habilitadas dentro del grupo de Cumplimiento** se ha habilitado en su entorno, los usuarios de PDV pueden elegir un almacén específico desde donde enviar en PDV, en lugar de elegir una tienda desde donde enviar. Por lo tanto, cuando esa función está habilitada, el almacén de envío ya no se utiliza, ya que el usuario seleccionará el almacén específico desde donde enviar el pedido cuando se crea el pedido.
- **Asignación de grupo de cumplimiento**: seleccione este botón (en la pestaña **Configuración** en el Panel de acciones) para vincular los grupos de cumplimiento a los que se hace referencia para mostrar opciones para ubicaciones de recolección u orígenes de envío cuando los pedidos de los clientes se crean en PDV.
- **Utilizar impuestos basados en el destino**: esta opción indica si la dirección de envío se utiliza para determinar el grupo de impuestos que se aplica a las líneas de pedido que se envían a la dirección del cliente.
- **Utilizar impuestos basados en el cliente**: esta opción indica si el grupo de impuestos que se define para la dirección de entrega del cliente se usa para gravar los pedidos de los clientes que se crean en PDV para su envío al domicilio del cliente.

![Configuración del canal de la tienda en la página Tiendas.](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Configurar parámetros de pedido de cliente

Antes de intentar crear pedidos de clientes en PDV, debe configurar los parámetros adecuados en la central de Commerce. Estos parámetros se pueden encontrar en la pestaña **Pedidos de los clientes** de la página **Parámetros de Commerce**.

- **Tipo de orden predeterminado**: puede especificar el tipo de orden que se asigna por defecto a los pedidos de clientes que se crean en el PDV. Estos pedidos de clientes pueden ser pedidos de venta o pedidos de presupuesto. Independientemente del tipo de pedido predeterminado, los usuarios aún pueden crear pedidos de cliente y pedidos de cliente desde PDV.
- **Porcentaje de depósito predeterminado**: permite especificar el porcentaje del importe total del pedido que el cliente debe pagar como depósito para que el pedido se pueda confirmar. Dependiendo de sus privilegios, los asociados de la tienda pueden anular la cantidad usando la operación **Anulación de depósito** en el PDV, si esa operación está configurada para el diseño de la pantalla de transacciones.
- **Modo de recogida de entrega**: especifica el modo de entrega que se debe aplicar a las líneas de pedidos que están configuradas para recogida en el PDV.
- **Modo de entrega para llevar**: especifique el modo de entrega que se debe aplicarse a las líneas de pedido de venta que se consideran líneas de pedido para llevar cuando se crea un carro mixto, donde algunas líneas serán recogidas o enviadas, y otras líneas serán ejecutadas por el cliente inmediatamente.
- **Porcentaje de cargo de cancelación**: si se debe aplicar un cargo cuando un pedido de cliente se cancela, especifique el importe de dicho cargo.
- **Código de cargo por cancelación**: especifique el código de cargo de Clientes que se debe usar cuando se aplica un cargo por cancelación a pedidos de clientes cancelados a través del PDV. El código de cargo define la lógica de contabilización financiera para el cargo de cancelación.
- **Código de cargo de envío**: si la opción **Utilizar cargos automatizados** se establece en **Sí**, este ajuste de parámetro no tiene ningún efecto. Si esa opción está configurada en **No**, se les pedirá a los usuarios que ingresen manualmente un cargo de envío cuando creen pedidos de clientes en PDV. Utilice este parámetro para asignar un código de cargo a Clientes que se aplicará a los pedidos cuando los usuarios especifiquen un cargo de envío. El código de cargo define la lógica de contabilización financiera para el cargo de envío.
- **Utilizar cargos automatizados avanzados**: establecer esta opción en **Sí** para usar cargos automatizados calculados por el sistema cuando los pedidos de los clientes se crean en PDV. Estos cargos automáticos se pueden usar para calcular tarifas de envío u otros cargos específicos de pedidos o artículos. Para obtener más información sobre cómo configurar y utilizar los cargos automatizados, consulte [Cargos automatizados avanzados de omnicanal](./omni-auto-charges.md).

![Pestaña de pedidos de clientes en la página de parámetros de Commerce.](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Actualizar diseños de pantalla de transacciones en PDV

Asegúrese de que el PDV [diseño de pantalla](./pos-screen-layouts.md) está configurado para admitir la creación y gestión de pedidos de clientes, y que todas las operaciones de PDV requeridas están configuradas. Estas son algunas de las operaciones de PDV que se recomiendan para respaldar correctamente la creación y gestión de pedidos de los clientes:
- **Enviar todos los productos**: esta operación se utiliza para especificar que todas las líneas del carrito de transacciones se enviarán a un destino.
- **Enviar productos seleccionados**: esta operación se utiliza para especificar que las líneas seleccionadas del carrito de transacciones se enviarán a un destino.
- **Recoger todos los productos**: esta operación se utiliza para especificar que todas las líneas del carrito de transacciones se recogerán en la ubicación de la tienda seleccionada.
- **Recoger los productos seleccionados**: esta operación se utiliza para especificar que las líneas seleccionadas del carrito de transacciones se recogerán en la ubicación de la tienda seleccionada.
- **Llevar todos los productos**: esta operación se utiliza para especificar que se recogerán todas las líneas del carrito de transacciones. Si esta operación se utiliza en PDV, el pedido del cliente se convertirá en una transacción al contado.
- **Llevar productos seleccionados**: esta operación se utiliza para especificar que las líneas seleccionadas en el carrito de transacciones las llevará en el cliente en el momento de realizar la compra. Esta operación es útil solo en un escenario de [pedidos híbridos](./hybrid-customer-orders.md).
- **Recuperar pedido**: esta operación se utiliza para buscar y recuperar pedidos de clientes para que los usuarios de PDV puedan editar, cancelar o realizar operaciones relacionadas con el cumplimiento en ellos según sea necesario.
- **Cambiar modo de entrega**: esta operación se puede utilizar para cambiar rápidamente el modo de entrega de las líneas que ya están configuradas para el envío, sin requerir que los usuarios vuelvan a pasar por el flujo de "enviar todos los productos" o "enviar productos seleccionados".
- **Anulación de depósito**: esta operación se puede utilizar para cambiar el importe del depósito que el cliente pagará por el pedido del cliente seleccionado.

![Operaciones en la pantalla de transacciones de PDV.](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Trabajar con pedidos de clientes en PDV

> [!NOTE]
> Actualmente, la funcionalidad de reconocimiento de ingresos no se admite para su uso en canales de Commerce (comercio electrónico, PDV, centro de llamadas). Los artículos configurados con reconocimiento de ingresos no deben agregarse a los pedidos creados en los canales de Commerce. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Crear un pedido de cliente para los productos que se enviarán al cliente

1. En la pantalla de transacciones de PDV, agregue un cliente a la transacción.
2. Agregue productos al carro.
3. Seleccione **Enviar elementos seleccionados** o **Enviar todo** para enviar los productos a una dirección en la cuenta del cliente.
4. Seleccione la opción para crear un pedido del cliente.
5. Confirme o cambie la ubicación de "enviar desde", confirme o cambie la dirección de envío y seleccione un método de envío.
6. Especifique la fecha de envío del pedido deseada por el cliente.
7. Use las funciones de pago para pagar cualquier importe calculado que se deba, o use la operación **Anulación de depósito** para cambiar los importes que se deben y luego aplicar el pago.
8. Si no se pagó el total del pedido, especifique una tarjeta de crédito que se capturará para el saldo adeudado en el pedido cuando se facture.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Crear un pedido de cliente para los productos que recogerá el cliente

1. En la pantalla de transacciones de PDV, agregue un cliente a la transacción.
2. Agregue productos al carro.
3. Seleccione **Recoger seleccionado** o **Recoger todo** para iniciar la configuración de recogida de pedidos.
4. Seleccione en la ubicación de la tienda donde recogerá el cliente los productos seleccionados.
5. Seleccione una fecha en la que se recogerá el artículo.
6. Use las funciones de pago para pagar cualquier importe calculado que se deba, o use la operación **Anulación de depósito** para cambiar los importes que se deben y luego aplicar el pago.
7. Si no se pagó el total del pedido, seleccione si el cliente efectuará el pago más tarde (en el momento de la recogida), o si se obtendrá un token de una tarjeta de crédito ahora para luego utilizarlo y cobrar en el momento de la recogida.

### <a name="edit-an-existing-customer-order"></a>Edición de un pedido de cliente ya existente

Los pedidos minoristas que se crean en el canal en línea o en la tienda se pueden recuperar y editar a través de POS según sea necesario.

> [!IMPORTANT]
> No todos los pedidos minoristas se pueden editar a través de la aplicación PDV. Los pedidos que se crean en un canal de centro de llamadas no se pueden editar a través del PDV si el valor de configuración [Habilitar la finalización del pedido](./set-up-order-processing-options.md#enable-order-completion) está activado para el canal del centro de llamadas. Para garantizar un procesamiento de pago correcto, los pedidos que se originaron en un canal de centro de llamadas y que utilizan la función Habilitar finalización de pedidos deben editarse a través de la aplicación del centro de llamadas en la central de Commerce.

> [!NOTE]
> Le recomendamos que no edite en el PDV pedidos y presupuestos creados por un usuario que no sea del centro de llamadas en la sede central de Commerce. Esos pedidos y presupuestos no utilizan el motor de precios de Commerce, por lo que si se editan en el PDV, el motor de precios de Commerce volverá a asignarles precio.


En la versión 10.0.17 y posteriores, los usuarios pueden editar los pedidos aptos a través de la aplicación PDV, incluso si el pedido se ha cumplimentado parcialmente. Sin embargo, los pedidos que se facturan en su totalidad aún no se pueden editar a través de PDV. Para habilitar esta capacidad, active la característica **Editar pedidos parcialmente cumplimentados en el punto de venta**, en el espacio de trabajo **Administración de características**. Si esta función no está habilitada, o si está utilizando la versión 10.0.16 o anterior, los usuarios solo podrán editar los pedidos de los clientes en PDV si el pedido está completamente abierto. Además, si la característica está habilitada, puede limitar las tiendas que pueden editar pedidos parcialmente cumplimentados. La opción para deshabilitar esta capacidad para tiendas específicas se puede configurar a través del **Perfil de funcionalidad** en la ficha desplegable **General**.


1. Seleccione **Recuperar pedido**.
2. Utilice **Buscar** para especificar filtros para encontrar el pedido, y luego seleccione **Aplicar**.
3. Seleccione el orden en la lista de resultados y luego seleccione **Editar**. Si el botón **Editar** no está disponible, el pedido se encuentra en un estado en el que no se puede editar.
4. Desde el carrito de transacciones, realice los cambios necesarios en el pedido del cliente. Es posible que algunos cambios estén prohibidos durante la edición.
5. Complete el proceso de edición seleccionando una operación de pago.
6. Para salir del proceso de edición sin guardar ningún cambio, puede utilizar la operación **Anular transacción**.

#### <a name="pricing-impact-when-orders-are-edited"></a>Impacto en los precios cuando se editan pedidos

Cuando los pedidos se realizan en PDV o en un sitio de comercio electrónico de Commerce, los clientes se comprometen a pagar un importe. Este importe incluye un precio y también puede incluir un descuento. Un cliente que realice un pedido y luego se ponga en contacto con el centro de llamadas para modificar ese pedido (por ejemplo, para agregar otro artículo) tendrá determinadas expectativas sobre la aplicación de descuentos. Incluso si las promociones en las líneas de pedido existentes han caducado, el cliente esperará que los descuentos que se aplicaron originalmente a esas líneas sigan vigentes. Sin embargo, si no había ningún descuento vigente cuando se realizó el pedido originalmente, pero ha entrado en vigor un descuento desde entonces, el cliente esperará que el nuevo descuento se aplique al pedido modificado. De lo contrario, el cliente podría cancelar el pedido existente y crear uno nuevo al que se aplique el nuevo descuento. Como muestra este escenario, se deben mantener los precios y descuentos que se hayan acordado con los clientes. Al mismo tiempo, los usuarios de PDV y del centro de llamadas deben tener la flexibilidad de volver a calcular los precios y los descuentos para las líneas de los pedido de ventas según sea necesario.

Cuando los pedidos se recuperan y editan en PDV, los precios y descuentos de las líneas de pedido existentes se consideran "bloqueados". Es decir, no cambian, incluso aunque se cancelen o cambien algunas líneas de pedido, o se agreguen líneas de pedido nuevas. Para cambiar los precios y descuentos de las líneas de pedidos de ventas existentes, el usuario de PDV debe seleccionar **Recalcular**. Entonces, se elimina el bloqueo de precio de las líneas de pedido existentes. Sin embargo, antes del lanzamiento de la versión 10.0.21 de Commerce, esta funcionalidad no estaba disponible en el centro de llamadas. Cualquier cambio en las líneas de pedido hacía que se volvieran a calcular los precios y descuentos.

En la versión 10.0.21 de Commerce, hay disponible una nueva función denominada **Impedir cálculo de precios no intencionado para pedidos de comercio electrónico** en el espacio de trabajo **Administración de características**. Esta función está activada de forma predeterminada. Cuando se activa, hay disponible una nueva propiedad **Precio bloqueado** para todos los pedidos de comercio electrónico. Una vez que se terminan de capturar los pedidos realizados desde cualquier canal, esta propiedad se habilita automáticamente (es decir, se activa la casilla) para todas las líneas de pedido. El motor de precios de Commerce excluye entonces esas líneas de pedido de todos los cálculos de precios y descuentos. Por tanto, si se edita el pedido, las líneas del pedido se excluirán del cálculo de precios y descuentos de forma predeterminada. Sin embargo, los usuarios del centro de llamadas pueden deshabilitar la propiedad (es decir, desactivar la casilla) para cualquier línea de pedido y luego seleccionar **Recalcular** para incluir las líneas de pedido existentes en los cálculos de precios.

Incluso cuando están aplicando un descuento manual a una línea de ventas existente, los usuarios del centro de llamadas deben deshabilitar la propiedad **Precio bloqueado** de la línea de ventas antes de aplicar el descuento manual.

Los usuarios del centro de llamadas también pueden deshabilitar la propiedad **Precio bloqueado** para líneas de pedido de forma masiva seleccionando **Quitar bloqueo de precio** en el grupo **Calcular** de la pestaña **Vender** en el panel de acciones de la página **Pedido de ventas**. En este caso, el bloqueo de precio se quita de todas las líneas de pedido, excepto de las líneas que no son editables (es decir, de las líneas cuyo estado es **Facturado parcialmente** o **Facturado**). Después, una vez que los cambios al pedido se completan y se han enviado, el bloqueo de precio se vuelve a aplicar a todas las líneas de pedido.

> [!IMPORTANT]
> Cuando la función **Impedir cálculo de precios no intencionado para pedidos de comercio electrónico** está activada, la configuración de la evaluación del acuerdo comercial se pasará por alto en los flujos de trabajo de precios. Es decir, los cuadros de diálogo de evaluación de acuerdos comerciales no mostrarán la sección **Relacionado con el precio**. Este comportamiento se produce porque tanto la configuración de evaluación del acuerdo comercial como la función de bloqueo de precios tienen un propósito similar: evitar cambios de precios no intencionados. Sin embargo, la experiencia del usuario para la evaluación de acuerdos comerciales no se adapta bien a los pedidos grandes en los que los usuarios deben seleccionar una o más líneas de pedido para cambiar el precio.

> [!NOTE]
> La propiedad **Precio bloqueado** solo se puede deshabilitar para una o más líneas seleccionadas cuando se utiliza el módulo **Centro de llamadas**. El comportamiento de PDV se mantiene sin cambios. Es decir, el usuario de PDV no puede desbloquear los precios de las líneas de pedido seleccionadas. Sin embargo, pueden seleccionar **Recalcular** para quitar el bloqueo de precio de todas las líneas de pedido existentes.

### <a name="cancel-a-customer-order"></a>Cancelar un pedido de cliente

1. Seleccione **Recuperar pedido**.
2. Utilice **Buscar** para especificar filtros para encontrar el pedido, y luego seleccione **Aplicar**.
3. Seleccione el orden en la lista de resultados y luego seleccione **Cancelar**. Si el botón **Cancelar** no está disponible, el pedido se encuentra en un estado que ya no se puede cancelar.
4. Si los cargos por cancelación están configurados, confírmelos. Puede ajustar los cargos de cancelación antes de confirmarlos, según sea necesario. 
5. Desde el carro de transacciones, complete el proceso de cancelación seleccionando una operación de pago. Si los depósitos que se pagaron exceden el cargo por cancelación, es posible que se deba realizar un reembolso.
6. Para salir del proceso de cancelación sin guardar ningún cambio, puede utilizar la operación **Anular transacción**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Finalizar el envío o recogida del pedido del cliente en un PDV

Después de que se crea un pedido, el cliente recogerá los artículos en una tienda o se enviarán, según la configuración del pedido. Para obtener más información sobre este proceso, consulte la documentación sobre el [realización de pedidos para recoger en la tienda](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flujo de transacciones asíncrono para pedidos de cliente

Los pedidos de cliente se pueden crear en el PDV en modo sincrónico o modo asincrónico. Si observa problemas de rendimiento o retrasos del usuario cuando crea pedidos de clientes en PDV, considere activar la creación de pedidos asincrónica.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilite los pedidos de cliente que se crearán en modo asincrónico

1. En la central de Commerce, en la página **Perfiles de funcionalidad**, seleccione el perfil de funcionalidad que corresponda a la tienda que desea configurar.
2. En la ficha desplegable **General**, establezca la opción **Crear pedido de cliente en modo asincrónico** en **Sí**.

Cuando la opción **Crear pedido de cliente en modo asincrónico** está establecido en **Sí**, los pedidos de cliente se crean siempre en modo asincrónico, incluso si Retail Transaction Service (RTS) está disponible. Si establece esta opción en **No**, los pedidos de cliente siempre se crean en modo sincrónico mediante RTS. Cuando los pedidos de los clientes se crean en modo asincrónico, se extraen y crean como transacciones minoristas en la central de Commerce desde los trabajos de Commerce Pull (P). Los pedidos de ventas correspondientes para las transacciones minoristas se crean cuando **Sincronizar pedidos** se ejecuta manualmente o mediante un proceso por lotes.

## <a name="additional-resources"></a>Recursos adicionales

[Pedidos de cliente híbridos](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
