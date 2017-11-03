---
title: "Configurar liquidación"
description: "Cómo y cuándo se liquidan las transacciones puede ser temas complejos, lo que es fundamental que entienda y defina correctamente los parámetros para satisfacer sus requisitos empresariales. Este artículo describe los parámetros que se usan para la liquidación tanto para Proveedores como Clientes."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ade348540a6d3e9210321d3661e97ac716efaf58
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="configure-settlement"></a>Configurar liquidación

[!include[banner](../includes/banner.md)]


Cómo y cuándo se liquidan las transacciones puede ser temas complejos, lo que es fundamental que entienda y defina correctamente los parámetros para satisfacer sus requisitos empresariales. Este artículo describe los parámetros que se usan para la liquidación tanto para Proveedores como Clientes. 

Los siguientes parámetros afectan al procesamiento de las liquidaciones en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. La liquidación es el proceso de liquidar una factura con un pago o una nota de abono. Estos parámetros se encuentran en el área **Liquidación** de las páginas **Parámetros de clientes** y **Parámetros de proveedores**.

-   **Liquidación automática**: establezca esta opción en **Sí** si se debe liquidar una transacción automáticamente con otras transacciones abiertas cuando se registre. Si esta opción se establece en **No**, los usuarios pueden liquidar transacciones manualmente al especificar pagos, o más adelante, mediante la página **Liquidar transacciones**.
-   **Administración del descuento por pronto pago**: especifique cómo [se controla un descuento por pronto pago cuando se sobrepaga una factura](cash-discount-handling-overpayments.md). Para un sobrepago, el descuento por pronto pago se puede reducir, se puede tratar como diferencia o puede quedar a cuenta para el proveedor o el cliente.
    -   **No específico**: el importe del descuento por pronto pago se reduce por el importe del sobrepago. Este funcionamiento se usa siempre, independientemente de si el importe del sobrepago es superior o inferior al importe que se especifica en el campo **Máximo de sobrepago/pago insuficiente**.
    -   **Específico**: el importe del sobrepago se registra en una cuenta contable de diferencia de descuento por pronto pago o permanece como saldo en la cuenta del cliente o del proveedor. El funcionamiento específico depende de si el importe del sobrepago se encuentra entre 0,00 y el importe especificado en el campo **Sobrepago o pago insuficiente máximo**, o si el importe del sobrepago es superior al importe de **Sobrepago o pago insuficiente máximo**.
-   **Diferencia máxima de decimales**: especifique la diferencia máxima de decimales permitida para las transacciones liquidadas. Si la diferencia es igual o menor que la diferencia de decimales especificada en este campo, la diferencia se registrará en la cuenta contable de diferencia de decimales que se especifica en la página **Cuentas para transacciones automáticas**.
-   **Máximo de sobrepago/pago insuficiente**: especifique el importe que se acepta para el sobrepago o pago insuficiente. Para calcular los impuestos sobre pagos insuficientes o sobrepagos, en la página **Parámetros de Contabilidad general**, haga clic en **Impuestos** y, a continuación, seleccione la opción **Impuestos de sobrepago/pago insuficiente**.
    -   Si el sobrepago o el pago insuficiente produce una diferencia menor que la diferencia definida en el campo **Diferencia máxima de decimales**, la diferencia de decimales se registra en la cuenta de diferencias de pago.
    -   Si el sobrepago o el pago insuficiente produce una diferencia de decimales mayor que la diferencia definida en el campo **Diferencia máxima de decimales**, el importe de la diferencia se registra en la cuenta de diferencia seleccionada para el tipo de registro **Descuento por pronto pago del cliente** o el tipo de registro **Descuento por pronto pago del proveedor** de la página **Cuentas para transacciones automáticas**.
