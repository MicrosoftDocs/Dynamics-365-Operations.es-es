---
title: La estación de empaquetado no muestra las notas del producto
description: La estación de empaquetado no muestra las notas del producto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSPack
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bf64de3e67c1000dad9d5b37fffe622ae0e300b3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026878"
---
# <a name="packing-station-doesnt-show-product-notes"></a>La estación de empaquetado no muestra las notas del producto

Número de KB: 4614615

## <a name="symptoms"></a>Síntomas

Las notas de empaquetado no se muestran en el formulario de empaquetado cuando las instrucciones de empaquetado se agregan como un archivo adjunto a un producto maestro o una variante del producto.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado.

La lógica actual para mostrar notas de empaquetado en el formulario de empaquetado requiere que las notas estén asociadas con los envíos.
