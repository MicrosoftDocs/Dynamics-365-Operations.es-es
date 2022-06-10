---
title: Registro de inventario
description: Este tema explica la pestaña de registro de inventario en la página de perfil de registro de inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783377"
---
# <a name="inventory-posting"></a>Registro de inventario

La pestaña **Inventario** en la página **Perfiles de contabilización de inventario** se utiliza para controlar cómo se contabilizarán las transacciones de inventario en la contabilidad general. Las transacciones de inventario son transacciones que no se crean a partir de pedidos de venta, pedidos de compra ni pedidos de producción. Publican automáticamente las actualizaciones físicas y financieras en el inventario simultáneamente. Una excepción son los pedidos de transferencia que separan las actualizaciones físicas y financieras cuando envía y recibe el inventario.

La tabla siguiente muestra algunos ejemplos de transacciones de inventario.

| Tipo de transacción | Recepción o emisión | Registro físico, registro financiero o ambos | Description |
|---|---|---|---|
| Movimiento | Ambas | Ambas | <p>Un diario de movimientos es un diario de inventario que puede usar para agregar o quitar inventario. Funciona como un diario de ajuste de inventario. Sin embargo, una diferencia clave es que se especifica la cuenta principal que compensa la entrada.</p><p>El diario de movimientos introduce los saldos iniciales y los ajustes únicos que se deben contabilizar como gastos. Por ejemplo, se usa cuando se elimina el inventario para una muestra de ventas.</p><p>Cuando se registra el diario, las actualizaciones físicas y financieras ocurren simultáneamente.</p><p>Las cantidades positivas de las líneas del diario representan recepciones y las cantidades negativas representan emisiones.</p> |
| Ajuste de inventario | Ambas | Ambas | Se utiliza un diario de ajuste de inventario para agregar o quitar inventario. No le permite seleccionar una cuenta de contrapartida. Sólo las cuentas que se especifican en la página **Perfil de registro de inventario** se utilizan para actualizar el asiento de contabilidad general. |
| Transferencia (diario) | Ambas | Ambas | <p>Un diario de transferencias se usa para mover el inventario de una ubicación a otra (usando dimensiones de almacenamiento). Actualiza la información del producto de una transacción de inventario con un nuevo producto o dimensiones de seguimiento.</p><p>Un diario de transferencias crea una línea para el movimiento de un artículo. Esta línea tiene campos "desde" y "hasta" para las dimensiones del inventario. Cada línea en un diario de transferencia crea dos transacciones de inventario. Una transacción se crea para las dimensiones de inventario "desde". Representa la emisión y tiene una cantidad negativa. La otra transacción se crea para las dimensiones de inventario "hasta". Representa la recepción y tiene una cantidad positiva.</p><p>Es posible que los diarios de transferencia no creen un comprobante si el movimiento del inventario se considera una transferencia no financiera. Las dimensiones de inventario que difieren en los valores "desde" y "hasta" no están marcadas con la opción **Inventario financiero** en la página **Grupo de dimensiones de almacenamiento** o **Grupo de dimensiones de seguimiento**. Por ejemplo, si la opción **Inventario financiero** no está marcada en la dimensión **Ubicación** y mueve el inventario de una ubicación a otra ubicación en el mismo sitio y almacén, no se crea ningún asiento.</p><p>Los diarios de transferencias difieren de los pedidos de transferencia en que no hay documentos para el movimiento. La actualización se realiza en una transacción al registrar el diario. Por el contrario, un pedido de transferencia puede generar documentos de selección y envío, y requiere dos actualizaciones para procesar la transacción.</p> |
| Envío de pedidos de transferencia | Problema | Ambas | <p>Cuando crea un nuevo pedido de transferencia, cada combinación de una línea y una dimensión de inventario tiene dos transacciones de inventario: una para el envío del pedido de transferencia y otra para la recepción del pedido de transferencia. Cuando envía el pedido de transferencia, se actualizan dos transacciones de inventario y se crean dos transacciones de inventario adicionales para el tránsito de mercancías, en total cuatro transacciones de inventario.</p><ol><li>La primera transacción de inventario se usa para eliminar el artículo del almacén y la ubicación de origen. El estado de emisión de esta transacción es **Vendido** para indicar que el artículo ya no está disponible en el almacén.</li><li>La segunda transacción de inventario se usa para agregar el artículo al almacén de tránsito que se selecciona para el almacén desde el que se transfiere el artículo. El estado de recepción de esta transacción es **Comprado**.</li><li>La tercera transacción de inventario es para la transferencia del almacén de tránsito al almacén de destino. El estado de emisión de esta transacción es **Físico reservado**. Este estado garantiza que otro proceso no pueda consumir el artículo mientras aún está en tránsito.</li><li>La cuarta transacción de inventario es para la recepción de mercancías en el almacén de destino. El estado de recepción de esta transacción es **Pedido**.</li></ol> |
| Recepción de pedidos de transferencia | Recepción | Ambas | Cuando se recibe un pedido de transferencia en el almacén de destino, el estado de inventario de la transacción de inventario que se encuentra en el almacén de tránsito (número 3 en el ejemplo anterior) se actualiza a **Vendido** y el estado de inventario de la transacción de inventario para el almacén de destino se actualiza a **Comprado**. |
| Listas de materiales | Ambas | Ambas | Puede usar un diario de lista de materiales (L. MAT.) para informar de un producto como terminado y consumir las materias primas que se consumieron durante el proceso sin usar un pedido de producción. Un diario de L. MAT generalmente incluye al menos una línea positiva para el producto terminado y una o más líneas negativas para las materias primas que se están consumiendo. La línea de bienes terminados es una recepción en el inventario, mientras que las líneas negativas son emisiones desde el inventario para las materias primas. Cuando crea un diario de lista de materiales, la primera línea es el encabezado de la lista de materiales, y las líneas posteriores que se agregan son las líneas de la lista de materiales. |
| Cambio de propiedad de inventario | Ambas | Ambas | Un diario de cambio de propiedad de inventario se usa para cambiar ela propiedad del inventario consignado del proveedor a la organización. Los diarios de cambio de propiedad de inventario se parecen a los diarios de transferencia de inventario en que dos transacciones de inventario están relacionadas con cada combinación de una línea y una dimensión de inventario. Una transacción de inventario elimina el inventario del proveedor en la dimensión **Propiedad**, y el otro agrega el artículo a la entidad jurídica en la dimensión **Propiedad**. |
| Recepción de artículos | Recepción | Físico | Se utiliza un diario de llegada de artículos para actualizar el estado de recepción del inventario a **Registrado**. Por lo general, se usa para la recepción de pedidos de compra de bienes y devoluciones de pedidos de venta. |
| Entrada desde producción. | Recepción | Físico | Un diario de entrada de producción se asemeja a un diario de llegada de artículos. La entrada de producción se utiliza para recibir productos terminados de un pedido de producción en el almacén. Una vez registrado el diario, el estado de la transacción de inventario se actualiza a **Registrado**. |
| Recuento | Ambas | Ambas | Un diario de conteo se usa para registrar la cantidad de artículos que se contaron para una combinación específica de dimensiones de inventario. Las transacciones de inventario se crean cuando la línea del diario tiene una diferencia de conteo. Una línea que tiene una cantidad contada más alta genera una recepción en el inventario. Una línea que tiene una cantidad contada menor genera una emisión en el inventario. Las líneas donde la cantidad contada coincide con la cantidad esperada no tienen transacciones de inventario. |
| Recuento de etiquetas | No aplicable | No aplicable | Un diario de recuento de etiquetas se utiliza para realizar un seguimiento de las etiquetas de inventario que se asignan y utilizan en un recuento de inventario completo. Puede usar el diario para asignar un número de etiqueta a una combinación específica de un artículo y una dimensión de inventario, y para realizar un seguimiento del estado de esa etiqueta durante un inventario completo. Los diarios de conteo de etiquetas no crean transacciones de inventario. |
| Pedidos de calidad | Problema | Físico | <p>Un pedido de calidad se usa para registrar los resultados de las pruebas para un lote determinado del inventario. Cada pedido de calidad está relacionado con una transacción de inventario existente o una parte de una transacción de inventario.</p><p>Un pedido de calidad generará una nueva transacción de inventario en dos situaciones:</p><ul><li>El pedido de calidad está marcado como **Prueba destructiva** en la pestaña **General**.</li><li>El pedido de calidad está marcado como **Cuarentena al fallar la validación** en la pestaña **General**, y la prueba falla la validación. En este caso, se crean dos transacciones de inventario. Una transacción de inventario elimina el artículo de la combinación de dimensiones del inventario original y de la ubicación, y la otra agrega el artículo al almacén de cuarentena.</li></ul> |
| Pedidos de cuarentena | Ambas | Ambas | <p>Las transacciones de inventario de los pedidos de cuarentena son como un pedido de transferencia. Se utiliza un almacén de cuarentena para realizar un seguimiento del inventario. Hay dos transacciones de recepción y dos transacciones de emisión.</p><p>Cuando crea inicialmente el pedido, se crean dos transacciones. La transacción de recepción tiene un estado de **Pedido** para el almacén de cuarentena que está vinculado al almacén donde se encuentra el artículo. La transacción de emisión tiene un estado de **En pedido** para el almacén donde se almacena el artículo.</p><p>Cuando inicia el pedido de cuarentena, se crean dos transacciones adicionales y se actualizan las transacciones existentes. El estado de la transacción de recepción para el almacén de cuarentena se actualiza a **Recibido**, y el estado de la transacción de emisión para el almacén de almacenamiento se actualiza a **Deducido**.</p><p>Las dos nuevas transacciones se utilizan para indicar el eventual movimiento de regreso al almacén de almacenamiento. La transacción de recepción tiene un estado de **Pedido** para el almacén de almacenamiento, y esa transacción de emisión tiene un estado de **Físico reservado** para el almacén de cuarentena.</p><p>Cuando informa un pedido de cuarentena como finalizado, esta operación representa la actualización física del pedido de cuarentena. El estado de recepción en el almacén de almacenamiento se actualiza a **Recibido**.</p><p>Cuando finaliza el pedido de cuarentena, esta operación representa la actualización financiera del pedido de cuarentena. El estado de las transacciones de emisión se actualiza a **Vendido** y el estado de las transacciones de recepción se actualiza a **Comprado**.</p><p>Alternativamente, puede desechar el pedido de cuarentena. Esta operación elimina el artículo del inventario. Cuando desecha un pedido de cuarentena, solo quedan tres transacciones. La transacción de recepción para el almacén de almacenamiento se elimina y el estado de la transacción de recepción restante se actualiza a **Comprado**. El estado de las dos transacciones de emisión se actualiza a **Vendido**. Esta operación es una actualización física y financiera del pedido.</p> |

