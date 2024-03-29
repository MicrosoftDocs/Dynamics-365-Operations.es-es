---
title: Los pagos se liquidan automáticamente antes de que se facturen o envíen los pedidos
description: Este artículo proporciona una guía para la resolución de problemas que puede ayudar cuando se liquida un pago en el portal de Adyen inmediatamente después de que se realiza un pedido, aunque el pedido de venta no se haya facturado ni enviado.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 6fdaf48600edc22b5423e0167177616758e2dc6e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282717"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Los pagos se liquidan automáticamente antes de que se facturen o envíen los pedidos

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la resolución de problemas que puede ayudar cuando se liquida un pago en el portal de Adyen inmediatamente después de que se realiza un pedido, aunque el pedido de venta no se haya facturado ni enviado.

## <a name="description"></a>Descripción

Después de efectuado un pedido, el pago se liquida inmediatamente en el portal de Adyen, aunque el pedido de venta no se haya facturado ni enviado.

## <a name="resolution"></a>Resolución

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Configurar la captura manual para pagos de comercio electrónico en el portal de Adyen

Para configurar la captura manual para pagos de comercio electrónico en el portal de Adyen, siga estos pasos.

1. Inicie sesión en el portal de Adyen.
1. En la esquina superior derecha, seleccione su cuenta de comerciante para el canal de comercio electrónico.
1. En la zona de navegación superior, seleccione **Cuenta** y luego seleccione **Configuración**.
1. En el campo **Retraso de captura**, seleccione **Manual**.

    ![Configuración de retardo de captura en el portal de Adyen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Recursos adicionales

[Captura de pago de Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector.md)

[Configurar el conector de pago de Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
