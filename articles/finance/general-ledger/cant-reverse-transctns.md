---
title: ¿Por qué no puedo revertir esta transacción?
description: En este tema se describen diferentes razones por las que no se pueden revertir las transacciones. También se muestran soluciones para este problema.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e18caf1dbdf8191713c17b1793f5da44cf2f182b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724540"
---
# <a name="why-cant-i-reverse-this-transaction"></a>¿Por qué no puedo revertir esta transacción?

[!include [banner](../includes/banner.md)]

En este tema se describen diferentes razones por las que no se pueden revertir las transacciones. También se muestran soluciones para este problema.

## <a name="symptom"></a>Síntoma

Las organizaciones pueden encontrarse en situaciones en las que deban revertir una transacción que han registrado. En ocasiones, el sistema les impedirá revertir estas transacciones. Este comportamiento puede plantear dos preguntas:

- ¿Por qué no puedo revertir la transacción?
- ¿Cómo afecta la función de reversión masiva a este comportamiento?

## <a name="resolution"></a>Resolución

Las transacciones deben cumplir criterios específicos para que puedan revertirse. Las secciones restantes de este tema proporcionan la validación de cada módulo. Aunque este tema se centra en las transacciones en Microsoft Dynamics 365 Finance, algunos de los conceptos y la validación se pueden aplicar a otras aplicaciones, como Dynamics 365 Supply Chain Management.

Además, el lugar donde se revierte una transacción puede afectar a si se puede revertir o no. Por ejemplo, un pago a un proveedor que se contabiliza como un cheque solo se puede revertir desde la sección **Cheques** en la página de transacción para las cuentas bancarias. No se puede revertir desde la página **Transacciones de asiento** de la contabilidad general.

Si la función **Reversión masiva de varios documentos** (también conocida como la función de reversión masiva) está activada en el espacio de trabajo de **Administración de características**, afecta a cuántas transacciones se pueden revertir y dónde se pueden revertir. Esta función ofrece dos ventajas cuando está activada:

- Para algunos tipos de transacciones, se puede seleccionar y revertir más de una transacción a la vez desde el diario desde el que se registró o desde la página **Transacciones de asiento**. Sin embargo, las transacciones individuales deben haber sido reversibles antes de que se activara la función. Antes de que se introdujera esta función, las transacciones debían revertirse de una en una.
- *Algunas* transacciones del subdiario contable se pueden revertir desde el diario (diario general) o desde la página **Transacciones de asiento**. No es necesario revertirlas desde la página del subdiario contable. Por ejemplo, un diario de facturas del proveedor solo podía revertirse antes desde la página **Transacciones del proveedor**. Sin embargo, ahora también se puede revertir desde la contabilidad general, desde el diario o desde la página **Transacciones de asiento**. En cada sección de este tema se explican los tipos de transacciones a las que no se aplica esta ventaja.

La función de reversión masiva **no** permite revertir más tipos de transacciones. Si un tipo de transacción no se podía revertir anteriormente, sigue sin poderse revertir después de activar esta función. Por ejemplo, las facturas de proveedor con pedido de compra no se pueden revertir, independientemente de si la función de reversión masiva está activada o no.

Para obtener más información sobre la función de reversión masiva, consulte [Revertir registro del diario](reverse-journal-posting.md).

## <a name="general-ledger"></a>Contabilidad General

Los ajustes de la contabilidad general solo se introducen mediante el uso de cuentas contables. Por tanto, solo actualizan la contabilidad general.

Si la función de reversión masiva está desactivada, la mayoría de los ajustes de la contabilidad general se pueden revertir individualmente desde la página **Transacciones para \<main account\>** para la contabilidad general (**LedgerTransAccount**). (El título exacto de la página varía, según la cuenta principal seleccionada). La página muestra cada transacción que se ha registrado en la cuenta principal. Normalmente se abre desde la página **Lista de saldo de comprobación** o seleccionando **Transacciones** en la página **Transacciones de asiento**.

