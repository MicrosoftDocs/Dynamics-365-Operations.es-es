---
title: Reconocimiento de ingresos en pedidos de ventas
description: En este tema se describe la funcionalidad básica para reconocer ingresos en pedidos de ventas y facturas. El reconocimiento de ingresos está disponible en el pedido de ventas y en la factura correspondiente que se crea a partir del pedido de ventas.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 7aaa5e7c3b568400c72a1a84b5f29082579aeeae
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725495"
---
# <a name="revenue-recognition-on-sales-orders"></a>Reconocimiento de ingresos en pedidos de ventas

[!include [banner](../includes/banner.md)]

> [!NOTE]
> La característica Reconocimiento de ingresos no se puede activar a través de Administración de características. Actualmente, debe utilizar las claves de configuración para activarla.

En este tema se describe la funcionalidad básica para reconocer ingresos en pedidos de ventas y facturas. El reconocimiento de ingresos está disponible en un pedido de ventas y en la factura correspondiente que se crea a partir del pedido de ventas. El pedido de ventas también se puede crear mediante un proyecto de tiempo y materiales.

> [!NOTE]
> En las ilustraciones de este tema, se han ocultado o agregado columnas en la cuadrícula para mostrar mejor los conceptos. Por lo tanto, las páginas y los datos de las ilustraciones pueden ser diferentes a los que ve en el producto.

## <a name="enter-a-sales-order"></a>Especificar un pedido de ventas

Se especifica el pedido de ventas siguiente e incluye tres artículos que se configuran para el reconocimiento de ingresos.

