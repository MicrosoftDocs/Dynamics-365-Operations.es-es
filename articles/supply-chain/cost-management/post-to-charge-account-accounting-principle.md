---
title: Registrar para cargar el principio contable de la cuenta
description: Este tema proporciona una descripción general del principio de contabilización de la cuenta de cargo.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45dc1775c0db83faa89a7a1fa799bdd070d1b09a
ms.sourcegitcommit: 283e237d7bd2a76dd3a8ff64685b0a5f146edd25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "8721404"
---
# <a name="post-to-charge-account-accounting-principle"></a>Registrar para cargar el principio contable de la cuenta

El principio de contabilidad *Publicar en cuenta de cargo* le permite contabilizar y reconciliar más fácilmente cualquier diferencia que ocurra en el precio unitario entre una contabilización física y una contabilización financiera, costos indirectos en artículos comprados o cargos en una orden de compra. 

Dos configuraciones para códigos de cargos de Cuentas por pagar en la página **Código de cargos** (**Cuentas por pagar \> Configuración de cargos \> Código de cargos**) puede hacer que una orden de compra afecte la valoración de los activos de inventario:

- Para códigos de cargos donde el campo **Tipo de débito** se establece en *Artículo* y el campo **Tipo de crédito** se establece en *Cuenta contable*, la cuenta contable seleccionada como cuenta de absorción actúa como cuenta de variación de existencias.
- Para códigos de cargos donde el campo **Tipo de débito** se establece en *Artículo* y el campo **Tipo de crédito** se establece en *Cliente/Proveedor*, el cargo se contabilizará como costo de material y se utilizará la cuenta de variación de existencias del artículo.

## <a name="european-special-accounting-rule"></a>Norma contable especial europea

En Europa, el principio contable *Publicar en cuenta de cargo* se utiliza a menudo para incorporar una regla de contabilidad especial. Por ejemplo, uno de los siguientes métodos suele utilizarse para contabilizar los cambios de inventario:

- **Método de costo de ventas** – La configuración del perfil de contabilización de inventario estándar admite este método. El principio contable *publicar en cuenta de cargo* no se requiere principio de contabilidad.
- **Naturaleza del método de gastos** – Las organizaciones más pequeñas suelen utilizar este método. Por lo general, implica los siguientes pasos:

    1. Los bienes o servicios se contabilizan como gastos en su totalidad en el momento de la recepción.
    2. Al final del período, se realiza un recuento cíclico.
    3. Se publica un ajuste manual de la cantidad y el valor en el inventario. (La cuenta de compensación es una cuenta de variación de existencias que compensa el gasto que se registró en el paso 1. Por lo tanto, verá la variación en el valor de las acciones solo en esta cuenta).

El principio *publicar en cuenta de cargo* le permite automatizar completamente las dos contabilizaciones. De esta forma, puede eliminar una contabilización de ajuste de cierre de período manual.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Habilitar el registro para cargar el principio contable de la cuenta

Para habilitar el principio de contabilidad *publicar en cuenta de cargo*, siga estos pasos.

1. Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.
2. En la pestaña **Factura**, en la ficha desplegable **Factura**, establezca la opción **Registrar en la cuenta de gastos del libro mayor** en *Sí*.
3. Cierre la página.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Requisitos previos y parámetros recomendados para el principio de contabilidad de cargo a cuenta

Si planea contabilizar los cargos de compra y las variaciones de existencias, se deben cumplir los siguientes requisitos previos:

- En la pestaña **Factura** de la página **Parámetros de proveedores** (**Proveedores \> Configuración \> Parámetros de proveedores**), la opción **Registrar en la cuenta de gastos del libro mayor** debe estar establecida en *Sí*.
- Sobre la página **Grupos de modelos de artículos** (**Manejo de costos \> Configuración de políticas de contabilidad de inventario \> Grupos de modelos de artículos**), todas las siguientes opciones deben establecerse en *Sí* para cada grupo de modelos relevante que contenga artículos incluidos en una orden de compra:

    - Registrar inventario físico
    - Registrar inventario financiero
    - Acumular pasivo en la recepción del producto

- Sobre la ficha **Entrega** de la página **Parámetros de adquisición y abastecimiento** (**Adquisiciones y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**), la opción **Generar cargos en la recepción del producto** debe estar configurada en *Sí*.
- Sobre la ficha **Contabilidad de inventario** de la página **Parámetros de gestión de inventario y almacén** (**Gestión del inventario \> Configuración \> Parámetros de gestión de inventario y almacén**), la opción **Registrar el albarán en el libro mayor** debe estar configurada en *Sí*.
- Sobre la ficha **Orden de compra** de la página **Destino** (**Gestión del inventario \> Configuración \> Destino \> Destino**), las cuentas principales que se aplican a cada artículo relevante deben especificarse para cada uno de los siguientes tipos de contabilización:

    - Gasto de compra, no facturado
    - Gasto de compra para el producto
    - Variación de existencias

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Escenario de ejemplo 1: cambio en el precio de costo unitario

Este escenario de ejemplo tiene los siguientes requisitos previos:

- Modelo de costeo primero en entrar, primero en salir (FIFO)

El siguiente procedimiento proporciona un ejemplo que muestra lo que sucede cuando cambia el precio de costo unitario en una orden de compra.

