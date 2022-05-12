---
title: Crear devoluciones en PDV.
description: Este tema describe cómo iniciar devoluciones para transacciones de pago al contado sin entrega a domicilio o pedidos de clientes en la aplicación del punto de venta (PDV) Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: c8e06c0d83e3bc2f5efea1e3a8124c700706aa2e
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648997"
---
# <a name="create-returns-in-pos"></a>Crear devoluciones en PDV.

[!include [banner](includes/banner.md)]

Este tema describe cómo iniciar devoluciones para transacciones de pago al contado sin entrega a domicilio o pedidos de clientes en la aplicación del punto de venta (PDV) Microsoft Dynamics 365 Commerce.

> [!NOTE]
> En el lanzamiento de Commerce versión 10.0.20 y posteriores, está disponible una nueva característica que se llama **Experiencia unificada de procesamiento de devoluciones en PDV**. Esta característica proporciona un proceso de devolución más consistente y unificado en PDV, independientemente del tipo de transacción (transacción de pago al contado sin entrega a domicilio o pedido del cliente) o el canal original en el que se creó el pedido. Recomendamos que todas las organizaciones activen esta nueva función para ayudar a mejorar la fiabilidad general del procesamiento de devoluciones a través de PDV.
>
> Una vez activada la función, no se puede desactivar.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Procesar devoluciones utilizando la operación de transacción de devolución

Le recomendamos que agregue la operación de transacción de devolución al [diseño de pantalla](pos-screen-layouts.md) de su PDV. En los lanzamientos anteriores al lanzamiento de la versión 10.0.20 de Commerce, la operación de transacción de devolución admite correctamente el procesamiento de devoluciones solo para transacciones de pago al contado sin entrega a domicilio. Después de activar la función **Experiencia unificada de procesamiento de devoluciones para PDV** en el lanzamiento de la versión 10.0.20 de Commerce o posterior, la operación de transacción de devolución también admite el procesamiento de devoluciones que se originan en pedidos de clientes, como pedidos de "recogida" o "envío a domicilio" que ya están facturados.

Desde la operación de transacción de devolución, los usuarios pueden buscar una transacción de pago al contado sin entrega a domicilio o un pedido de cliente para devolver ingresando cualquiera de los siguientes cuatro criterios de búsqueda. Los usuarios pueden ingresar estos criterios usando un teclado de dispositivo, un teclado en pantalla o un escáner de código de barras.

- Id. de recepción
- Número de pedido
- Id. de referencia del canal (también conocido como id. de confirmación del pedido)
- Id. de factura

Si se encuentra una transacción o un pedido que coincide con los criterios de búsqueda, aparece la página **Productos que se pueden devolver**. Allí, los usuarios pueden especificar los artículos que se devuelven. También pueden ingresar cantidades de devolución y códigos de motivo.

Para cada línea de pedido en la lista de productos que se pueden devolver, el PDV muestra información sobre la cantidad de compra original y las cantidades de las devoluciones que se procesaron previamente. La cantidad de devolución que ingresa un usuario para una línea de pedido debe ser menor o igual al valor del campo **Disponible para la devolución**.

![Página de productos que se pueden devolver.](media/returnslist.png)

Durante el proceso de devolución, si un usuario tiene el producto físico y ese producto tiene un código de barras, el usuario puede escanear el código de barras para registrar la devolución. Cada lectura del código de barras aumenta la cantidad de devolución en un artículo. Sin embargo, si la etiqueta del código de barras tiene una cantidad incrustada, esa cantidad se ingresará en el campo **En devolución**.

Los usuarios también pueden seleccionar manualmente los artículos para devolver en la página **Productos que se pueden devolver** y luego actualizar el campo **En devolución** utilizando el panel de detalles a la derecha.

Si se especifica la cantidad máxima disponible de **En devolución** para una transaccion, el usuario puede seleccionar la operación **Seleccionar todo** en la barra de la aplicación del PDV para establecer la cantidad máxima que se puede devolver en todas las líneas.

