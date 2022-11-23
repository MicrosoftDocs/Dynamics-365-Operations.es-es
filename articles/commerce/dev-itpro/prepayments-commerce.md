---
title: Pagos por adelantado en Dynamics 365 Commerce
description: Este artículo proporciona una visión general del procesamiento de transacciones de pago adelantado en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780375"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Pagos por adelantado en Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Este artículo proporciona una visión general del procesamiento de transacciones de pago adelantado en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce procesa transacciones de pago por adelantado para los siguientes tipos de pago que se utilizan en Clientes o Commerce:

- **Pago de depósito de cuenta de cliente**: un cliente paga un depósito en el punto de venta (PDV). Commerce procesa el pago del depósito como una transacción de pago por adelantado. Cuando registra la transacción, se crea y registra un diario de pagos en la página **Asiento del diario** de Commerce headquarters. La casilla **Asiento del diario de anticipos** de la pestaña **Pago** se selecciona automáticamente para el diario de pagos. Para obtener más información, incluido el pago por adelantado y la información específica de impuestos que sea relevante para la región de destino, consulte [Recursos de globalización: contenido de ayuda específico del país o región](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Pedido de cliente que tiene un depósito**: un cliente crea un pedido de cliente en el PDV. El cliente puede pagar un depósito por el pedido, en función del porcentaje de depósito predeterminado que está configurado en la página **Pedidos de cliente** en Commerce headquarters (**Parámetros de comercio \> Pedidos de cliente**). Commerce procesa el pago del depósito para el pedido del cliente como una transacción de pago por adelantado. Cuando registra la transacción, se crea y registra un diario de pagos en la página **Asiento del diario**. La casilla **Asiento del diario de anticipos** de la pestaña **Pago** se selecciona automáticamente para el diario de pagos. El pago se liquida y la factura del cliente se emite automáticamente cuando se recoge o entrega el pedido.
- **Pedidos de ventas del centro de llamadas**: un representante de servicio al cliente del centro de llamadas crea un pedido de ventas en nombre de un cliente, y el atributo de **pago por adelantado** se establece en **Sí** durante la captura del pago.

Comercio realiza las siguientes tareas para procesar un pago por adelantado:

- **Procesar un pago de depósito de cuenta de cliente**: un pago de depósito que hace un cliente se transfiere a Commerce mediante un servicio que sincroniza datos. Commerce crea una transacción de pago minorista para el pago. Cuando registra la transacción minorista, se registra un diario de efectivo o un diario de pagos del cliente. La casilla **Comprobante de diario de anticipo** de la pestaña **Pago** de la página **Asiento del diario** de Commerce headquarters se selecciona automáticamente para el diario de pagos. Los pagos por adelantado no se pueden procesar si el importe del pago es negativo.
- **Procesar un pedido de cliente o un pedido de ventas que tenga un depósito**: un cliente paga un depósito requerido para un pedido de cliente utilizando Commerce Data Exchange: Real-time Service. Commerce crea un diario de pago del cliente o un diario de efectivo, según el método de pago que utilice el cliente. La casilla **Comprobante de diario de anticipo** de la pestaña **Pago** de la página **Asiento del diario** se selecciona automáticamente para el diario en Commerce headquarters. Si un cliente utiliza varios métodos de pago para realizar pagos parciales, Commerce procesa cada pago parcial, según el método de pago que se utilizó.

Para tarjetas de crédito y carteras digitales que tienen métodos de pago con tarjeta de crédito subyacentes, Commerce envía una solicitud de "captura" después de una autorización correcta. (Los fondos se capturan antes de que se facture el pedido de ventas).

Si cancela un pedido de cliente, se reembolsa el importe del pago por adelantado y se registra un diario de pagos de reembolso por el importe del depósito. El importe del reembolso se calcula y registra, según el método de pago que especificó cuando registró el pago del reembolso. Commerce podría aplicar un cargo por cancelación, según el porcentaje que establezca en la página **Parámetros de comercio** de Commerce headquarters.

Si devuelve un pedido de cliente, se crean un pedido de devolución y un diario de pagos de reembolso. Cuando registre el pedido de devolución, Commerce crea un diario de pagos de cliente o un diario de efectivo, según el método de pago que el cliente usó para la transacción original.
