---
title: "Asiento único con varios registros de cliente o proveedor"
description: "Este tema proporciona una visión general de lo que sucede cuando se registra un documento único con varios registros del cliente o del proveedor. Esta función se cancelará en futuras versiones de Microsoft Dynamics 365 for Operations, por eso no se recomienda el uso de este método de registro debido al impacto contable en el procesamiento del acuerdo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 10b96749fd8bfaa1ae98f7f5a0fa3f7dac2d16bb
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>Asiento único con varios registros de cliente o proveedor

[!include[banner](../includes/banner.md)]


Este tema proporciona una visión general de lo que sucede cuando se registra un documento único con varios registros del cliente o del proveedor. Esta función se cancelará en futuras versiones de Microsoft Dynamics 365 for Operations, por eso no se recomienda el uso de este método de registro debido al impacto contable en el procesamiento del acuerdo. 

Algunos ejemplos comunes donde el asiento se usa para varios clientes o proveedores incluyen las transacciones de saldos entre clientes, y la compensación de saldos entre clientes y proveedores de la misma organización. 

Un asiento que contiene más de un cliente o proveedor se puede especificar mediante uno de los métodos siguientes:

-   Usando un diario que tenga la opción **Solo un número de asiento** seleccionado para que cada línea añadida al diario se incluya en el mismo asiento.
-   Usando un asiento multilínea, donde no hay cuenta contable de contrapartida, con más de un cliente o proveedor.
-   Indicando un asiento con la cuenta y la cuenta de contrapartida de proveedor/proveedor, cliente/cliente, proveedor/cliente o cliente/proveedor.

Este tema muestra cómo se procesará el acuerdo cuando se registre un asiento con varios registros de cliente o proveedor. Además, este tema proporciona soluciones para ayudarle a comprender cómo evitar el uso de un asiento con varios clientes o proveedores. En particular, hay ejemplos que muestran dos casos de acuerdo comunes que se han visto afectados por el uso de un asiento con varios clientes o proveedores:

-   Contabilidad de descento en efectivo
-   Contabilidad de revalorización

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Cómo afecta el acuerdo al uso del asiento único
Al registrar un asiento que contiene varios registros de cliente o de proveedor, se crea un solo documento contable que contiene varios saldos de cuentas de clientes o proveedores. Durante el proceso de liquidación, las entradas contables originales se usan para crear las entradas contables para el descuento por pronto pago, las pérdidas y ganancias no realizadas, las pérdidas y ganancias realizadas y la liberación del extracto de cuenta del documento original. Por ejemplo, si se obtiene un descuento por pronto pago al liquidar un pago de proveedor a una factura, la contabilidad del descuento de efectivo debe registrarse en la cuenta contable de proveedores de la factura original. Si la factura original se ha registrado en un documento que contiene registros de varios proveedores, se resume la contabilidad original. En este caso, ya que no es posible tener acceso a la entrada contable detallada de cada transacción de proveedor en el documento único, no hay manera de determinar cómo pretendía el usuario contabilizar el descuento de efectivo.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Un documento con varios proveedores y el impacto en la contabilidad del descuento de efectivo

En el siguiente ejemplo, se registran varias facturas de proveedor en la Contabilidad general en un documento único en la página **Diario general**. Estas facturas se distribuyen a través de dimensiones de varias cuentas.

|             |                  |              |                 |           |            |
|-------------|------------------|--------------|-----------------|-----------|------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta**  | **Descripción** | **Débito** | **Crédito** |
| GNJL001     | Proveedor           | 1001         | INV1            |           | 100,00     |
| GNJL001     | Proveedor           | 1001         | INV2            |           | 200,00     |
| GNJL001     | Proveedor           | 1001         | INV3            |           | 300,00     |
| GNJL001     | Contabilidad           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Contabilidad           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Contabilidad           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Contabilidad           | 606300-004-- | INV3            | 300,00    |            |

