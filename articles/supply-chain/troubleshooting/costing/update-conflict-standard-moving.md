---
title: Conflicto de actualización cuando el método de valoración de inventario es coste estándar o media móvil
description: Se produce un conflicto de actualización cuando el método de valoración de inventario es coste estándar o media móvil
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477554"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Se produce un conflicto de actualización cuando el método de valoración de inventario es coste estándar o media móvil

## <a name="symptoms"></a>Síntomas

Cuando registra documentos como diarios de inventario, facturas de pedidos de compra o facturas de pedidos de venta en paralelo para mejorar la escalabilidad y el rendimiento, es posible que reciba un mensaje de error sobre un conflicto de actualización y que algunos de los documentos no se registren. Este problema puede producirse cuando el método de valoración de inventario es *Coste estándar* o *Media móvil*. Ambos métodos son métodos de gestión de costes perpetuos. Es decir, el coste final se determina en el momento de la publicación.

Si está usando el método *Media móvil*, el mensaje de error se parece a este ejemplo:

> No se espera el valor de inventario xx.xx después del cálculo de gasto proporcional

Si está usando el método *Coste estándar*, el mensaje de error se parece a este ejemplo:

> El coste estándar no coincide con el valor del inventario financiero después de la actualización. Valor = xx.xx, Cant. = yy.yy, Coste estándar = zz.zz

## <a name="workaround"></a>Solución alternativa

Hasta que Microsoft publique una solución para solucionar el problema, considere usar las siguientes soluciones para ayudar a evitar o reducir estos errores:

- Vuelva a publicar los documentos fallidos.
- Cree documentos que tengan menos líneas.
- Evite valores decimales en el coste estándar. Intente definir el coste estándar para que el campo **Cantidad de precio** esté configurado en *1*. Si debe especificar un valor de **Cantidad de precio** que sea mayor que *1*, trate de minimizar el número de decimales en el coste estándar unitario. (Idealmente, debería haber menos de dos cifras decimales). Por ejemplo, evite definir configuraciones de coste estándar como **Precio** = *10* y **Cantidad de precio** = *3*, porque producirán un coste estándar unitario de 3,333333 (donde el valor decimal se repite).
- En la mayoría de los documentos, evite tener varias líneas que contengan la misma combinación de dimensiones de inventario financiero y de producto.
- Reduzca el grado de paralelización. (En este caso, su sistema puede volverse más rápido, porque se producen menos conflictos de actualización y reintentos).
