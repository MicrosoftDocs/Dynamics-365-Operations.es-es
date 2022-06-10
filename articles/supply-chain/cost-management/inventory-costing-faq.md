---
title: P+F de gestión de costes de inventario
description: Este tema responde a algunas preguntas frecuentes acerca del sistema de gestión de costes de inventario en Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45f65bd4a5cfb9bd0c4eb03ceb56eca452f6ec95
ms.sourcegitcommit: cbe9493d479f96f271d94599ec1b85131b26169f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809295"
---
# <a name="inventory-costing-faq"></a>P+F de gestión de costes de inventario

[!include [banner](../includes/banner.md)]

Este tema responde a algunas preguntas frecuentes acerca del sistema de gestión de costes de inventario en Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Cierre de inventario, ajustes y recálculo

### <a name="is-the-inventory-close-required"></a>¿Se requiere el cierre de inventario?

Si planea utilizar la característica de archivo de inventario, se requiere el cierre de inventario. Si no planea utilizar la característica de archivado de inventario, le recomendamos encarecidamente que siga ejecutando el cierre de inventario, independientemente de los modelos de gestión de costes que utilice.

### <a name="how-often-should-the-inventory-close-be-run"></a>¿Con qué frecuencia se debe ejecutar el cierre de inventario?

El cierre de inventario debe ejecutarse al menos una vez por período contable. Por ejemplo, si su libro mayor está configurado en un calendario fiscal basado en meses naturales, debe ejecutar el cierre de inventario una vez al mes.

### <a name="is-the-inventory-recalculation-required"></a>¿Se requiere recalcular el inventario?

No, no se requiere recalcular el inventario. Si utiliza un modelo de gestión de costes periódico como primero en entrar, primero en salir (FIFO), o último en entrar, primero en salir (LIFO) o promedio ponderado, debe considerar cuidadosamente si ejecutará el recálculo del inventario. Puede proporcionar costes más precisos en los modelos heurísticos que ha seleccionado.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>¿Con qué frecuencia se debe ejecutar el recálculo de inventario?

Si planea ejecutar el recálculo de inventario, le recomendamos que considere ejecutarlo diariamente como un proceso por lotes. Si su organización no requiere informes frecuentes de los valores de inventario para modelos de costes periódicos, puede considerar ejecutar el cálculo de inventario con menor frecuencia.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>¿Cuándo debo usar el ajuste de inventario disponible en la página Cierre y ajustes?

El ajuste de inventario disponible sólo se puede ejecutar despúes de completado el cierre de inventario. Por lo general, se ejecuta para la fecha posterior al último cierre. El ajuste disponible puede ajustar solo el inventario que todavía está disponible en la fecha en que ejecuta el ajuste.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>¿Cuándo debo usar el ajuste de transacciones de inventario en la página Cierre y ajustes?

Debe usar el ajuste de transacciones de inventario antes de ejecutar un cierre de inventario. Por lo general, se usa para corregir recepciones incorrectas. No puede registrar el ajuste de transacción de inventario después de ejecutar un cierre de inventario y liquidar la transacción.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>¿Las devoluciones de pedidos de compra se tratan como otros problemas durante el cierre del inventario?

Sí. Una recepción de pedido de compra es un problema que se liquida en una recepción en el modelo heurístico que seleccione para el artículo. Si usa un modelo de gestión de costes periódico, puede usar el marcado para anular el coste heurístico.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>¿Qué sucede con las devoluciones de pedidos de ventas durante el cierre de inventario?

Cuando ejecuta el cierre de inventario, una devolución de pedido de venta se trata como una recepción en el inventario. Las incidencias se liquidan contra el inventario, según el modelo heurístico que seleccione para el elemento.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>¿Qué precio de coste se utiliza en una devolución de pedido de ventas?

Cuando crea una devolución relacionada con un pedido de ventas, el valor del campo **Precio unitario** se copia del pedido de venta original y el campo **Precio de coste de devolución** de la devolución se establece en el precio de coste ajustado de la transacción de inventario original para la línea de pedido de venta que se está devolviendo. Si la opción **Valor abierto** para la transacción de inventario relacionada se establece en *Sí*, el cierre de inventario puede provocar actualizaciones en el coste de emisión en el pedido de venta original. El campo **Precio de coste de devolución** no se actualiza en este escenario. Sin embargo, cuando registra un albarán de pedido de devolución, el sistema verificará el precio de coste y utilizará el coste actualizado en la transacción de inventario de devolución.

Para una devolución de un artículo de coste estándar relacionado con un pedido de venta, el sistema utilizará el coste estándar desde el momento del pedido de venta original, incluso si hay un nuevo coste estándar activo para el artículo.

Cuando crea una devolución que no está relacionada con un pedido de ventas, el campo **Precio de coste de devolución** se establece en el precio del artículo activo que tiene para el artículo en el sitio para el que está creando el pedido de devolución. Si no tiene un precio de coste activo en una versión de gestión de costes para el artículo, el valor será 0 (cero). Si deja el valor en 0 (cero), recibirá una advertencia que indica que no se especifica el id. del lote de devolución o el precio de coste de devolución.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>¿Cuál es el rendimiento esperado del cierre del inventario?

Muchos factores pueden afectar el rendimiento del cierre del inventario. Estos factores incluyen la cantidad total de artículos, la cantidad total de transacciones en el período, los modelos de inventario que usa y la cantidad de ayudantes de lotes que configure en los parámetros de administración de inventario y almacén. Puede esperar que el cierre tarde desde unos pocos minutos hasta varias horas. No hay una guía específica sobre la cantidad de tiempo que debe tardar el cierre en ejecutarse. Debe definir sus requisitos comerciales no funcionales para el rendimiento del cierre de inventario y trabajar en estrecha colaboración con su socio para definir la programación para ejecutar el proceso de cierre de inventario. Si experimenta un rendimiento inesperadamente bajo del proceso de cierre de inventario, debe abrir un ticket de soporte.

## <a name="costing-sheet-and-indirect-costs"></a>Hoja de gestión de costes y costes indirectos

### <a name="which-costing-models-support-the-costing-sheet"></a>¿Qué modelos de gestión de costes admite la hoja de gestión de costes?

Aunque la hoja de cálculo de costes suele utilizarse en organizaciones que utilizan gestión de costes estándar, puede utilizarla con cualquier modelo de gestión de costes que esté disponible en Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>¿Puedo tener múltiples hojas de cálculo de costes para varias partes de mi organización?

No Solo puede tener una hoja de cálculo de costes por entidad jurídica.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>¿Puedo tener diferentes hojas de cálculo de costes para cada sitio?

No, no puede tener diferentes hojas de cálculo de costes para cada sitio. Solo puede crear una hoja de cálculo de costes por cada entidad jurídica. Sin embargo, puede configurar nodos totales, grupos de costes o nodos de costes indirectos por sitio. Esta configuración es un proceso manual y debe mantener la jerarquía y las asignaciones de artículos en la hoja de cálculo de costes cuando se producen cambios organizativos u operativos. Si un solo artículo se produce o compra en más de un sitio, no existe ningún mecanismo que le permita tratar el artículo de manera diferente en la hoja de cálculo de costes de cada sitio. Además, tenga en cuenta que todos los códigos de costes indirectos tienen una tasa o suplemento que se define en su versión de gestión de costes. Los costes que defina siempre son específicos del sitio.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>¿Puedo desactivar y activar versiones de la hoja de gestión de costes?