Después del registro, se crea un documento.

|             |              |                  |                                    |
|-------------|--------------|------------------|------------------------------------|
| **Asiento** | **Cuenta**  | **Tipo de registro** | **Importe en divisa de la transacción** |
| GNJL001     | 606300-001-- | Diario contable   | 50,00                              |
| GNJL001     | 606300-002-- | Diario contable   | 50,00                              |
| GNJL001     | 606300-003-- | Diario contable   | 200,00                             |
| GNJL001     | 606300-004-- | Diario contable   | 300,00                             |
| GNJL001     | 200110-001-  | Saldo del proveedor   | -100,00                            |
| GNJL001     | 200110-001-  | Saldo del proveedor   | -200,00                            |
| GNJL001     | 200110-001-  | Saldo del proveedor   | -300,00                            |

Observe que el documento contiene tres entradas del tipo de registro de saldo de proveedor en el documento único. No es posible indicar que el débito de 50,00 para 606300-001 y el débito de 50,00 para 606300-002 están pensados para compensar la entrada de saldos de proveedor 200110-001. Esto se debe a que el usuario introdujo los registros de varios proveedores en un documento único.

Mediante este ejemplo, podemos analizar el impacto que tiene el uso de un documento en la contabilidad del acuerdo de sentido descendente. Supongamos que debe pagar 197,00 de la factura de 200,00, con un descuento de 3,00. Observe que el valor de la cuenta de descuento de efectivo se asignará a todas las dimensiones de las cuentas de gastos del documento de la factura. Esto es porque se ha usado un documento para registrar la factura mencionada anteriormente, sin indicar cómo pretende el usuario correlacionar las distribuciones de gastos al saldo del proveedor en el documento único.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Asiento** | **Cuenta**  | **Tipo de registro**     | **Débito** | **Crédito** |
| APPAYM001   | 200110-001-  | Saldo del proveedor       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banco                 |           | 197.00     |
| 14000056    | 520200-001-- | Descuento por pronto pago del proveedor |           | 0.25       |
| 14000056    | 520200-002-- | Descuento por pronto pago del proveedor |           | 0.25       |
| 14000056    | 520200-003-- | Descuento por pronto pago del proveedor |           | 1,00       |
| 14000056    | 520200-004-- | Descuento por pronto pago del proveedor |           | 1.50       |
| 14000056    | 200110-001-  | Saldo del proveedor       | 3,00      |            |

Si el usuario no está satisfecho con el descuento de efectivo que se asigna a todas las distribuciones de gastos de la factura original, en lugar de un documento, debería usar varios documentos para registrar las facturas. A continuación se muestra un ejemplo de cómo se pueden especificar varios documentos en la Contabilidad general, en lugar de uno solo, como se muestra al principio de este ejemplo.

|             |                  |              |                 |           |            |                 |                    |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta**  | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| GNJL001     | Proveedor           | 1001         | INV1            |           | 100,00     | Contabilidad          | &lt;espacio en blanco&gt;      |
| GNJL001     | Contabilidad           | 606300-001-- | INV1            |   50,00   |            | Contabilidad          | &lt;espacio en blanco&gt;      |
| GNJL001     | Contabilidad           | 606300-002-- | INV1            |   50,00   |            | Contabilidad          | &lt;espacio en blanco&gt;:      |
| GNJL002     | Proveedor           | 1001         | INV2            |           | 200,00     | Contabilidad          | 606300-003--       |
| GNJL003     | Proveedor           | 1001         | INV3            |           | 300,00     | Contabilidad          | 606300-004--       |

Ahora, cuando se pague INV2, se creará la siguiente entrada. Observe que las dimensiones financieras del descuento de efectivo siguen a las dimensiones financieras de gastos asociados.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Asiento** | **Cuenta**  | **Tipo de registro**     | **Débito** | **Crédito** |
| APPAYM001   | 200110-001-  | Saldo del proveedor       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banco                 |           | 197.00     |
| 14000056    | 520200-003-- | Descuento por pronto pago del proveedor |           | 3,00       |
| 14000056    | 200110-001-  | Saldo del proveedor       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Un documento con varios proveedores y el impacto en la contabilidad de pérdidas/ganancias realizadas

