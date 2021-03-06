---
title: La página de entrada de la tarjeta de crédito muestra un error al finalizar la compra
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando la sección Método de pago no está cargada y muestra un mensaje de error.
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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018515"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>La página de entrada de la tarjeta de crédito muestra un error al finalizar la compra

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando la sección **Método de pago** no está cargada y muestra un mensaje de error.

## <a name="description"></a>Descripción

Cuando abre la página de pago de una tienda en línea, la sección **Método de pago** no está cargada y se muestra el siguiente mensaje de error: "Algo salió mal. Vuelva a intentarlo más tarde".

![Error de módulo de pago](media/payment-module-error.jpg)

## <a name="resolution"></a>Resolución

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Espere a que expire la caché de Commerce Scale Unit

La configuración del servicio de pago en la página de pago de la tienda en línea se almacena en caché en Commerce Scale Unit y puede tardar hasta 15 minutos en aparecer en el sitio de comercio electrónico. Esta configuración del servicio de pago incluye cambios en el id. de la cuenta del comerciante, la clave de API en la nube y varias opciones de configuración relacionadas con el método de pago.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un canal en línea](../channel-setup-online.md)
