---
title: Conciliar cuenta bancaria
description: Este artículo describe cómo conciliar una cuenta bancaria.
author: angelad116
ms.date: 11/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: angelading
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12de50f26127c54c2f82ace43487de10e7125aea
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804246"
---
# <a name="reconcile-a-bank-account"></a>Conciliar cuenta bancaria

[!include[banner](../includes/banner.md)]

Cuando reciba un extracto bancario, deberá conciliar periódicamente las transacciones bancarias de la entidad jurídica con las transacciones del extracto bancario.

No se puede conciliar un extracto bancario con una cuenta bancaria si alguno de los pagos mediante cheque o resguardo de depósito que aparecen en el extracto tiene actualmente el estado de **Cancelación pendiente**. Después de que un revisor registre o rechace la anulación del cheque o la cancelación del pago mediante resguardo de depósito, el estado dejará de ser **Cancelación pendiente** y se podrá conciliar la cuenta bancaria.

1. Vaya a **Gestión de efectivo y de banco** \> **Cuentas bancarias** \> **Cuentas bancarias**. Seleccione la cuenta bancaria para conciliar con el extracto bancario y seleccione **Conciliar** > **Conciliación de cuentas**.

2. Especifique la información en **Fecha del extracto bancario** y **Extracto bancario**. En el campo **Saldo final**, puede especificar el saldo de la cuenta tal y como aparece en el extracto bancario.

3. Seleccione **Transacciones** para abrir la página **Conciliación de cuentas**.

4. Para cada transacción incluida en el extracto bancario, active la casilla **Compensado** si el importe de Dynamics 365 Finance se corresponde con el importe del extracto bancario. También puede especificar o modificar el valor del campo **Tipo de transacción bancaria**. El valor de este campo es importante para las estadísticas de transacciones bancarias y para algunos informes.
    

>[!NOTE]
>No seleccione la casilla de verificación **Compensado** en las transacciones que no se encuentren en el extracto bancario. Estas transacciones seguirán mostrándose en la página hasta que se concilien con un futuro extracto bancario.
>La casilla de verificación **Compensado** no está disponible si la transacción tiene un estado de **Cancelación pendiente**. Es posible que las transacciones tengan este estado si Finance está configurado para requerir que las anulaciones o cancelaciones se envíen para revisarlas antes de registrarlas. Después de que un revisor registre o rechace la anulación o cancelación, el estado dejará de ser **Cancelación pendiente** y se podrá conciliar la cuenta con el extracto bancario.


Para activar la casilla **Compensado** para un intervalo de cheques mostrados en el extracto bancario, haga clic en **Marcar intervalo de cheques** y, a continuación, indique el intervalo.

5.  Si el importe de una transacción de cuenta bancaria no se corresponde con el importe de la transacción en el extracto bancario, especifique el importe de la corrección en el campo **Importe de la corrección**.
    

> [!NOTE]
> Si el período fiscal de la transacción que se debe corregir está cerrado, no se puede utilizar el campo **Importe de la corrección**. En su lugar, cree una línea que contenga una fecha de transacción con un período fiscal abierto para la corrección. En este caso, se deberán agregar las dimensiones financieras utilizadas en la transacción original, además de la cuenta principal de contrapartida.



6.  Cree transacciones para entradas, tales como cuotas o intereses, que se encuentran en el extracto bancario, pero que no están registradas en Finance. Especifique el **Tipo de transacción bancaria** y las dimensiones financieras adecuadas.

7.  Puesto que las transacciones del extracto bancario están marcadas como **Compensado**, el importe del campo **No conciliado**, que se vuelve a calcular continuamente a medida que se realizan modificaciones, se aproxima a cero. Cuando sea cero, seleccione **Conciliar cuenta** para registrar la conciliación, las transacciones y las correcciones que se hayan creado.
    
    Una vez registrada la conciliación, las transacciones incluidas ya no se podrán modificar ni corregir y no se mostrarán en futuras conciliaciones de cuentas.

8.  Para ver las transacciones bancarias que no se hayan conciliado aún, utilice el informe **Transacciones bancarias no conciliadas**. Para ver el extracto bancario de una cuenta, utilice el informe **Extracto bancario**.

## <a name="cancel-bank-statement-reconciliation"></a>Cancelar conciliación de extracto bancario 

La funcionalidad **Cancelar conciliación de extracto bancario** permite cancelar la conciliación del extracto bancario. Para utilizar esta función, active **Cancelar conciliación de extracto bancario** en el espacio de trabajo **Administración de características**. También deberá habilitar el parámetro **Permitir edición del extracto bancario**. Para ello, vaya a **Gestión de efectivo y bancos > Configuración > Parámetros de gestión de efectivo y bancos > Conciliación bancaria**.
 
Las conciliaciones de extracto bancario se pueden cancelar únicamente en el orden cronológico en el que se especificaron. Cuando una conciliación de extracto bancario se cancela, las nuevas transacciones y correcciones se invierten y el resto de transacciones se marcan como no conciliadas.
 
Para cancelar una conciliación de extracto bancario, seleccione el extracto bancario y **Extracto bancario > Cancelar conciliación bancaria**. En la página **Cancelar conciliación bancaria**, proporcione **Código de motivo**, **Comentario del motivo**, y **Fecha de cancelación**. Seleccione **Aceptar** para iniciar la cancelación. Tenga en cuenta que la fecha de cancelación del extracto bancario debe ser igual o posterior a la fecha del extracto bancario. Una vez que la conciliación del extracto bancario se ha cancelado, el campo **Fecha de cancelación** del extracto bancario se actualiza con la **Fecha de cancelación** que ha proporcionado. Seleccione el botón **Transacciones** para ver las transacciones para las que se ha cancelado la conciliación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