|             |                  |             |                 |           |            |                  |              |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de cuenta** | **Cuenta**  |
| GNJL001     | Proveedor           | 1001        | INV1            |           | 100,00     | Contabilidad           | 606300-001-- |
| GNJL001     | Proveedor           | 1001        | INV2            |           | 200,00     | Contabilidad           | 606300-002-- |

En el siguiente ejemplo, se registran varias facturas de proveedor en la Contabilidad general en un documento único en la página **Diario general**. Estas facturas se distribuyen a través de dimensiones de varias cuentas. Después del registro, se crea un documento.

|             |              |                  |                                          |                                         |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| **Asiento** | **Cuenta**  | **Tipo de registro** | **Importe en la divisa de transacción (EUR)** | **Importe en la divisa de contabilidad (USD)** |
| GNJL001     | 606300-001-- | Diario contable   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Diario contable   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Saldo del proveedor   | -100,00                                  | -114,00                                 |
| GNJL001     | 200110-001-  | Saldo del proveedor   | -200,00                                  | -228,00                                 |

Observe que el documento contiene dos entradas del tipo de registro de saldo de Proveedor en el documento único. No es posible indicar que el débito para 606300-001 está pensando para compensar la entrada de saldos de proveedor de 100,00 a 200110-001. Esto se debe a que el usuario introdujo registros de varios proveedores en un documento único. 

Mediante este ejemplo, podemos analizar el impacto que tiene el uso de un documento en la contabilidad del acuerdo de sentido descendente. Supongamos que la divisa de contabilidad es USD y las transacciones antes mencionadas se han registrado en una divisa de la transacción de EUR. Supongamos que paga por completo la factura de 200,00 EUR pero encuentra una pérdida realizada debido a una diferencia en el tipo de cambio entre el momento en que registró la factura y el pago. Observe que el valor de la cuenta de pérdida realizada se asigna a todas las dimensiones de las cuentas de gastos del documento de la factura. En este caso, se asignó tanto la dimensión 001 como la 002, aunque la percepción del usuario sea de que solo la 002 pertenece a la cuenta de gastos de la factura que se liquida. Esto es porque se ha usado un documento para registrar la factura mencionada anteriormente, sin indicar manera alguna de cómo pretende el usuario correlacionar las distribuciones de gastos al saldo del proveedor en el documento único.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Asiento** | **Cuenta** | **Tipo de registro**   | **Importe en la divisa de transacción (EUR)** | **Importe en la divisa de contabilidad (USD)** |
| APPAYM001   | 200110-001- | Saldo del proveedor     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banco               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Pérdida en el ajuste del cambio | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Pérdida en el ajuste del cambio | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Saldo del proveedor     |                                          | -2,00                                   |

Si el usuario no está satisfecho con la pérdida de Tipo de cambio que se asigna a todas las distribuciones de gastos de la factura original, en lugar de un documento, debería usar varios documentos para registrar las facturas. A continuación se muestra un ejemplo de cómo se pueden especificar varios documentos en la Contabilidad general, en lugar de uno solo como se muestra al principio de este ejemplo.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| GNJL002     | Proveedor           | 1001        | INV1            |           | 100,00     | Contabilidad          | 606300-001--       |
| GNJL003     | Proveedor           | 1001        | INV2            |           | 200,00     | Contabilidad          | 606300-002--       |

