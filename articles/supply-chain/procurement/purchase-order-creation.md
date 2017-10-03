---
title: Crear pedidos de compra
description: "Este artículo describe el proceso y las opciones al crear un pedido de compra manualmente."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: fbf5337ac41ceae6e911c056db5226c8ed1cefb0
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

# <a name="create-purchase-orders"></a>Crear pedidos de compra

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Este artículo describe el proceso y las opciones al crear un pedido de compra manualmente.

Cuando crea un pedido de compra, se especifica información general acerca de toda la orden en el encabezado del pedido de compra y, a continuación, agrega una o más líneas de pedido de compra. Este artículo describe algunas de las opciones usadas con más frecuencia que están disponibles.  

También puede crear pedidos de compra copiando líneas de otro documento de pedido de compra o un pedido de ventas. En este caso, puede invertir el signo en el inventario, como lo invertiría en una factura para indicar crédito.  

Aunque puede crear pedidos de compra manualmente, se suelen generar más desde otros procesos. Los pedidos se pueden crear automáticamente en función de otros documentos, como solicitudes. De forma alternativa, se pueden crear como parte del proceso de planificación maestra a través de pedidos de compra planificados. Si utiliza acuerdos de compra, los pedidos de compra se pueden crear mediante la acción **Pedido parcial**. También hay métodos más avanzados para la creación automática de un pedido de compra. Por ejemplo, se pueden crear pedidos al usar entrega directa o cadenas de pedidos de empresas vinculadas.

## <a name="creating-a-purchase-order-header"></a>Creación de un encabezado de pedido de compra
Al crear un nuevo pedido de compra, aparece un cuadro de diálogo, donde puede especificar la información más común para el encabezado del pedido de compra. Al hacer clic en **Aceptar** para cerrar el cuadro de diálogo, se crea el pedido y, a continuación, puede especificar información adicional en el encabezado.  

El primer detalle que debe considerar al crear un pedido de compra es el tipo de pedido. El tipo **Pedido de compra** es el más usado. Sin embargo, si se requiere una factura de crédito, puede utilizar el tipo **Pedido devuelto**.  

Debe especificar el proveedor en el campo **Cuenta de proveedor**. Para este campo, puede buscar en la cuenta o el nombre del proveedor. Si un proveedor entrega desde varias ubicaciones, pero utiliza una cuenta de factura única, puede seleccionar esa cuenta de factura en el campo **cuenta de facturación** y, a continuación, utilizarla con cuentas diferentes de proveedores. Si tiene que crear un pedido de compra para productos que no se pidieron repetidamente, puede utilizar la opción **Proveedor de una sola vez**. Esta opción crea automáticamente una nueva cuenta de proveedor que está marcada como cuenta plantilla, para admitir un proceso de limpieza posterior para cuentas plantilla en el módulo **Proveedores**. Al seleccionar una cuenta de proveedor, muchos campos del encabezado del pedido de compra heredarán valores predeterminados de la información que está asociada a la cuenta del proveedor. Por ejemplo, el sitio de entrega predeterminado y el almacén se copian desde la información del proveedor. Sin embargo, puede anular estos valores predeterminados si la compra está pensada para otra ubicación.  

Si el proveedor ha proporcionado un número de referencia para el pedido, puede registrar esta información en el campo **Referencia del proveedor**. Para los pedidos devueltos, debe especificar un valor en el campo **RMA** para hacer referencia a la autorización del proveedor para el procesamiento de la devolución.  

Si hay un acuerdo de compra asociado al pedido, debe especificar esta información en el campo **Acuerdo de compra**.  

El encabezado del pedido de compra también contiene información acerca de los cargos que se aplican a todo el pedido en lugar de líneas individuales. Los cargos se pueden agregar automáticamente al pedido si se han configurado cargos automáticos para el proveedor o el grupo de cargos del proveedor. También puede agregar manualmente cargos al encabezado del pedido haciendo clic en **Mantener gastos** en el panel de acciones.

