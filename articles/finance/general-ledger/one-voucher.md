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
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: cada62078b71dd304e90951ab0f4c1643beaa48c
ms.sourcegitcommit: bd4763cc6088e114818e80bb1c27c6521b039743
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "5107729"
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

La funcionalidad de asiento único produce problemas durante el acuerdo, el cálculo de impuestos, la inversión de transacción, la conciliación de un subdiario contable en la contabilidad general, el informe financiero, etc. (Para obtener más información acerca de problemas que pueden ocurrir durante el acuerdo, consulte, por ejemplo, [Asiento único con varios clientes o registros de proveedores](https://docs.microsoft.com/dynamics365/finance/accounts-payable/single-voucher-multiple-customer-vendor-records).) Para trabajar y notificar correctamente, estos procesos e informes requieren detalles de la transacción. Aunque algunos escenarios pudieran funcionar correctamente, según la configuración de la organización a menudo hay problemas cuando varias transacciones se introducen en un asiento.

Por ejemplo, registra el siguiente asiento múltiple.

[![Ejemplo de un asiento multilínea](./media/example.png)](./media/example.png)

A continuación, genere el informe **Gastos por proveedor** en el espacio de trabajo **Información financiera**. En este informe, los saldos de cuenta de gastos se agrupan por grupo de proveedores y el proveedor. Cuando se genera el informe, el sistema no puede determinar qué grupos de proveedores/proveedores incurrieron en el gasto de 250.00. Dado que faltan detalles de la transacción, el sistema presupone que el primer proveedor que se encuentra en el asiento incurrió la totalidad de gastos de 250,00. Por lo tanto, el gasto de 250,00, que se incluye en el saldo de la cuenta principal 600120, se muestra en ese grupo de proveedores/proveedor. Sin embargo, es muy probable que el primer proveedor del asiento no sea el proveedor correcto. Por lo tanto, el informe es probablemente incorrecto.

[![Informe de gastos por proveedor](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>El futuro de un asiento

Debido a los problemas que pueden producirse cuando se usa Un asiento, esta funcionalidad acabará quedando en desuso. Sin embargo, dado que hay espacios funcionales que dependen de esta funcionalidad, no quedará obsoleta de repente en todos los espacios. En su lugar, se utilizará la programación siguiente:

- **Versión de primavera de 2018**: esta funcionalidad se desactivó de forma predeterminada mediante el parámetro **Permitir varias transacciones en un asiento** en la pestaña **General** de la página **Parámetros de contabilidad general**. Sin embargo, puede activarla si su organización tiene un escenario que cae dentro de uno de los espacios funcionales que se mencionan más adelante en este tema.

    - Si su escenario empresarial no requiere Un asiento, le recomendamos que deje la funcionalidad desactivada. Si la utiliza aunque exista una solución alternativa, Microsoft no corregirá los "errores" en las áreas que se mencionarán más adelante en este tema.
    - Le recomendamos que deje de usar Un asiento para las integraciones, a menos que la funcionalidad sea necesaria para uno de los espacios funcionales documentados.

- **Versiones posteriores**: hay varios requisitos empresariales que solo se pueden cumplir con Un asiento. Microsoft debe asegurarse de que se puedan cumplir todos los requisitos empresariales identificados en el sistema después de que la funcionalidad quede en desuso. Por lo tanto, es probable que haya que agregar nuevas características para rellenar los vacíos funcionales. Microsoft no puede proporcionar una solución específica porque cada vacío funcional es diferente y debe evaluarse en función de los requisitos empresariales. Es probable que algunos vacíos funcionales se reemplacen con características que ayuden a cumplir los requisitos empresariales específicos. Sin embargo, se pueden llenar otros vacíos si se sigue permitiendo la entrada en un diario, como cuando se usa un asiento, pero mejorando el sistema para rastrear más detalles según sea necesario.

Una vez que se hayan cubierto todos los espacios funcionales, Microsoft comunicará que la función queda en desuso. Sin embargo, esto no entrará en vigor durante al menos un año tras la comunicación. Aunque Microsoft no puede proporcionar una estimación sobre cuándo quedará en desuso la funcionalidad de Un asiento, es probable que pasen al menos dos años antes de que se produzca. La directiva de Microsoft es dejar que transcurran al menos 12 meses entre el anuncio de la funcionalidad obsoleta y la obsolescencia real, para que los clientes y los proveedores de software independientes (ISV) tengan tiempo de prepararse para el cambio. Por ejemplo, es posible que una organización tenga que actualizar sus procesos de negocio, entidades e integraciones.

La obsolescencia de Un asiento es un cambio importante que recibirá una amplia difusión. Como parte de esa comunicación, Microsoft actualizará este tema, publicará una entrada de blog en el blog de Microsoft Dynamics 365 Finance, actualizará el tema "Características quitadas o en desuso", comunicará el cambio en las conferencias de Microsoft correspondientes, etc.

## <a name="why-use-one-voucher"></a>¿Por qué usar un asiento?

Basado en conversaciones con clientes, Microsoft ha compilado la siguiente lista de escenarios donde los clientes usan la funcionalidad de Un asiento o motivos por los que la usan. Algunos de estos requisitos empresariales se pueden cumplir solo con un asiento. Sin embargo, para muchos casos, las opciones alternativas pueden cumplir los mismos requisitos empresariales.

### <a name="scenarios-that-require-one-voucher"></a>Situaciones que requieren un asiento

Las situaciones siguientes se pueden realizar solo con la funcionalidad de asiento único. Si su organización tiene cualquiera de estos escenarios, debe habilitar la especificación de varias transacciones en un asiento modificando el valor del parámetro **Permitir varias transacciones en un asiento** en la página **Parámetros de contabilidad general**. Estas lagunas funcionales se abordarán con otras características en posteriores lanzamientos.

> [!Note]
> [Para cada uno de los siguientes escenarios el campo **Permitir varias transacciones en un asiento** se debe establecer en Sí en la pestaña desplegable **General** en la página **Parámetros de contabilidad general**].

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

> [!Note]
> Cuando especifique transacciones, asegúrese de que todas las transacciones se aplican al mismo activo fijo. El asiento no se registrará si incluye más de un activo fijo, incluso si el campo **Nuevo asiento** se establece en un número de asiento únicamente en la página **Nombres de diario** en contabilidad general. Si incluye más de un activo fijo en el asiento, aparecerá el mensaje **Solo puede haber una transacción de activo fijo por asiento** y no se podrá registrar el asiento.  

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

Este escenario se encuentra normalmente en las organizaciones en las que los clientes pueden usar varias formas de pago para pagar compras. En este escenario, la organización debe poder registrar varios pagos sin registrar y liquidarlos con la factura de cliente.

Una nueva función que se ha agregado en Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016) permite liquidar varios pagos no registrados contra una única factura. Los pagos de varios clientes ya no tienen que especificarse en un asiento único.

### <a name="import-bank-statement-transactions"></a>Importar transacciones de extracto bancario

Los bancos a menudo pagan y reciben pagos en nombre una organización y estas transacciones se registran en Finance a través de un archivo que se recibe del banco. Las organizaciones a menudo desean agrupar juntas esas transacciones mediante el número de extracto bancario en el archivo. Como cada transacción se muestra en detalle en el extracto bancario, no se requiere ninguna recapitulación en el subdiario de banco.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]