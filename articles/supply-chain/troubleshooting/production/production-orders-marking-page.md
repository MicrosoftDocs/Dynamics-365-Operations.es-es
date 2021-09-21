---
title: Las órdenes de producción no se muestran en la página Marcado
description: Algunas órdenes de producción no se muestran en la página Marcado. Este tema explica las tres configuraciones de producto que no están disponibles para marcar.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477470"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>Las órdenes de producción no se muestran en la página Marcado

## <a name="symptoms"></a>Síntomas

Cuando se trabaja con fabricación discreta, algunas órdenes de producción no se muestran en la página **Calificación**.

## <a name="resolution"></a>Resolución

Los productos que tienen las siguientes configuraciones no están disponibles para marcar. Por lo tanto, no se mostrarán en la página **Calificación**:

- Los productos se definen como productos del tipo *peso capturado*.
- Están habilitados para los procesos de almacén avanzados.
- Están configurados para ser controlados por el principio *Costo estándar*.