## <a name="adding-purchase-order-lines"></a>Adición de líneas de pedido de compra
Los pedidos de compra pueden ser para productos físicos o para servicios. Una configuración en el grupo de modelos de inventario determina si se aplica un número de artículo determinado a un producto o un servicio. Normalmente, el artículo que se compra se especifica por un número de artículo. Sin embargo, si el pedido es para productos o servicios que se consumen directamente, también puede especificar el artículo usando una categoría de compras.  

Las líneas de pedido de compra contienen numerosos campos, pero muchos de estos tienen un valor predeterminado o un valor que se hereda del encabezado del pedido. Se establecen campos adicionales al seleccionar un producto o servicio. Los campos que se establecen manualmente más a menudo incluyen los campos para el número de artículo, la cantidad y la fecha de entrega solicitada. La información acerca del precio unitario y los descuentos también es muy importante, pero los valores de esos campos a menudo se determinan mediante acuerdos comerciales o acuerdos de compra.  

Al seleccionar un producto, puede buscar en todo o parte del nombre del producto en lugar de utilizar el número de artículo. Si el producto tiene diversas variantes, tales como diferentes tamaños, puede ver un resumen de las variantes disponibles usando la función **Agregar líneas** o mediante la búsqueda que está disponible en el campo **Número de variante**.  

A menudo, tendrá que especificar varias dimensiones para el artículo seleccionado en cada línea de pedido de compra. Las dimensiones que se deben especificar dependen de los grupos de dimensiones que se han asignado a la definición de producto. Por ejemplo, a menudo tendrá que especificar un sitio y un almacén para indicar la ubicación en la que debe entregarse el producto. Identifica variantes de producto especificando un número de variante, o especificando valores para una o más dimensiones de producto, como el color, el tamaño, la configuración o el estilo. Las dimensiones de seguimiento, como el lote y el número de serie, le permiten identificar de forma exclusiva cada lote de inventario. Una vez haya creado un pedido, puede capturar los valores de dimensión del pedido con la acción **Registro**. Por ejemplo, ha realizado un pedido de una cantidad de cinco piezas de un artículo. Posteriormente, registra que tres de esas piezas serán negras y dos de ellas serán azules. Este enfoque es una alternativa a la captura de la información de dimensiones durante el registro de llegada.  

Puede comprobar los detalles del estado de transacción de inventario de los productos mantenidos en existencias. Por ejemplo, es posible que desee comprobar el inventario disponible para ayudarle a decidir cuánta cantidad pedir. O bien, puede que desee revisar el estado del inventario de una cantidad pedida para ver si se ha producido el registro de llegada entrante.  

Una línea de pedido de compra que se utiliza para devolver un producto al proveedor tendrá una cantidad negativa. Puede seleccionar un lote específico para devolver mediante la acción **Reserva**.  

A veces, es posible que desee dividir la cantidad que ha solicitado, de manera que diferentes partes de la misma se entreguen en fechas diferentes. Puede configurar estas entregas con la acción **Programación de entrega**, que está disponible en el menú **Línea de pedido de compra** de la vista **Líneas**.  

Los cargos se pueden agregar automáticamente a las líneas de pedido de compra si se han configurado cargos automáticos para el proveedor o el grupo de cargos del proveedor, y para el artículo o el grupo de cargos del artículo. Sin embargo, por lo general, los cargos se agregan manualmente en el nivel de línea de pedido. Para agregar un cargo, abra la página **Mantener gastos** con la acción **Mantener gastos** del menú **Operaciones financieras** de la vista **Líneas**. La ventaja de agregar cargos directamente en el nivel de línea de pedido es que el cargo se puede asignar como coste de inventario. Para configurar códigos de cargos a coste de producto de cuenta, utilice la opción de débito **Artículo**. Estos tipos de cargos deben asignarse desde el encabezado del pedido de compra a las líneas para se pueda confirmar el pedido. Por ejemplo, puede que desee asignar cargos basados en la cantidad de cada línea. La categoría de cargo también afecta a cómo se contabilizan los cargos. Por ejemplo, los gastos fijos especifican un importe fijo y los gastos de porcentaje se calculan como un porcentaje del importe neto de la línea de pedido. Se pueden asignar pedidos de compra a una carga y la carga podría incluir una estimación de los gastos previsto para el coste de transporte. Puede asignar este gasto de la carga de nuevo a las líneas de pedido de compra.

