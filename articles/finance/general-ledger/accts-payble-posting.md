---
title: Registros de proveedores
description: Este tema explica cómo se configuran los registros en Proveedores y proporciona ejemplos de configuraciones de registro.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb3ebad31c9f41e405b9fc31a0f71df05fa1cc60
ms.sourcegitcommit: 10b85a09e8a550155a69aa2a8877a7c88b887242
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2022
ms.locfileid: "8014462"
---
# <a name="accounts-payable-posting"></a>Registro de proveedores

[!include [banner](../includes/banner.md)]

El perfil de registro principal para el módulo **Proveedores** es el perfil de registro del proveedor. Este perfil de registro determina la cuenta de resumen que se utiliza cuando los saldos de proveedores se registran en la contabilidad general. Un extracto de cuenta es una cuenta principal. También se conoce como la cuenta de resumen de proveedor.

Para obtener más información, consulte [Perfiles de contabilización del proveedor](../accounts-payable/vendor-posting-profiles.md).

Varias configuraciones de registro además del perfil de registro del proveedor están disponibles en Proveedores. En las secciones siguientes se ofrece más información acerca de otras configuraciones de registro.

## <a name="methods-of-payment-posting-accounts"></a>Cuentas de registro de métodos de pago

Los métodos de pago definen cómo se registrará un pago en la contabilidad general. También controlan el comportamiento de la salida del pago. Por lo general, se crea un método de pago para cada tipo de pago que realiza su organización (por ejemplo, efectivo, cheque, tarjeta de crédito, giro postal y transferencia).

Los campos en la sección **Registro** en la ficha desplegable **General** en la página **Métodos de pago** (**Proveedores > Configuración de pago > Métodos de pago**) controlan cómo se registrará un pago en la contabilidad general. Primero debe seleccionar un valor en el campo **Tipo de cuenta**. El tipo de cuenta que seleccione controla el comportamiento del campo **Cuenta de pago**. Le recomendamos que seleccione **Banco** en el **Tipo de cuenta** y luego seleccione la cuenta bancaria en el campo **Cuenta de pago**. La ventaja de este enfoque es que el sistema registrará el pago en la contabilidad auxiliar del banco, que respalda la conciliación y otros procesos relacionados con el efectivo. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro si está utiliza el módulo **Gestión de efectivo y bancos**.

| Tipo de registro | Tipo de cuenta | Ejemplo de nombre de cuenta de pago | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Banco | Banco | Banco de Estados Unidos | Cuenta bancaria que está vinculada a un activo | Débito | No | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta de pago**. |

Si no tiene previsto utilizar Gestión de efectivo y bancos, debe seleccionar **Contabilidad** en el **Tipo de cuenta** y luego seleccione la cuenta principal en el campo **Cuenta de pago**. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro si está **no** utiliza el módulo Gestión de efectivo y bancos.

| Tipo de registro | Tipo de cuenta |Ejemplo de cuenta de pago | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Contabilidad | Contabilidad | 100100: Banco de Estados Unidos | Activo | Débito | No | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta de pago**. |

## <a name="bridging-accounts"></a>Cuentas puente

La registro de puente es un proceso de dos pasos que se utiliza cuando se registran los pagos. Es una caractéristica opcional que se puede usar con cuentas bancarias con saldo cero, por ejemplo. Puede ayudar a garantizar un proceso de conciliación bancaria más fluido y oportuno. En el primer paso, se registra un pago en una cuenta temporal (la cuenta puente). En el segundo paso, la entrada registrada se revierte y se registra en la cuenta bancaria cuando el pago se liquida en el banco. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro para el registro puente.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Diario contable | 130725 | Efectivo no compensado | Pasivo | Débito | Sí | Para cada método de pago, introduzca la cuenta principal en el campo **Cuenta puente**. |

Para más información, consulte [Configurar y procesar pagos puente](../accounts-receivable/set-up-and-process-bridged-payments.md).

## <a name="customer-cash-discounts-posting-accounts"></a>Cuentas de registro de descuentos por pronto pago del cliente

Si su organización recibe descuentos por pronto pago de los proveedores a cambio de un pago rápido, debe configurar los códigos de descuento por pronto pago y especificar cómo deben registrarse en la contabilidad general. Hay varias opciones disponibles para especificar la cuenta principal que se utiliza para registrar un descuento por pronto pago del cliente.