Para cada línea que tiene una cantidad de **En devolución**, el usuario debe seleccionar un código de motivo de devolución mediante el panel de detalles. Para devoluciones de transacciones de pago al contado sin entrega a domicilio, los códigos de motivo de devolución se configuran como códigos de información en el perfil de funcionalidad de la tienda. Para devoluciones de pedidos de clientes, los códigos de motivo de devolución se configuran en la página **Códigos de motivo de devolución** en la sede central de Dynamics 365 Commerce.

Una vez que se han establecido la cantidad de devolución y el código de motivo para cada artículo que debe devolverse, el usuario puede seleccionar la operación **Devolución** en la barra de aplicaciones del PDV para continuar con el procesamiento. Aparece la página de transacción del PDV, donde los artículos que se pueden devolver que fueron seleccionados en la página anterior se han agregado al carrito. Las cantidades de **En devolución** de los artículos aparecen como líneas de cantidad negativa en la transacción y se calcula el reembolso total.

Los usuarios pueden agregar líneas a una transacción de devolución si están creando una orden de cambio. Los usuarios también pueden agregar más artículos de devolución ad-hoc a una transacción de devolución utilizando la operación **Devolver producto** para una línea de ventas de cantidad positiva seleccionada que se ha agregado.

> [!NOTE]
> La operación **Devolver producto** en el PDV no proporciona ninguna validación frente a ninguna transacción original y permite la devolución de cualquier producto. Por lo tanto, recomendamos que solo los usuarios autorizados puedan realizar esta operación, o que se requiera una invalidación del administrador si se utiliza esta operación.

Si vence un reembolso al finalizar la compra, las organizaciones pueden configurar como [políticas de reembolso de pagos](refund_policy_returns.md) que se limiten los métodos de pago que se pueden utilizar para reembolsar a los clientes. Si la transacción original se pagó con una tarjeta de crédito, según el procesador de pagos y la configuración del sistema, los usuarios pueden tener la opción de [emitir un reembolso a la tarjeta original](dev-itpro/linked-refunds.md). En este caso, el reembolso se puede procesar sin necesidad de que el cliente vuelva a pasar su tarjeta de crédito. El token del pago original se utiliza para emitir el reembolso.

## <a name="other-return-options-in-pos"></a>Otras opciones de devolución en el PDV

Cuando la función **Experiencia unificada de procesamiento de devoluciones en el PDV** está activada, los usuarios también pueden utilizar la operación **Mostrar diario** en el PDV para iniciar una devolución para una transacción de pago al contado sin entrega a domicilio o un pedido de un cliente. Luego pueden seleccionar una transacción en el diario y luego seleccionar la operación **Devolución** en la barra de aplicaciones del PDV. Esta operación está disponible solo si hay líneas que se pueden devolver en el pedido. Inicia la misma experiencia de usuario que la operación **Transacción de devolución**.

Los usuarios también pueden utilizar la operación **Recuperar pedido** en el PDV para buscar y recuperar pedidos de clientes. (Esta operación no se puede utilizar para transacciones de pago al contado con entrega a domicilio). En este caso, después de seleccionar un pedido de cliente, la operación **Devolver** en la barra de la aplicación PDV se puede utilizar para iniciar una devolución del pedido del cliente. Esta operación está disponible solo si hay líneas que se pueden devolver en el pedido. Inicia la misma experiencia de usuario que la operación **Transacción de devolución** o **Mostrar diario**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>Las órdenes de devolución se contabilizan en la sede central de Commerce como pedidos de venta. 

Cuando la función **Experiencia unificada de procesamiento de devoluciones en el PDV** está activada, todas las devoluciones que se crean en el PDV se escriben en la sede central de Commerce como pedidos de venta que tienen líneas negativas. En las versiones anteriores a la versión 10.0.20 de Commerce, los usuarios pueden seleccionar si las órdenes de devolución deben registrarse como pedidos de venta que tienen líneas negativas o si deben ser pedidos de devolución creados mediante el proceso de autorización de devolución de mercancías (RMA). 

