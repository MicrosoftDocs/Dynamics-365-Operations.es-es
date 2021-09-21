---
title: El texto se sobrescribe cuando se configura un artículo en una línea de pedido de venta
description: Cuando se configura un producto en una línea de pedido de venta, el texto modificado se sobrescribe con texto estándar. Cambie el texto después de haber configurado la línea, no antes.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477478"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>El texto del artículo se sobrescribe cuando se configura un producto en una línea de pedido de venta

## <a name="symptoms"></a>Síntomas

Este problema ocurre cuando crea una línea de orden de venta para un artículo configurable y luego modifica el texto del artículo. Cuando configura el elemento y selecciona **Aceptar**, el texto se sobrescribe con el texto estándar.

## <a name="resolution"></a>Resolución

Este comportamiento es esperado. El campo de texto incluye el nombre de la variante, que se completa solo después de configurar la línea. Por lo tanto, debe cambiar el texto después de haber configurado la línea, no antes.
