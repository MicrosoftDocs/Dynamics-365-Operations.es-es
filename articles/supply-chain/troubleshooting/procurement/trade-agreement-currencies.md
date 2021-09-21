---
title: Problemas de conversión de divisa comercial
description: Los precios de los acuerdos comerciales no se vuelven a calcular según la divisa cuando esta difiere en un pedido de compra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477488"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problemas de conversión de divisa comercial

## <a name="symptoms"></a>Síntomas

Los precios de los acuerdos comerciales no se vuelven a calcular según la divisa cuando esta difiere en un pedido de compra.

## <a name="resolution"></a>Resolución

La característica *Divisa genérica* permite definir precios y descuentos en una sola divisa. A continuación, puede convertir a otras divisas que necesite. Además, una vez realizada la conversión, la función puede aplicar automáticamente el redondeo psicológico.
