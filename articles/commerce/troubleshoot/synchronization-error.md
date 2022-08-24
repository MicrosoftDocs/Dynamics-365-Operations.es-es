---
title: Error de sincronización de pedidos relacionado con el servicio de pago predeterminado
description: Este artículo proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.
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
ms.openlocfilehash: aa57366fb8f351a8275c947220de78fe809b7b5a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276699"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Error de sincronización de pedidos relacionado con el servicio de pago predeterminado

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía de resolución de problemas que puede ayudar a corregir un error que podría ocurrir cuando se sincroniza un pedido en línea.

## <a name="description"></a>Descripción

Cuando sincroniza un pedido en línea, recibe el siguiente mensaje de error: "Debe haber un servicio de pago predeterminado para procesar transacciones con tarjeta de crédito".

![Error del servicio de pago predeterminado que falta.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Resolución

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Confirmar o configurar el servicio de pago en la sede de Commerce

Para confirmar o configurar el servicio de pago en la sede de Commerce, siga estos pasos.

1. Vaya a **Clientes \> Configuración de pagos \> Servicios de pago**.
1. Asegúrese de que la opción **Procesador predeterminado para nuevas tarjetas de crédito** esté configurada en **Sí** para un servicio de pago.

## <a name="additional-resources"></a>Recursos adicionales

[Configuración, autorización y captura de tarjetas de crédito](../../finance/accounts-receivable/credit-card-authorizations.md)