## <a name="purchase-order-actions"></a>Acciones del pedido de compra
Una vez haya agregado el encabezado y las líneas al pedido de compra, a menudo debe completar pasos adicionales para que el pedido esté listo para su confirmación. Dado que hay muchas opciones disponibles, es posible que le resulte útil usar [Búsqueda de acción](/dynamics365/unified-operations/fin-and-ops/get-started/action-search) para encontrar el elemento de menú relevante.  

Puede configurar los productos del pedido para que tengan artículos adicionales. Los artículos adicionales son productos que deben comprarse o que se pueden comprar junto con otros productos. Los productos adicionales se pueden agregar de manera gratuita como productos complementarios, o puede decidir si desea agregarlos al pedido o no. Puede revisar los artículos adicionales después de cada línea de pedido que se agrega. Sin embargo, probablemente encontrará más adecuado revisar y agregar artículos adicionales pertinentes para todas las líneas de pedido con la página **Artículos adicionales**, que puede abrir en el panel de acciones.  

Se suelen agregar descuentos a las líneas conforme se crean. Sin embargo, se aplican algunos descuentos a todo el pedido:

-   La acción **Descuento total** calcula un porcentaje de descuento total que se aplica al pedido completo. No confunda este descuento con el porcentaje de descuento por pronto pago. Se aplican descuentos por pronto pago cuando se paga la factura y dependen de la liquidación de pago para una fecha específica.
-   Si se aplica un descuento multilínea, debe utilizar la acción **Descuento multilínea** para calcularlo y asignarlo al pedido. Los descuentos multilínea son descuentos que se pueden ofrecer si una combinación de productos en el pedido supera un umbral conjunto. Solo algunas empresas utilizan este tipo de descuento.

Los cargos que tienen un código de cargo que utiliza el tipo de débito **Artículo** deben asignarse al nivel de línea antes de que se pueda confirmar el pedido. Puede que resulte adecuado asignar estos cargos en el nivel de encabezado de pedido, para que pueda especificar el importe total del cargo. Sin embargo, en este caso, el cargo se debe asignar entonces a cada línea antes de que se pueda confirmar el pedido. Puede utilizar la acción **Asignar gastos** para dividir los importes de los cargos que se asignan en el nivel de encabezado a las líneas de pedido. Los cargos se pueden dividir según el importe neto de cada línea, en función de la cantidad que se ha pedido o de forma equitativa en las líneas de pedido. Una vez haya asignado cargos a las líneas, el cargo se quita del encabezado del pedido.  

Los pedidos de compra se pueden configurar para requerir la asignación de fondos presupuestarios al pedido para que se pueda procesar. En este caso, puede utilizar la acción **Comprobaciones presupuestarias** para asignar el presupuesto.  

Es posible que deba retrasar la finalización de un pedido de compra. Por ejemplo, es posible que requiera información adicional sobre productos o servicios, o que tenga que obtener autorización para el gasto. Hay varias maneras de retener un pedido. Por ejemplo, puede esperar para confirmar el pedido. De forma alternativa, si se utiliza un flujo de trabajo de administración de cambios, no envíe el pedido para su aprobación. Si debe bloquear todos los pedidos para un proveedor determinado, también puede marcar el proveedor como **En espera** para su procesamiento en el maestro de proveedores. También hay circunstancias que pueden impedir el procesamiento del pedido. Por ejemplo, es posible evitar el procesamiento si se han superado los límites de crédito o si los fondos presupuestarios necesarios no están disponibles.

<a name="see-also"></a>Consulte también
--------

[Visión general de pedidos de compra](purchase-order-overview.md)

[Confirmación y aprobación del pedido de compra](purchase-order-approval-confirmation.md)

[Recepción de producto frente a pedidos de compra](product-receipt-against-purchase-orders.md)

[Visión general de facturas de proveedores](/dynamics365/unified-operations/financials/accounts-payable/vendor-invoices-overview)




