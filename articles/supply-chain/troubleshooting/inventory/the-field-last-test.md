---
title: El campo Fecha de la última prueba no se actualiza cuando se crean varios pedidos de calidad
description: El campo Fecha de la última prueba no se actualiza cuando se crean varios pedidos de calidad.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742037"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>El campo Fecha de la última prueba no se actualiza cuando se crean varios pedidos de calidad

Número de KB: 4612803

## <a name="symptoms"></a>Síntomas

El campo **Fecha de la última prueba** no se actualiza cuando se crean varios pedidos de calidad.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. La última fecha de prueba no está relacionada con pedidos de calidad. Almacena la fecha en la que los productos terminados se compraron o fabricaron por primera vez. Esta fecha se utiliza para calcular la fecha recomendada de vida útil.
