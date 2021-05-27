---
title: Se rechaza el reembolso de un pedido de devolución
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se rechaza un reembolso en un pedido de devolución porque la tarjeta de crédito que se usa para la facturación es diferente de la tarjeta que se usó durante la autorización de pago original.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 99fd4b816b1a3a1fe3c2d1579be45b43fdc3d385
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020765"
---
# <a name="refund-on-a-return-order-is-declined"></a>Se rechaza el reembolso de un pedido de devolución

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando se rechaza un reembolso en un pedido de devolución porque la tarjeta de crédito que se usa para la facturación es diferente de la tarjeta que se usó durante la autorización de pago original.

## <a name="description"></a>Descripción

Se rechaza un reembolso cuando la tarjeta de crédito que se utiliza para facturar un pedido de devolución difiere de la tarjeta que se utilizó durante la autorización de pago original. Recibirá el siguiente mensaje de error: "Algunos pagos no están en el estado correcto para su registro. Vuelva a validar el estado de todos los pagos antes de la facturación".

Los detalles de la autorización de pago incluirán el siguiente mensaje de error: "La puerta de enlace de Adyen SendRequest () falló con estado 'InternalServerError'.22144; se devolvió una respuesta vacía desde Adyen.(22001);"

![Se rechaza el reembolso de un error de pedido de devolución](media/refund-order-decline.jpg)

## <a name="resolution"></a>Resolución

### <a name="enable-blind-returns-in-adyen"></a>Habilitar devoluciones ciegas en Adyen

Para habilitar las devoluciones ciegas, siga los pasos de [Solucionar problemas de del conector de Dynamics 365 Payment para problemas de Adyen](adyen-support.md) para ponerse en contacto con el equipo de soporte de Adyen y solicitar que se habiliten las devoluciones ciegas en su cuenta de comerciante de Adyen.

## <a name="additional-resources"></a>Recursos adicionales

[Conector de pago de Dynamics 365 para Adyen](../dev-itpro/adyen-connector.md)

[Configurar el conector de pago de Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
