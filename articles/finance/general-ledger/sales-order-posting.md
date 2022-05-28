---
title: Publicación de pedido de ventas
description: Este tema proporciona información sobre la pestaña Pedido de ventas de la página de perfil de registro de inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5d84723b51d6977867fa162c4a47befa61bd9ef6
ms.sourcegitcommit: dc3053625dfe24aef64399dd1d002214e7f7619f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755939"
---
# <a name="sales-order-posting"></a>Publicación de pedido de ventas

La pestaña **Órdenes de venta** en la página **Perfiles de contabilización de inventario** se utiliza para controlar cómo se contabilizarán los pedidos de venta en el libro mayor. Dos actividades principales se registran en el libro mayor para una orden de venta: 

- Albarán
- Factura

Para que una transacción física (albarán) se registre en el libro mayor para una orden de venta, se deben cumplir las siguientes condiciones:

- Sobre la página **Parámetros de gestión de inventario y almacén**, la casilla **Registrar el albarán en el libro mayor** debe estar seleccionada.
- Sobre la página **Grupo de modelo de artículo** para el artículo seleccionado en la línea de orden de venta, la casilla **Registrar el inventario físico en el libro mayor** debe estar seleccionada.
- Sobre la página **Perfil de contabilización de inventario**, las cuentas principales deben especificarse para los siguientes tipos de contabilización:
  - Coste de unidades, entregadas
  - Coste de bienes vendidos, entregados

Para que una transacción financiera (factura) se registre en el libro mayor para una orden de venta, se deben cumplir las siguientes condiciones:

- Sobre la página **Grupo de modelo de artículo** para el artículo seleccionado en la línea de orden de venta, la casilla **Registrar el inventario financiero en el libro mayor** debe estar seleccionada.
- Las cuentas principales deben especificarse en la página **Perfil de contabilización de inventario** para los siguientes tipos de contabilización:
  - Coste de unidades, facturadas
  - Coste de bienes vendidos, facturados
  - Ingresos
  - Descuento\*

> [!NOTE]
> La cuenta de descuento es opcional. Muchas regulaciones contables, como GAAP e IFRS, requieren que los descuentos reduzcan los ingresos por ventas y, por lo tanto, estas cuentas no se usan en muchos escenarios. Si las regulaciones locales lo permiten, use una cuenta principal separada para registrar la parte del precio de venta que se descuenta.

Para contabilizar el valor de ingresos diferidos (estimados) en el libro mayor cuando genera un albarán para un pedido de ventas, se deben cumplir las siguientes condiciones:

- Sobre la página **Grupo de modelo de artículo** para el artículo seleccionado en la línea de orden de venta, la casilla **Registrar el inventario físico en el libro mayor** debe estar seleccionada.
- Sobre la página **Grupo de modelo de artículo**, la casilla **Registrar en la cuenta de ingresos diferidos en la entrega de ventas** debe estar seleccionada.
- Sobre la página **Parámetros de gestión de inventario y almacén**, la casilla **Registrar el albarán en el libro mayor** debe estar seleccionada.
- Sobre la página **Parámetros de gestión de inventario y almacén**, la casilla **Registrar impuestos de ventas físicos** debe estar seleccionada.
- Sobre la página **Parámetros de clientes**, la casilla **Registrar el albarán en el libro mayor** debe estar seleccionada.
- Sobre la página **Perfil de contabilización de inventario**, las cuentas principales deben especificarse para los siguientes tipos de contabilización:
  - Ingresos diferidos a la entrega
  - Contrapartida de ingresos diferidos a la entrega
  - Impuestos diferidos en la entrega

> [!NOTE]
> En general, recomendamos que habilite las opciones **Publicar inventario físico** y **Registrar el albarán en el libro mayor**. Habilitar estas opciones puede ayudar a acelerar los procedimientos de cierre de fin de mes, ya que no será necesario calcular ni publicar aplazamientos manualmente. Además, los estados financieros reflejarán los montos diferidos automáticamente sin intervención manual.

