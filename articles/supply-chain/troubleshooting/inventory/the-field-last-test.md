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
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026892"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>El campo Fecha de la última prueba no se actualiza cuando se crean varios pedidos de calidad

Número de KB: 4612803

## <a name="symptoms"></a>Síntomas

El campo **Fecha de la última prueba** no se actualiza cuando se crean varios pedidos de calidad.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. La última fecha de prueba no está relacionada con pedidos de calidad. Almacena la fecha en la que los productos terminados se compraron o fabricaron por primera vez. Esta fecha se utiliza para calcular la fecha recomendada de vida útil.