Aunque no se mantiene un historial de versiones detallado para la hoja de cálculo de costes, puede realizar cambios en la hoja de cálculo de costes y luego, cuando esté listo, guardarla y validarla. No existe ningún mecanismo que le permita volver a una versión anterior de la hoja de gestión de costes o ver los cambios que se realizaron en la hoja de gestión de costes. Si inicia cambios y no desea que surtan efecto, puede cerrar la página sin guardar y validar los cambios. Se le pedirá que descarte los cambios.

### <a name="can-i-create-indirect-costs-for-each-item"></a>¿Puedo crear costes indirectos para cada artículo?

En su hoja de gestión de costes, puede crear códigos de costes indirectos donde el campo **Tipo de nodo** se establece en *Suplemento*, *Tasa* o *Basado en unidades de salida*. A continuación, puede definir la tasa o el suplemento para que sea específico de un número de artículo. En la ficha desplegable **Tasa** o **Suplemento**, agregue una fila a la cuadrícula. Establezca el campo **Valido para** en *Tabla* y el campo **Relación** en el número de artículo específico.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>¿Puedo crear un coste indirecto que no esté relacionado con un artículo específico?

Sí. Puede crear un código de coste indirecto donde el campo **Tipo de nodo** se establezca en *Basado en unidad de salida*. A continuación, puede configurar el campo **Subtipo** en *Cantidad*, *Peso* o *Volumen* para especificar la cantidad, el peso o el volumen del artículo que está produciendo. La tasa que especifique en la ficha desplegable **Tasa** se aplicará al subtipo que seleccionó. Por ejemplo, establezca el campo **Subtipo** en *Cantidad* y el campo **Velocidad** en *1,00 USD*  y, a continuación, cree un pedido de producción o de lote para una cantidad de 10. En este caso, el coste indirecto que se agregará al bien terminado es de 10,00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>¿Puedo usar la hoja de gestión de costes para dividir mis costes de producción por horas y materiales?

Sí. Puede crear nodos de **Total** en su hoja de cálculo de costes para separar los costes por cualquier agrupación que elija. Por ejemplo, puede crear un nodo **Total** que se llama *Horas* y otro que se llame *Materiales*. En el nodo **Horas**, agregue cada grupo de códigos que esté relacionado con sus horas. En el nodo **Materiales**, agregue cada grupo de costes que esté relacionado con sus materiales.

## <a name="dimension-groups"></a>Grupo de dimensiones de inventario

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>¿Puedo administrar el coste a nivel de lote o número de serie?

Sí, si está utilizando un modelo de gestión de costes periódico como FIFO, LIFO, fecha LIFO, promedio ponderado o fecha promedio ponderada, puede habilitar la opción **Inventario financiero** de la dimensión **Lote** o **Número de serie** en el grupo de dimensiones de seguimiento para realizar un seguimiento de los costes a un nivel detallado.

### <a name="can-i-manage-costs-at-the-location-level"></a>¿Puedo administrar los costes a nivel de ubicación?

No, no puede habilitar la opción **Inventario financiero** para la dimensión **Ubicación** en el grupo de dimensiones de almacenamiento. Si su organización debe realizar un seguimiento de los costes a un nivel más detallado, considere si puede crear almacenes virtuales y luego seleccione la opción **Inventario financiero** para la dimensión **Almacén** en su grupo de dimensiones de almacenamiento.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>¿Debo habilitar la opción Usar procesos de administración de almacenes para el grupo de dimensiones de almacenamiento?

Si cree que podría querer usar las características avanzadas de administración de almacenes en el futuro, debe habilitar la opción **Utilizar procesos de administración de almacenes**. Después de guardar un grupo de dimensiones de almacenamiento, ya no puede cambiar la configuración de la opción **Utilizar procesos de administración de almacenes** para el mismo. Si decide utilizar procesos de administración de almacenes más adelante, deberá crear un nuevo almacén donde la opción esté habilitada. No existe un proceso automatizado que pueda usar para mover todo el inventario de un almacén a otro, o para copiar configuraciones relacionadas a un nuevo almacén.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>¿Puedo habilitar el uso de procesos de administración de almacenes para el grupo de dimensiones de almacenamiento incluso si no planeo usar almacenamiento avanzado?

Sí, incluso si no planea usar las funciones avanzadas de administración de almacenes, puede habilitar la opción **Utilizar procesos de administración de almacenes** para el grupo de dimensiones de almacenamiento. Para crear y procesar transacciones, deberá completar la configuración mínima, como jerarquías de reserva y grupos de secuencia de unidades. Sin embargo, la configuración del almacenamiento avanzado generalmente se ignora cuando procesa manualmente las listas de selección, los albaranes y las recepciones de productos (por ejemplo, en las páginas de pedidos de ventas y pedidos de compra).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>¿Cuándo debo habilitar la opción de inventario físico para un grupo de dimensiones de seguimiento o almacenamiento?

Debe habilitar la opción **Inventario físico** para el almacenamiento y seguimiento de grupos de dimensiones cuando deba mantener registros de inventario detallados basados en esa dimensión. Por lo general, cualquier dimensión que esté activa también se rastreará físicamente. Por lo tanto, cualquier recepción, incidencia o movimiento del inventario será rastreado por la dimensión seleccionada. Si una dimensión no es obligatoria (por ejemplo, la matrícula), puede habilitar las opciones **Recepción en blanco permitido** y **Emisión en blanco permitida** para permitir que los usuarios reciban, emitan o muevan inventario incluso cuando no se especifica la dimensión.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>¿Cuándo debo habilitar la opción de inventario físico financiero para un grupo de dimensiones de seguimiento o almacenamiento?

Debe habilitar la opción **Inventario financiero** para el almacenamiento y seguimiento de grupos de dimensiones cuando deba mantener registros financieros detallados basados en esa dimensión. Las dimensiones de **Sitio** siempre se siguen financieramente, mientras que otras dimensiones son opcionales para el seguimiento financiero. Si utiliza un modelo de gestión de costes periódica como FIFO, LIFO o promedio ponderado, lo que permite que la opción **Inventario financiero** de una dimensión indique que realizará liquidaciones solo en los casos en que la recepción y la emisión tengan los mismos valores de dimensión. Por ejemplo, si habilita la opción **Inventario financiero** para la dimensión **Almacén**, tendrá un coste diferente en cada almacén, y no se pueden liquidar recepciones e incidencias de diferentes almacenes.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>¿Puedo realizar cambios en un producto, almacenamiento o grupo de dimensiones de seguimiento después de que existan las transacciones?

Después de crear un grupo de modelos de artículos, puede cambiar la configuración de los campos **Plan de cobertura por dimensión**, **Por precios de compra** y **Por precios de venta** si la casilla **Activo** está seleccionada para una dimensión en el grupo de modelos de artículo. No se permiten otros cambios. Por ejemplo, no puede habilitar ni deshabilitar las opciones **Activo**, **Emisión en blanco permitida**, **Recepción en blanco permitido**, **Inventario físico** e **Inventario financiero**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>¿Puedo cambiar el producto, el almacenamiento o el grupo de dimensión de almacenamiento para un producto expedido?

Si el inventario disponible para un producto es 0 (cero) y la opción **Valor abierto** está configurada en *No* para todas las transacciones de inventario, puede cambiar los grupos de dimensiones de seguimiento y almacenamiento en la página de producción expedida. No puede cambiar el grupo de dimensión de producto después de crear el registro.

## <a name="item-model-groups"></a>Grupos de modelos de artículo