En la función **Experiencia unificada de procesamiento de devoluciones en el PDV**, la opción de utilizar el proceso RMA para crear devoluciones en el PDV ha quedado obsoleta. Una vez activada esta función, todas las devoluciones se crearán como pedidos de venta que tienen líneas negativas.

## <a name="offline-return-processing-improvements"></a>Mejoras en el procesamiento de devoluciones sin conexión

En la mayoría de los casos, cuando se procesa una devolución en el PDV, el sistema intenta realizar una llamada de servicio en tiempo real (RTS) a la sede central de Commerce para validar las cantidades actuales que están disponibles para su devolución. Esta validación ayuda a prevenir escenarios fraudulentos en los que un cliente intenta devolver el mismo artículo en varias ubicaciones.

Para gestionar situaciones en las que no se puede realizar la llamada RTS debido a problemas de red o conectividad, se ha implementado un proceso para sincronizar periódicamente los datos de cantidad devuelta desde la sede de Commerce con la base de datos del canal de una tienda. Este seguimiento de devolución del lado del canal ayuda a garantizar que las cantidades **Disponibles para su devolución** que se muestran en el PDV sean razonablemente precisas, incluso cuando el PDV está fuera de línea. También asegura que el PDV pueda continuar validando la información del lado del canal para ayudar a prevenir devoluciones fraudulentas.

Para utilizar el proceso de devolución fuera de línea de la manera adecuada, las organizaciones deben programar el lote d eproceso **Actualizar cantidades devueltas** en la sede central de Commerce para que se ejecute con frecuencia. Recomendamos que este trabajo se ejecute con la misma frecuencia que el trabajo P que extrae nuevas transacciones de los canales de Commerce a la sede central de Commerce.

El trabajo **Actualizar cantidades devueltas** calcula la cantidad que está disponible para devolución para todos los pedidos de venta que se encuentran en la sede central de Commerce. Los datos que calcula el trabajo deben enviarse a las bases de datos del canal, para que los canales de la tienda puedan actualizarse. El trabajo de distribución de **Cantidades devueltas** (1200) se utiliza para este propósito. Debido a que los datos sobre la cantidad que se puede devolver se sincronizan desde la sede central de Commerce, si se procesa una devolución en el PDV, pero no se puede realizar la llamada RTS, el PDV puede usar la información de devolución del lado del canal para validar las cantidades **Disponibles para su devolución** para una línea de ventas determinada.

Cuando no se pueden realizar llamadas RTS, y el PDV está utilizando datos del lado del canal para la validación de la devolución, un mensaje de advertencia informa a los usuarios que están creando una devolución "sin conexión". Por tanto, son conscientes de que la cantidad **Disponible para su devolución** que se muestra en el PDV puede estar desactualizada y ya no es precisa, dependiendo de cuándo se procesó el último trabajo de **Actualización de cantidades de devolución** y se sincronizó con el canal.

Por ejemplo, un cliente procesó recientemente una devolución de una línea de pedido en otro canal, pero esos datos aún no se han sincronizado con las bases de datos del canal a través del trabajo **Actualizar cantidades de devolución**. Luego, el cliente va a una tienda diferente e intenta devolver el mismo artículo nuevamente. En este caso, si la tienda no puede realizar la llamada RTS a la sede central de Commerce para obtener datos de devolución en tiempo real, el PDV permitirá que el artículo se devuelva nuevamente. Sin embargo, se advierte al usuario que la información que se está utilizando para validar la devolución puede estar desactualizada. El mensaje que recibe el usuario es solo un mensaje de advertencia. No impide que el usuario continúe tramitando la devolución.

