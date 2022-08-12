---
title: Registro de pedido de compra
description: Este artículo describe la pestaña Pedido de ventas de la página de Perfiles de registro de inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 38a9e2740232b18255109ba867fcdddd5b890774
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151044"
---
# <a name="purchase-order-posting"></a>Registro de pedido de compra

La pestaña **Pedidos de compra** en la página **Perfiles de contabilización de inventario** se utiliza para controlar cómo se contabilizarán los pedidos de compra en el libro mayor. Dos actividades principales se registran en el libro mayor para una orden de compra: 

- Recepción de producto
- Factura

Para que una transacción física (recibo de producto) se registre en el libro mayor para una orden de compra, se deben seleccionar las casillas de verificación siguientes:

- La casilla de verificación **Registrar recibo de producto en el libro mayor** de la página **Registrar el albarán en el libro mayor** debe estar seleccionada.
- Las casillas de verificación **Publicar inventario físico** y **Devengar responsabilidad en la recepción del producto** en la página **Grupos de modelos de artículos**.

Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** para los siguientes tipos de contabilización:

- Coste de materiales comprados recibidos
- Gasto de compra, no facturado
- Acumulación de compras

Para que una transacción financiera (factura) se registre en el libro mayor para una orden de compra, se deben cumplir las siguientes condiciones:

- La casilla de verificación **Registrar el inventario financiero** debe estar seleccionada en la página **Grupos de modelo de artículo** para el artículo seleccionado en la línea de pedido de compra.
- Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** para los siguientes tipos de contabilización:
  - Coste de materiales comprados facturados
  - Gasto de compra para el producto
  - Gasto de compra para gasto
  - Descuento (opcional)

## <a name="fixed-receipt-price-posting"></a>Registro de precio de recepción fijo

Puede usar el precio de recibo fijo como costo estándar para un producto como alternativa a seleccionar la opción **Coste estándar** en el campo **Modelo de inventario** campo en la página **Grupos de modelos de artículos** de un artículo. La principal diferencia cuando usa **Precio de recibo fijo**, el precio de coste que se usará para el artículo cuando se registre el recibo en el inventario. No hay proceso de revalorización de costes para **Precio de recibo fijo**; cuando se contabiliza una actualización financiera, se utiliza el precio de costo actual en el momento de la contabilización. Si hay una diferencia entre el precio de costo que se usa en la recepción y la factura, la desviación se contabilizará en las cuentas de pérdidas y ganancias del precio de recepción fijo.

Para usar un precio de recibo fijo para un producto, debe configurar lo siguiente:

- En la página **Grupos de modelos de artículos** seleccione las casillas de verificación **Registrar inventario físico** y **Precio de recibo fijo**. 
- Sobre la página **Parámetros de gestión de inventario y almacén**, seleccione la casilla **Registrar el albarán en el libro mayor**.
- Especifique las cuentas principales de los siguientes tipos de registro en la página **Perfil de contabilización de inventario**:
  - Ganancias del precio de recepción fijo
  - Pérdidas del precio de recepción fijo
  - Contrapartida del precio de recepción fijo