Ahora, cuando se pague INV2, se creará la siguiente entrada. Observe que las dimensiones financieras de la pérdida de tipo de cambio siguen a las dimensiones financieras de gastos asociados.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Asiento** | **Cuenta** | **Tipo de registro**   | **Importe en la divisa de transacción (EUR)** | **Importe en la divisa de contabilidad (USD)** |
| APPAYM001   | 200110-001- | Saldo del proveedor     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banco               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Pérdida en el ajuste del cambio | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Saldo del proveedor     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Un documento para las transferencias de saldo y las situaciones de compensación
Dos situaciones de uso general que utilizan un documento que contiene varios clientes o proveedores incluyen las transferencias de saldos de un lciente/proveedor a otro cliente/proveedor, y la compensación de un cliente y un proveedor que son la misma organización. Los dos ejemplos siguientes muestran el método preferido para especificar estas situaciones en Dynamics 365 for Operations, como alternativa a incorporarlas en un documento. 

Una *transferencia de saldo* es un documento con varios clientes, inscritos con el fin de transferir el saldo de un cliente a otro cliente (lo mismo para proveedores). Esta situación puede ocurrir cuando la responsabilidad de pagar las facturas se traspasa a otra parte, como una empresa secundaria que traspasa la responsabilidad a la empresa matriz. 

En este ejemplo se presupone una venta en la que el cliente es apto para un descuento de efectivo si el pago se realiza en un plazo de 10 días. El cliente de este ejemplo usa una empresa aseguradora que será la responsable de pagar la factura. La empresa aseguradora se configura como un segundo cliente en el sistema. El saldo del cliente original se transfiere a la empresa aseguradora, que paga la factura, con un descuento por pronto pago del 2% por pagar dentro del período de descuento. 

Para mostrarlo, supongamos que se realiza la venta siguiente al cliente ACME. Las entradas contables siguientes representan la venta.

|                    |                  |           |            |
|--------------------|------------------|-----------|------------|
| **Cuenta contable** | **Tipo de registro** | **Débito** | **Crédito** |
| 401100-002-023-    | Ingresos          |           | 100        |
| 130100-002-        | Saldo del cliente | 100       |            |

A continuación, el usuario transfiere el saldo pendiente de ACME a la empresa aseguradora, en un documento del diario de pago de cuentas de clientes. En Dynamics 365 for Operations, la empresa aseguradora está configurada como un Seguro del cliente.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| ARPAYM001   | Cliente          | ACME        | Transferir        |           | 100,00     | Cliente         | Seguro          |

Observe que la entrada anterior está contenida en un documento. Este documento contiene dos registros de cliente. El siguiente documento se crea cuando se registra la entrada de Contabilidad general anterior.

|             |             |                  |                                    |
|-------------|-------------|------------------|------------------------------------|
| **Asiento** | **Cuenta** | **Tipo de registro** | **Importe en divisa de la transacción** |
| ARPAYM001   | 130100-002- | Saldo del cliente | 100,00                             |
| ARPAYM001   | 130100-002- | Saldo del cliente | -100,00                            |

A continuación, suponga que recibe un pago de 98,00 del cliente del Seguro y opta por liquidar el pago con la factura creada por la transferencia de saldo. Esto dará lugar al envío del siguiente documento. Puede que existan expectativas de que el acuerdo usa las dimensiones financieras de la factura original, pero no es posible porque no hay un documento de factura para el cliente del Seguro. Observe que de forma predeterminada, las dimensiones de distribución del descuento de efectivo proceden de la transacción del cliente creada de la transferencia, no de la cuenta de ingresos de la factura original. El valor predeterminado es el resultado de usar un documento para transferir los saldos.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Asiento** | **Cuenta** | **Tipo de registro** | **Débito** | **Crédito** |
| ARPAYM002   | 110110-002- | Banco             | 98.00     |            |
| ARPAYM002   | 130100-002- | Saldo del cliente |           | 98.00      |

En el documento relacionado para el descuento de efectivo, el valor predeterminado de la dimensión financiera procede de la transacción de cliente creada de la transferencia, porque la transferencia tiene más de un cliente.

