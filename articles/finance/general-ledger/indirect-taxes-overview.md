---
title: Visión general de impuestos
description: Este tema proporciona una visión general del sistema de impuesto sobre las ventas. Explica los elementos de la configuración de los impuesto y de cómo funcionan juntos.
author: ShylaThompson
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c64607f5dfbe00bd8a2e7cc80fb4771f11a6d1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188449"
---
# <a name="sales-tax-overview"></a>Visión general de impuestos

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general del sistema de impuesto sobre las ventas. Explica los elementos de la configuración de los impuesto y de cómo funcionan juntos.

## <a name="overview"></a>Visión general

El marco de impuestos admite muchos tipos de impuestos indirectos, como impuestos, impuesto sobre el valor añadido (IVA), impuesto de bienes y servicios (GST), cuotas basadas en unidad y retención de impuestos. Estos impuestos se calculan y se documentan durante transacciones de compra y de ventas. Periódicamente, se notifican y se pagan a las autoridades fiscales. 

En el diagrama siguiente se muestran las entidades de la configuración de impuestos y cómo se relacionan.

[![Diagrama que muestra la información general de las entidades de configuración de impuestos](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Para todos los impuestos que una empresa debe tener en cuenta, se debe definir un código de impuestos. Un código de impuestos almacena las tasas de impuestos y las reglas de cálculo para los impuestos. 

Cada código de impuestos se debe vincular a un período de liquidación de impuestos. Los períodos de liquidación de impuestos definen los intervalos en los que se deben notificar los impuestos y pagarse a la autoridad fiscal. Cada período de liquidación de impuestos se debe asignar a una autoridad fiscal. Una autoridad fiscal representa la entidad a la que se notifican y se pagan los impuestos. También define el diseño del informe de impuestos. Las autoridades fiscales pueden estar relacionadas con cuentas de proveedor. Para obtener más información, consulte [Configurar los periodos de liquidación de los impuestos](tasks/set-up-sales-tax-settlement-periods.md).

Cada código de impuestos también se debe vincular a un grupo de registro. Un grupo de registro especifica las cuentas principales en las que se registrarán los importes para los códigos de impuestos. 

También se pueden definir los códigos de notificación de impuestos opcionales. Estos se pueden asignar en códigos de impuestos para los diversos tipos de importes que se calculan para el código de impuestos. El informe **Pago de impuestos por código** muestra totales por código de notificación de impuestos para un intervalo y período de liquidación de impuestos determinados. 

Todas las transacciones para las que se deben calcular y registrar los impuestos deben tener un grupo de impuestos y un grupo de impuestos de artículos. Los grupos de impuestos están relacionados con la parte (por ejemplo, cliente o proveedor) de la transacción, mientras que los grupos de impuestos de artículos están relacionados con el recurso (por ejemplo, categoría de compras o artículo) de la transacción. Los grupos de impuestos contienen una lista de códigos de impuestos. Los impuestos que están presentes tanto en el grupo de impuestos como en el grupo de impuestos del artículo para una transacción son el código de impuestos que se aplica a la transacción. 

La siguiente tabla describe las entidades y la secuencia para la configuración de impuestos.

| Actividad de configuración                                                  | Necesario/opcional y descripción                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Crear cuentas principales.                                           | Requerido. Para poder configurar la función de impuestos, se deben crear las cuentas principales que la empresa utiliza para pagar y registrar impuestos.                                                                                                                                                                             |
| Configuración de grupos de contabilidad para impuestos.                     | Requerido. Los grupos de registro definen las cuentas principales para el registro y el pago de impuestos.   Para obtener más información, consulte [Configurar los grupos de apuntes de los impuestos en el libro mayor](tasks/set-up-ledger-posting-groups-sales-tax.md).                                                                                 |
| Configure las autoridades fiscales.                                   | Requerido. Las autoridades fiscales son las entidades a la que se deben notificar y pagar los impuestos.    Para obtener más información, consulte [Configurar las autoridades fiscales](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Configurar períodos de liquidación de impuestos.                            | Requerido. Los períodos de liquidación de impuestos contienen información acerca de cuándo y con qué frecuencia se deben notificar y pagar los impuestos. Están relacionados con una autoridad fiscal.                                                                                                                                                       |
| Configure los códigos de notificación de impuestos.                               | Opcional. Los códigos de notificación de impuestos se pueden asignar a códigos de impuestos para notificar importes para múltiples códigos de impuestos con un código de notificación de impuestos. Para obtener más información, consulte [Configurar los códigos de informes de los impuestos](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Configure códigos de impuesto sobre las ventas.                                         | Requerido. Los códigos de impuestos contienen tasas de impuestos y reglas de cálculo para cada impuesto. Los códigos de impuestos están relacionados con un período de liquidación de impuestos y un grupo de registro. Para obtener más información, consulte [Configurar los códigos de los impuestos](tasks/set-up-sales-tax-codes.md).                                |
| Configure los grupos de impuestos.                                        | Requerido. Los grupos de impuestos contienen una lista de códigos de ventas que solicitan la parte (cliente o proveedor) de una transacción. Para una transacción determinada, la intersección de códigos de impuestos en el grupo de impuestos y en el grupo de impuestos de artículos determina los códigos de impuestos que se aplican a esa transacción.                  |
| Configurar grupos de impuestos de artículos.                                   | Requerido. Los grupos de impuestos de artículos contienen una lista de códigos de ventas que solicitan el recurso (producto, servicio, etc.) de una transacción. Para una transacción determinada, la intersección de códigos de impuestos en el grupo de impuestos y en el grupo de impuestos de artículos determina los códigos de impuestos que se aplican a esa transacción. Para obtener más información, consulte [Configurar grupos de impuestos y grupos de impuestos de artículos de venta](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Configurar los parámetros de impuestos en las páginas de parámetros de la solicitud. | Requerido. Distintas áreas, como Contabilidad general, Clientes y Proveedores, deben configurar parámetros para el cálculo correcto de impuestos indirectos. Aunque la mayoría de estos parámetros tienen valores predeterminados, se deben modificar para ajustarse a los requisitos de cada empresa.                                          |

## <a name="sales-tax-on-transactions"></a>Impuestos en transacciones
En cada transacción (líneas de documentos de ventas/compras, etc.), debe especificar un grupo de impuestos y un grupo de impuestos de artículos para calcular los impuestos. Los grupos predeterminados se especifican en datos maestros (por ejemplo, cliente, proveedor, artículo y categoría de compras), pero puede cambiar manualmente los grupos en una transacción si es necesario. Ambos grupos contienen una lista de códigos de impuestos y la intersección entre las dos listas de códigos de impuestos determina la lista de códigos de impuestos aplicables para la transacción. 

En cada transacción, para buscar los impuestos calculados, abra la página **Transacción de impuestos**. Puede buscar los impuestos para una línea de documento o para todo el documento. Para determinados documentos (por ejemplo, factura de proveedor y diarios generales), puede ajustar los impuestos calculados si el documento original muestra importes irregulares.

## <a name="sales-tax-settlement-and-reporting"></a>Liquidación de impuestos y generación de informes
Los impuestos se deben notificar y pagar a las autoridades fiscales en intervalos regulados (mensuales, trimestrales, etc.). Puede liquidar cuentas de impuestos para el intervalo y compensar los saldos con la cuenta de liquidación de impuestos, como se especifica en los grupos de registro. Puede obtener acceso a esta función en la página **Liquidar y registrar impuestos**. Debe especificar el período de liquidación de impuestos para el que se deben liquidar los impuestos. 

Después de que se hayan pagado los impuestos, el saldo de la cuenta de liquidación de impuestos se debe equilibrar con la cuenta bancaria. Si la autoridad fiscal que está especificada en el período de liquidación de impuestos está relacionada con una cuenta de proveedor, el saldo de los impuestos se registra como factura de proveedor abierta y se puede incluir en la propuesta de pago normal.

## <a name="conditional-sales-tax"></a>Impuesto no realizado
El impuesto condicional es un impuesto que se paga de forma proporcional al importe real que se paga en una factura. Inversamente, los impuestos estándar se calculan en el momento de la facturación. El impuesto condicional se debe pagar a la autoridad fiscal cuando se registra el pago, no cuando se registra la factura. Cuando se registra la factura, la transacción se debe informar en el informe de libro de impuestos. Sin embargo, la transacción se debe excluir del informe de pago de impuestos. 

Si activa la casilla Impuesto no realizado en el formulario Parámetros de contabilidad general, no se puede deducir ningún impuesto hasta que haya pagado la factura. Se trata de un requisito legal en algunos países o regiones.

> [!NOTE]
> Si activa la casilla Impuesto no realizado, debe configurar códigos de impuestos y grupos de impuestos, así como crear grupos de registro contable para admitir la funcionalidad. |

###  <a name="example"></a>Ejemplo

Usted liquida los impuestos cada mes. El 15 de junio, crea una factura de cliente de 10.000, más impuestos.
-   El impuesto es un 25 por ciento, o 25,00.
-   El pago de la factura vence el 30 de julio.

Normalmente tendría que liquidar y pagar 2.500 a la autoridad fiscal cuando se registra la factura en junio, aunque no haya recibido el pago del cliente. 

Sin embargo, si usa un impuesto condicional, se liquida con la autoridad fiscal cuando recibe el pago del cliente el 30 de julio.

### <a name="postdated-check"></a>Cheque con fecha futura

Si usa el cheque con fecha futura como método de pago, cuando se realiza el pago, la cuenta bancaria no se borra. En algunos países, el IVA se convierte en pasivo “realizado” cuando el pago borra el banco, que significa que el cheque con fecha futura se liquida. Puede habilitarlo seleccionando **Realizar los impuestos condicionales cuando se toman los cheques con fecha futura** en **Efectivo y gestión bancaria > Configuración > Parámetros de gestión de efectivo y bancos > Cheques con fecha futura**.

Para obtener más información, consulte [Configurar la retención de impuestos](tasks/set-up-withholding-tax.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]