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
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a><span data-ttu-id="93b36-103">El almacén en el diario de la lista de selección no se actualiza en una línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="93b36-103">The warehouse in the picking list journal isn't updated on a BOM line</span></span>

<span data-ttu-id="93b36-104">Número de KB: 4614848</span><span class="sxs-lookup"><span data-stu-id="93b36-104">KB number: 4614848</span></span>

## <a name="symptoms"></a><span data-ttu-id="93b36-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="93b36-105">Symptoms</span></span>

<span data-ttu-id="93b36-106">El almacén en el diario de la lista de selección no se actualiza en una línea de lista de materiales (L. MAT.).</span><span class="sxs-lookup"><span data-stu-id="93b36-106">The warehouse in the picking list journal isn't updated on a bill of materials (BOM) line.</span></span>

## <a name="resolution"></a><span data-ttu-id="93b36-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="93b36-107">Resolution</span></span>

<span data-ttu-id="93b36-108">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="93b36-108">The system is behaving as designed.</span></span> <span data-ttu-id="93b36-109">Si se crea una línea de diario de lista de selección que tiene una referencia (a través del Id. de lote) a una línea de L. MAT. de producción, el almacén en la línea de la L. MAT. de producción no se actualizará si la dimensión del almacén en la línea de diario de lista de selección de producción se cambia posteriormente.</span><span class="sxs-lookup"><span data-stu-id="93b36-109">If a picking list journal line is created that has a reference (via the lot ID) to a production BOM line, the warehouse on the production BOM line won't be updated if the warehouse dimension on the production picking list journal line is changed later.</span></span>
