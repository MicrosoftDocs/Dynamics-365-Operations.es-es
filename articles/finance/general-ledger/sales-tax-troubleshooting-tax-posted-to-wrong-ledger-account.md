---
title: El impuesto se registra en la cuenta contable incorrecta en el asiento
description: Este tema proporciona información para la resolución de problemas que puede ayudar cuando los impuestos se registran en la cuenta contable incorrecta en el asiento.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6834b460d3a78e47edb2edb7a72651e8454bf0ac
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343823"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>El impuesto se registra en la cuenta contable incorrecta en el asiento

[!include [banner](../includes/banner.md)]

Durante el registro, el impuesto puede registrarse en la cuenta contable incorrecta en el asiento. Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario. Los ejemplos de este tema utilizan un pedido de ventas como documento cempresarial.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Busque el código de impuestos de la transacción de impuestos registrada incorrectamente

1. En la página **Transacciones de asientos**, seleccione la transacción con la que desea trabajar y luego seleccione **Impuesto registrado**.

    [![Botón de impuesto registrado en la página de transacciones de asientos.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Revise el valor en el campo **Código de impuestos**. En este ejemplo, es **IVA 19**.

    [![Campo de código de impuesto en la página Impuesto registrado.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Comprobar el grupo de registro del libro mayor del código de impuestos

1. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.
2. Busque y seleccione el código de impuestos y luego revise el valor en el campo **Grupo de registro del libro mayor**. En este ejemplo, es **IVA**.

    [![Campo Grupo de registro del libro mayor en la página de códigos de impuestos.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. El vaor del campo **Grupo de registro del libro mayor** es un vínculo. Para ver los detalles de la configuración del grupo, seleccione el vínculo. Alternativamente, seleccione y mantenga presionado (o haga clic con el botón derecho) en el campo y luego seleccione **Ver detalles**.

    [![Comando Ver detalles.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. En el campo **Impuesto a pagar**, verifique que el número de cuenta sea correcto, según el tipo de transacción. Si no es así, seleccione la cuenta correcta para registrar. En este ejemplo, el impuesto sobre las ventas del pedido de ventas debe contabilizarse en la cuenta de impuestos a pagar 222200.

    [![Campo Impuestos a pagar en Grupos de registro de contabilidad.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    La siguiente tabla proporciona información sobre cada campo de la página **Grupos de registro de contabilidad**.

    | Campo                  | Descripción |
    |------------------------|-------------|
    | Impuestos repercutidos      | La cuenta principal de los impuestos repercutidos que son pagaderos a la autoridad fiscal. |
    | Impuestos soportados   | La cuenta principal de impuestos soportados que se reciben de la autoridad fiscal. |
    | Gasto de IVA de importación        | La cuenta principal que se utiliza para registrar los impuestos sobre el uso deducibles que los proveedores no reclaman o informan a la autoridad fiscal como parte del impuesto sobre bienes y servicios (GST) de la Unión Europea (UE) de cobro revertido/Impuesto armonizado (HST). **IVA de importación** debe seleccionarse para el código de impuestos del grupo de impuestos que se usa en la transacción. Este campo no estará disponible si se selecciona **Aplicar reglas de tasación de impuestos** en la página **Parámetros de contabilidad general**. |
    | IVA de importación repercutido        | La cuenta principal que se utiliza para registrar los IVA de importación que se pagan a las autoridades fiscales. |
    | Cuenta de liquidación     | La cuenta principal que se utiliza para registrar el saldo neto de las cuentas contables especificadas en los campos **IVA de importación repercutido** e **Impuestos soportados**. |
    | Descuento por pronto pago del proveedor   | La cuenta principal que se usa para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro de contabilidad. |
    | Descuento en ciertos casos a clientes | La cuenta principal que se usa para registrar el descuento por pronto pago para los códigos de impuestos asociados a este grupo de registro de contabilidad. |

    Para obtener más información, consulte [Configurar los grupos de registro en el libro mayor para impuestos](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Depurar en código para comprobar las dimensiones del libro mayor

En el código, la cuenta contable está determinada por la dimensión contable del libro mayor. La dimensión contable guarda el id. de registro de una cuenta en la base de datos.

1. Para un pedido de ventas, agregue un punto de interrupción en los métodos **Tax::saveAndPost()** y **Tax::post()**. Preste atención al valor de **\_ledgerDimension**.

    [![Ejemplo de código de pedido de ventas que tiene un punto de interrupción.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    Para una orden de compra, agregue un punto de interrupción en los métodos **TaxPost::saveAndPost()** y **TaxPost::postToTaxTrans()**. Preste atención al valor de **\_ledgerDimension**.

    [![Ejemplo de código de pedido de compra que tiene un punto de interrupción.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Ejecute la siguiente consulta SQL para encontrar el valor de visualización de la cuenta en la base de datos, según el id. de registro que guarda la dimensión del libro mayor.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Valor de visualización del id. de registro.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Examine la pila de llamadas para encontrar valor asignado de **_ledgerDimension**. Por lo general, el valor es de **TmpTaxWorkTrans**. En este caso, debe agregar un punto de interrupción en **TmpTaxWorkTrans::insert()** y **TmpTaxWorkTrans::update()** para encontrar dónde se asignó el valor.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