[![Especificar un pedido de ventas.](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Existen dos conceptos para el reconocimiento de ingresos:

- **Determine el precio de ingresos.** El precio de ingresos se calcula en función de la configuración de los productos emitidos. El precio de ingresos nunca se muestra al cliente y se utiliza únicamente para la contabilidad de la factura del pedido de ventas. Las líneas del pedido de ventas y los documentos que se imprimen como parte de la venta siguen mostrando el precio de lista por unidad.
- **Determine cuándo se debe realizar el reconocimiento de ingresos.** Una programación de ingresos se usa para determinar cuándo se deben reconocer los ingresos.

    En este ejemplo, el primer artículo, S0001, se asigna a una programación de ingresos **1O** (una repetición). Esta línea representa una situación de tipo hito, en la que los ingresos se reconocerán después de que produzca la instalación en el futuro. Por lo tanto, los ingresos se diferirán hasta que se complete la instalación.

    El segundo artículo, S0008, es un artículo de servicio que se configura como artículo de soporte postcontrato (PCS). Los servicios de ingeniería sostenidos se proporcionan al cliente durante un período de 12 meses. Por lo tanto, se asigna una programación de ingresos **12M** al producto de forma predeterminada. Dado que este artículo es un artículo PCS, se deben definir las fechas iniciales y finales del contrato. De forma predeterminada, las fechas iniciales y finales del contrato se encuentran en la pestaña Configuración de los detalles del artículo. En la programación de ingresos, se define la configuración para **12M** de forma que las condiciones del contrato se rellenen automáticamente como se muestra en la ilustración siguiente.

    [![Programaciones de ingresos.](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    El tercer artículo, S0012, es hardware y no se ha asignado ninguna programación de ingresos de forma predeterminada. Los ingresos de hardware se reconocen en el momento en que se factura el artículo.

## <a name="confirm-the-sales-order"></a>Confirmar el pedido de ventas

Para ver detalles adicionales acerca del precio de ingresos y la programación de ingresos, use los botones del grupo **Reconocimiento de ingresos** en la pestaña **Gestionar** en el panel de acciones del pedido de ventas. Como el pedido de ventas no se confirma en este punto, los botones que se usan para el reconocimiento de ingresos no están disponibles. Estos botones pasan a estar disponibles o no disponibles conforme el pedido de ventas avanza por las etapas que conducen a su cumplimiento.

[![Encabezado de pedidos de ventas.](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

Los primeros tres botones proporcionan información detallada acerca del precio de ingresos para los artículos de la configuración del pedido de ventas para el reconocimiento de ingresos.

- **Asignación de precio de ingresos**: este botón está disponible después de que se confirme el pedido de ventas o se registre una factura. La confirmación del pedido de ventas y el registro de la factura calculan los ingresos para reconocer el precio que se reconocerá o diferirá en la entrada contable. En función de la configuración, el precio de ingresos que se calcula puede ser diferente del precio unitario que se muestra al cliente.
- **Reasignar precio con nuevas líneas de pedido**: este botón está disponible después de que se confirme el pedido de ventas o se registre una factura. El proceso de reasignación se usa para volver a calcular los ingresos que se deben reconocer después de que se agregue una nueva línea al pedido de ventas actual, tras facturarse, o a un nuevo pedido de ventas. En ambos casos, la adición de un nuevo artículo produce un cambio en el contrato. Por lo tanto, el precio de ingresos se debe volver a asignar.
- **Actualizar asignación de precio de ingresos**: este botón está disponible después de que se confirme el pedido de ventas, pero deja de estar disponible después de que este se haya facturado. La actualización se usa para volver a ejecutar la asignación de precios de ingresos sin tener que confirmar el pedido de ventas. Una vez facturado el pedido de ventas, el precio de ingresos no se puede volver a calcular.

Los dos últimos botones proporcionan información detallada acerca de la programación de ingresos para los artículos del pedido de ventas que tienen una programación de ingresos.

- **Programación prevista de reconocimiento de ingresos**: este botón está disponible después de que se confirme el pedido de ventas, pero deja de estar disponible después de que este se haya facturado. Abre una página que muestra la programación de ingresos prevista. La programación final puede cambiar, porque la programación prevista utiliza la fecha de envío solicitada, mientras que la programación final utiliza la fecha de envío real.
- **Programación de reconocimiento de ingresos**: este botón está disponible después de que se haya facturado el pedido de ventas. La programación final de reconocimiento de ingresos no se crea cuando se produce una confirmación o se crea un albarán. Se crea únicamente cuando se factura el pedido de ventas.

En el siguiente ejemplo, la asignación de precios de ingresos se ha producido cuando el pedido de ventas se ha confirmado. Tenga en cuenta que, aunque los precios de ingresos se asignan de forma diferente, el importe total del campo **Ingresos que se van a reconocer** debe seguir siendo igual a la suma de las líneas de pedido de ventas que se han facturado al cliente. Por ejemplo, la suma de las líneas de pedido de ventas, sin incluir impuestos es de 1499 $. Por lo tanto, la suma de los valores de **Ingresos que se van a reconocer** también debe ser 1499 $.

[![Asignación de precios de ingresos.](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

La programación prevista de reconocimiento de ingresos también se crea. La programación de ingresos utiliza el valor de **Ingresos que se van a reconocer** como el importe que se va a diferir. El artículo S0001 difiere $321.21 en lugar de $300 y el artículo S0008 difiere $160.61 en lugar de $100. El artículo S0012 no se muestra en la programación prevista porque los ingresos no se difieren. Cuando se produce el registro, el artículo S0012 registra 1017,18 $ directamente en la cuenta contable de ingresos.

[![Programación prevista de reconocimiento de ingresos.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Crear el albarán

A continuación, se puede crear el albarán para el pedido de ventas. No se reconocen ingresos cuando se registra el albarán. Si el pedido de ventas no se ha confirmado, el registro del albarán no desencadena el cálculo del precio de ingresos. Tampoco desencadena la creación de la programación prevista o final de reconocimiento de ingresos. Si se configura el grupo de modelos de artículo para diferir los ingresos en el albarán, se continuará registrando mediante el uso de las cuentas contables del perfil de contabilización actual y no de las nuevas cuentas de ingresos diferidos que se utilizan en el registro de facturas.

## <a name="create-the-invoice"></a>Crear la factura

El último paso es facturar el pedido de ventas. Si examina el asiento de la factura, observará que los ingresos de los artículos S0001 y S0008 se han diferido ($321.21 + 160.61 = 481.82) y el importe restante del artículo S0012 se ha registrado en los ingresos (1,017.18). Estos valores suman 1499 $, lo que coincide con la suma de las líneas de pedido de ventas.

[![Transacciones de asiento.](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

Una vez creada la factura, los botones **Asignación de precios de ingresos**, **Reasignar precio con nuevas líneas de pedido** y **Programación de reconocimiento de ingresos** para el reconocimiento de ingresos estarán disponibles, pero los botones **Actualizar asignación de precios de ingresos** y **Programación prevista de reconocimiento de ingresos** dejarán de estarlo.

[![Disponibilidad del botón de reconocimiento de ingresos disponible.](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

El botón **Asignación de precios de ingresos** aún está disponible para que pueda ver el cálculo del precio de ingresos. Si no ha cambiado nada en el pedido de ventas después de que se haya confirmado, el registro de la factura no cambiará el importe calculado en el campo **Ingresos que se van a reconocer**.

La programación prevista de reconocimiento de ingresos se quita y se reemplaza con la programación final de reconocimiento de ingresos. Los detalles de la programación de ingresos se mantienen para cada línea de pedido de ventas y se utilizan para liberar los ingresos diferidos en los ingresos reales a medida que se cumplen las obligaciones contractuales.

[![Programación final de reconocimiento de ingresos.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