1. Cree un pedido de compra para una cantidad de 1 de un artículo con un precio unitario de 100,00.
2. Confirme el pedido de compra.
3. Registre la recepción de producto para el pedido de compra.
4. Valide el bono en la recepción del producto. La siguiente tabla muestra un cupón de ejemplo.

    | Tipo de registro | Cuenta principal | Nombre de la cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | ¿Físico/financiero? | Importe |
    |---|---|---|---|---|---|---|---|
    | Compra, variación de existencias | 600170 | Materiales de variación de existencias | Gasto | Crédito | No | Físico | -100,00 |
    | Coste de materiales comprados recibidos | 140100 | Inventario de materiales | Activo | Débito | Sí | Físico | 100.00 |
    | Gasto de compra, no facturado | 600180 | Recibos de material | Gasto | Débito | Sí | Físico | 100.00 |
    | Acumulación de compras | 200140 | Compras acumuladas | Pasivo | Crédito | Sí | Físico | -100,00 |

5. Registre la factura de la orden de compra que tiene un precio unitario actualizado de 110,00.
6. Valide el número de asiento en la factura. La siguiente tabla muestra un cupón de ejemplo.

    | Tipo de registro | Cuenta principal | Nombre de la cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | ¿Físico/financiero? | Importe |
    |---|---|---|---|---|---|---|---|
    | Compra, variación de existencias | 600170 | Materiales de variación de existencias | Gasto | Crédito | No | Financiero | -10,00 |
    | Coste de materiales comprados recibidos | 140100 | Inventario de materiales | Activo | Débito | Sí | Financiero | -100,00 |
    | Gasto de compra, no facturado | 600180 | Recibos de material | Gasto | Débito | Sí | Financiero | -100,00 |
    | Acumulación de compras | 200140 | Compras acumuladas | Pasivo | Crédito | Sí | Financiero | 100.00 |
    | Coste de materiales comprados facturados | 140100 | Inventario de materiales | Activo | Débito | No | Financiero | 110.00 |
    | Gasto de compra para el producto | 600180 | Recibo de materiales | Gasto | Crédito | No | Financiero | 110.00 |
    | Saldo del proveedor | 211000 | Comercio de proveedores | Pasivo | Crédito | No | Financiero | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Ejemplo 2: Cargos y costos indirectos en la orden de compra

Este escenario de ejemplo tiene los siguientes requisitos previos:

- Modelo de costeo FIFO
- **Código de cargos 1:** Partida de débito y cuenta de libro mayor de crédito por 10%
- **Código de cargos 2:** Partida de débito y cliente/proveedor de crédito por 10,00 proporcional
- **Costo indirecto:** 2,00% añadido al precio de compra

El siguiente procedimiento proporciona un ejemplo que muestra lo que sucede cuando incluye cargos y costos indirectos en una orden de compra.

1. Cree un pedido de compra para una cantidad de 1 de un artículo con un precio unitario de 100,00.
2. Agregue un código de cargos por el 10 por ciento que debita el artículo y acredita el libro mayor.
3. Agregue un código de cargos por el 10,00 que debita el artículo y acredita el cliente/proveedor.
4. Asigne los gastos a las líneas de pedidos de compra.
5. Confirme el pedido de compra.
6. Registre la recepción de producto para el pedido de compra.
7. Valide el bono en la recepción del producto. La siguiente tabla muestra un cupón de ejemplo.

    | Tipo de registro | Cuenta principal | Nombre de la cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Físico o financiero | Importe |
    |---|---|---|---|---|---|---|---|
    | Compra, variación de existencias | 600170 | Materiales de variación de existencias | Gasto | Crédito | No | Físico | -110,00 |
    | Coste indirecto estimado absorbido | 600520 | Costes indirectos absorbidos | Gasto | Crédito | Sí | Físico | -2,40 |
    | Flete de la compra | 600120 | Flete/costes de transporte | Gasto | Crédito | No | Físico | -10,00 |
    | Coste de materiales comprados recibidos | 140100 | Inventario de materiales | Activo | Débito | Sí | Físico | 122.40 |
    | Gasto de compra, no facturado | 600180 | Recibos de material | Gasto | Débito | Sí | Físico | 110.00 |
    | Acumulación de compras | 200140 | Compras acumuladas | Pasivo | Crédito | Sí | Físico | -110,00 |

8. Registrar la factura del pedido de compra.
9. Valide el número de asiento en la factura. La siguiente tabla muestra un cupón de ejemplo.

    | Tipo de registro | Cuenta principal | Nombre de la cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | ¿Físico/financiero? | Importe |
    |---|---|---|---|---|---|---|---|
    | Compra, variación de existencias | 600170 | Materiales de variación de existencias | Gasto | Crédito | No | Financiero | 0,00 |
    | Coste indirecto estimado absorbido | 600520 | Costes indirectos absorbidos | Gasto | Débito | Sí | Financiero | 2.40 |
    | Coste indirecto absorbido | 600520 | Costes indirectos absorbidos | Gasto | Débito | No | Financiero | -2,40 |
    | Coste de materiales comprados recibidos | 140100 | Inventario de materiales | Activo | Crédito | Sí | Financiero | -110,00 |
    | Gasto de compra, no facturado | 600180 | Recibos de material | Gasto | Crédito | Sí | Financiero | -110,00 |
    | Acumulación de compras | 200140 | Compras acumuladas | Pasivo | Débito | Sí | Financiero | 110.00 |
    | Coste de materiales comprados facturados | 140100 | Inventario de materiales | Activo | Débito | No | Financiero | 110.00 |
    | Gasto de compra para el producto | 600180 | Recibo de materiales | Gasto | Crédito | No | Financiero | 110.00 |
    | Saldo del proveedor | 211000 | Comercio de proveedores | Pasivo | Crédito | No | Financiero | -110,00 |