Si la función de reversión masiva está activada, ahora se pueden revertir uno o más asientos de la contabilidad general desde la página **Transacciones de asiento** y desde el diario desde el que se registró la transacción. Las excepciones son las transacciones de revalorización de divisa extranjera, consolidación y cierre de fin de año de la contabilidad general. Esas transacciones se revierten desde las páginas desde las que se ejecutó el cierre de fin de año.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Razones por las que las transacciones no se pueden revertir

Las transacciones no se pueden revertir por las siguientes razones:

- Diario general:

    - El período fiscal está en espera o cerrado permanentemente:

        - Si la fecha de reversión se encuentra en un período fiscal que no está abierto, la transacción no se puede revertir.
        - Si la transacción admite la entrada de una fecha de reversión, la transacción aún se puede revertir cambiando la fecha de reversión a un período abierto.

    - Se ha ejecutado el proceso de cierre de fin de año:

        - La fecha contable de la transacción corresponde a un ejercicio que ha pasado por un cierre de fin de año. Aunque es posible que un período del ejercicio todavía esté abierto, la transacción no se puede revertir si se ha ejecutado el proceso de cierre de fin de año para el año fiscal. El año fiscal tiene un estado diferente al de los períodos que contiene.
        - El cierre de fin de año se puede revertir y entonces la transacción se puede revertir. Es posible que este enfoque no sea una solución. Puede ser más fácil introducir manualmente una transacción de reversión en un período abierto del ejercicio cerrado o del siguiente ejercicio, según el estado del proceso de cierre fiscal. Si se contabiliza una nueva transacción en un período abierto del ejercicio que ha pasado por el proceso de cierre de fin de año, se debe ejecutar de nuevo el cierre de fin de año.

    - La reversión de la transacción ya está en curso:

        - Si la transacción está en proceso de reversión, ese proceso debe completarse. No se puede realizar un proceso de reversión distinto. 
        - Una vez completada la reversión, se puede revertir de nuevo una transacción revertida (es decir, se puede revertir la reversión).

    - Liquidación de contabilidad:

        - Si una o varias líneas de la transacción se han liquidado en la contabilidad general utilizando la tarea periódica **Liquidaciones de contabilidad** (**Contabilidad general \> Tareas periódicas \> Liquidaciones de contabilidad**), para que el registro exista en la tabla LedgerTransSettlement, la transacción no se puede revertir.
        - La liquidación de contabilidad se puede revertir y entonces el asiento se puede revertir.

    - Empresas vinculadas:

        - Si la transacción es una transacción entre empresas vinculadas, no se puede revertir.
        - La transacción **no** es una transacción entre empresas vinculadas, pero se ha registrado en una cuenta principal "por pagar" o "por cobrar" que se definió en la página **Configuración de empresas vinculadas**.

    - Provisiones:

        - Si se revierte el asiento aprovisionado de la contabilidad general, se revertirán la entrada acumulada y todas las subtransacciones acumuladas correspondientes.
        - Las subtransacciones acumuladas individuales no se pueden revertir.

- Diario de reconocimiento de ingresos:

    - Las transacciones de reconocimiento de ingresos no se pueden revertir.
    - Cuando los ingresos se reconocen a través del diario de reconocimiento de ingresos, el asiento solo se registra en las cuentas contables. Por tanto, en páginas como **Transacciones de asiento**, las transacciones aparecen como si fueran solo asientos de la contabilidad general.

- Revalorización de divisa extranjera:

    - Las transacciones de revalorización de divisa extranjera se pueden revertir, pero solo desde la página **Revalorización de divisa extranjera** de la contabilidad general desde la que se ejecutó la revalorización.
    - La reversión solo se puede completar si se contabiliza en un período fiscal abierto.

- Consolidación:

    - Las transacciones de consolidación se pueden revertir, pero solo desde la página **Transacciones de consolidación**.
    - La reversión solo se puede completar si se contabiliza en un período fiscal abierto.

