---
title: Un asiento
description: Un asiento para diarios financieros (diario, diario de activos fijos, diario de pago del proveedor, etc.) le permite especificar varias transacciones de subcontabilidad en el contexto de un asiento único.
author: kweekley
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: 3c3873991c33347c1358dc98381c6b5f4c6ce2aa
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846907"
---
# <a name="one-voucher"></a>Un asiento

[!include [banner](../includes/banner.md)]


## <a name="what-is-one-voucher"></a>¿Qué es Un asiento?

La funcionalidad existente para los diarios financieros (diario, diario de activos fijos, diario de pago del proveedor, etc.) le permite especificar varias transacciones de subcontabilidad (cliente, proveedor, activos fijos, proyecto y banco) en el contexto de un asiento único. Microsoft se refiere a esta funcionalidad *un asiento*. Puede crear un único asiento con uno de los siguientes métodos:

- Configure el nombre de diario (**contabilidad general** \> **Configuración del diario** \> **Nombres de diario**) para que el campo **Nuevo asiento** esté establecido en **Solo un número de asiento**. Cada línea que agrega al diario ahora se incluye en el mismo asiento. Por lo tanto, el asiento se puede introducir como asiento multilínea, como una cuenta/cuenta de contrapartida en la misma línea o como una combinación.

    [![Una línea](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > La definición de Un asiento **no** incluye los casos donde los nombres de diario se configuran como **Solo un número de asiento** pero el usuario escribe un asiento que incluye solo tipos de cuenta contable. En este tema, Un asiento significa que hay un único asiento que contiene más de un proveedor, cliente, banco, activo fijo o proyecto.

- Especifique un asiento multilínea donde no haya cuenta de contrapartida.

    [![Asiento multilínea](./media/Multi-line.png)](./media/Multi-line.png)

- Introduzca un asiento en el que tanto la cuenta como la cuenta de contrapartida contengan un tipo de cuenta de subdiario contable, como **proveedor**/**proveedor**, **cliente**/**cliente**, **proveedor**/**cliente** o **banco**/**banco**.

    [![Asiento de subdiario](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problemas con un comprobante

La funcionalidad de asiento único produce problemas durante el acuerdo, el cálculo de impuestos, la inversión de transacción, la conciliación de un subdiario contable en la contabilidad general, el informe financiero, etc. (Para obtener más información acerca de problemas que pueden ocurrir durante el acuerdo, consulte, por ejemplo, [Asiento único con varios clientes o registros de proveedores](https://docs.microsoft.com/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records).) Para trabajar y notificar correctamente, estos procesos e informes requieren detalles de la transacción. Aunque algunos escenarios pudieran funcionar correctamente, según la configuración de la organización a menudo hay problemas cuando varias transacciones se introducen en un asiento.

Por ejemplo, registra el siguiente asiento múltiple.

[![Ejemplo ](./media/example.png)](./media/example.png)

A continuación, genere el informe **Gastos por proveedor** en el espacio de trabajo **Información financiera**. En este informe, los saldos de cuenta de gastos se agrupan por grupo de proveedores y el proveedor. Cuando se genera el informe, el sistema no puede determinar qué grupos de proveedores/proveedores incurrieron en el gasto de 250.00. Dado que faltan detalles de la transacción, el sistema presupone que el primer proveedor que se encuentra en el asiento incurrió la totalidad de gastos de 250,00. Por lo tanto, el gasto de 250,00, que se incluye en el saldo de la cuenta principal 600120, se muestra en ese grupo de proveedores/proveedor. Sin embargo, es muy probable que el primer proveedor del asiento no sea el proveedor correcto. Por lo tanto, el informe es probablemente incorrecto.

[![Gastos](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>El futuro de un asiento

Debido a los problemas indicados previamente, la funcionalidad de Un asiento quedará obsoleta. Sin embargo, dado que hay espacios funcionales que dependen de esta funcionalidad, la funcionalidad no quedará obsoleta de repente. En su lugar, se utilizará la programación siguiente:

- **Lanzamiento de primavera de 2018** De forma predeterminada, la funcionalidad se desactivará con el parámetro **Permitir varias transacciones en un asiento** en la pestaña **General** de la página **Parámetros de contabilidad general**. Sin embargo, puede activar la funcionalidad si su organización tiene un escenario que entra en una de las lagunas funcionales que aparecen más adelante en este tema.

    - Si los clientes tienen un escenario empresarial que no requiere Un asiento, no deberían activar la funcionalidad. Microsoft no corregirá los "errores“ en las áreas que se identificarán más adelante en este tema si esta funcionalidad se usa aunque exista otra solución.
    - Deje de usar un asiento para las integraciones en Microsoft Dynamics 365 for Finance and Operations, a menos que la funcionalidad sea necesaria para una de las lagunas funcionales.

- **Últimas versiones** Se atenderán todas las lagunas funcionales. **Una vez que se hayan atendido las lagunas funcionales y se entreguen las nuevas características, se tardará al menos un año en desactivar la funcionalidad de asiento permanentemente**, ya que los clientes y los fabricantes independientes de software (ISVs) deben tener tiempo suficiente para reaccionar a la nueva funcionalidad. Por ejemplo, es posible que tengan que actualizar sus procesos de negocio, entidades e integraciones.

> [!IMPORTANT]
> La opción **Solo un número de asiento** **no** se ha eliminado de la configuración del nombre de diario. Esta opción sigue admitiéndose cuando el asiento contiene solo tipos de cuenta contable. Los clientes deben tener cuidado al utilizar este valor porque el asiento no se registrará si usan la opción **Solo un número de asiento** pero especifican más de un cliente, proveedor, banco, activo fijo, o proyecto. Además, los clientes pueden introducir una combinación de tipos de cuenta del subdiario contable, como un pago en un asiento único que contiene los tipos de cuenta de **proveedor**/**banco**.

## <a name="why-use-one-voucher"></a>¿Por qué usar un asiento?

Basado en conversaciones con clientes, Microsoft ha compilado la siguiente lista de escenarios donde los clientes usan la funcionalidad de Un asiento o motivos por los que la usan. Algunos de estos requisitos empresariales se pueden cumplir solo con un asiento. Sin embargo, para muchos casos, las opciones alternativas pueden cumplir los mismos requisitos empresariales.

### <a name="scenarios-that-require-one-voucher"></a>Situaciones que requieren un asiento

Las situaciones siguientes se pueden realizar solo con la funcionalidad de asiento único. Si su organización tiene cualquiera de estos escenarios, debe habilitar la especificación de varias transacciones en un asiento modificando el valor del parámetro **Permitir varias transacciones en un asiento** en la página **Parámetros de contabilidad general**. Estas lagunas funcionales se abordarán con otras características en posteriores lanzamientos.

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Registrar los pagos de cliente o de proveedor en formulario resumen en una cuenta bancaria

**Escenario** Una organización comunica una lista de proveedores e importes al banco y el banco usa esta lista para pagar a los proveedores en nombre la organización. El banco registra la suma de los pagos como una sola retirada en la cuenta bancaria.

La recapitulación de pagos de proveedor se admite solo a través de un asiento. Cada proveedor se especifica en una línea independiente para mantener los detalles en el subdiario de los proveedores. Sin embargo, el importe resumido de todos los pagos se compensa en una única línea para la cuenta bancaria. Por lo tanto, la retirada se muestra como un solo importe resumido en el subdiario de banco.

**Escenario** Una organización deposita pagos de cliente o el banco deposita los pagos de cliente en nombre de la organización y el depósito se muestra como suma total en la cuenta bancaria.

La recapitulación de pagos de cliente se admite normalmente con la funcionalidad de depósito. Sin embargo, si utiliza "puente" en la forma de pago, este escenario se admite sólo a través de Un asiento. Los pagos de cliente se especifican de la misma forma que se describe para la recapitulación de pago de proveedor.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Mecanismo para agrupar transacciones de un evento de negocio

**Escenario** Una organización tiene un solo evento de negocio que activa varias transacciones. Sin embargo, el departamento de contabilidad desea ver las entradas contables de forma conjunta para una mejor auditabilidad.

Si una organización debe ver los asientos contables de un evento de negocio de forma conjunta, debe usar Un asiento. 

### <a name="country-specific-features"></a>Funciones específicas de un país o región

**Escenario** La característica de (SAD) de Documento Único Administrativo para Polonia requiere actualmente que se use un asiento único. Hasta que una opción de agrupación esté disponible para esta función, debe continuar utilizando la funcionalidad de asiento único. Puede haber características específicas del país adicionales que requieran la funcionalidad de asiento.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Diario de pagos de anticipo del cliente que tiene impuestos sobre las varias "líneas"

En esta situación, los clientes del asiento único son el mismo cliente, porque la transacción simula las líneas de un pedido de cliente. El anticipo se debe especificar en un asiento único, ya que el cálculo de impuestos se debe crear en las “líneas” del pago único que realizó el cliente.

### <a name="customer-reimbursement"></a>Reembolso al cliente

**Escenario** Un cliente realiza un anticipo para un pedido y las líneas del pedido tienen diferentes impuestos que se deben registrar para el anticipo. El anticipo de cliente es una transacción que simula las líneas de pedido, para poder registrar los impuestos adecuados para el importe de cada línea.

Si la tarea periódica de reembolso se ejecuta desde el módulo Clientes, crea una transacción para mover el saldo de un cliente a un proveedor. Para esta situación, un asiento se debe usar para el reembolso al cliente.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Mantenimiento de activos fijos: La recuperación de la depreciación, división de activos, calcula la depreciación en la cancelación
Las siguientes transacciones de activos fijos también crean varias transacciones en un asiento único:

- Se crea una adquisición adicional en un activo y se calcula la depreciación de "actualización".
- Un activo está dividido.
- Un parámetro para calcular la depreciación al cancelar se habilita y luego el activo se cancela.
- La fecha de servicio de un activo es anterior a la fecha de adquisición. Por lo tanto, se registra un ajuste de depreciación.

### <a name="bills-of-exchange-and-promissory-notes"></a> Letras de cambio y pagarés
Las letras de cambio y pagarés que requieren que se use un asiento, pues las transacciones pasan al cliente o el saldo de proveedor de una cuenta contable de clientes/proveedores a otra, en función del estado del pago.

## <a name="scenarios-that-dont-require-one-voucher"></a>Situaciones que no requieren un asiento

Las situaciones siguientes pueden ser realizadas con otros medios y no deberían usar la funcionalidad de un asiento.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Registrar los pagos de cliente en formulario resumen en la cuenta bancaria

Una organización deposita pagos de cliente o el banco deposita los pagos de cliente en nombre de la organización y el depósito se muestra como suma total en la cuenta bancaria.

La recapitulación de pagos de cliente se admite con la funcionalidad de depósito cuando no se usa el "puente" en la forma de pago.

### <a name="netting"></a>Compensación

En la red, los saldos para un proveedor y el cliente están uno junto al otro ya que el proveedor y el cliente son la misma parte. Este enfoque minimiza el intercambio de dinero entre una organización y la parte del cliente o proveedor.

El trabajo en red se logra especificando el aumento y la reducción de asientos independientes, y luego enviando la contrapartida a una cuenta contable de eliminación.

### <a name="post-in-summary-to-the-general-ledger"></a>Registrar en resumen en la contabilidad general.

Las organizaciones a menudo desean registrar en la contabilidad general en forma de resumen para minimizar la cantidad de datos. Sin embargo, esas organizaciones normalmente requieren que se mantengan los detalles de transacción. Cuando el registro se realiza en forma de resumen mediante un asiento único, no se conocen los detalles de la transacción y no se pueden mantener.

- Dado que los detalles de la transacción no se pueden mantenerse actualmente, se recomienda que la organización **no** use Un asiento para registrar de forma resumida.
- Una vez que el soporte de Un asiento se elimina, se pueden implementar los marcos del documento de origen y de contabilidad en los diarios. Estos marcos mantendrán los detalles de la transacción y admitirán el resumen en la contabilidad general.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Liquidar varios pagos no contabilizados en la misma factura

Este escenario se encuentra normalmente en las organizaciones al por menor en las que los clientes pueden usar varias formas de pago para pagar compras. En este escenario, la organización debe poder registrar varios pagos sin registrar y liquidarlos con la factura de cliente.

Una nueva función que se ha agregado en Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016) permite liquidar varios pagos no registrados contra una única factura. Los pagos de varios clientes ya no tienen que especificarse en un asiento único.

### <a name="import-bank-statement-transactions"></a>Importar transacciones de extracto bancario

Los bancos a menudo pagan y reciben pagos en nombre una organización y estas transacciones se registran en Finance and Operations a través de un archivo que se recibe del banco. Las organizaciones a menudo desean agrupar juntas esas transacciones mediante el número de extracto bancario en el archivo. Como cada transacción se muestra en detalle en el extracto bancario, no se requiere ninguna recapitulación en el subdiario de banco.

Las transacciones se pueden agrupar con otros campos del diario, como el número de lote del diario en sí o el número de documento.


### <a name="transfer-balances"></a>Transferir saldos

Una organización podría tener que transferir un saldo de un proveedor a otro proveedor, ya sea debido a un error o debido a que otro proveedor ha asumido el pasivo. Las transferencias de este tipo también se producen para los tipos de cuenta como **cliente** y **Banco**.

Las transferencias de saldo a partir de una cuenta (proveedor, cliente, banco, etc.) a otra cuenta se pueden realizar a través de los asientos independientes y la contrapartida se puede registrar en una cuenta contable de compensación.

### <a name="enter-beginning-balances"></a>Introducir saldos iniciales

Las organizaciones a menudo especifican saldos iniciales para cuentas de subcontabilidad (proveedores, clientes, activos fijos, etc.) como una transacción de asiento. Los saldos iniciales para cada cuenta de subcontabilidad se pueden especificar como asientos independientes y la contrapartida se puede registrar en una cuenta contable de compensación.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Corregir el asiento contable de un documento registrado del cliente o de proveedor

Una organización puede tener que corregir la cuenta contable de los clientes o de los proveedores para una entrada contable de una factura registrada, pero dicha factura no se puede invertir o corregir a través de otro mecanismo.

Si tiene que realizarse una corrección en la cuenta contable de clientes o de proveedores, se debe realizar un ajuste directamente en la cuenta contable. El ajuste no puede realizarse registrando a través del proveedor o el cliente. Este enfoque requiere que el ajuste se efectúe durante un "tiempo de inactividad”, de modo que la cuenta contable pueda permitir temporalmente la entrada manual.

### <a name="the-system-allows-it"></a>"El sistema lo permite"

Las organizaciones a menudo usan la funcionalidad de un asiento simplemente porque el sistema les permite utilizarla, sin comprender las implicaciones.