-   **Calcular descuento por pronto pago para pagos parciales**: establezca esta opción en **Sí** para permitir que los descuentos por pronto pago se calculen automáticamente para pagos parciales.
    -   Este efecto de esta opción depende del valor del campo **Utilizar descuento por pronto pago** en la página **Liquidar transacciones**. Si esta opción se establece en **Sí**, el descuento se toma cuando el campo **Utilizar descuento por pronto pago** se establece en **Normal**. Cuando el campo **Utilizar descuento por pronto pago** se establece en **Siempre**, siempre se obtiene el descuento por pronto pago, independientemente de la configuración de este campo. Cuando el campo **Utilizar descuento por pronto pago** se establece en **Nunca**, nunca se obtiene el descuento por pronto pago, independientemente de la configuración de este campo.
    -   Si esta opción se establece en **Sí**, y un usuario cambia el valor del campo **Importe para liquidar** en la página **Liquidar transacciones**, el descuento se calcula automáticamente y se muestra como entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar**.
    -   Si esta opción se establece en **No**, y un usuario cambia el valor del campo **Importe para liquidar** en la página **Liquidar transacciones**, la entrada predeterminada del campo **Importe de descuento por pronto pago para aplicar** es **0** (cero).
-   **Calcular descuentos por pronto pago para notas de abono**: establezca esta opción en **Sí** para calcular automáticamente un descuento por pronto pago para notas de abono. En Clientes, una transacción de nota de abono es una transacción negativa que tiene un valor en el campo **Factura** de la página **Factura de servicios** o una devolución en la página **Pedido de ventas**.
    -   El efecto de esta opción depende del valor del campo **Utilizar descuento por pronto pago** en la página **Liquidar transacciones**. Si esta opción se establece en **Sí**, el descuento se toma cuando el campo ****Utilizar descuento por pronto pago**** se establece en **Normal**. Cuando el campo ****Utilizar descuento por pronto pago**** se establece en **Siempre**, siempre se obtiene el descuento por pronto pago, independientemente de la configuración de este campo. Cuando el campo ****Utilizar descuento por pronto pago**** se establece en **Nunca**, nunca se obtiene el descuento por pronto pago, independientemente de la configuración de este campo.
    -   Si esta opción se establece en **Sí**, y se marca una nota de abono en la página **Liquidar transacciones**, el descuento se calcula automáticamente y se muestra como entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar**.
    -   Si esta opción se establece en **No**, y se marca una nota de abono en la página **Liquidar transacciones**, la entrada predeterminada en el campo **Importe de descuento por pronto pago para aplicar** es **0** (cero).
-   **Cuentas de contrapartida para descuentos (solo Proveedores)**: defina la cuenta contable de descuento por pronto pago predeterminada que se debe usar para el asiento contable para descuentos por pronto pago.
    -   **Usar cuenta principal para descuentos de proveedor**: el descuento por pronto pago se registra en la cuenta principal definida en la página **Configuración de descuento por pronto pago**.
    -   **Cuentas en las líneas de factura**: el descuento por pronto pago se registra en las cuentas contables en la factura original.
-   **Marcar líneas en notas de interés y facturas de servicios (solo Proveedores)**: establezca esta opción en **Sí** para habilitar el botón **Marcar líneas de factura** de las páginas **Introducir pagos de cliente**, **Asiento del diario de pagos** y **Liquidar transacciones**. Este botón le permite a los usuarios marcar líneas individuales para la liquidación.
-   **Priorizar liquidación (solo Proveedores)**: establezca esta opción en **Sí** para habilitar el botón **Marcar por prioridad** en las páginas **Introducir pagos de cliente** y **Liquidar transacciones**. Este botón permite a los usuarios asignar el orden de liquidación predeterminado a las transacciones.  Después de que el pedido de liquidación se haya aplicado a una transacción, el pedido y la asignación de pago se puede modificar antes del registro.
-   **Use la prioridad para las liquidaciones automáticas**: establezca esta opción en **Sí** para usar el orden de prioridad definido cuando las transacciones se liquidan automáticamente. Este campo sólo está disponible si **Priorizar liquidación** y **Liquidación automática** se establecen en **Sí**.





