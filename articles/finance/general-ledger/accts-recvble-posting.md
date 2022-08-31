---
title: Registro de clientes
description: Este artículo explica cómo se configuran los registros en Clientes y proporciona ejemplos de configuraciones de registro.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d679595a1f702c4e3ade138a87c817d245fcf79
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324341"
---
# <a name="accounts-receivable-posting"></a>Contabilización de clientes

[!include [banner](../includes/banner.md)]

El perfil de registro principal para el módulo **Clientes** es el perfil de registro del cliente. Este perfil de registro determina la cuenta de resumen que se utiliza cuando los saldos de clientes se registran en la contabilidad general. Un extracto de cuenta es una cuenta principal. También se conoce como la cuenta de resumen de clientes.

El informe **Conciliación de cliente a libro mayor** se puede utilizar después de la contabilización para ayudar a conciliar los saldos de las cuentas del cliente y del libro mayor. El informe utiliza la información que se encuentra en la cuenta de resumen para el perfil de contabilización del cliente. No utiliza la cuenta resumen de la contabilidad que se crea para el documento. Si realiza cambios en el perfil de contabilización del cliente o en el grupo de clientes asignado al cliente después de haber contabilizado las transacciones, el informe puede mostrar diferencias entre el cliente y el saldo de la cuenta contable. Para ver solo las líneas que tienen diferencias y las líneas para las que las cuentas de clientes y la cuenta contable son cero, seleccione el parámetro **Solo diferencias** al imprimir el informe.

Para obtener más información, consulte [Perfiles de contabilización del cliente (formulario)](../accounts-receivable/customer-posting-profiles.md).

Varias configuraciones de registro además del perfil de registro del cliente están disponibles en Clientes. En las secciones siguientes se ofrece más información acerca de otras configuraciones de registro.

## <a name="posting-accounts-for-methods-of-payment"></a>Cuentas de registro de métodos de pago

Los métodos de pago definen cómo se registrará un pago en la contabilidad general. También controlan el comportamiento de la salida del pago. Por lo general, se crea un método de pago para cada tipo de pago que acepta su organización (por ejemplo, efectivo, cheque, tarjeta de crédito, giro postal y transferencia).

Los campos de la sección **Destino** en la ficha desplegable **General** controlan cómo se publicará un pago en el libro mayor. Primero debe seleccionar un valor en el campo **Tipo de cuenta**. El tipo de cuenta que seleccione controla el comportamiento del campo **Cuenta de pago**. Le recomendamos que seleccione **Banco** en el **Tipo de cuenta** y luego seleccione la cuenta bancaria en el campo **Cuenta de pago**. La ventaja de este enfoque es que el sistema registrará el pago en la contabilidad auxiliar del banco, que respalda la conciliación y otros procesos relacionados con el efectivo. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro si está utiliza el módulo **Gestión de efectivo y bancos**.

| Tipo de registro | Tipo de cuenta | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Banco | Banco | Bank of Contoso | Cuenta bancaria que está vinculada a un activo | Crédito | No | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta de pago**. |

Si no tiene previsto utilizar Gestión de efectivo y bancos, debe seleccionar **Contabilidad** en el **Tipo de cuenta** y luego seleccione la cuenta principal en el campo **Cuenta de pago**. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro si está no utiliza el módulo Gestión de efectivo y bancos.

| Tipo de registro | Tipo de cuenta | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Contabilidad | Contabilidad | 100100: Bank of Contoso | Activo | Crédito | No | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta de pago**. |

## <a name="bridging-accounts"></a>Cuentas puente

La registro de puente es un proceso de dos pasos que se utiliza cuando se registran los pagos. Es una caractéristica opcional que se puede usar con cuentas bancarias con saldo cero, por ejemplo. Puede ayudar a garantizar un proceso de conciliación bancaria más fluido y oportuno. En el primer paso, se registra un pago en una cuenta temporal (la cuenta puente). En el segundo paso, la entrada registrada se revierte y se registra en la cuenta bancaria cuando el pago se liquida en el banco. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro para el registro puente.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diario contable | 130725 | Efectivo no compensado | Pasivo | Débito | Sí | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta puente**. |