Para obtener más información, consulte [Descuentos por pronto pago](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Cuentas de registro de cuotas de pago

Las cuotas de pago le permiten agregar automáticamente una cuota al pago de un proveedor cuando se aplica un conjunto de condiciones. Las cuotas de pago se pueden pagar al proveedor o se pueden registrar en su cuenta bancaria como un gasto. A continuación, encontrará algunos ejemplos:

- Un proveedor le cobra el 3 por ciento del total del pago si paga con tarjeta de crédito.
- Su banco le cobra 1 dólar por cada transferencia bancaria que procese y la tarifa de la transferencia se registra como gasto.

Cuando configura una cuota de pago de proveedor, si establece el campo **Cargo** a **Proveedor**, el campo **Cuenta principal** deja de estar disponible y el sistema utiliza el perfil de registro del proveedor para registrar la cuota. Si configura el campo **Cargo** a **Contabilidad**, debe configurar el campo **Cuenta principal** a la cuenta principal donde se registrará la cuota de pago. Normalmente, esta cuenta principal es una cuenta de gastos. La siguiente tabla muestra un ejemplo de la configuración del perfil de registro para el registro de cuota de pago.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Diario contable | 618190 | Gasto de cuota bancaria | Gasto | Débito | No | Si se selecciona **Contabilidad** en el campo **Cargo**, seleccione esta cuenta en el campo **Cuenta principal** en la página **Cuota de pago**. |

Para obtener más información, consulte [Definir tarifas de pago del proveedor](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Cuentas de registro de código de cargos

Si debe realizar un seguimiento de los importes, además de los artículos de línea, puede usar códigos de cargos. Por ejemplo, su proveedor podría cobrarle cuotas de flete y gestión, o podría cobrar algunas cuotas de flete y gestión internamente. Puede especificar si estos importes se registran en las cuentas de gastos o si se añaden al coste de los artículos.

Puede crear los códigos de cargos para clientes y proveedores. Cuando configura un código de cargos, debe definir el registro. El registro controla tanto la cuenta de débito como la cuenta de crédito. Cuando crea códigos de cargo, puede seleccionar el tipo de registro que se utiliza para cada código de cargo. La siguiente tabla muestra ejemplos de códigos de cargo típicos para Proveedores en la página **Códigos de cargos**.

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | ¿Debe/Haber? | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Cuota de la compra | Deje el campo en blanco. | No aplicable | Artículo | Débito | No | **Ejemplo de una cuota de compra de un artículo:** </p><ul><li>Campo **Tipo de débito** campo = **Articulo**</li><li>  Campo **Tipo de crédito** = **Cliente/Proveedor**.</li><li> El registro de artículos utiliza la cuenta principal del perfil de registro de inventario. |
| Pedido, flete | 600120 | Flete en | Ingresos | Débito | No | **Ejemplo de flete que se paga a un proveedor:** </p><ul><li>Campo **Tipo de débito** = **Cuenta contable**</li><li> Campo **Tipo de crédito** = **Cliente/Proveedor** |
| Devolución\* | 503160 | Devolución del proveedor (contra COGS)| Gasto | Crédito | No | **Ejemplo de devolución de proveedor:**</p><ul><li>Campo **Tipo de débito** = **Cliente/Proveedor**</li><li>Campo **Tipo de crédito** = **Cuenta contable** |

\* Para el ejemplo de devolución, el registro se usa solo cuando se agrega un código de cargos a un encabezado o línea de pedido de compra. La funcionalidad avanzada de devolución que está disponible en Microsoft Dynamics 365 Supply Chain Management proporciona más control y automatización de las devoluciones. Para obtener más información, consulte [Devoluciones de proveedor](../../supply-chain//procurement/vendor-rebates.md).

La tabla anterior muestra tres ejemplos típicos de tipos de registro que se pueden usar para códigos de cargos. Debe utilizarse como una guía y una selección de muestras. No proporciona una lista completa de todas las posibles combinaciones o tipos de registro que se pueden usar.

Para obtener más información, consulte [Crear códigos de cargos](../accounts-receivable/create-charges-codes.md).