> [!IMPORTANT]
> La opción **Registrar en la cuenta de ingresos diferidos en la entrega de ventas** no se utiliza con el reconocimiento de ingresos. Para obtener más información sobre el reconocimiento de ingresos, vaya a [Descripción general del reconocimiento de ingresos](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Ejemplo de configuración del perfil de publicación 

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones:
 
- La columna **Cuenta de compensación** indica que el tipo de contabilización es una cuenta de compensación. El importe registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior. 
- La columna **F/F** indica **p** para publicación física y **f** para la contabilización financiera. 
- La columna **Seguir** indica si la cuenta principal para un tipo de publicación específico suele ser la misma que para otro tipo de publicación. El valor de la columna indica el tipo de publicación que se suele utilizar.

> [!NOTE]
> Estas cuentas principales y nombres de cuentas principales son solo sugerencias. Le recomendamos que trabaje con su contador para determinar la mejor configuración para sus necesidades comerciales.


| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | P/F | Seguir | Description |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Coste de unidades, entregadas | 140100</br>140101 | Inventario de materiales</br>Materiales enviados, no facturados | Activo | Crédito | Sí | C | Coste de unidades, facturadas | Se utiliza cuando se registra un albarán de pedido de ventas. La compensación a la cuenta es el Costo de los bienes vendidos, entregados. El importe registrado en esta cuenta se revierte cuando se registra una factura de pedido de ventas. Es posible que desee utilizar una cuenta de materiales enviados no facturados para representar el inventario físico y reservar la cuenta de inventario de materiales para la actualización financiera. |
| Coste de bienes vendidos, entregados | 500150 | COGS diferido | Gasto | Débito | Sí | C  | Se utiliza cuando se registra un albarán de pedido de ventas. La compensación a la cuenta es el Costo de unidades, entregados. El importe registrado en esta cuenta se revierte cuando se registra una factura de pedido de ventas. |
| Coste de unidades, facturadas | 140100 | Inventario de materiales | Activo | Crédito | No | V | Coste de unidades, entregadas | Se utiliza cuando se registra una factura de pedido de ventas. La compensación a esta cuenta es el Costo de los bienes vendidos, facturados. Esta cuenta representa el inventario en su hoja de balance. |
| Coste de bienes vendidos, facturados | 500100 | Materiales COGS | Gasto | Débito | No | V  | Se utiliza cuando se registra una factura de pedido de ventas. La compensación a esta cuenta es el Costo de unidades, facturadas. Esta cuenta representa el COGS en su declaración P&amp;L. |
| Ingresos (ingresos de pedidos de ventas*) | 400100 | Materiales de ingresos | Ingresos | Crédito | No | V   | Se utiliza cuando se registra una factura de pedido de ventas. La contrapartida de esta cuenta es la cuenta Resumen (saldo del cliente*) en el **Perfil de contabilización de cuentas por cobrar**. |
| Comisión (Venas, comisión*) | 602150 | Gasto por comisión | Gasto | Débito | No | V  | Se usa cuando la comisión está habilitada y calculada para una venta y registrada durante el proceso de factura de la orden de venta. La contrapartida a esta cuenta es la Comisión a pagar. |
| Compensación de comisiones (Ventas, compensación de comisiones*) | 201110 | Comisiones por pagar | Pasivo | Crédito | Sí | V | Se usa cuando la comisión está habilitada y calculada para una venta y registrada durante el proceso de factura de la orden de venta. La contrapartida a esta cuenta es los gastos de comisión. |
| Ingresos diferidos en la entrega (Ventas - ingresos de albaranes*) | 401400 | Ventas acumuladas | Ingresos | Crédito | Sí | C  | Se usa cuando Ingresos diferidos para entrega está habilitado y se registra cuando procesa un albarán de pedido de ventas. La cuenta de contrapartida de esta cuenta es la compensación de ingresos diferidos. Los importes de esta cuenta se invierten automáticamente cuando registra la factura del pedido de venta. |
| Compensación de ingresos diferidos en la entrega (Ventas - compensación de ingresos de albaranes)* | 130400 | Clientes- No facturado | Activo | Débito | Sí | C  | Se usa cuando Ingresos diferidos para entrega está habilitado y se registra cuando procesa un albarán de pedido de ventas. La cuenta de contrapartida de esta cuenta son los ingresos diferidos en la entrega. Los importes de esta cuenta se invierten automáticamente cuando registra la factura del pedido de venta. |
| Impuestos sobre ventas diferidas en la entrega (Ventas, impuestos de albaranes*) | 250500 | Impuestos de ventas diferidas | Pasivo | Crédito | Sí | C  | Se usa cuando Ingresos diferidos para entrega está habilitado y Publicar impuesto sobre las ventas físicas está habilitado. El importe del impuesto se registra cuando procesa un albarán de pedido de ventas. |

\*Los valores que se muestran entre paréntesis en esta tabla representan el valor que se usa en el campo **Tipo de publicación** en la página **Transacciones de cupones**. Puede ver el **tipo de registro** en la página **Transacciones de asiento** en la pestaña **General**.

## <a name="sales-category-posting"></a>Registro de categoría de ventas

Como alternativa a la configuración del registro de inventario para todos los artículos, un grupo de artículos o un solo artículo, puede configurar categorías y controlar el registro contable por categorías de ventas. Para obtener más información sobre cómo configurar una jerarquía de categorías y asignar categorías a los productos, vaya a [Crear una jerarquía de clasificación de productos](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) y [Clasificar un producto utilizando jerarquías de categorías](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

Después de crear una jerarquía de categorías, debe asignar la jerarquía a uno o más tipos. Para usar una jerarquía de categorías en pedidos de ventas, debe asignar la categoría al tipo de jerarquía de categorías Ventas. Para obtener más información, vaya a [Acerca de jerarquías de categoría](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Crear registros de ingresos por categoría de ventas

Para asignar registros contables para un pedido de ventas en función de una categoría de ventas, siga estos pasos:

1. Vaya a **Gestión de inventarios** > **Configurar** > **Registro** > **Registro**.
2. Seleccione la pestaña **Ventas**.
3. Seleccione el botón de opción para el tipo de publicación que desea configurar (por ejemplo, **Ingresos**).
4. Seleccione **Nuevo**.
5. En el campo **Código de artículo**, seleccione **Categoría**.
6. Use el campo **Relación de categoría** para seleccionar la categoría del perfil de registro.
7. En el campo **Código de cuenta**, seleccione una opción para **Tabla**, **Grupo** o **Todos**. Por ejemplo, para aplicar el perfil de contabilización a todos los clientes, seleccione **Todos**.
   - Si seleccionó **Tabla** en el paso 6, seleccione el **Numero de vendedor** específico para el perfil de publicación en el campo **Relación de cuenta**.
   - Si seleccionó **Grupo** en el paso 6, seleccione el **Grupo de vendedores** específico para el perfil de publicación en el campo **Relación de cuenta**.
   - Si seleccionó **Todos** en el paso 6, el campo **Relación de cuenta** se dejará en blanco.

8. Para asociar un grupo de impuestos concreto que tiene el tipo de registro seleccionado, seleccione un **Grupo de impuestos de ventas**. Si este campo se deja en blanco, el tipo de registro se aplica a todos los grupos impositivos existentes. El registro que se especifica para los grupos impositivos se aplica sólo a las transacciones que se realizan para compras y ventas.

9. En el campo **Cuenta principal**, especifique el número de cuenta para contabilizar el tipo de cuenta. Seleccionar uno de los números de cuenta existentes en el plan contable.