### <a name="when-should-i-enable-the-stocked-product-option"></a>¿Cuándo debo habilitar la opción de producto en existencias?

Debe habilitar la opción **Producto en existencias** para cualquier artículo que se vaya a rastrear en el inventario. Cuando esta opción está habilitada, se mantienen transacciones de inventario detalladas que rastrean la recepción y emisión del artículo. Esta opción suele estar habilitada para cualquier artículo tangible que tenga en su almacén, por ejemplo. También debe habilitar esta opción si planea agregar un artículo no tangible, como un artículo de servicio, a sus listas de materiales (L.M.) o fórmulas. Si no habilita la opción **Producto almacenado** no se realiza un seguimiento de las transacciones de inventario en el libro mayor auxiliar de inventario, y el coste de los artículos generalmente se contabiliza como gasto en la contabilidad general. Esta opción se usa a menudo, por ejemplo, para suministros o servicios de tiendas que no están incluidos en sus listas de materiales o fórmulas.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>¿Cuándo debo habilitar la opción Registrar inventario físico?

La opción **Registrar inventario físico** suele estar habilitada cuando la opción **Producto en existencias** está habilitada. Cuando habilita esta opción, el sistema rastreará la actualización física del artículo en la transacción de inventario. Esta opción se usa en coordinación con parámetros de Proveedores, Clientes y Control de producción que especifiquen que la actualización física debe crear un asiento. Por lo general, habilitará esta opción cuando desee que el libro mayor se actualice cada vez que actualice físicamente el inventario. Si Supply Chain Management no es su sistema de registro para las finanzas, es posible que desee deshabilitar esta opción.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>¿Cuándo debo habilitar la opción posterior de inventario financiero?

La opción **Posterior al inventario financiero** suele estar habilitada cuando la opción **Producto en existencias** está habilitada. Esta opción se usa en coordinación con parámetros de Proveedores, Clientes y Control de producción que especifiquen que la actualización financiera debe crear un asiento. Por lo general, habilitará esta opción cuando desee que el libro mayor se actualice cada vez que actualice financieramente el inventario (por ejemplo, al facturar pedidos de venta y pedidos de compra, o al finalizar un pedido de producción). Si Supply Chain Management no es su sistema de registro para las finanzas, es posible que desee deshabilitar esta opción.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>¿Cuándo debería habilitar la opción Registrar en la cuenta de ingresos diferidos en la entrega de ventas?

Utilice la opción **Registrar en la cuenta de ingresos diferidos en la entrega de ventas** para indicar si desea reconocer los ingresos en contabilidad general cuando registra un albarán para un pedido de ventas. Esta opción generalmente se usa cuando hay una gran demora entre el albarán y la factura de un pedido de ventas, o cuando no es posible facturar todos los pedidos de ventas del período. Por lo general, deshabilitará esta opción si registra sus facturas de pedidos de ventas inmediatamente después de registrar el albarán. De esta forma, evita generar registros adicionales de contabilidad general que se revertirán inmediatamente cuando facture un pedido de venta.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>¿Cuándo debo habilitar la opción Acumular pasivo a la recepción del producto?

En la mayoría de las organizaciones, deseará habilitar la opción **Acumular pasico a la recepción del producto** para todos los grupos de modelos de artículos, independientemente de si tiene un producto en existencia o un producto sin existencias. Esta opción se utiliza para contabilizar una acumulación en contabilidad general, en función del precio de recepción del producto. Debido a que suele haber un retraso entre el registro de la recepción del producto para un pedido de compra y el registro de la factura, la mayoría de las organizaciones deben reconocer el pasivo en el balance de situación para cumplir con las reglamentaciones locales, como las prácticas contables generalmente aceptadas (GAAP). Si Supply Chain Management no es su sistema de registro para las finanzas, es posible que desee deshabilitar esta opción. Si su organización usa categorías de compras en los pedidos de compra, puede controlar el requisito de acumulación habilitando la opción **Acumular gasto de compra a la recepción** para la regla de directiva de categoría en la página **Directivas de compra**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>¿Cómo puedo evitar que un usuario registre una recepción de producto de pedido de compra si aún no se ha registrado una recepción?

Puede evitar que un usuario registre una recepción de producto de pedido de compra si aún no se ha registrado un pedido de compra habilitando la opción **Requisitos de registro** para el grupo de modelo de artículo. Esta opción se usa normalmente en organizaciones que utilizan un proceso de recepción de dos pasos o en escenarios en los que debe registrar un lote o un número de serie, por ejemplo, en los artículos que está recibiendo. La opción **Requisito de registro** se aplica a *todos* las recepciones de inventario para un artículo, no solo para pedidos de compra. Por ejemplo, se aplica a un diario de inventario que tiene una cantidad positiva y un informe de pedido de producción como diario terminado.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>¿Cómo puedo evitar que un usuario registre una factura de pedido de compra si aún no se ha registrado una recepción de producto?

Puede evitar que un usuario registre una factura de producto de pedido de compra si aún no se ha registrado una recepción de producto de pedido de compra habilitando la opción **Requisitos de recepción** para el grupo de modelos de artículo. Esta opción generalmente se usa en organizaciones que requieren que las recepciones se reconozcan físicamente en contabilidad general para acumulaciones. La opción **Requisito de recepción** se aplica a *todos* las recepciones de inventario para un artículo, no solo para pedidos de compra. Por ejemplo, se aplica a un diario de inventario que tiene una cantidad positiva y un informe de pedido de producción como diario terminado. Si su organización usa categorías de compras en los pedidos de compra, puede controlar el requisito para una recepción habilitando la opción **Requisitos de recepción** para la regla de directiva de categoría en la página **Directivas de compra**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>¿Cómo puedo evitar que un usuario registre un albarán de pedido de ventas si aún no se ha publicado una lista de selección de pedidos de ventas?

Puede evitar que un usuario registre un albarán o una factura de producto de pedido de ventas si aún no se ha registrado una recepción de producto de pedido de ventas habilitando la opción **Requisitos de selección** para el grupo de modelos de artículo. Esta opción se usa normalmente en organizaciones que realizan un proceso de selección física en el almacén (por ejemplo, mediante el uso del dispositivo móvil del almacén para realizar la selección). La opción **Requisito de selección** se aplica a *todos* los incidentes de inventario para un artículo, no solo para pedidos de ventas. Por ejemplo, se aplica a un diario de inventario que tiene una cantidad negativa y un diario de lista de selección de pedido de producción.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>¿Cómo puedo evitar que un usuario registre una factura de pedido de ventas si aún no se ha registrado el albarán del pedido de ventas?

Puede evitar que un usuario registre una factura de pedido de ventas si aún no se ha registrado un albarán de pedido de ventas habilitando la opción **Requisitos de deducción** para el grupo de modelos de artículo. Esta opción se usa normalmente en organizaciones que realizan un proceso de embalaje físico en el almacén (por ejemplo, mediante el uso de la aplicación móvil Warehouse Management para hacer el embalaje o generando un documento que se incluirá con los artículos que se envían). La opción **Requisito de deducción** se aplica a *todos* los incidentes de inventario para un artículo, no solo para pedidos de ventas. Por ejemplo, se aplica a un diario de inventario que tiene una cantidad negativa y un diario de lista de selección de pedido de producción.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>¿Puedo evitar que se vendan artículos que están registrados?

