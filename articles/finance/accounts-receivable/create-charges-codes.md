---
title: Crear códigos de gastos
description: Este tema explica cómo configurar códigos de cargos para Proveedores y Clientes.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 034be190890a67fd0921d40fffdc704b9d6d5df7
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014075"
---
# <a name="create-charges-codes"></a>Crear códigos de gastos

Este tema explica cómo configurar códigos de cargos para Proveedores y Clientes. Si su organización requiere que se realice un seguimiento de los importes de las ventas o de las compras, además de las partidas en un pedido de ventas o de compra, puede utilizar códigos de cargo para este fin. Por ejemplo, es posible que pague flete y seguro en un pedido de compra, y estos importes se detallen por separado en el pedido de compra. En este caso, puede especificar si estos importes se registran en las cuentas de gastos o si se añaden al coste de los artículos.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Configurar códigos de cargos para clientes

Para crear códigos de cargos para Clientes, siga estos pasos.

1. Vaya a **Clientes** &gt; **Configuración de cargos** &gt; **Código de gastos**.
2. Seleccione **Nuevo**.
3. En el campo **Código de cargos**, escriba un código para el cargo.
3. En el campo **Descripción**, introduzca una descripción del cargo.
4. Opcional: en el campo **Grupos de impuestos de artículos**, seleccione un grupo de impuestos.
5. En la ficha desplegable **Registro**, especifique si se va a abonar y a adeudar automáticamente el cargo.
6. Si ha seleccionado **Cuenta contable** como tipo de débito o crédito, especifique un tipo de registro en los campos **Registro**, además de la cuenta principal en los campos **Cuenta**.

### <a name="example"></a>Ejemplo

El cliente paga el cargo. Por lo tanto, el cargo se agrega a los totales del pedido de ventas. Debe configurar la siguiente información de registro:

- En el campo **Tipo** en la sección **Débito**, seleccione **Cliente/Proveedor** para agregar el cargo de la factura a la cuenta del cliente.
- En el campo **Tipo** en la sección **Crédito**, seleccione **Cuenta contable**. A continuación, en el campo **Cuenta**, seleccione la cuenta principal para los ingresos de cargos de la factura.

> [!NOTE]
> Si el tipo de débito o tipo de crédito para el código seleccionado es **Cuenta contable** o **Artículo**, puede introducir una divisa diferente para la transacción del cargo.

Puede imprimir el texto de cargos en el idioma asignado al cliente. Para especificar el texto para el código de los cargos en otros idiomas, seleccione **Traducciones**.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Configurar códigos de cargos para proveedores

Para crear códigos de cargos para Proveedores, siga estos pasos.

1. Siga uno de estos pasos:

    - Vaya a **Proveedores** &gt; **Configuración** **de cargos** &gt; **Código de gastos**.
    - Vaya a **Adquisiciones y abastecimiento** &gt; **Configuración** &gt; **Cargos** &gt; **Código de cargos**.

2. Seleccione **Nuevo**.
3. En el campo **Código de cargos**, escriba un código para el cargo.
3. En el campo **Descripción**, introduzca una descripción del cargo.
4. Opcional: en el campo **Grupos de impuestos de artículos**, seleccione un grupo de impuestos.
5. Opcional: en el campo **Importe máximo**, escriba el importe máximo de cancelación permitido para el código de gastos.

    Este campo se usa para validar los cargos para facturas de proveedor. Para habilitar la validación de cargos, seleccione la casilla **Habilitar validación de conciliación de facturas** en la pestaña **Validación de facturas** de la página **Parámetros de proveedores**.

    > [!IMPORTANT]
    > Para validar los cargos para las facturas, también deberá crear una instancia de un tipo de regla de directivas basadas en los cargos de la directiva de factura de proveedor específica.

6. En la ficha desplegable **Registro**, especifique si se va a abonar y a adeudar automáticamente el cargo.
7. Si ha seleccionado **Cuenta contable** como tipo de débito o crédito, especifique un tipo de registro en los campos **Registro del débito** y **Registro el crédito**, además de la cuenta principal en los campos **Cuenta de débito** y **cuenta de crédito**.
8. Para permitir la comparación de los valores de cargos de una factura que incluye cargos en la cabecera o líneas correspondientes del pedido de compra, seleccione la casilla **Comparar pedido de compra y valores de factura**.

### <a name="example"></a>Ejemplo

Puede registrar el cargo como gasto como parte del total del pedido de compra o la factura de proveedor. Siga estos pasos para configurar la información de registro. 

- En el campo **Tipo** en la sección **Crédito**, seleccione **Cliente/Proveedor** para agregar el cargo de la factura a la cuenta del proveedor.
- En el campo **Tipo** en la sección **Débito**, seleccione **Cuenta contable**. A continuación, en el campo **Cuenta**, seleccione la cuenta principal para los gastos de cargos de la factura.

Siga estos pasos para configurar la información de registro para que el cargo por unidad se agregue al coste del artículo.

- En el campo **Tipo** en la sección **Crédito**, seleccione **Cliente/Proveedor** para agregar el cargo de la factura a la cuenta del proveedor.
- En el campo **Tipo** de la sección **Débito**, seleccione **Artículo** para agregar el cargo al coste del artículo.

> [!NOTE]
> Se recomienda que use una divisa diferente de la divisa que se especifica en el pedido de compra o la factura. Puede introducir una divisa diferente si el tipo de débito o crédito para el código de gastos seleccionado es **Cuenta contable** o **Artículo**.

Puede imprimir el texto de cargos en el idioma asignado al cliente. Para especificar el texto para el código de los cargos en otros idiomas, seleccione **Traducciones**.
