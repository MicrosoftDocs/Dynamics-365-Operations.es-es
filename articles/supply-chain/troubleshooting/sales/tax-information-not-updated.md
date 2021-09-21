---
title: La información fiscal no se actualiza si se cambia la ubicación en el encabezado de un pedido de ventas
description: Si se cambia el sitio, el almacén o la dirección de entrega, ya sea en el encabezado de un pedido de ventas o en el nivel de línea, la información fiscal del caso no se actualiza en las líneas. Debe hacer esto manualmente.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477528"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>La información fiscal no se actualiza si se cambia la ubicación en el encabezado de un pedido de ventas

## <a name="symptoms"></a>Síntomas

Si se cambia el sitio, el almacén o la dirección de entrega, ya sea en el encabezado de un pedido de ventas o en el nivel de línea, la información fiscal del caso no se actualiza en las líneas.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. El problema se produce porque la dirección de entrega, el sitio y el almacén no se cambian automáticamente en las líneas. Debe actualizarlos manualmente.