Si la información del lado del canal no está actualizada por algún motivo y se procesa una devolución fuera de línea por una cantidad que excede la cantidad **Disponible para su devolución** real, se puede generar un error cuando se ejecuta la contabilización del extracto para crear la transacción en la sede central de Commerce.

> [!NOTE]
> Cuando la función **Experiencia unificada de procesamiento de devoluciones en el PDV** está activada, se encuentran disponibles nuevas funciones opcionales que admiten la validación de devoluciones de productos serializados. Para más información, consulte [Devolver productos controlados por número de serie en el punto de venta (PDV)](POS-serial-returns.md).

## <a name="version-details"></a>Detalles de versión

La siguiente lista proporciona los requisitos mínimos de versión para los distintos componentes.
- Sede central de Commerce: Versión 10.0.20
- Commerce Scale Unit (CSU): Versión 9.30
- Punto de venta (PDV): Versión 9.30

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial

Esta característica garantiza que cuando se devuelve un pedido con varias facturas, los impuestos serán, finalmente, iguales al importe de impuestos cargado originalmente.

1. En el espacio de trabajo **Administración de características** busque **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial**.
1. Seleccione la característica **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial** y luego seleccione **Habilitar**.

## <a name="set-up-return-locations-for-retail-stores"></a>Configurar ubicaciones de devolución para tiendas

Commerce le permite configurar las ubicaciones de devolución que se basan en códigos de información comercial y códigos de motivo de ventas y marketing. Cuando los clientes devuelven sus compras, los cajeros suelen indicar el motivo de la devolución. Puede especificar que los productos devueltos se asignen a diferentes ubicaciones de devolución en el inventario, según los códigos de información y los códigos de motivo que los cajeros seleccionan en la caja regitradora.

Por ejemplo, un cliente devuelve un producto defectuoso y el cajero procesa la transacción de devolución. Cuando Retail POS muestra el código de información para devoluciones, el cajero selecciona el subcódigo para devoluciones defectuosas. El producto devuelto se asigna automáticamente a una ubicación de devolución específica.

Una ubicación de devolución puede ser un almacén, una ubicación de una tienda o un almacén, o incluso un pallet específico, en función de las ubicaciones de inventario que haya configurado la organización. Puede asignar cada lugar de devolución a uno o más códigos de información de venta al público y códigos de razón de venta y marketing.

### <a name="prerequisites"></a>Requisitos previos

Para poder configurar las ubicaciones de devolución, debe configurar los siguientes elementos:

- **Códigos de información comercial:** preguntas en el PDV que se establecen en el módulo **Retail**. Para obtener más información, vea [Configurar códigos de información](/dynamicsax-2012/appuser-itpro/setting-up-info-codes).
- **Códigos de motivo de ventas y marketing:** preguntas en las cajas registradoras de PDV que se configuran en el módulo de **Ventas y marketing**. Para obtener más información, vea [Configurar códigos de motivo](/dynamicsax-2012/appuser-itpro/set-up-return-reason-codes).
- **Ubicaciones de inventario:** lugares donde se guarda el inventario. Para obtener más información, consulte [Configurar ubicaciones de inventario](/dynamicsax-2012/appuser-itpro/about-locations).
    
### <a name="set-up-return-locations"></a>Configurar ubicaciones de devolución

Para establecer ubicaciones de devolución, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración del canal \> Almacenes** y seleccione un almacén.
1. En la ficha desplegable **Retail** en el campo **Ubicación de devolución por defecto**, seleccione la ubicación del inventario que se utilizará para las devoluciones en las que los códigos de información o los códigos de motivo no están asignados a las ubicaciones de devolución.
1. En el campo **pallet de devolución por defecto**, seleccione el pallet que se utilizará para las devoluciones en las que los códigos de información o los códigos de motivo no están asignados a las ubicaciones de devolución.
1. Vaya a **Retail y Commerce \> Gestión de inventarios \> Ubicaciones de devolución**.
1. Seleccione **Nueva** para crear una nueva directiva de ubicaciones de devoluciones.
1. Escriba un nombre único para la ubicación de devolución y una descripción.

    > [!NOTE]
    > Si se ha configurado una secuencia numérica para las ubicaciones de devolución, el nombre se escribe automáticamente.

