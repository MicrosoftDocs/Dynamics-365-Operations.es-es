---
title: Configurar liquidación
description: Cómo y cuándo se liquidan las transacciones puede ser temas complejos, lo que es fundamental que entienda y defina correctamente los parámetros para satisfacer sus requisitos empresariales. Este tema describe los parámetros que se usan para la liquidación tanto para Proveedores como Clientes.
author: kweekley
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 094b8876b3b10b6dcbc0ce399a1a9915271459ed
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188381"
---
# <a name="configure-settlement"></a>Configurar liquidación

[!include [banner](../includes/banner.md)]

Cómo y cuándo se liquidan las transacciones puede ser temas complejos, lo que es fundamental que entienda y defina correctamente los parámetros para satisfacer sus requisitos empresariales. Este tema describe los parámetros que se usan para la liquidación tanto para Proveedores como Clientes. 

Los siguientes parámetros afectan al procesamiento de las liquidaciones en Microsoft Dynamics 365 Finance. La liquidación es el proceso de liquidar una factura con un pago o una nota de abono. Estos parámetros se encuentran en el área **Liquidación** de las páginas **Parámetros de clientes** y **Parámetros de proveedores**.

- **Liquidación automática**: establezca esta opción en **Sí** si se debe liquidar una transacción automáticamente con otras transacciones abiertas cuando se registre. Si esta opción se establece en **No**, los usuarios pueden liquidar transacciones manualmente al especificar pagos, o más adelante, mediante la página **Liquidar transacciones**.
- **Administración del descuento por pronto pago**: especifique cómo [se controla un descuento por pronto pago cuando se sobrepaga una factura](cash-discount-handling-overpayments.md). Para un sobrepago, el descuento por pronto pago se puede reducir, se puede tratar como diferencia o puede quedar a cuenta para el proveedor o el cliente.
  -   **No específico**: el importe del descuento por pronto pago se reduce por el importe del sobrepago. Este funcionamiento se usa siempre, independientemente de si el importe del sobrepago es superior o inferior al importe que se especifica en el campo **Máximo de sobrepago/pago insuficiente**.
  -   **Específico**: el importe del sobrepago se registra en una cuenta contable de diferencia de descuento por pronto pago o permanece como saldo en la cuenta del cliente o del proveedor. El funcionamiento específico depende de si el importe del sobrepago se encuentra entre 0,00 y el importe especificado en el campo **Sobrepago o pago insuficiente máximo**, o si el importe del sobrepago es superior al importe de **Sobrepago o pago insuficiente máximo**.
- **Diferencia máxima de decimales**: especifique la diferencia máxima de decimales permitida para las transacciones liquidadas. Si la diferencia es igual o menor que la diferencia de decimales especificada en este campo, la diferencia se registrará en la cuenta contable de diferencia de decimales que se especifica en la página **Cuentas para transacciones automáticas**.
- **Máximo de sobrepago/pago insuficiente**: especifique el importe que se acepta para el sobrepago o pago insuficiente. Para calcular los impuestos sobre pagos insuficientes o sobrepagos, en la página **Parámetros de Contabilidad general**, haga clic en **Impuestos** y, a continuación, seleccione la opción **Impuestos de sobrepago/pago insuficiente**.
  -   Si el sobrepago o el pago insuficiente produce una diferencia menor que la diferencia definida en el campo **Diferencia máxima de decimales**, la diferencia de decimales se registra en la cuenta de diferencias de pago.
  -   Si el sobrepago o el pago insuficiente produce una diferencia de decimales mayor que la diferencia definida en el campo **Diferencia máxima de decimales**, el importe de la diferencia se registra en la cuenta de diferencia seleccionada para el tipo de registro **Descuento por pronto pago del cliente** o el tipo de registro **Descuento por pronto pago del proveedor** de la página **Cuentas para transacciones automáticas**.
- **Calcular descuento por pronto pago para pagos parciales**: establezca esta opción en **Sí** para permitir que los descuentos por pronto pago se calculen automáticamente para pagos parciales.
  -   El efecto de esta opción depende del valor del campo **Utilizar descuento por pronto pago** en la página **Liquidar transacciones**. Si esta opción se establece en **Sí**, el descuento se toma cuando el campo **Utilizar descuento por pronto pago** se establece en **Normal**. Cuando el campo **Utilizar descuento por pronto pago** se establece en **Siempre**, siempre se obtiene el descuento por pronto pago, independientemente de la configuración de este campo. Cuando el campo **Utilizar descuento por pronto pago** se establece en **Nunca**, nunca se obtiene el descuento por pronto pago, independientemente de la configuración de este campo.
  -   Si esta opción se establece en **Sí**, y un usuario cambia el valor del campo **Importe para liquidar** en la página **Liquidar transacciones**, el descuento se calcula automáticamente y se muestra como entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar**.
  -   Si esta opción se establece en **No**, y un usuario cambia el valor del campo **Importe para liquidar** en la página **Liquidar transacciones**, la entrada predeterminada del campo **Importe de descuento por pronto pago para aplicar** es **0** (cero).