- Cierre de fin de año:

    - Las transacciones de cierre de fin de año (tanto de cierre como de apertura) se pueden revertir de estas formas:

        - Si la función de mejoras de cierre de fin de año de la contabilidad general está desactivada, seleccione la opción **Deshacer cierre anterior** en el cuadro de diálogo **Cierre de fin de año**.
        - Si la función de mejoras de cierre de fin de año de la contabilidad general está activada, seleccione los registros de empresa y del ejercicio que se crearon para el cierre de fin de año en la página **Cierre de fin de año** y, a continuación, seleccione **Revertir cierre de fin de año**.

    - Tenga en cuenta que la reversión del cierre de fin de año elimina en realidad las transacciones de cierre y apertura. Nunca se contabiliza un asiento de reversión.

## <a name="accounts-payable"></a>Proveedores

Varios tipos de transacciones actualizan el subdiario contable Proveedores. Por ejemplo, facturas de proveedores, diarios de facturas de proveedores e informes de gastos.

Si la función de reversión masiva está desactivada, las transacciones se pueden revertir individualmente desde la página **Transacciones del proveedor** para las facturas o desde la página **Cuenta bancaria** para los pagos por cheque.

Si la función de reversión masiva está activada, también se pueden revertir una o más transacciones de Proveedores desde la página **Transacciones de asiento** y desde el diario desde el que se registraron las transacciones. Sin embargo, los pagos a proveedores solo se pueden revertir desde la cuenta bancaria. Además, las transacciones del proveedor no se pueden revertir desde la página **Transacciones para \<main account\>** para la contabilidad general. Solo se pueden revertir desde la página **Transacciones de asiento**.

Tenga en cuenta que algunas transacciones no se pueden revertir. Por ejemplo, facturas de proveedor con pedido de compra y pagos electrónicos a proveedores.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Razones por las que los asientos no se pueden revertir

Los asientos no se pueden revertir por las siguientes razones:

- El período fiscal está en espera o cerrado:

    - Si la fecha de reversión se encuentra en un período fiscal que no está abierto, la transacción no se puede revertir.
    - Si la transacción admite la entrada de una fecha de reversión, la transacción aún se puede revertir cambiando la fecha de reversión a un período abierto.

- Se ha ejecutado el proceso de cierre de fin de año de la contabilidad general:

    - La fecha contable de la transacción corresponde a un ejercicio que se ha cerrado en la contabilidad general. Aunque es posible que un período del ejercicio todavía esté abierto, la transacción no se puede revertir si se ha ejecutado el proceso de cierre de fin de año para el año fiscal. El año fiscal tiene un estado diferente al de los períodos que contiene.
    - El cierre de fin de año se puede revertir y entonces la transacción se puede revertir. Es posible que este enfoque no sea una solución. Puede ser más fácil introducir manualmente una transacción de reversión en un período abierto del ejercicio cerrado o del siguiente ejercicio, según el estado del proceso de cierre fiscal. Si se contabiliza una nueva transacción en un período abierto del ejercicio que ha pasado por el proceso de cierre de fin de año, se debe ejecutar de nuevo el cierre de fin de año.

- El asiento del subdiario contable no se ha transferido a la contabilidad general:

    - Esta razón se aplica solo a las facturas de proveedor sin pedido de compra.
    - Utilice la página **Asientos del subdiario contable aún no transferidos** para transferir el asiento a la contabilidad general. Entonces, la factura de proveedor sin pedido de compra se puede revertir desde la página **Transacciones del proveedor**.

- Liquidación:

    - La transacción (como una factura o un pago) se liquida o se marca para su liquidación.

        - Puede comprobar si una transacción está liquidada o marcada para su liquidación si selecciona **Ver liquidaciones** o **Liquidación \> Historial de liquidaciones** en la página **Transacciones del proveedor**.
        - También puede revertir una liquidación desde la página **Transacciones del proveedor** (**Liquidación \> Deshacer liquidación**) si se debe debe revertir una de las transacciones.

- El asiento contiene más de una transacción de subdiario contable que se introdujo utilizando el mismo número de asiento (problema con un asiento).
- La factura no se ha aprobado:

    - Si la casilla **Aprobación** no está activada en la factura, la factura no se puede revertir.

        - En este caso, la aprobación no se refiere a las aprobaciones en el proceso de flujo de trabajo, sino a la opción **Aprobación** de la factura. Esta opción se utiliza para evitar que se pague una factura. Por lo general, se usa para las facturas del registro de facturas de proveedor.