## <a name="fixed-receipt-price-posting"></a>Registro de precio de recepción fijo

El precio de recepción fijo le permite usar un coste estándar para un producto. Es una alternativa a seleccionar la opción **Coste estándar** en la página **Grupo de modelos de artículo** de un artículo. La principal diferencia cuando usa un precio de recepción fijo es que el precio de coste que está configurado actualmente se usará para el artículo cuando se registre la recepción en el inventario. No existe un proceso de revalorización de costes para un precio de recepción fijo. Cuando se registra una actualización financiera, se utiliza el precio de coste actual en el momento del registro. Si el precio de coste que se usa en la recepción y la factura difieren, la desviación se contabilizará en las cuentas de pérdidas y ganancias del precio de recepción fijo.

Para utilizar opcionalmente un precio de recepción fijo para un producto, debe completar la siguiente configuración:

- Seleccione la casilla **Posinventario físico**, en la página **Grupo de modelos de artículo** para el artículo seleccionado en la línea de transacción de inventario.
- Seleccione la casilla **Precio de recepción fijo** en la página **Grupo de modelos de artículo**.
- Especifique las cuentas principales de los siguientes tipos de registro en la página **Perfil de contabilización de inventario**:

    - Ganancias del precio de recepción fijo
    - Pérdidas del precio de recepción fijo

