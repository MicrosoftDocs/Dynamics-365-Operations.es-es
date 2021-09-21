---
title: Se confirmó el envío para carga, pero no se registran líneas
description: La confirmación del envío no afecta la publicación. Solo actualiza el estado del envío y la carga. La publicación debe ocurrir en un proceso separado.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e754f1461672c1e9f2d8dd1a7ceffc81f3809120
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477559"
---
# <a name="shipment-for-load-has-been-confirmed-but-no-lines-are-posted"></a>Se ha confirmado el envío para carga, pero no se registran líneas

## <a name="symptoms"></a>Síntomas

Al trabajar con operaciones de almacén de salida, es posible que reciba el siguiente mensaje:

> Se ha confirmado el envío para la carga 1%.

Sin embargo, no se produjeron más publicaciones.

## <a name="resolution"></a>Resolución

Esto se debe al diseño. La confirmación del envío no afecta la publicación. Solo actualiza el estado del envío y la carga. La publicación debe ocurrir en un proceso separado.