- La transacción está en el grupo de facturas:

    - Una factura del grupo no se puede revertir directamente desde la página **Transacciones del proveedor**. En su lugar, se debe revertir mediante el proceso de cancelación en la página **Diario de aprobación de facturas**.

- La transacción tiene una factura principal que se ha corregido (localización de India).
- La transacción tiene un estado de pagaré de **Factura remesada**.
- La transacción se utiliza para una liquidación parcial de impuestos.
- La transacción contiene una cuenta de proveedor pero se revierte desde una página incorrecta, como la página **Transacciones para \<main account\>**:

    - Como sugiere esta razón, incluso aunque la función de reversiones masivas esté activada, algunas transacciones del subdiario contable solo pueden revertirse desde determinadas páginas.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transacciones que no se pueden revertir

Los siguientes tipos de transacciones no se pueden revertir:

- Revalorización de divisa extranjera:

    - A diferencia de lo que ocurre con la revalorización de divisa extranjera de la contabilidad general, la revalorización de divisa extranjera de Clientes y Proveedores no se pueden revertir. En su lugar, la revalorización debe ejecutarse de nuevo utilizando la fecha de la factura. En este caso, la revalorización utiliza el tipo de cambio de la fecha de la factura y esencialmente lleva las pérdidas o ganancias no realizadas a 0 (cero). Por tanto, el resultado es similar al resultado de revertir la revalorización anterior. Sin embargo, tenga en cuenta que el mismo importe no se revertirá si se modificó el tipo de cambio predeterminado en la factura.