Cuando un artículo se registra en su inventario en Supply Chain Management, la cantidad está físicamente disponible para ser despachada en el sistema. Si los artículos que han sido registrados pero aún no se han recibido *no* deben estar disponibles para despacharse a pedidos de venta o pedidos de producción, por ejemplo, considere usar las características de estado de inventario, bloqueo de inventario, pedidos de calidad, pedidos de cuarentena o reservas para administrar el proceso comercial.

## <a name="production-costing"></a>Gestión de costes de producción

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>¿Puedo usar un modelo de gestión de costes para las materias primas y otro para los productos terminados?

Sí, puede usar diferentes modelos de costes para cada artículo. No es raro que los fabricantes utilicen un modelo de gestión de costes periódico para las materias primas y un coste estándar para los bienes semiacabados y acabados.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>¿Cómo puedo sacar los gastos generales de los costes de máquinas?

Para sacar los gastos generales de los costes de máquinas, debe crear recursos y grupos de recursos para cada máquina, de acuerdo con los requisitos de su negocio. Cada recurso o grupo de recursos se puede asignar a categorías de costes para controlar el coste de la máquina. Cada categoría de costes se puede vincular a un grupo de costes, y cada grupo de costes se puede usar como base para calcular los costes indirectos en la hoja de gestión de costes.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>¿Cómo reconozco el coste relacionado con el consumo de energía (por ejemplo, consumo de agua, energía o gas) en la hoja de gestión de costes?

En general, puede reconocer los costes relacionados con el consumo de energía de una de dos maneras:

- Cree una línea en su lista de materiales o fórmula. Por lo general, esta línea se crea como un artículo de servicio y puede especificar la unidad de medida que está consumiendo en relación con la cantidad que está produciendo. De esta forma, el usuario puede consumir una cantidad diferente durante el proceso de producción. Puede consumir automáticamente los artículos en función del valor que seleccione en el campo **Principio de vaciado**.
- Cree un coste indirecto en su hoja de gestión de costes. Por lo general, este enfoque se usa para asignar el coste total de su consumo de energía a través de su proceso de producción. Puede usar el grupo de costes y la base de absorción para escalar el consumo según los materiales o la mano de obra en su ruta, por ejemplo.

Debe seleccionar la mejor opción, en función de sus requisitos operativos, de conciliación y de generación de informes.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>¿Puedo capturar detalles de recursos en la lista de materiales o fórmula?

Los detalles del recurso solo se pueden capturar en una operación de ruta. Aunque puede crear un artículo de servicio para representar un recurso y asignar un coste para aumentar el cálculo del coste de un bien terminado, normalmente no recomendamos este enfoque. En su lugar, le recomendamos que cree una ruta simple que tenga una línea para realizar un seguimiento de los costes de los recursos y que configure la operación para que se consuma automáticamente al inicio o al final del pedido de producción.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>¿Puedo ver los detalles del cálculo si el coste se introduce manualmente?

No Si introduce manualmente el precio en la página **Precio del articulo**, no estarán disponibles los botones **Ver detalles de cálculo** ni **Informar de detalles de cálculo**. Si selecciona el botón **Resumen de costes por grupo de costes** para un precio de coste que se introduce manualmente, se muestra una línea resumida y todos los costes se transfieren al artículo terminado.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>¿El sistema calcula las desviaciones de un pedido de producción cuando introduzco manualmente el coste?

Sí, el sistema calcula las desviaciones cuando se introduce manualmente un coste estándar. Sin embargo, cuando introduce manualmente un coste estándar en lugar de calcularlo, todos los consumos de materiales, rutas y costes indirectos del pedido de producción se consideran una desviación de sustitución. Si hay desviaciones adicionales, como el consumo de materiales extra o mano de obra, también se registrarán como desviaciones de lista de materiales de producción. Por lo tanto, le recomendamos encarecidamente que siempre ejecute un cálculo para los artículos que tengan una lista de materiales, una ruta o costes indirectos.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>¿Cómo puedo trasladar las desviaciones de un pedido de subproducción al pedido de producción principal?

Cuando utiliza un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado, los costes de una subproducción se reconocerán en el modelo heurístico que haya seleccionado para los artículos. Si necesita una gestión de costes real, considere usar el principio de marcado para indicar qué subproducción se envía a un pedido de producción principal. Alternativamente, considere usar la opción **Inventario financiero** para la dimensión **Lote** o **Número de serie** en el grupo de dimensión de seguimiento, por ejemplo.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>¿Cómo afecta el principio de vaciado al consumo?

El principio de vaciado en una lista de materiales, fórmula o línea de ruta controla el tiempo y la técnica que se utiliza para consumir el artículo o la mano de obra. Si selecciona *Inicio*, el artículo o la mano de obra se consume automáticamente cuando inicia el pedido de producción. Si selecciona *Terminación*, el artículo o la mano de obra se consume automáticamente cuando informa del pedido de producción como terminado. Si selecciona *Manual*, los usuarios deben seleccionar materiales manualmente o registrar el tiempo en un diario de trabajo o tarjeta de ruta. Las listas de materiales y las fórmulas también tienen una opción *Disponible en el lugar*. Si selecciona esta opción, los artículos se consumen automáticamente después de que se transfieran a la ubicación del piso de producción.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>¿Cómo debo ejecutar los cálculos de costes si tengo listas de materiales o fórmulas de varios niveles?

En general, le recomendamos que comience en el nivel más bajo de sus listas de materiales o fórmulas para el cálculo. Para facilitar el filtrado cuando ejecuta cálculos de costes en masa, puede usar grupos de cálculo para ayudar a segregar productos. También le recomendamos que ejecute el trabajo periódico *Recalcular niveles de L. MAT.* antes de comenzar a ejecutar cálculos de costes en masa. Cada organización debe considerar la combinación de productos y definir una estrategia que satisfaga las necesidades específicas de su producto y estructuras de fórmula o L. MAT.

## <a name="transfer-order-costing"></a>Gestión de costes de pedidos de transferencia

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>¿Hay alguna manera de asignar el flete a un coste de pedido de transferencia?

Puede agregar cargos a un pedido de transferencia para agregar costes. El código de cargos define el débito y crédito del cargo que está agregando. Primero debe crear códigos de cargos en el módulo **Gestión del inventario**. Para agregar un cargo a un pedido de transferencia, seleccione **Cargos** en la línea del pedido de transferencia a la que desea agregar un cargo.

## <a name="variances"></a>Desviaciones

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>¿Puedo tratar las desviaciones de manera diferente, según el sitio o el almacén?

No hay ninguna opción para configurar cuentas de desviación por sitio. Cuando usa la gestión de costes estándar para un producto emitido, puede seleccionar la cuenta principal que se usa para las contabilizaciones de desviación de coste estándar en la página **Registro**. Puede seleccionar configurar las cuentas para un artículo, un grupo de artículos o todos los artículos. También puede configurar un grupo de costes, un grupo de grupos de costes o todos los grupos de costes.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>¿Puedo separar las desviaciones que son el resultado de los tipos de cambio de moneda de otros tipos de desviaciones?

Si una desviación es el resultado de una diferencia de tipo de cambio de moneda entre el precio del pedido de compra y el coste estándar de un artículo, no hay forma de separar la diferencia de tipo de cambio de otras desviaciones.

## <a name="reporting"></a>Notificación

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>¿Cuántas configuraciones de informes de valores de inventario puedo crear y usar?

No hay límite para la cantidad de configuraciones de informes de valores de inventario que puede crear. Debe evaluar sus requisitos de informes específicos y crear la cantidad de configuraciones que necesita para cumplir con esos requisitos. Necesitará al menos una configuración de informes de valor de inventario para ejecutar el informe o la opción de almacenamiento de informes.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>¿Puedo usar el informe de valor de inventario para analizar el coste de un artículo en cada almacén?