Para obtener más información, consulte [Precio de recepción fijo](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Registro de peso capturado

Los productos con peso capturado se suelen usar en sectores, como la industria alimentaria, en los que los productos pueden variar ligeramente en peso, tamaño o ambos aspectos. Los productos de peso capturado utilizan dos unidades de medida: una unidad de inventario y una unidad de peso capturado. El peso del inventario, cuando ellega a un almacén, puede ser diferente del peso cuando se emite el inventario fuera del almacén. El procesamiento de productos con peso capturado ajusta el inventario.

Si hay una desviación en el peso capturado, las diferencias se registran en las cuentas que se especifican en los campos **Pérdida de peso capturado** y **Ganancia de peso capturado**, en la página **Perfil de contabilización de inventario**. Normalmente, la misma cuenta principal se especifica en ambos campos.

La siguiente tabla muestra ejemplos de los tipos de registro predeterminados, e incluye ejemplos de cuentas principales y descripciones.

- La columna "¿Debe/Haber?" indica si la transacción generalmente se registra en el debe o el haber. En algunos casos, una transacción puede registrar débitos o créditos.
- La columna "Cuenta de compensación" indica que el tipo de registro es una cuenta de compensación. En otras palabras, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.
- La columna "P/F" indica el tipo de registro. "P" representa registro física y "F" representa registro financiero.
- La columna "Seguir" indica si la cuenta principal del tipo de publicación específico suele ser la misma que la cuenta principal de otro tipo de publicación. Específicamente, indica el tipo de publicación que se usa normalmente para el registro.

> [!NOTE]
> Las cuentas principales y los nombres de las cuentas principales de la tabla son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|---|---|---|---|---|---|---|---|---|
| Cuenta de pérdidas de peso capturado  | 510520 | Ajuste de inventario | Gasto | | No | Ambas | Cuenta de ganancias de peso capturado  | Esta cuenta se usa cuando registra una transacción de inventario donde el importe del peso capturado es menor. |
| Cuenta de ganancias de peso capturado  | 510520 | Ajuste de inventario | Gasto | | No | Ambas | Cuenta de pérdidas de peso capturado  | Esta cuenta se usa cuando se registra una transacción de inventario en la que el importe del peso capturado es mayor. |

Para obtener más información sobre productos de peso capturado, consulte [Acerca de los artículos con peso capturado](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md) y [Procesamiento de productos de peso capturado con administración de almacenes](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Registro de transferencia de inventario a activo fijo

El inventario del diario de activos fijos (**Activos fijos** \> **Diarios** \> **Diario de inventario a activo fijo**) se utiliza para sacar artículos del inventario y convertirlos en activos fijos. Para obtener más información, consulte [Integración de activos fijos](/fixed-assets/fixed-asset-integration.md).

La siguiente tabla muestra ejemplos de los tipos de registro predeterminados, e incluye ejemplos de cuentas principales y descripciones.

- La columna "¿Debe/Haber?" indica si la transacción generalmente se registra en el debe o el haber. En algunos casos, una transacción puede registrar débitos o créditos.
- La columna "Cuenta de compensación" indica que el tipo de registro es una cuenta de compensación. En otras palabras, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.
- La columna "P/F" indica el tipo de registro. "P" representa registro física y "F" representa registro financiero.
- La columna "Seguir" indica si la cuenta principal del tipo de publicación específico suele ser la misma que la cuenta principal de otro tipo de publicación. Específicamente, indica el tipo de publicación que se usa normalmente para el registro.

> [!NOTE]
> Las cuentas principales y los nombres de las cuentas principales de la tabla son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|---|---|---|---|---|---|---|---|---|
| Emisión de activo fijo | 180100 | Activos fijos tangibles | Activo | Crédito | No | Ambas | No aplicable | Esta cuenta se usa cuando registra un inventario en el diario de activos fijos para eliminar un artículo del inventario y convertirlo en un activo fijo. |

## <a name="moving-average-posting"></a>Registro de media móvil

El promedio móvil es un método de gestión de costes perpetuo que se basa en el principio del promedio. Los costes de las emisiones de inventario no cambian cuando lo hace el coste de compra. La diferencia se capitaliza y se basa en un cálculo proporcional. El importe restante se anota como gasto.

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones.

- La columna "¿Debe/Haber?" indica si la transacción generalmente se registra en el debe o el haber. En algunos casos, una transacción puede registrar débitos o créditos.
- La columna "Cuenta de compensación" indica que el tipo de registro es una cuenta de compensación. En otras palabras, el importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior.
- La columna "P/F" indica el tipo de registro. "P" representa registro física y "F" representa registro financiero.
- La columna "Seguir" indica si la cuenta principal del tipo de publicación específico suele ser la misma que la cuenta principal de otro tipo de publicación. Específicamente, indica el tipo de publicación que se usa normalmente para el registro.

> [!NOTE]
> Las cuentas principales y los nombres de las cuentas principales de la tabla son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|---|---|---|---|---|---|---|---|---|
| Diferencia de precios para la media móvil | 510600 | Diferencia de precios de media móvil | Gasto | Ambas | No | Ambas | No aplicable | Esta cuenta se utiliza cuando existe una diferencia de coste entre la recepción y la factura. |
| Revalorización para la media móvil | 510610 | Revalorización de la media móvil | Gasto | Ambas | No | Ambas | No aplicable | Esta cuenta se usa al ajustar el coste de media móvil para un producto |

## <a name="sample-posting-profile-configuration"></a>Ejemplo de configuración del perfil de publicación

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|---|---|---|---|---|---|---|---|---|
| Emisión de inventario | 140100 | Inventario de materiales | Activo | Crédito | No | Ambas | Recepción de inventario | Esta cuenta se usa cuando una transacción de inventario que se registra es una emisión (cantidad negativa) y no está relacionada con ventas, compras ni producción. La contrapartida de esta cuenta es la Gastos de inventario, cuenta de pérdidas. Esta cuenta representa típicamente el inventario en el balance de situación. |
| Gasto de inventario, pérdidas | 510100 | Pérdidas y ganancias de inventario | Gasto | Débito | No | Ambas | Gasto de inventario, ganancias | Esta cuenta se usa cuando una transacción de inventario que se registra es una emisión (cantidad negativa) y no está relacionada con ventas, compras ni producción. La contrapartida de esta cuenta es la cuenta de emisiones de inventario. |
| Recepción de inventario | 140100 | Inventario de materiales | Activo | Débito | No | Ambas | Emisión de inventario | Esta cuenta se usa cuando una transacción de inventario que se registra es una recepción (cantidad positiva) y no está relacionada con ventas, compras ni producción. La contrapartida de esta cuenta es la Gastos de inventario, cuenta de ganancias. Esta cuenta representa típicamente el inventario en el balance de situación. |
| Gasto de inventario, ganancias | 510100 | Pérdidas y ganancias de inventario | Gasto | Crédito | No | Ambas | Gasto de inventario, pérdidas | Esta cuenta se usa cuando una transacción de inventario que se registra es una recepción (cantidad positiva) y no está relacionada con ventas, compras ni producción. La contrapartida de esta cuenta es la cuenta de recepciones de inventario. |
| Cuentas interunidad de proveedores | 231500 | Pagable entre unidades | Pasivo | Débito | No | Ambas | | Esta cuenta se usa cuando el inventario se transfiere entre dimensiones de inventario, como sitios, y el coste de un artículo difiere entre los sitios. |
| Cuentas interunidad de clientes | 131500 | Recibible entre unidades | Activo | Crédito | No | Ambas | | Esta cuenta se usa cuando el inventario se transfiere entre dimensiones de inventario, como sitios, y el coste de un artículo difiere entre los sitios. |