Para obtener más información, vaya a [Precio de recibo fijo](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Gastos de compra y contabilización de variaciones de stock

Si planea contabilizar los cargos de compra y las variaciones de existencias, haga lo siguiente:

- En la página **Parámetros de proveedores**, en la pestaña **Factura**, seleccione la casilla **Registrar en cuenta de cargos en libro mayor**.
- En la página **Grupos de modelos de artículos** para el artículo seleccionado en la línea de orden de compra, seleccione las casillas de verificación **Registrar inventario físico**, **Registrar inventario financiero**, y **Devengar responsabilidad en el recibo de producto**.
- En la página **Parámetros de adquisición y abastecimiento**, seleccione la casilla de verificación **Generar cargos en la recepción del producto**.
- Sobre la página **Parámetros de gestión de inventario y almacén**, seleccione la casilla **Registrar el albarán en el libro mayor**.

Sobre la página **Perfil de contabilización de inventario**, debe especificar las cuentas principales para los siguientes tipos de contabilización:

- Gasto de compra, no facturado
- Gasto de compra para el producto
- Variación de existencias

> [!NOTE]
> El tipo de registro **Cargo** no se utiliza cuando el parámetro **Registrar en cuenta de cargo en el libro mayor** se selecciona.

Para más información, vaya a [Registrar en cuenta de cargo](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Ejemplo de configuración del perfil de publicación

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones:

- La columna **Cuenta de compensación** indica que el tipo de contabilización es una cuenta de compensación. El importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior. 
- La columna **F/F** indica **p** para publicación física y **f** para la contabilización financiera. 
- La columna **Seguir** indica si la cuenta principal para un tipo de publicación específico suele ser la misma que para otro tipo de publicación. El valor de la columna indica el tipo de publicación que se suele utilizar.

> [!NOTE]
> Las cuentas principales y nombres de cuentas principales son solo sugerencias. Recomendamos<!--note from editor: Via Writing Style Guide.--> que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.


| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Coste de materiales comprados recibidos | 140100</br>140101 | Inventario de materiales</br>Materiales enviados, no facturados | Activo | Débito | Sí | C | Coste de materiales comprados facturados | Se usa cuando se registra un recibo de producto de orden de compra, la compensación a la cuenta es Gasto de compra, sin factura. El importe registrado en esta cuenta se revierte cuando se registra una factura de pedido de compras. |
| Gasto de compra, no facturado | 600180 | Recibos de material | Gasto | Débito | Sí | C | |Para un pedido de compra, esto ocurre cuando se registra la recepción del producto. Se crean dos comprobantes para el recibo para realizar un seguimiento de las variaciones del precio de compra cuando se utiliza el costo estándar. La compensación a la cuenta en el primer comprobante es la acumulación de Compra. La compensación en el segundo comprobante es la suma de las cuentas Costo de los materiales comprados recibidos y Variación del precio de compra. Los importes registrado en esta cuenta se revierten cuando se registra una factura de pedido de compras. |
| Coste de materiales comprados facturados | 140100 | Inventario de materiales | Activo | Débito | No | V  |Coste de materiales comprados recibidos | Se utiliza cuando se registra una factura de pedido de compras. La compensación a la cuenta es Gasto de compra por producto. Esta cuenta representa el inventario en su hoja de balance. La cuenta utilizada suele ser la misma cuenta utilizada para Coste de unidades entregadas y Coste de unidades facturadas para pedidos de venta. |
| Gasto de compra para el producto | 600180 | Recibo de materiales | Gasto | Crédito | Sí | V  | |Se utiliza cuando se registra una factura de pedido de compras. Se crean dos comprobantes para la factura para realizar un seguimiento de las variaciones del precio de compra cuando se utiliza el costo estándar. La compensación a esta cuenta es Gasto de compra por producto, cuenta sin factura que se utiliza en el registro de recibos y se invierte durante la contabilización de facturas. Representa los costes del inventario comprado en la facturación que no se reflejan en la cuenta de inventario en el balance de situación. Este es un registro de pérdidas y ganancias para la desviación en el precio de compra que se ve más comúnmente en las compras de artículos de coste estándar.|
| Beneficio de precio de recibo fijo (Compra, beneficio de precio de recibo fijo*) | 510310 | Desviación de precio de compra | Gasto | Crédito | No | V | Pérdidas del precio de recepción fijo | Se usa cuando se registra una factura de orden de compra y hay una diferencia entre el precio facturado y el costo predeterminado del artículo. Esta cuenta se utiliza cuando la diferencia es mayor. La cuenta de contrapartida de esta cuenta es la compensación precio de recibo fijo. |
| Pérdidas de precio de recibo fijo (Compra, pérdidas de precio de recibo fijo*) | 510310 | Desviación de precio de compra | Gasto | Débito | No | V | Ganancias del precio de recepción fijo | Se usa cuando se registra una factura de orden de compra y hay una diferencia entre el precio facturado y el costo predeterminado del artículo. Esta cuenta se utiliza cuando la diferencia es menor. La cuenta de contrapartida de esta cuenta es la compensación precio de recibo fijo. |
| Contrapartida de precio de recibo fijo (Compra, contrapartida de precio de recibo fijo*) | 140900 | Variación de existencias | Activo | Ambas | No | V  | |Se usa cuando se registra una factura de orden de compra y hay una diferencia entre el precio facturado y el costo predeterminado del artículo. Esta cuenta es la compensación de las cuentas de pérdidas y ganancias de precio de recibo fijo. |
| Cargo | No disponible | No disponible | No disponible | No disponible | No disponible | No disponible | No disponible | Esta cuenta ya no se usa. En su lugar, utilice la variación de Stock. |
| Variación de existencias | 600170 | Variación de existencias | Gasto | Crédito | No | Ambas | | Esta cuenta se utiliza cuando: <ul><li>Hay una diferencia en el precio unitario entre la recepción del producto y la factura.</li><li>Los cargos se registran en el artículo.</li><li>Los costos indirectos han sido<!--note from editor: Edit okay?--> añadidos a los artículos comprados. </li><li>La compensación a esta cuenta es Gasto de compra, cuenta sin factura.</li></ul> |
| Acumulación de compras | 200140 | Compras acumuladas | Pasivo | Crédito | Y | C | |Se usa cuando se registra un recibo de producto de orden de compra y la opción para acumular montos de compra está habilitada. |
| Impuestos acumulados en la recepción | 250500 | Impuestos acumulados | Pasivo | Crédito | Y | Ambas  | |Esta cuenta se utiliza cuando selecciona la opción **Registrar impuesto físico** en el **Parámetros de gestión de inventario y almacén** y tiene una orden de compra con impuestos. El monto se registra cuando actualiza la orden de compra físicamente (recibo del producto) y se invierte cuando registra la orden de compra financieramente (factura). |
| Recibo de activo fijo (débito de activo fijo*) | 180100 | Activos fijos tangibles | Activo | Débito | N | Ambas | Ambas | Esta cuenta se usa cuando selecciona la opción en la línea de orden de compra para Activos fijos. La integración de la orden de compra se ha configurado para adquirir el activo fijo al recibir el producto o la factura. Para obtener más información sobre la integración de órdenes de compra de activos fijos, vaya a [Adquirir activos a través de adquisiciones](/fixed-assets/acquire-assets-procurement). |
| Gasto de compra para gasto | 618900 | Gastos varios | Gasto | Débito | N | Ambas | |Se usa cuando se registra un recibo de producto o una factura para una orden de compra donde los artículos no están almacenados o se usa una categoría de compras. |
| Pagos por adelantado | 132190 | Gasto de pago por adelantado | Activo | Débito | N | Ambas | | Se utiliza al procesar una factura de prepago en una orden de compra. |


\*Los valores que se muestran entre paréntesis representan el valor que se usa en el campo **Tipo de publicación** en la página **Transacciones de cupones**. Puede ver el **tipo de registro** en la página **Transacciones de asiento** en la pestaña **General**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Contabilización de activos fijos con órdenes de compra

Si usa el módulo **Activos fijos** módulo y plan de compra de activos fijos a través de órdenes de compra, debe configurar el tipo de registro **Recibo de activo fijo** en la pestaña **Orden de compra** de la página **Perfil de contabilización de inventario**. Para obtener más información, vaya a [Integración de activos fijos](/fixed-assets/fixed-asset-integration.md) y [Crear y adquirir activos de proveedores](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Registrar factura de prepago de pedido de compra

Si planea usar la función **Factura de prepago** para órdenes de compra, el tipo de contabilización **Prepago** debe seleccionarse en la pestaña **Orden de compra** en la página **Perfil de contabilización de inventario**. Para obtener más información, vaya a [Facturas de prepago vs prepagos](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Solicitud de compra y registro de confirmación de orden de compra

Las solicitudes de compra y las confirmaciones de órdenes de compra también se pueden configurar para publicar compromisos previos y compromisos en el libro mayor. Estas contabilizaciones están controladas por una definición de contabilización. Para obtener más información, vaya a [Sobre reservas de gastos de pedidos de compra](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Contabilización de categoría de adquisición

Como alternativa a la configuración del registro de inventario para todos los artículos, un grupo de artículos o un solo artículo, puede configurar categorías y controlar el registro contable por categorías de adquisiciones. Para obtener más información sobre cómo configurar categorías y asignarlas a productos, vaya a [Ejemplo de configuración del perfil de publicación](#sample-posting-profile-configuration) anteriormente en este artículo.

Cuando se utilizan categorías con órdenes de compra o facturas de proveedores, la jerarquía de categorías debe asignarse al tipo **Jerarquía de categorías de compras** en la página **Asignaciones de roles de jerarquía de categorías**.

### <a name="vendor-invoices-with-procurement-categories"></a>Factoras de proveedor con categorías de compras

Si su organización usa órdenes de compra para algunas compras y no para otras, puede procesar facturas no relacionadas con órdenes de compra de varias maneras. Esto incluye el uso de diarios en **Proveedores** o por la página **Facturas de proveedores pendientes** que se utiliza para generar facturas para órdenes de compra. Al crear facturas para facturas no relacionadas con órdenes de compra, deberá crear categorías de compras para cada tipo de gasto. Deberá asignar la categoría a la cuenta de gastos correcta en la página **Perfiles de contabilización de inventario**.

El número exacto de categorías variará según el número de cuentas de gastos que utilice para registrar sus facturas. Necesitará al menos una categoría de compras para cada cuenta principal en la que gaste facturas que no sean órdenes de compra. Se pueden usar muchas categorías para una sola cuenta principal. Esto puede ser útil para la usabilidad, la capacidad de búsqueda y el informe de los tipos de gastos que utiliza.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Beneficios de usar categorías de compras para facturas de proveedores

Algunos beneficios de usar categorías de compras para facturas de proveedores incluyen:

- Experiencia de usuario uniforme: cuando configura categorías de compras para todos los gastos no relacionados con órdenes de compra, los usuarios pueden recibir capacitación en un proceso de facturación mediante la página **Facturas de proveedores pendientes**.
- Experiencia de generación de informes mejorada: cuando configura categorías de compras para todos los artículos y todos los gastos no relacionados con órdenes de compra, el informe de gastos de compras analizará los gastos por proveedor, categoría y más.
- Flujo de trabajo coherente: cuando utiliza **Facturas de proveedores pendientes** para procesar todas las facturas, puede crear un flujo de trabajo coherente y un proceso de aprobación mediante un único flujo de trabajo.

## <a name="consignment-inventory-posting"></a>Contabilización de inventario de entrega

El inventario de entrega utiliza la misma contabilización en el libro mayor que otros artículos comprados. La diferencia clave es que cuando se recibe el inventario, no se registran transacciones en el libro mayor. Para transferir la propiedad a la organización cuando un **Cambio de propiedad del inventario** se contabiliza el diario, se genera un comprobante para registrar el costo del artículo. Para obtener más información, vaya a [Configurar entregas](/supply-chain/inventory/consignment.md).
