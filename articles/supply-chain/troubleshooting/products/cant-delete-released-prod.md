---
title: No puede eliminar un producto publicado
description: Puede eliminar un producto lanzado y todas sus variantes solo si el producto lanzado no tiene ninguna transacción relacionada.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477556"
---
# <a name="you-cant-delete-a-released-product"></a>No puede eliminar un producto publicado

## <a name="symptoms"></a>Síntomas

Puede eliminar un producto lanzado y todas sus variantes solo si el producto lanzado no tiene ninguna transacción relacionada.

## <a name="resolution"></a>Resolución

Siga estos pasos para eliminar un producto publicado o un producto maestro.

1. Cierre todas las transacciones abiertas para los artículos.
1. Reducir el inventario a 0 (cero).
1. Realizar cierre de inventario.
1. Elimine todas las variantes de producto del producto maestro que desea eliminar.
