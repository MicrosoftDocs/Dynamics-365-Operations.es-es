---
title: La programación de la producción no considera los márgenes de seguridad
description: La programación de la producción no considera los márgenes de seguridad que se establecen en la cobertura del artículo para el suministro vinculado
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477503"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>La programación de la producción no considera los márgenes de seguridad

## <a name="symptoms"></a>Síntomas

La planificación maestra considera los márgenes de seguridad. Sin embargo, los márgenes de seguridad se ignoran cuando se programan órdenes de producción planificadas.

## <a name="resolution"></a>Resolución

Los márgenes se consideran solo durante la planificación maestra, no durante la programación manual. Los márgenes están diseñados para actuar como un amortiguador durante la fase de planificación, para dar algún "margen" para el proceso real.

Para obtener el resultado deseado, puede eliminar el margen. Luego, la ruta debe actualizarse para que incluya el tiempo deseado (por ejemplo, como tiempo de espera). Tanto la planificación maestra como la programación manual deberían producir el mismo resultado.