Sí. Puede habilitar la opción **Vista** o **Total** para cada dimensión de **Almacén** en la configuración del informe de valores de inventario. Sin embargo, el informe solo mostrará valores para dimensiones donde la opción **Inventario financiero** esté habilitada para el grupo de dimensión de almacenamiento. Para otras dimensiones, se mostrarán solo columnas en blanco. Para más información, consulte [Ejemplos y lógica de informes de valor de inventario](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>¿Cómo puedo ver la cantidad de inventario a partir de una fecha específica con el promedio ponderado?

Puede usar el informe **Vencimiento del inventario**, que incluye una columna **Coste unitario medio** que muestra el valor del inventario en una fecha específica. Para más información, consulte [Ejemplos y lógica de informes de vencimiento de inventario](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>¿Cómo puedo ver qué transacciones de recepción se liquidan contra una transacción de emisión?

Puede ver las liquidaciones de una transacción de inventario seleccionando **Liquidaciones** o **Explorador de costes** en la pestaña **Inventario** del panel de acciones de la página **Transacción de inventario** o **Detalles de transacciones de inventario**. Si selecciona una recepción para ver los problemas relacionados con la transacción, el explorador de costes no muestra los detalles. Los detalles se muestran solo si selecciona una transacción de emisión.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>¿Cómo muestra el informe de valor de inventario los artículos que tienen una cantidad física positiva y un valor financiero negativo?

El informe de valor de inventario separa los importes y las cantidades físicas y financieras en sus propias columnas. Los valores que se muestran en el informe corresponden al intervalo de fechas que seleccionó cuando generó el informe. El nivel de resumen que se muestra depende de la configuración que haya seleccionado. Si un artículo tiene transacciones que se han recibido físicamente y emitido financieramente, las cantidades y los valores se suman de forma independiente. Si seleccionó ver el nivel de detalle como transacciones, las filas para cada recepción y emisión se muestran por separado, y se muestran las cantidades e importes físicos y financieros, respectivamente. Para más información, consulte [Ejemplos y lógica de informes de valor de inventario](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>¿Cuál es el impacto de los grupos de dimensiones de seguimiento y almacenamiento en el informe de valor de inventario?

Si habilita la opción **Valor financiero** para una dimensión en un grupo de dimensiones de almacenamiento o seguimiento, puede seleccionar la opción **Vista** o **Total** opción para la dimensión de la configuración del informe de valores de inventario. Si selecciona la opción **Vista** o **Total** para una dimensión donde la opción **Valor financiero** no está seleccionada, la columna estará en blanco en la salida del informe. Si ha habilitado la opción **Valor financiero** para una dimensión en un grupo de dimensiones de almacenamiento o seguimiento, y no selecciona la opción **Vista** o **Total** en la configuración del informe de valores de inventario, el sistema resumirá los valores de las dimensiones seleccionadas donde se realiza un seguimiento financiero.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>¿Puedo personalizar los informes insertados de Power BI para gestión de costes?

Sí, los usuarios que tienen los permisos de seguridad correctos pueden actualizar el lienzo de diseño del informe para cualquier informe de Power BI insertado en Supply Chain Management. Para obtener más información, consulte [personalizar informes insertados en áreas de trabajo analíticas](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>¿Dónde puedo ver la declaración del análisis de varianza?

Puede acceder a la declaración de análisis de varianza yendo a **Administración de costes \> Consultas e informes \> Contabilidad de inventario: informes de análisis** o **Administración de costes \> Consultas e informes \> Contabilidad de fabricación: informes de análisis**. Ambas opciones abren el mismo informe y el informe tiene el mismo comportamiento.

## <a name="item-prices-and-default-costs"></a>Precios de artículos y costes predeterminados

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>¿Puedo mantener el coste de cada variante del producto?

Sí. Puede habilitar la opción **Utilizar precio de coste por variante** en la ficha desplegable **Administrar coste** de la página **Producto remitido** para habilitar la gestión de precios por variante de producto. (Esta opción solo está disponible para productos maestros). Luego, en la página **Precio del articulo** (que puede abrir desde la página **Versión de costes** de la página **Producto expedido**), puede seleccionar **Visualización de dimensiones** para especificar si desea mostrar la dimensión **Configuración**, **Tamaño**, **Color** o **Estilo**. Para guardar la configuración y usar las dimensiones seleccionadas cada vez que abra la página, habilite la opción **Guardar configuración** y luego seleccione **Aceptar**. Puede introducir las dimensiones solo para artículos donde las dimensiones están activas en el grupo de dimensiones del producto.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>¿Puedo mantener el coste para cada almacén?

No, no se puede mantener el precio del artículo por almacén. Sin embargo, puede mantener acuerdos comerciales para precios de compra o precios de venta por almacén. Primero, seleccione la opción **Por precios de compra** o **Por precios de venta** para la dimensión en la página **Grupo de dimensiones de almacenamiento**. Luego, cuando cree el diario de acuerdos comerciales y abra las líneas para las dimensiones, seleccione **Inventario \> Dimensiones a mostrar** para seleccionar qué dimensión debe mostrarse en la cuadrícula. Para guardar la configuración y usar las dimensiones seleccionadas cada vez que abra la página, habilite la opción **Guardar configuración** y luego seleccione **Aceptar**. Puede introducir las dimensiones solo para artículos donde las dimensiones están activas en el grupo de dimensiones del producto.

### <a name="what-are-price-charges"></a>¿Qué son los cargos de precios?

Los cargos de precios brindan una forma de agregar una cantidad fija al precio unitario del precio del artículo o del acuerdo comercial. Cuando introduce una cantidad en el campo **Cargos de precio**, también puede introducir un valor en el campo **Cantidad de cargos**. Los cargos de precio se amortizan sobre la cantidad de cargos que especifique. Habilite la opción **Incluir en precio unitario** si desea incluir los cargos de precio en el precio unitario del artículo. Esta opción siempre está habilitada para un coste estándar.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>¿Cómo debo configurar los precios de los artículos que se adquieren en varias monedas?

Si introduce un precio predeterminado en el campo **Precio de compra** en la página **Producto emitido**, se supone que está en la divisa contable del libro mayor de la entidad jurídica en la que se encuentra. Asimismo, si introduce un precio de compra en una versión de gestión de costes en la que el campo **Tipo de precio** está establecido en *Compra*, se supone que el precio está en la moneda contable de su entidad jurídica. Cuando crea un pedido de compra para un proveedor que tiene una moneda diferente, el sistema convertirá automáticamente la moneda del importe de la moneda de contabilidad a la moneda de la transacción, utilizando el tipo de cambio que especifique en el campo **Tipo de cambio de moneda de contabilidad** de la contabilidad general.

Cuando crea un diario de acuerdos comerciales, puede especificar la moneda en la que está expresando el precio en cada línea. Puede crear acuerdos comerciales para varias divisas, proveedores específicos y muchas otras combinaciones de factores. Si crea un pedido de compra donde existe un acuerdo comercial para la moneda que ha seleccionado, el sistema utilizará el acuerdo comercial que tiene la moneda coincidente. Cuando registra transacciones como recepciones de productos o facturas, el importe se convertirá a la moneda contable del libro mayor mediante el tipo de cambio de moneda contable que especifique en el libro mayor.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>¿Cómo debo configurar los costes de los artículos que se adquieren en varias monedas?

Los costes no se pueden configurar en más de una moneda. El coste que especifica para el precio del artículo o los costes predeterminados que introduce en el campo **Precio** de la ficha desplegable **Administrar coste** de la página **Producto emitido** siempre se expresan en la divisa contable del libro mayor de la entidad jurídica que haya seleccionado.

Si su organización utiliza gestión de costes estándar, debe definir una estrategia para definir los costes cuando hay varias monedas. También debe definir un proceso para actualizar regularmente el coste, para ayudar a reducir la cantidad de desviaciones que se registran.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>¿Puedo usar la configuración Beneficios en la página Grupo de costes para calcular los precios de venta?

Sí, puede usar el ajuste **Beneficio** en la página **Grupo de costes** para agregar un porcentaje cuando los precios de venta se calculan mediante un cálculo de costes. Para obtener más información, consulte [Cálculos de L. MAT.](bom-calculations.md).

## <a name="marking"></a>Marcado

### <a name="how-does-marking-affect-periodic-costing-models"></a>¿Cómo afecta el marcado a los modelos de gestión de costes periódico?

Si utiliza un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado, y marcó una transacción de recepción contra una transacción de emisión, el modelo heurístico del artículo se ignora durante el proceso de cierre de inventario. En su lugar, el sistema utilizará el coste real de la recepción para el coste de la emisión.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>¿Qué sucede durante el cierre del inventario cuando utilizo el marcado?

Cuando marca recepciones y emisiones, el cierre de inventario liquidará las transacciones que se marquen juntas. Cuando se utiliza el marcado para crear la liquidación, el campo **Principio** de la página **Liquidación** se establecerá en *Marcado*. Si una transacción se marca antes de que se actualice física o financieramente, la emisión utilizará el coste de la recepción marcado en lugar del coste promedio móvil. Si las transacciones se marcan tras la actualización financiera, el proceso de cierre y ajuste de inventario ajustará el coeste de emisión, de forma que coincida con el coste de la recepción.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>¿Puedo marcar manualmente las transacciones cuando uso la gestión de costes estándar o el promedio móvil?

No, no puede marcar manualmente las recepciones o las emisiones cuando utiliza la gestión de costes estándar o el promedio móvil. Si las transacciones (por ejemplo, entrega directa o pedidos de empresas vinculadas) se marcan automáticamente, el registro de marcado permanecerá y actuará como una reserva en firme. Sin embargo, cuando utiliza la gestión de costes estándar o el promedio móvil, el marcado de los registros no tiene efecto en el coste de los artículos.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>¿Cómo afecta el marcado a la cuenta de pérdidas y ganancias?

Cuando marca una transacción de emisión contra una recepción, el coste de la emisión coincidirá con la recepción seleccionado. Cuando registre física y financieramente la emisión, la publicación afectará a las cuentas **Coste de bienes vendidos, entregados** y **Coste de bienes vendidos, facturados** que especifique en el perfil de contabilización de inventario. Si una transacción se marca después de la actualización física o financiera, el proceso *Cierre y ajuste de inventario* creará un ajuste que tiene un asiento coincidente que ajusta la cuenta **Coste de bienes vendidos, facturados** y pone la contrapartida en la cuenta que especifique para **Coste de unidades, facturados** (inventario).

### <a name="how-does-marking-affect-master-planning"></a>¿Cómo afecta el marcado a la planificación maestra?

La pestaña **Actualización estándar** de la página **Parámetros de planificación maestra** incluye un campo que se llama **Actualizar marcado**. La opción que seleccione allí se usa cuando pone en firme un pedido planificado generado por la planificación maestra. Las siguientes opciones están disponibles:

- *No*: el sistema no realiza ningún marcaje.
- *Estándar*: el sistema marca las recepciones contra las emisiones de acuerdo con el diagrama de árbol. Un pedido de requisitos está marcado frente a un pedido de proceso de entrega. Si queda alguna cantidad en el proceso de entrega, no se marca el pedido de proceso de entrega.
- *Extendido*: el sistema marca los pedidos de requisitos y los pedidos de proceso de entrega, independientemente de si queda abierta alguna cantidad en el pedido de proceso de entrega.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Inventario negativo

### <a name="when-should-i-allow-physical-negative-inventory"></a>¿Cuándo debo permitir el inventario negativo físico?

En general, no recomendamos que permita el inventario negativo físico, porque no es posible tener menos de 0 (cero) de un artículo tangible en su almacén. Sin embargo, los procesos comerciales de algunas industrias y escenarios comerciales pueden restringir las operaciones, de forma que requieren que se permita que el inventario se vuelva físicamente negativo. Por ejemplo, es posible que los minoristas no deseen evitar la venta de un artículo que se lleva a la caja registradora, incluso cuando el sistema indica que no hay artículos disponibles. Los fabricantes de procesos proporcionan otro ejemplo. Para estos fabricantes, la cantidad que se consume puede exceder lo recomendado en la fórmula. Alternativamente, el consumo podría estimarse en lugar de ser preciso, de modo que el consumo exceda la cantidad en una ubicación específica, como un depósito.

Siempre que sea posible, debe evaluar su proceso comercial y tratar de mejorarlo para asegurarse de que el inventario no pueda ser negativo. Si debe permitir el inventario negativo, debe tener un proceso empresarial claro para corregir el inventario negativo, ya que puede afectar negativamente a los costes.

### <a name="when-should-i-allow-financial-negative-inventory"></a>¿Cuándo debo permitir el inventario negativo financiero?

En general, recomendamos que la mayoría de las organizaciones permitan el inventario financiero negativo. (En la mayoría de los casos, las facturas de pedidos de compra no se procesan antes de que pueda enviar los artículos). Debe habilitar esta opción cuando tenga procesos comerciales específicos que requieran que el precio de venta refleje el coste final de un pedido de compra. Por ejemplo, este requisito podría aplicarse en una industria de fabricación a la orden o en regiones específicas donde lo dicte la ley.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>¿Qué sucede con el coste de mis emisiones cuando el inventario es negativo?

Cuando el inventario de su artículo es negativo y emite más artículos de los que tiene físicamente, el sistema usará el precio predeterminado del artículo para calcular el promedio móvil si usa un modelo de cálculo de costes periódicos como FIFO, LIFO o promedio ponderado. Si no se especifica un precio predeterminado para el artículo, el sistema emitirá el inventario con un valor de 0 (cero). Este comportamiento puede hacer que los cálculos futuros de su promedio móvil sean inexactos.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>¿Puedo evitar que los artículos se seleccionen, empaquen o vendan en pedidos de venta y pedidos de producción si no hay suficiente inventario disponible?

Sí. Le recomendamos que deshabilite la opción **Negativo físico** para el grupo de modelos de artículos para evitar que los artículos se seleccionen, empaqueten o vendan en pedidos de venta y pedidos de producción.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>¿Puedo evitar que se facturen artículos en un pedido de venta si no se han facturado pedidos de compra para el mismo artículo?

Sí. Le recomendamos que deshabilite la opción **Negativo financiero** para el grupo de modelos de artículos, para evitar que los artículos se facturen en un pedido de venta si no se han facturado pedidos de compra para el mismo artículo.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>¿Cómo afecta el inventario negativo a los indicadores financieros, como el margen de beneficio bruto?

Cuando permite que su inventario se vuelva negativo, el valor de inventario en su balance de situación y el coste de bienes vendidos en su estado de pérdidas y ganancias pueden subestimarse, especialmente si no se configura un precio predeterminado para los artículos. Por lo tanto, los informes financieros y los indicadores, como los márgenes de utilidad bruta, pueden exagerarse porque el coste es incorrecto. Si utiliza un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado, el valor de las emisiones se puede ajustar cuando ejecuta el cierre de inventario y el proceso de ajuste, después de que se hayan corregido las cantidades negativas de inventario. Sin embargo, si usa el promedio móvil, no hay forma de volver a evaluar las transacciones individuales.

### <a name="how-should-i-correct-negative-inventory"></a>¿Cómo debo corregir el inventario negativo?

Recomendamos que controle y corrija con frecuencia el inventario negativo cuando su organización o sus requisitos comerciales obliguen a que permita que su inventario se vuelva negativo. Puede corregir los valores de inventario realizando un recuento cíclico, registrando un ajuste o registrando un diario de movimientos. Si debe reconocer las ganancias inesperadas en el inventario en una cuenta de contabilidad general específica, debe planear usar un diario de movimientos. De lo contrario, cuando utilice el proceso de recuento cíclico o ajuste de inventario, el sistema registrará el ajuste de inventario en la cuenta **Recepción de inventario** y pondrá la contrapartida en las cuentas de **Gastos de inventario, beneficio** que especifique en el perfil de registro de inventario.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>¿Tengo que crear un artículo nuevo si mi inventario se ha vuelto negativo y uso el promedio móvil?

No Si su organización permite que el inventario se vuelva físicamente negativo y está usando el promedio móvil como modelo de inventario, el sistema usará la secuencia de costes alternativos que se asigna en la página **Parámetros de administración de inventario y almacén** para determinar cómo se asignará el coste a sus emisiones. En general, le recomendamos que evite permitir que su inventario se vuelva físicamente negativo. Para obtener más información, consulte otras preguntas en la sección [Inventario negativo](#negative-inventory) de este tema.

## <a name="not-stocked-products"></a>Productos no mantenidos en existencias

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>¿Puedo registrar listas de selección pedidos de ventas para productos que no están en existencias?

Cuando genera una lista de selección para un pedido de ventas que incluye artículos que están en un grupo de modelos de artículo que no está en inventario, no verá ninguna línea para esos artículos que no están en existencias. No puede usar la aplicación móvil Warehouse Management para procesar los artículos que no estén en existencias.

Cuando genera un albarán para un pedido de ventas que incluye artículos que están en un grupo de modelos de artículos que no está en existencias, configure el campo **Cantidad** en *Cantidad seleccionada y productos no almacenados* para incluir los artículos no almacenados en la generación de documentos. Si selecciona *Todos*, solo los artículos en existencias se incluirán en el albarán.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>¿Debo usar un producto no en existencias o una categoría (categoría de ventas o categoría de compras)?

La elección entre un producto sin existencias y una categoría depende de los requisitos comerciales específicos. Los productos no en existencias generalmente ofrecen más control sobre los valores predeterminados, como las cantidades y los precios en los pedidos de compra y los pedidos de venta. Por lo tanto, se prefieren los productos sin existencias en escenarios donde el mismo producto o servicio se compra o vende más de una vez. Las categorías son útiles en escenarios en los que el precio, los artículos, las descripciones, etc., son incoherentes de una transacción a otra. Las categorías también se pueden usar en cualquier producto para ayudar a clasificar el tipo de producto que se vende o compra.

## <a name="service-items"></a>Artículos de servicio

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>¿Cuál es la diferencia entre un artículo de servicio y un producto no en existencias?

Un artículo de servicio es un tipo de producto. Cuando crea un producto recién lanzado, puede configurar el campo **Tipo de producto** en *Artículo* o *Servicio*. *Artículo* normalmente se selecciona para indicar que el artículo es tangible, mientras que *Servicio* normalmente se selecciona para indicar que el artículo es intangible.

Cualquier producto lanzado, independientemente de si se trata de un artículo o un producto de servicio, se puede almacenar o no almacenar. La configuración de existencias o no existencias está controlada por el grupo de modelos de artículos que seleccione para el producto emitido. Cuando selecciona un grupo de artículos que no está en existencias, el sistema no crea transacciones de inventario para el pedido de compra o el pedido de venta relacionada, por ejemplo.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>¿Puedo incluir artículos no en existencias en una L. MAT.?

No, no puede incluir un producto lanzado que esté vinculado a un grupo de modelos de artículos donde la opción **En existencias** está deshabilitada en una L. MAT. o fórmula. No importa si el campo **Tipo de producto** está establecido en *Artículo* o *Servicio*. Solo los artículos que están en existencias se pueden incluir en las listas de materiales o en las líneas de fórmula.

## <a name="costing-modelspecific-questions"></a>Preguntas específicas del modelo de costes

### <a name="which-costing-model-should-i-use"></a>¿Qué modelo de gestión de costes debo usar?

Los modelos de gestión de costes que debe seleccionar dependen de los requisitos de su negocio. Antes de seleccionar un modelo de gestión de costes para usar en Supply Chain Management, debe validar que el modelo esté permitido por las normativas locales. Le recomendamos que valide su selección con un contable titulado de su región.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>¿Puedo usar más de un modelo de gestión de costes en mi organización?

Sí. No hay límite para la cantidad de grupos de modelos de artículos o modelos de costes que puede seleccionar en Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>¿Puedo usar más de un modelo de gestión de costes para cada artículo?

No Puede seleccionar solo un modelo de gestión de costes para cada producto lanzado. Este comportamiento está controlado por el grupo de modelos de artículos. Si debe usar más de un modelo de cálculo de costes para generar informes sobre valores de inventario, debería considerar usar el complemento Contabilidad de inventario global.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>Cuando uso la ejecución de fabricación, ¿qué metodología de gestión de costes debo usar?

Los modelos de gestión de costes que debe seleccionar dependen de los requisitos de su negocio. No existe una ventaja o desventaja específica en el uso de cualquier modelo de gestión de costes cuando su organización también utiliza la ejecución de fabricación.

### <a name="when-is-fefo-used"></a>¿Cuándo se usa FEFO?

Primero vencido, primero en salir (FEFO) no es una metodología de costes. En cambio, es una técnica de reserva que se usa a menudo en las organizaciones de fabricación. Puede habilitar las reservas FEFO para un grupo de modelos de artículos al habilitar la opción **FEFO controlado por fecha** opción y luego seleccionando un valor en el campo **Criterios de selección**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>¿Hay beneficios de rendimiento al seleccionar un modelo de gestión de costes sobre otro?

En general, el modelo de gestión de costes que seleccione para un artículo tiene un impacto mínimo en el rendimiento general del sistema. Sin embargo, la cantidad de tiempo que se requiere para ejecutar el cierre de inventario o el proceso de nuevo cálculo puede verse afectada por el modelo de cálculo de costes de inventario que seleccione. Por ejemplo, si usa el coste estándar o el promedio móvil, el proceso de cierre de inventario tiene un impacto mínimo en el sistema, porque no actualiza cada transacción de inventario ni crea liquidaciones. Sin embargo, un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado puede aumentar la cantidad de tiempo que se requiere para completar el proceso de cierre de inventario. Específicamente, el proceso de cierre puede ser más largo cuando introduce un número alto en el campo **Número máximo de iteraciones permitidas por artículo** o un número bajo en el campo **Cantidad mínima permitida** para el proceso *Cerrar inventario*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>¿Cuándo debo usar la opción Precio de recepción fijo?

Cuando selecciona la casilla **Precio de recepción fijo** en la página **Grupo de modelo de artículo** para un artículo, el sistema usará el precio de recepción como un coste estándar para la recepción de inventario. Si existe una diferencia entre el precio de compra y el precio de coste predeterminado del artículo que está configurado para un producto, la diferencia se registrará en la cuenta **Beneficio de precio de recepción fijo** o **Pérdida de precio de recepción fijo** y la contrapartida será la cuenta **Desviación de precio de recepción fijo**. (Todas estas cuentas se especifican en la página **Destino**).

Debe seleccionar la casilla **Precio de recepción fijo** cuando utiliza un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado, y requiere que se realice un seguimiento de la desviación del precio de compra en el libro mayor si el precio de una recepción difiere del coste predeterminado del artículo.

### <a name="moving-average"></a>Media móvil

### <a name="is-moving-average-the-same-as-a-floating-average"></a>¿La media móvil es lo mismo que la media flotante?

Los términos promedio móvil y promedio flotante a menudo se usan como sinónimos. De estos términos, el promedio móvil es el único modelo oficial de cálculo de costes que está disponible en Supply Chain Management. Aunque el promedio móvil no es un modelo de cálculo de costes oficial, es la técnica que se utiliza cuando se usa un modelo de gestión de costes periódico como FIFO, LIFO o promedio ponderado. El término promedio flotante no se usa en Supply Chain Management y puede tener connotaciones diferentes en otros sistemas.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>¿Cómo puedo acomodar la diferencia entre el precio de la recepción del producto y el precio de la factura cuando uso el promedio móvil?

Cuando usa el promedio móvil, el coste físico (precio de la recepción) se usa para calcular el promedio móvil para todas las transacciones de emisión. Si existe una diferencia entre el coste físico (precio de recepción) y el coste financiero (precio de factura), el sistema contabilizará automáticamente la diferencia en la cuenta principal que se especifica para el tipo de registro **Diferencia de precio para la media móvil** en la pestaña **Inventario** de la página **Perfil de contabilización de inventario**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>¿Dónde se presenta la diferencia de precio para el promedio móvil en la contabilidad general?

Cuando existe una diferencia de precio entre el registro de una actualización física y una actualización financiera para una recepción, la diferencia se registra en la cuenta principal que se especifica para el tipo de registro **Diferencia de precio para la media móvil** en la pestaña **Inventario** de la página **Perfil de contabilización de inventario**. Para obtener más información, consulte [Media móvil](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Cuando uso el promedio móvil, ¿qué sucede si hay una emisión antes de la recepción?

Por lo general, puede haber un problema antes de la recepción, ya sea porque permite un inventario físico negativo para el grupo de modelos de artículos o porque el problema proviene de antes. Para obtener más información, consulte la sección [Inventario negativo](#negative-inventory) de este tema.

Si está retrocediendo transacciones, le recomendamos que considere detenidamente su proceso comercial y sus operaciones para determinar si hay alguna manera de evitar este escenario. Si retrocede una transacción para un artículo que utiliza un promedio móvil, el sistema asignará el promedio móvil actual a la transacción. Las emisiones posteriores no se ajustan. Para obtener más información sobre el promedio móvil con transacciones retrocedidas, consulte [Media móvil](moving-average.md).

### <a name="standard-costing"></a>Gestión de costes estándar

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>¿Cuál es la diferencia entre la gestión de costes estándar y el precio de recepción fijo?

El cálculo de costes estándar requiere que defina un precio de artículo y active el coste en una versión de gestión de costes. Ese coste se utiliza para todos las recepciones y emisiones. Las desviaciones de las recepciones para el inventario se registran en el libro mayor mediante las cuentas de desviación de coste estándar que especifique en la pestaña **Coste estándar** de la página **Perfil de contabilización de inventario**.

Sin embargo, cuando usa el precio de recepción fijo, solo se fija el coste de las recepciones y el sistema usa el coste que usted especifica en la ficha desplegable **Administrar costes** de la página **Producto emitido**. Las diferencias entre el coste predeterminado y el precio del pedido de compra harán que la desviación del precio de compra se registre en las cuentas de pérdidas y ganancias del precio de recepción fijo. Las emisiones no utilizan un precio de recepción fijo. En su lugar, los problemas se valorarán según el promedio móvil en el momento de la publicación (a menos que utilice el marcado) y se volverán a evaluar según el modelo heurístico que seleccione cuando ejecute el cierre de inventario.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>¿Puedo usar reservas FEFO con costes estándar?

Sí, puede usar reservas FEFO en un grupo de modelos de artículos cuando selecciona la gestión de costes estándar. Las reservas FEFO controlan la lógica de reserva que se utiliza para el manejo físico de los artículos, mientras que la gestión de costes estándar controla el coste físico y financiero de un artículo.

### <a name="can-i-upload-pending-prices"></a>¿Puedo cargar los precios pendientes?

Sí, puede usar el complemento de Excel o el marco Administración de datos para cargar un precio pendiente. Le recomendamos que utilice las siguientes entidades:

- Precios de artículo pendientes (V2)
- Costes unitarios de categoría de coste de ruta pendientes
- Factores de cálculo de nodos de hoja de gestión de costes (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>¿Con qué frecuencia puedo actualizar el coste estándar de un artículo?

No hay límite en la frecuencia con la que puede activar un nuevo coste estándar. Si activa un nuevo coste para un artículo el mismo día en que se activó el último coste, el sistema utilizará el coste activado más reciente en nuevas transacciones o actualizaciones (como actualizaciones de transacciones existentes).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>¿Puedo desactivar o eliminar un coste activado?

No, no puede desactivar ni eliminar un coste activado. Si activó un coste incorrectamente, puede activar un nuevo coste que tenga el coste correcto.

### <a name="are-calculation-groups-used-with-standard-costing"></a>¿Se utilizan grupos de cálculo con la gestión de costes estándar?

Los grupos de cálculo se pueden utilizar con cualquier artículo, independientemente del grupo de modelo de artículo que elija. Los grupos de cálculo se usan durante el proceso de acumulación de costes o de cálculo de costes para determinar la configuración que se debe usar para los artículos para los que está ejecutando el cálculo. Para obtener más información acerca de los grupos de cálculo, vea [Grupos de cálculo de L. MAT.](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>¿Cuándo debo utilizar una versión de gestión de costes planificada?

Las versiones de gestión de costes pueden tener un tipo *Coste estándar* o *Coste planificado*. El tipo *Coste estándar* se utiliza para los costes que están activos en el sistema y se registrarán en las transacciones. El tipo *Coste planificado* se utiliza para ejecutar simulaciones de costes y no afecta al coste de las transacciones.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>¿Se puede transferir el coste total de una entidad a otra como coste de venta?

No existe una forma automatizada de copiar costes de una empresa a otra. Además, no existe una forma automatizada de copiar costes de un precio de compra a un precio de venta. Si su organización debe completar una de estas tareas, considere si puede usar el marco Administración de datos para exportar los datos de su versión de costes y cargarlos en una empresa diferente, ya sea como un precio de venta en la versión de gestión de costes o como un acuerdo comercial. Puede ser necesaria la manipulación manual de los archivos.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>¿Cuál es la mejor forma de copiar los costes planificados a una versión de gestión de costes estándar?

Puedes usar el botón **Copiar** de la página **Versiones de gestión de costes** para copiar precios de artículos, precios de categorías de costes o costes indirectos de una versión de gestión de costes a otra.