- **Calcular descuentos por pronto pago para notas de abono**: establezca esta opción en **Sí** para calcular automáticamente un descuento por pronto pago para notas de abono. En Clientes, una transacción de nota de abono es una transacción negativa que tiene un valor en el campo **Factura** de la página **Factura de servicios** o una devolución en la página **Pedido de ventas**.
  - El efecto de esta opción depende del valor del campo <strong>Utilizar descuento por pronto pago</strong> en la página <strong>Liquidar transacciones</strong>. Si esta opción se establece en <strong>Sí</strong>, el descuento se toma cuando el campo *<strong><em>Utilizar descuento por pronto pago</em></strong>* se establece en <strong>Normal</strong>. Cuando el campo *<strong><em>Utilizar descuento por pronto pago</em></strong>* se establece en <strong>Siempre</strong>, siempre se obtiene el descuento por pronto pago, independientemente de la configuración de este campo. Cuando el campo *<strong><em>Utilizar descuento por pronto pago</em></strong>* se establece en <strong>Nunca</strong>, nunca se obtiene el descuento por pronto pago, independientemente de la configuración de este campo.
  - Si esta opción se establece en **Sí**, y se marca una nota de abono en la página **Liquidar transacciones**, el descuento se calcula automáticamente y se muestra como entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar**.
  - Si esta opción se establece en **No**, y se marca una nota de abono en la página **Liquidar transacciones**, la entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar** es **0** (cero).

- **Cuentas de contrapartida para descuentos (solo Proveedores)**: defina la cuenta contable de descuento por pronto pago predeterminada que se debe usar para el asiento contable para descuentos por pronto pago.
  -   **Usar cuenta principal para descuentos de proveedor**: el descuento por pronto pago se registra en la cuenta principal definida en la página **Configuración de descuento por pronto pago**.
  -   **Cuentas en las líneas de factura**: el descuento por pronto pago se registra en las cuentas contables en la factura original.
- **Marcar líneas en notas de interés y facturas de servicios (solo Proveedores)**: establezca esta opción en **Sí** para habilitar el botón **Marcar líneas de factura** de las páginas **Introducir pagos de cliente**, **Asiento del diario de pagos** y **Liquidar transacciones**. Este botón le permite a los usuarios marcar líneas individuales para la liquidación.
- **Priorizar liquidación (solo Proveedores)**: establezca esta opción en **Sí** para habilitar el botón **Marcar por prioridad** en las páginas **Introducir pagos de cliente** y **Liquidar transacciones**. Este botón permite a los usuarios asignar el orden de liquidación predeterminado a las transacciones.  Después de que el pedido de liquidación se haya aplicado a una transacción, el pedido y la asignación de pago se puede modificar antes del registro.
- **Use la prioridad para las liquidaciones automáticas**: establezca esta opción en **Sí** para usar el orden de prioridad definido cuando las transacciones se liquidan automáticamente. Este campo sólo está disponible si **Priorizar liquidación** y **Liquidación automática** se establecen en **Sí**.

## <a name="fixed-dimensions-on-accounts-receivableaccounts-payable-main-accounts"></a>Dimensiones fijas en cuentas principales de clientes/proveedores

Cuando las dimensiones fijas se utilizan en la cuenta principal de clientes/proveedores, las entradas adicionales contables y dos transacciones de proveedor adicionales se enviarán por el proceso de liquidación. La liquidación compara la cuenta contable de clientes/proveedores de la factura y el pago.  Una vez que se completan conjuntamente el pago y la liquidación, que es el escenario típico, el asiento contable del pago no se registra en la contabilidad general hasta después de que se complete también el proceso de liquidación. Debido al orden de los eventos de procesamiento, la liquidación no puede determinar la cuenta contable real de clientes/proveedores del asiento contable del pago. La liquidación reconstruye cuál será la cuenta contable para el pago. Esto se convierte en un problema cuando se emplea una dimensión fija para la cuenta principal de clientes/proveedores.

Para reconstruir la cuenta contable, la cuenta principal de clientes/proveedores se recupera del perfil de registro y las dimensiones financieras se recuperan del registro de transacciones del proveedor para el pago, como se define en el diario de pagos. Las dimensiones fijas no se establecen de manera predeterminada en los diarios de pago, sino que por el contrario se aplican a la cuenta principal como el último paso del proceso de registro. Como consecuencia, es probable que el valor de la dimensión fija no esté contenido en la transacción del proveedor, salvo que se establezca de manera predeterminada desde otro origen, como el proveedor. La cuenta reconstruida no incluirá la dimensión fija. El procesamiento de la liquidación determinará que debe crearse un asiento de ajuste, ya que la factura registrada con el valor de la dimensión fija y la cuenta de pago reconstruida no lo harán.  A medida que la liquidación continúa con el registro del asiento de ajuste, el último paso en el registro es que se aplique la dimensión fija. Al agregar la dimensión fija al asiento de ajuste, se registra con un débito y un crédito en la misma cuenta contable. La liquidación no puede revertir el asiento contable.

Para evitar los asientos contables adicionales, el débito y el crédito en la misma cuenta contable, deben considerarse las siguientes soluciones en función de sus requisitos empresariales. 

-   Las organizaciones suelen usar dimensiones fijas para rellenar de ceros una dimensión financiera que no es necesaria. Este es habitualmente el caso para cuentas de balance de situación, como clientes/proveedores. Las estructuras contables se pueden utilizar para no realizar un seguimiento de las dimensiones financieras que suelen rellenarse de ceros.  Puede quitar la dimensión financiera para las cuentas de balance de situación eliminando la necesidad de usar dimensiones fijas.
-   Si su organización requiere dimensiones fijas en la cuenta principal de clientes/proveedores, encuentre una forma de establecer de manera predeterminada la dimensión fija en el pago, de manera que se el valor de la dimensión fija se almacene en la transacción de proveedor para el pago. Esto permitirá al sistema reconstruir la cuenta principal de clientes/proveedores para incluir los valores de la dimensión fija. El valor de la dimensión fija se puede definir como predeterminado en los proveedores o en el nombre del diario para el diario de pagos.