- Factura de proveedor con pedido de compra:

    - Se debe crear una nota de abono para revertir la factura del proveedor. Para obtener más información sobre cómo crear una transacción de reversión, consulte [Crear un pedido de devolución de compra](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Pagaré
- Envío de exportación de carta de crédito bancario

## <a name="accounts-receivable"></a>Clientes

Varios tipos de transacciones actualizan los subdiarios contables de Clientes. Por ejemplo, facturas de clientes de pedidos de venta, facturas de clientes que se introducen a través del diario general, facturas de servicios, pagos de clientes y cancelaciones.

Si la función de reversión masiva está desactivada, las transacciones se pueden revertir individualmente desde la página **Transacciones del cliente** para las facturas o desde la página **Cuentas bancarias** para los depósitos. Para obtener información sobre cómo revertir un pago, consulte la sección [Gestión de efectivo y bancos](cant-reverse-transctns.md#cash-and-bank-management) más adelante en este tema.

Si la función de reversión masiva está activada, también se pueden revertir una o más transacciones de Clientes desde la página **Transacciones de asiento** y desde el diario desde el que se registraron. Sin embargo, los depósitos solo se pueden revertir desde la cuenta bancaria y las facturas de servicios solo se pueden revertir desde la página de origen (si la función que permite las correcciones está activada). Además, las transacciones del cliente no se pueden revertir desde la página **Transacciones para \<main account\>** para la contabilidad general. Sin embargo, se pueden revertir desde la página **Transacciones de asiento**.

Tenga en cuenta que algunas transacciones no se pueden revertir. Por ejemplo, facturas de clientes de pedido de venta y cancelaciones.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Razones por las que las transacciones no se pueden revertir

Las transacciones no se pueden revertir por las siguientes razones:

- El período fiscal está en espera o cerrado permanentemente:

    - Si la fecha de reversión se encuentra en un período fiscal que no está abierto, la transacción no se puede revertir.
    - Si la transacción admite la entrada de una fecha de reversión, la transacción aún se puede revertir cambiando la fecha de reversión a un período abierto.

- Se ha ejecutado el proceso de cierre de fin de año de la contabilidad general:

    - La fecha contable de la transacción corresponde a un ejercicio que ha pasado por un cierre de fin de año de la contabilidad general. Aunque es posible que un período del ejercicio todavía esté abierto, la transacción no se puede revertir si se ha ejecutado el proceso de cierre de fin de año para el año fiscal. El año fiscal tiene un estado diferente al de los períodos que contiene.
    - El cierre de fin de año se puede revertir y entonces la transacción se puede revertir. Es posible que este enfoque no sea una solución. Puede ser más fácil introducir manualmente una transacción de reversión en un período abierto del ejercicio cerrado o del siguiente ejercicio, según el estado del proceso de cierre fiscal. Si se contabiliza una nueva transacción en un período abierto del ejercicio que ha pasado por el proceso de cierre de fin de año, se debe ejecutar de nuevo el cierre de fin de año.

- El asiento del subdiario contable no se ha transferido a la contabilidad general:

    - Esta razón se aplica solo a las facturas de servicios.
    - Utilice la página **Asientos del subdiario contable aún no transferidos** para transferir el asiento a la contabilidad general. Entonces, la factura de servicios se puede revertir o corregir si la función de correcciones está habilitada.

- Liquidación:

    - La transacción (como una factura o un pago) se liquida o se marca para su liquidación.

        - Puede comprobar si una transacción está liquidada o marcada para su liquidación si selecciona **Ver liquidaciones** o **Liquidación \> Historial de liquidaciones** en la página **Transacciones del cliente**.
        - También puede revertir una liquidación desde la página **Transacciones del cliente** (**Liquidación \> Deshacer liquidación**) si se debe debe revertir una de las transacciones.

- La transacción contiene más de una transacción de subdiario contable que se introdujo utilizando el mismo número de asiento (problema con un asiento).
- La factura no se ha aprobado:

    - Si la casilla **Aprobación** no está activada en la factura, la factura no se puede revertir.

        - En este caso, la aprobación no se refiere a las aprobaciones en el proceso de flujo de trabajo, sino a la opción **Aprobación** de las líneas de asiento. Esta opción se utiliza para evitar que se pague una factura. Aunque esta opción se usa normalmente en Proveedores, también está disponible para facturas de Clientes introducidas a través de diarios.

- La transacción tiene una factura principal que se ha corregido (localización de India).
- La transacción contiene una cuenta de cliente pero se revierte desde una página incorrecta, como la página **Transacciones para \<main account\>**:

    - Como sugiere esta razón, incluso aunque la función de reversiones masivas esté activada, algunas transacciones del subdiario contable solo pueden revertirse desde determinadas páginas.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transacciones que no se pueden revertir

Los siguientes tipos de transacciones no se pueden revertir:

- Revalorización de divisa extranjera:

    - A diferencia de lo que ocurre con la revalorización de divisa extranjera de la contabilidad general, la revalorización de divisa extranjera de Clientes y Proveedores no se pueden revertir. En su lugar, la revalorización debe ejecutarse de nuevo utilizando la fecha de la factura. En este caso, la revalorización utiliza el tipo de cambio de la fecha de la factura y esencialmente lleva las pérdidas o ganancias no realizadas a 0 (cero). Por tanto, el resultado es similar al resultado de revertir la revalorización anterior. Sin embargo, tenga en cuenta que el mismo importe no se revertirá si se modificó el tipo de cambio predeterminado en la factura.

- Una transacción que tiene retenciones de impuestos ajustadas
- Factura de cliente de pedido de ventas:

    - Se debe crear una nota de abono o una devolución para revertir la transacción. Para obtener información sobre cómo crear la transacción de reversión, consulte [Devoluciones de ventas](../../supply-chain/warehousing/sales-returns.md).

- Letra de cambio
- Transacción de caja registradora
- Ajuste avanzado
- Nota de interés
- Carta de cobros
- Carta de crédito bancario
- Envío de exportación
- Diario de reconocimiento de ingresos:

    - Cuando reconoce los ingresos a través del diario de reconocimiento de ingresos, los asientos se registran en las cuentas contables. Por tanto, aparecen como si fueran solo entradas de contabilidad general. Estas entradas no se pueden revertir porque la programación de ingresos no se volverá a abrir para reconocer los ingresos de nuevo.

## <a name="cash-and-bank-management"></a>Gestión de efectivo y bancos

Varios tipos de transacciones actualizan el subdiario de banco a través del diario general. Por ejemplo, pagos a proveedores, pagos de clientes y transferencias bancarias.

Si la función de reversión masiva está desactivada, las transacciones se pueden revertir individualmente desde la página **Cuentas bancarias** para los cheques y depósitos o desde la página **Transacciones del cliente** para los pagos de clientes.

Si la función de reversión masiva está activada, también se pueden revertir una o más transacciones de pago desde la página **Transacciones de asiento** y desde el diario desde el que se registraron las transacciones. Sin embargo, los depósitos solo se pueden revertir desde la cuenta bancaria. Además, las transacciones bancarias no se pueden revertir desde la página **Transacciones para \<main account\>** de la contabilidad general. Sin embargo, se pueden revertir desde la página **Transacciones de asiento**.

Tenga en cuenta que algunas transacciones no se pueden revertir. Por ejemplo, los pagos electrónicos a proveedores.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Razones por las que las transacciones no se pueden revertir

Las transacciones no se pueden revertir por las siguientes razones:

- El período fiscal está en espera o cerrado permanentemente:

    - Si la fecha de reversión se encuentra en un período fiscal que no está abierto, la transacción no se puede revertir.
    - Si la transacción admite la entrada de una fecha de reversión, la transacción aún se puede revertir cambiando la fecha de reversión a un período abierto.

- Se ha ejecutado el proceso de cierre de fin de año de la contabilidad general:

    - La fecha contable de la transacción corresponde a un ejercicio que ha pasado por un cierre de fin de año de la contabilidad general. Aunque es posible que un período del ejercicio todavía esté abierto, la transacción no se puede revertir si se ha ejecutado el proceso de cierre de fin de año para el año fiscal. El año fiscal tiene un estado diferente al de los períodos que contiene.
    - El cierre de fin de año se puede revertir y entonces la transacción se puede revertir. Es posible que este enfoque no sea una solución. Puede ser más fácil introducir manualmente una transacción de reversión en un período abierto del ejercicio cerrado o del siguiente ejercicio, según el estado del proceso de cierre fiscal. Si se contabiliza una nueva transacción en un período abierto del ejercicio que ha pasado por el proceso de cierre de fin de año, se debe ejecutar de nuevo el cierre de fin de año.

- Liquidación:

    - La transacción (pago) se liquida o se marca para su liquidación.

        - Puede comprobar si una transacción está liquidada o marcada para su liquidación si selecciona **Ver liquidaciones** o **Liquidación \> Historial de liquidaciones** en la página **Transacciones del proveedor** o **Transacciones del cliente**.
        - También puede revertir una liquidación desde la página **Transacciones del proveedor** o **Transacciones del cliente** (**Liquidación \> Deshacer liquidación**) si se debe debe revertir una de las transacciones.

- La transacción contiene más de una transacción de subdiario contable que se introdujo utilizando el mismo número de asiento (problema con un asiento).
- Transacciones puente:

    - Si la transacción está relacionada con un pago puente, no se puede revertir.
    - Si el pago puente se debe revertir, primero hay que abonar el pago de la cuenta puente al banco. Entonces se puede revertir el pago, siempre y cuando cumpla los demás criterios de validación.

- La transacción contiene una cuenta bancaria, pero se revierte desde la página **Transacciones para \<main account\>** o desde un subdiario contable incorrecto, como Clientes o Proveedores:

    - Como sugiere esta razón, incluso aunque la función de reversiones masivas esté activada, algunas transacciones del subdiario contable solo pueden revertirse desde determinadas páginas.

- Revalorización de divisa extranjera del banco:

    - La revalorización de divisa extranjera del banco se puede revertir. Sin embargo, se puede impedir la reversión si completa los pasos de reversión sin seguir el orden cronológico. Por ejemplo, si ejecutó la revalorización en marzo y abril, la revalorización de marzo no se puede revertir hasta que no se revierta la revalorización de abril.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Tipos de transacciones que no se pueden revertir

Los siguientes tipos de transacciones no se pueden revertir:

- Pagos a proveedores que se realizaron como transferencias electrónicas de fondos (EFT)
- Pagarés
- Letras de cambio

## <a name="fixed-assets"></a>Activos fijos

Varios tipos de transacciones actualizan el subdiario contable de Activos fijos. Por ejemplo, adquisiciones y depreciación.

Si la función de reversión masiva está desactivada, las transacciones se pueden revertir individualmente desde la página **Transacciones del proveedor**, desde la página **Transacciones de activos fijos** o desde Arrendamiento de activos, según el tipo de transacción.

Si la función de reversión masiva está activada, también se pueden revertir una o más transacciones de activos fijos desde la página **Transacciones de asiento** en el diario desde el que se registraron las transacciones.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Razones por las que las transacciones no se pueden revertir

Las transacciones no se pueden revertir por las siguientes razones:

- El período fiscal está en espera o cerrado permanentemente:

    - Si la fecha de reversión se encuentra en un período fiscal que no está abierto, la transacción no se puede revertir.
    - Si la transacción admite la entrada de una fecha de reversión, la transacción aún se puede revertir cambiando la fecha de reversión a un período abierto.

- Se ha ejecutado el proceso de cierre de fin de año de la contabilidad general:

    - La fecha contable de la transacción corresponde a un ejercicio que se ha cerrado en la contabilidad general. Aunque es posible que un período del ejercicio todavía esté abierto, la transacción no se puede revertir si se ha ejecutado el proceso de cierre de fin de año para el año fiscal. El año fiscal tiene un estado diferente al de los períodos que contiene.
    - El cierre de fin de año se puede revertir y entonces la transacción se puede revertir. Es posible que este enfoque no sea una solución. Puede ser más fácil introducir manualmente una transacción de reversión en un período abierto del ejercicio cerrado o del siguiente ejercicio, según el estado del proceso de cierre fiscal. Si se contabiliza una nueva transacción en un período abierto del ejercicio que ha pasado por el proceso de cierre de fin de año, se debe ejecutar de nuevo el cierre de fin de año.

- Adquisiciones:

    - Si la adquisición se realizó en una factura de proveedor con pedido de compra, la reversión debe realizarse introduciendo una nota de abono de proveedor. Para obtener información sobre cómo introducir la transacción de reversión, consulte [Crear un pedido de devolución de compra](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - La adquisición se produjo en una transacción de proyecto.
    - La adquisición no se puede revertir después de que se registre la depreciación del activo. La depreciación debe revertirse antes de que se pueda revertir la adquisición.
    - Si el estado del modelo de valor o el libro de amortización de un activo fijo no está abierto, la transacción no se puede revertir.

- Cancelaciones:

    - La cancelación se realiza a través de una factura de servicios:

        - La corrección de una factura de servicios está bloqueada si contiene un activo fijo. Sin embargo, si el activo se cancela a través de un diario, la factura de servicios se puede revertir desde el registro del activo fijo.

    - Si el estado del modelo de valor o el libro de amortización de un activo fijo no está abierto, la transacción no se puede revertir.

- Depreciación:

    - La depreciación se **puede** revertir si también se registra la depreciación posterior. Sin embargo, recibirá una advertencia porque este enfoque no es una práctica recomendada.
    - Si el estado del modelo de valor o el libro de amortización de un activo fijo no está abierto, la transacción no se puede revertir.

- Existen transacciones (o transacciones de reversión) para un activo y un libro de activos específico para la fecha de transacción del asiento u otra posterior.
- La transacción contiene una cuenta de activo, pero se revierte desde la página **Transacciones para \<main account\>** o desde un subdiario contable incorrecto, como Clientes o Proveedores:

    - Como sugiere esta razón, incluso aunque la función de reversiones masivas esté activada, algunas transacciones del subdiario contable solo pueden revertirse desde determinadas páginas.
    - Si se realiza una adquisición en una factura de proveedor sin pedido de compra o en un diario de facturas de proveedor, solo se puede revertir desde la página **Transacciones del proveedor** de Proveedores.
    - Si un activo se adquiere mediante arrendamiento de activos, se puede revertir desde la página **Transacciones de pasivo** en Arrendamiento de activos.