1. En la ficha desplegable **General**, establezca la opción **Imprimir etiquetas** en **Sí** para imprimir etiquetas para todos los productos que se asignan a las ubicaciones de devolución.
1. Establezca la opción **Bloquear inventario** en **Sí** para sacar los productos devueltos en la ubicación de devolución predeterminada del inventario y evitar que se vendan.
1. Para asignar códigos y subcódigos de información minorista específicos a ubicaciones de devolución, siga estos pasos:

    1. En la ficha desplegable **Códigos de información comercial**, seleccione **Agregar**.
    1. En el campo **Código de información**, seleccione un código de información para las devoluciones.
    1. En el campo **Subcódigo**, seleccione un subcódigo para el motivo de la devolución. El campo **Descripción** muestra la descripción del subcódigo seleccionado.
    1. En el campo **Tienda** seleccione la tienda donde se utiliza el código de información.
    1. Utilice los campos **Almacén**, **Ubicación** e **ID de pallet** para especificar una ubicación de devolución. Por ejemplo, para especificar una ubicación concreta de una tienda, seleccione una tienda en el campo **Tienda** y una ubicación en el campo **Ubicación**.
    1. Seleccione la casilla **Bloquear inventario** para sacar los productos devueltos del inventario y evitar que se vendan.

1. Para asignar códigos de motivo de ventas y marketing específicos a las ubicaciones de devolución, siga estos pasos:

    1. En la ficha desplegable **Códigos de motivo de ventas y marketing** seleccione **Agregar**.
    1. En el campo **Código de motivo**, seleccione un nuevo código para devoluciones. El campo **Descripción** muestra la descripción del código de motivo seleccionado.
    1. En el campo **Tienda** seleccione la tienda donde se utiliza el código de motivo.
    1. Utilice los campos **Almacén**, **Ubicación** e **ID de pallet** para especificar una ubicación de devolución. Por ejemplo, para especificar un pallet concreto en una ubicación de un almacén, seleccione un almacén en el campo **Almacén**, una ubicación en el campo **Ubicación** y un pallet en el campo **ID de pallet**.
    1. Seleccione la casilla **Bloquear inventario** para sacar los productos devueltos del inventario y evitar que se vendan.

    > [!NOTE]
    > Si se usa una directiva de ubicación de devoluciones para un artículo, pero el motivo de devolución que selecciona un cajero no coincide con ningún código que se especifica en la ficha desplegable **Códigos de información comercial** o **Códigos de motivo de ventas y marketing**, el artículo se envía a la ubicación de devolución predeterminada que se define en la página **Almacén**. Adicionalmente, la configuración de la casilla **Bloquear inventario** en la ficha desplegable **General** de la página **Ubicaciones de devolución** determina si el artículo devuelto debe bloquearse en el inventario.

1. Vaya a **Retail y Commerce \> Jerarquía de productos de Commerce**.
1. En la ficha desplegable **Administrar propiedades de categoría de inventario** en el campo **Ubicación de devolución**, seleccione una ubicación de devolución. Debido a que se pueden definir varias directivas de ubicación de devolución para la misma tienda, el valor que seleccione aquí determina la directiva de ubicación de devolución que se utiliza.

## <a name="additional-resources"></a>Recursos adicionales

[Devolver productos controlados por número de serie en el punto de venta (PDV)](POS-serial-returns.md)

[Reembolsos vinculados de transacciones previamente aprobadas y confirmadas](dev-itpro/linked-refunds.md)

[Crear y actualizar una directiva de devoluciones y reembolsos para un canal](refund_policy_returns.md)

[Configuraciones visuales de la interfaz de usuario de PDV](pos-screen-layouts.md)