Para más información, consulte [Configurar y procesar pagos puente](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="posting-accounts-for-customer-cash-discounts"></a>Cuentas de registro de descuentos por pronto pago del cliente

Si su organización ofrece descuentos por pronto pago a los clientes a cambio de un pago rápido, debe configurar los códigos de descuento por pronto pago y especificar cómo deben registrarse en la contabilidad general. Hay varias opciones disponibles para especificar la cuenta principal que se utiliza para registrar un descuento por pronto pago del cliente.

Para obtener más información, consulte [Descuentos por pronto pago](../cash-bank-management/cash-discounts.md).

## <a name="posting-accounts-for-payment-fees"></a>Cuentas de registro de cuotas de pago

Las cuotas de pago le permiten agregar automáticamente una cuota al pago de un cliente cuando se aplica un conjunto de condiciones. Las cuotas de pago se pueden cargar al cliente o se pueden registrar en su cuenta bancaria como un gasto. A continuación, encontrará algunos ejemplos:

- Le carga a los clientes el 3 por ciento del total del pago si pagan con tarjeta de crédito.
- Su banco le cobra 1 dólar por cada transferencia bancaria que procese y la tarifa de la transferencia se registra como gasto.

Cuando configura una cuota de pago de cliente, si establece el campo **Cargo** a **Cliente**, el campo **Cuenta principal** deja de estar disponible y el sistema utiliza el perfil de registro del cliente para registrar la cuota. Si configura el campo **Cargo** a **Contabilidad**, debe configurar el campo **Cuenta principal** a la cuenta principal donde se registrará la cuota de pago. Normalmente, esta cuenta principal es una cuenta de gastos. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro para el registro de cuota de pago.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diario contable | 618190 | Gasto de cuota bancaria | Gasto | Débito | No |  Si se selecciona **Contabilidad** en el campo **Cargo**, seleccione esta cuenta en el campo **Cuenta principal** para la cuota de pago. |

Para obtener más información, consulte [Establecer tarifas de pago del cliente](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Cuentas de registro de códigos de cargos

Si debe realizar un seguimiento de los importes de venta, además de los artículos de línea, puede usar códigos de cargos. Por ejemplo, usted podría cobrarle cuotas de flete y gestión a sus clientes, o podría cobrar algunas cuotas de flete y gestión internamente. Puede especificar si estos importes se registran en las cuentas de gastos o si se añaden al coste de los artículos.

Puede crear los códigos de cargos para clientes y proveedores. Cuando configura un código de cargos, debe definir el registro. El registro controla tanto la cuenta de débito como la cuenta de crédito. Para los códigos de cargo que crea, puede seleccionar el tipo de registro que se utiliza. La siguiente tabla muestra ejemplos típicos de códigos de cargo para Clientes.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Cuota de pago | 411400 | Ingresos – Tarifas | Ingresos | Crédito | No | **Ejemplo de fondos insuficientes:** cuenta de débito de cliente/proveedor y cuenta de libro mayor de crédito |
| Pedido, flete | 403500 | Ingresos – Flete | Ingresos | Crédito | No | **Ejemplo de flete que se cobra a un cliente:** cuenta de débito de cliente/proveedor y cuenta de libro mayor de crédito |
| Devolución\* | 403200 | Descuento | Ingresos | Débito | No | **Ejemplo de devolución a cliente:** cuenta de libro mayor de débito y cuenta de cliente/proveedor de crédito |

\* Para el ejemplo de devolución, el registro se usa solo cuando se agrega un código de cargos a un encabezado o línea de pedido de compra. La funcionalidad avanzada de devolución que está disponible en Microsoft Dynamics 365 Supply Chain Management proporciona más control y automatización de las devoluciones. Para obtener más información, consulte [Devoluciones a clientes](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md).

La tabla anterior muestra tres ejemplos típicos de tipos de registro que se pueden usar para códigos de cargos. Debe utilizarse como una guía y un ejemplo. No proporciona una lista completa de todas las posibles combinaciones o tipos de registro que se pueden usar.

Para obtener más información, consulte [Crear códigos de cargos](../accounts-receivable/create-charges-codes.md).

## <a name="posting-accounts-for-commissions"></a>Cuentas de registro de comisiones

Opcionalmente, puede configurar el sistema para calcular las comisiones de un representante de ventas o un grupo de representantes de ventas en un pedido de ventas determinado. Si habilita esta funcionalidad, debe configurar la cuenta de registro que se utiliza para calcular la comisión. Esta configuración se realiza en la página **Registro de comisiones** del módulo **Ventas y marketing**.

Para obtener más información, consulte [Configurar las reglas de comisiones de ventas](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md).
