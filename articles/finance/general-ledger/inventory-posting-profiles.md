---
title: Perfiles de registro de inventario
description: Este tema proporciona una visión general de los perfiles de registro de inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28e3a3051978f921e01a929496e96909e6c32429
ms.sourcegitcommit: 00b39900d3cbdbc9ca1ab3145265007f5dc98a3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "8806380"
---
# <a name="inventory-posting-profiles"></a>Perfiles de registro de inventario

[!include [banner](../includes/banner.md)]

Los perfiles de registro de inventario controlan las transacciones del submayor de inventario en la contabilidad general. Las transacciones del submayor de inventario se pueden generar a partir de muchos módulos, incluidos **Ventas y marketing**, **Adquisiciones y abastecimiento**, **Control de producción**, etc. Las transacciones del submayor de inventario se pueden registrar cada vez que se utiliza un artículo en un pedido de compra o de venta. 

Es posible que se registren transacciones adicionales del submayor de inventario:
- Cada vez que se actualiza un documento.
- Cuando se registra un albarán o una factura de pedido de ventas.
- Cuando se genera una recepción o factura de producto de pedido de compra.

Para obtener más información, vaya a las transacciones de submayor de inventario.

## <a name="inventory-transaction-overview"></a>Información general de transacciones de inventario

Cada transacción del submayor de inventario contiene:
 - Quantity 
 - Precio 
 - Sitio 
 - Almacén 
 - Ubicación 

Las transacciones del submayor de inventario crean dos entradas en de contabilidad general a través del registro físico y el registro financiero. Para obtener más información, vaya a [Actualizaciones físicas y financieras](/supply-chain/cost-management/physical-financial-updates.md).
El siguiente ejemplo es un pedido de compra con tres líneas. Para este ejemplo, suponga que todo el pedido es para un solo sitio y almacén. Cada línea de pedido de compra tiene un único registro InventTrans relacionado, también conocido como transacción de inventario, y cada línea es para una cantidad de 10. El siguiente diagrama muestra la relación de un encabezado de pedido de compra con tres líneas de pedido de compra, cada una con un registro InventTrans.

![Diagrama de relación para un pedido de compra con tres líneas, cada una con un registro InventTrans.](./media/InventTransRelationship.PNG)

Se ha recibido una cantidad de 5 en la primera línea del pedido de compra. La cantidad total de la segunda línea y ninguna cantidad recibida en la tercera línea del pedido de compra. Ahora hay una segunda transacción de inventario relacionada con la primera línea del pedido de compra. La transacción de la segunda línea del pedido de compra se actualizará a **Recibido**, y la tercera transacción seguirá siendo la misma. El siguiente diagrama muestra la relación con el registro adicional InventTrans para la línea de pedido de compra 1.

![Diagrama de relación para un pedido de compra con tres líneas. Una línea se recibe parcialmente y muestra dos registros InventTrans.](./media/InventTransRelationshipPartialReceipt.PNG)

En este ejemplo, se registrará un asiento en contabilidad general; este es el asiento físico. El grupo de modelos de artículos está configurado para registrar el inventario físico y todos los artículos utilizan el mismo grupo de modelos de artículos. El perfil de registro de inventario utiliza un único conjunto de cuentas principales. Se creará un único comprobante y el registro InventTrans vinculará tanto InventTrans 1 como InventTrans 2 al mismo comprobante.

A continuación, se recibe una factura por la cantidad que se recibe en las líneas 1 y 2. Se crea otro comprobante en contabilidad general; este es el comprobante financiero. El grupo de modelos de artículo está configurado para registrar inventario financiero. El nuevo segundo asiento está relacionado con InventTrans 1 e InventTrans 2.

Según el modelo de gestión de costes, puede existir una tercera contabilización en contabilidad general para las transacciones del sublibro auxiliar de inventario relacionadas con el cierre y la liquidación del inventario. Para obtener más información, consulte [Cierre de inventario](/supply-chain/cost-management/inventory-close.md). Puede ver los detalles de todas las transacciones de inventario yendo a **Gestión del inventario** > **Consultas e informes** > **Transacciones**.

>[!Important]
> Las transacciones de inventario se dividirán para cada combinación única de dimensiones de inventario y para cada actualización parcial. Esto se mostró en el ejemplo anterior para actualizaciones parciales.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Dividir inventario basado en el ejemplo de dimensión de inventario

La línea de pedido de compra 3 del ejemplo es un artículo serializado. Se registran diez números de serie para el pedido de compra durante el proceso de recepción. La transacción de inventario se dividirá en 10 transacciones de inventario. El siguiente diagrama muestra la relación y las transacciones de inventario adicionales, cada una con su propio número de serie relacionado con la línea de pedido de compra 3.

![Diagrama de relación para un pedido de compra con tres líneas. Una línea está serializada y muestra registros InventTrans adicionales](./media/InventTransRelationshipSerialNumber.PNG)