|             |             |                        |           |            |
|-------------|-------------|------------------------|-----------|------------|
| **Asiento** | **Cuenta** | **Tipo de registro**       | **Débito** | **Crédito** |
| ARP-00001   | 403300-002- | Descuento por pronto pago del cliente | 2.00      |            |
| ARP-00001   | 130100-002- | Saldo del cliente       |           | 2.00       |

Si el usuario no está satisfecho con el valor predeterminado de las dimensiones financieras para el descuento de efectivo, en lugar de un documento, debería utilizar varios documentos para registrar la transferencia de saldo. Esta situación se debería conseguir mediante la creación de una nota de crédito para el cliente en la que el saldo se mueve DESDE, y una nota de débito o una factura creada para el cliente HACIA el que se mueve el saldo. El siguiente ejemplo muestra cómo varios documentos se pueden especificar en el diario de pagos de cuentas de clientes para transferir el saldo, en lugar de usar un documento, como se muestra anteriormente en este ejemplo.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| ARPAYM001   | Cliente          | ACME        |                 |           | 100,00     | Contabilidad          | 401100-002-023-    |
| ARPAYM002   | Cliente          | Seguro   |                 | 100,00    |            | Contabilidad          | 401100-002-023-    |

Esto significa que cuando el cliente del Seguro paga 98,00 con el documento ARPAYM02, se usarán las dimensiones financieras correctas de la entrada de la cuenta contable del documento ARPAYM002.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Asiento** | **Cuenta** | **Tipo de registro** | **Débito** | **Crédito** |
| ARPAYM003   | 110110-002- | Banco             | 98.00     |            |
| ARPAYM003   | 130100-002  | Saldo del cliente |           | 98.00      |

En el asiento relacionado para el descuento de efectivo, se usarán las dimensiones financieras de la cuenta de ingresos de compensación que aparece en el documento ARPAYM002.

|             |                 |                        |           |            |
|-------------|-----------------|------------------------|-----------|------------|
| **Asiento** | **Cuenta**     | **Tipo de registro**       | **Débito** | **Crédito** |
| ARP-00001   | 403300-002-023- | Descuento por pronto pago del cliente | 2.00      |            |
| ARP-00001   | 130100-002-     | Saldo del cliente       |           | 2.00       |

### 

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Un documento con una compensación para varios clientes y proveedores
La compensación puede ser útil cuando una organización compra y vende a la misma empresa. En lugar de pagar las facturas de proveedor y esperar a recibir el pago para las facturas de cliente, se compensan las facturas de proveedor y cliente. La transacción de compensación se liquida con los saldos pendientes. 

Para mostrarlo, supongamos que el proveedor 1001 y el cliente US-008 son la misma entidad, por lo que la organización desea compensar los saldos de proveedores y clientes antes de pagar/recibir el saldo restante. Suponga que el registro de cliente debe 75,00 EUR y el registro de proveedor debe 100,00 EUR, lo que significa que preferiría compensar los balances y pagar solo al proveedor 25,00 EUR. Supongamos que la divisa de contabilidad es USD. En este caso, se especifica una transacción de compensación en un documento del diario de la cuenta de proveedores.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| APPAYM001   | Proveedor           | 1001        | Compensación         |  75,00    |            | Cliente         | US-008             |

Para evitar problemas no deseados con acuerdos futuros para esta transacción, en lugar de usar un documento, debería especificar varios documentos en el diario para registrar la transacción de compensación. Observe que los saldos de cliente y proveedor se compensan con una sola cuenta de compensación para evitar el uso de un documento que contenga varios saldos de cliente y de proveedor.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Asiento** | **Tipo de cuenta** | **Cuenta** | **Descripción** | **Débito** | **Crédito** | **Tipo de contrapartida** | **Cuenta de contrapartida** |
| 001         | Cliente          | US-008      |                 |           |  75,00     | Contabilidad          | 999999---          |
| 002         | Proveedor           | 1001        |                 |  75,00    |            | Contabilidad          | 999999---          |

 




