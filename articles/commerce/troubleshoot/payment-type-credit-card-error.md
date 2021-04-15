---
title: El tipo de pago debe ser un error de tarjeta de crédito en la página del pedido de ventas
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se muestra un mensaje de error en la página del pedido de ventas después de sincronizar un pedido.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eabc64acc74645c7e6c7c4ab5794ed9fdb9dc997
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801684"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Error "El tipo de pago debe ser tarjeta de crédito" en la página del pedido de ventas

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se muestra un mensaje de error en la página del pedido de ventas después de sincronizar un pedido.

## <a name="description"></a>Descripción

Cuando abre la página de pedido de ventas después de sincronizar un pedido, recibe el siguiente mensaje de error: "El tipo de pago debe ser tarjeta de crédito, ya que se ha especificado el número de tarjeta de crédito".

![Error de que El tipo de pago debe ser tarjeta de crédito](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Resolución

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Establezca el tipo de pago en la sede de Commerce

1. Vaya a **Clientes \> Configuración de pagos \> Condiciones de pago**.
1. En la zona de navegación de la izquierda, seleccione sus términos de pago.
1. En el campo **Tipo de pago**, asegúrese de que **Tarjeta de crédito** está seleccionado.

## <a name="additional-resources"></a>Recursos adicionales

[Registro de ventas y pagos en línea](../tasks/posting-online-sales-payments.md)