En el ejemplo anterior, si cada número de serie se recibe en una sola recepción de producto, se creará un asiento adicional. El campo del asiento físico estará vinculado a cada número de serie. Lo mismo ocurre con la actualización financiera, cuando se factura el pedido de compra.

## <a name="inventory-transactions"></a>Transacciones de inventario

Puede ver las transacciones de inventario en la página **Transacciones de inventario**, en **Gestión de inventarios y almacenes** o **Administración de costes**. También puede ver las transacciones de inventario relacionadas con una línea de documento de origen específica, como una línea de pedido de compra o una línea de pedido de venta, seleccionando **Inventario** y luego seleccionando **Transacciones**. 

La página **Transacciones de inventario** contiene los siguientes campos.

| Campo            | Description                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Número de artículo      | El número de artículo relacionado con la transacción.                                                                  |
| Fecha física    | La fecha en que el inventario llega al almacén, sale del almacén, se consume en producción o se produce. Por ejemplo, la fecha de registro del
albarán registra un pedido de venta o la contabilización de la recepción del producto para un pedido de compra.                             |
| Fecha financiera   | La fecha en que se cierra la transacción de inventario y el coste se registra en contabilidad general. Por ejemplo, la fecha de registro de la generación 
de la factura para un pedido de compra o de ventas. No se permiten actualizaciones al documento de referencia después de rellenada la fecha financiera. |
| Referencia        | Indica el origen de la transacción y el tipo de documento que se muestra en el campo **Número**. Por ejemplo, pedido de venta, pedido de compra o recepción de pedido de transferencia.                                                 |
| Número           | Indica el id. de referencia de una transacción. Por ejemplo, si el campo **Referencia** indica pedido de venta, el campo **Número** indica el número de pedido de venta.                                                       |
| Recepción (estado) | Para las transacciones de inventario que son recepciones, este campo indica el estado de la recepción. Por ejemplo, un pedido de compra es una recepción y el estado puede ser **Pedido** o **Comprado**.                                                            |
| Emisión (estado)   | Para las transacciones de inventario que son emisiones, este campo indica el estado de la emisión. Por ejemplo, un pedido de ventas es una emisión, y el estado puede ser **En pedido** o **Vendido**.                         |
| Quantity         | La cantidad de la transacción de inventario. Los números positivos se usan para recepciones de inventario, mientras que los números negativos se usan para emisiones de inventario.                                                                                                                          |
| Unidad             | La unidad de medida en la que se expresa la cantidad.                                                                                   |
| Cantidad PC      | La cantidad de peso capturado para la transacción. Para obtener más información, vaya a [Acerca de los artículos de peso capturado](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Unidad de PC          | La unidad de medida de peso capturado en que se expresa la cantidad de peso capturado.                                                         |
| Importe de coste      | El coste final de la transacción de inventario. Este campo se rellena cuando una transacción se actualiza financieramente. Dependiendo de la metodología de gestión de costes, el proceso de ajuste y cierre de inventario puede actualizar este campo.                            |

## <a name="inventory-status"></a>Estado de inventario

Cada transacción de inventario tiene un estado que se muestra en el campo **Recepción** o **Emisión**. El campo que se usa depende del tipo de transacciones de inventario. Las recepciones son transacciones que aumentan el inventario. Por ejemplo, un pedido de compra con una cantidad positiva o una devolución de un pedido de venta con una cantidad negativa. Las emisiones son transacciones de inventario que reducen el inventario. Por ejemplo, un pedido de ventas con una cantidad positiva o una devolución de un pedido de compra con una cantidad negativa.

### <a name="receipt-status"></a>Estado de la recepción

En la siguiente tabla se describe cada estado de **Recepción**.

| **Estado de la recepción** | **Descripción**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Pedido            | El estado inicial de cualquier transacción de inventario que represente una recepción. Esto incluye pedidos de compra con una cantidad positiva, pedidos de producción o devoluciones de pedidos de venta con una cantidad negativa.                                                   |
| Registrada         | Este estado se utiliza cuando existe un proceso de recepción de dos pasos o cuando se utiliza la llegada del artículo para indicar que el producto ha llegado. Se utiliza cuando los números de lote o de serie se "asignan" o registran en el pedido. Para obtener más información sobre la llegada de artículos, vaya a [Información general sobre llegadas](/supply-chain/inventory/arrival-overview.md). |
| Recibido           | Este estado se utiliza cuando la transacción se actualiza físicamente. Para un pedido de compra, esto ocurre cuando se registra la recepción del producto. Para una devolución de un pedido de ventas, esto ocurre al registrar el albarán.                                                                            |
| Comprado          | Este estado se utiliza cuando la transacción se actualiza financieramente. Para un pedido de compra o una devolución de pedido de ventas, esto ocurre cuando se genera la factura.                                                                                             |

### <a name="issue-status"></a>Estado de la emisión

En la siguiente tabla se describe el estado **Emisión**.

| **Estado de la emisión**  | **Descripción**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| En pedido          | El estado inicial de cualquier transacción de inventario que represente una emisión. Esto incluye pedidos de ventas con una cantidad positiva, L. MAT. de pedidos de producción o líneas de fórmula, o devoluciones de pedidos de venta con una cantidad negativa.                                             |
| Pedido reservado  | Este estado de inventario indica que el inventario está reservado para un pedido que se ha creado, pero que aún no se ha recibido físicamente en el inventario. Cuando se recibe el inventario, el estado se actualizará automáticamente a **Físico reservado**. Para más información sobre reservas, vaya a [Cantidades de inventario de reserva](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Física reservada | Este estado indica que el inventario se ha asignado o reservado para un pedido específico. Cuando se reserva el inventario, deja de estar físicamente disponible para otros pedidos.                                 |
| Seleccionado         | Esto indica que el inventario se ha recogido del almacén. El inventario todavía está físicamente en el almacén, no se ha eliminado, pero no está disponible para otros pedidos.  |
| Deducido          | Este estado se utiliza cuando la transacción se actualiza físicamente. Para un pedido de venta, ocurre cuando se contabiliza el albarán; para una devolución de pedido de compra, ocurre cuando se registra la recepción del producto.                                                                      |
| Vendido              | Este es el estado utilizado cuando la transacción se actualiza financieramente. Para un pedido de compra o un pedido de ventas, esto ocurre cuando se genera la factura.|

Para obtener más información sobre las transacciones de inventario, vaya a [Detalle de transacciones de inventario](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Configurar un perfil de registro de inventario

Para configurar un perfil de registro de inventario, siga estos pasos:

1.  Abra **Gestión de inventarios** > **Configurar** > **Registro** > **Registro**.
2.  Seleccione la pestaña del tipo de transacción. Por ejemplo, seleccione **Pedido de compra**.
3.  Seleccione el botón de radio del tipo de registro. Por ejemplo, seleccione **Gasto de compra para gasto**.
4.  Seleccione **Nuevo**.
5.  En el campo **Código de artículo**, seleccione una opción para **Tabla**, **Grupo**, **Todos** o **Categoría**. Por ejemplo, para configurar un perfil de registro para un grupo de artículos específico, seleccione **Grupo**.
     - Si seleccionó **Tabla** en el paso 5, seleccione el número de artículo específico para el perfil de registro en el campo **Relación de artículo**.
     - Si seleccionó **Grupo** en el paso 5, seleccione el **Grupo de artículos** para el perfil de registro en el campo **Relación de artículo**.
     - Si seleccionó **Todos** en el paso 5, el campo **Relación de artículo** se dejará en blanco.
     - Si seleccionó **Categoría** en el paso 5, el campo **Relación de artículo** se dejará en blanco. Use el campo **Relación de categoría** para seleccionar la categoría a la que se aplica el perfil de registro.

6.  En el campo **Código de cuenta**, seleccione una opción para **Tabla**, **Grupo** o **Todos**. Por ejemplo, para aplicar el perfil de registro a todos los proveedores, seleccione **Todos**.
     - Si seleccionó **Tabla** en el paso 5, seleccione el número de proveedor específico para el perfil de registro en el campo **Relación de cuenta**.
     - Si seleccionó **Grupo** en el paso 5, seleccione el grupo de proveedores específico para el perfil de publicación en el campo **Relación de cuenta**.
     - Si seleccionó **Todos** en el paso 5, el campo **Relación de cuenta** estará en blanco.

7.  Para asociar un grupo de impuestos concreto que tiene el tipo de registro seleccionado, seleccione un **Grupo de impuestos de ventas**. Si este campo está en blanco, el tipo de registro se aplica a todos los grupos impositivos existentes. El registro que se especifica para los grupos impositivos se aplica sólo a las transacciones de ventas y compras.
8.  Especifique el número de cuenta para registrar el tipo de cuenta en el campo **Cuenta principal**. Si aún no se ha creado ningún número de cuenta para usarlo como tipo de contabilidad, puede crear una nueva cuenta. Puede crear una nueva cuenta en la página **Detalles de cuenta principal** en contabilidad general.

## <a name="additional-resources"></a>Recursos adicionales

Cada pestaña de la página **Perfil de registro de inventario** se relaciona con un submayor en Dynamics 365 Supply Chain Management. Para obtener más información, vaya a:
-   [Publicación de pedido de ventas](sales-order-posting.md)
-   [Registro de pedido de compra](purchase-order-posting.md)
-   [Registro de inventario](inventory-posting.md)
-   [Registro de control de producción](production-posting.md)
-   [Registro de desviación de coste estándar](standard-cost-variance-posting.md)
