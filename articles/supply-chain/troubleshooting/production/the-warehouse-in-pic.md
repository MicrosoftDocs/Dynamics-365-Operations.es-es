---
title: El almacén en el diario de la lista de selección no se actualiza en una línea de L. MAT.
description: El almacén en el diario de la lista de selección no se actualiza en una línea de lista de materiales (L. MAT.).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5d24c0b8538f3894fd1d2a3edb3a6ed8633c9609
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026872"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>El almacén en el diario de la lista de selección no se actualiza en una línea de L. MAT.

Número de KB: 4614848

## <a name="symptoms"></a>Síntomas

El almacén en el diario de la lista de selección no se actualiza en una línea de lista de materiales (L. MAT.).

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. Si se crea una línea de diario de lista de selección que tiene una referencia (a través del Id. de lote) a una línea de L. MAT. de producción, el almacén en la línea de la L. MAT. de producción no se actualizará si la dimensión del almacén en la línea de diario de lista de selección de producción se cambia posteriormente.
