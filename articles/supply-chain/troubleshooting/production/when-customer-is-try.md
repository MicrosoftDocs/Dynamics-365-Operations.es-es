---
title: El número de lote se borra cuando se selecciona un nuevo Id. de lote
description: Cuando revisa una línea de diario de la lista de selección, el valor del campo Número de lote se borra si selecciona un nuevo valor en el campo Id. de lote.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026866"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="7964d-103">El número de lote se borra cuando se selecciona un nuevo Id. de lote</span><span class="sxs-lookup"><span data-stu-id="7964d-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="7964d-104">Número de KB: 4613107</span><span class="sxs-lookup"><span data-stu-id="7964d-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="7964d-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="7964d-105">Symptoms</span></span>

<span data-ttu-id="7964d-106">Cuando revisa una línea de diario de la lista de selección, el valor del campo **Número de lote** se borra si selecciona un nuevo valor en el campo **Id. de lote**.</span><span class="sxs-lookup"><span data-stu-id="7964d-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="7964d-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="7964d-107">Resolution</span></span>

<span data-ttu-id="7964d-108">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="7964d-108">The system is behaving as designed.</span></span> <span data-ttu-id="7964d-109">Si cambia el Id. de lote, cambia el contexto del artículo.</span><span class="sxs-lookup"><span data-stu-id="7964d-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="7964d-110">Por lo tanto, se restablece el número de lote.</span><span class="sxs-lookup"><span data-stu-id="7964d-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="7964d-111">Para asociar el número de lote con un Id. de lote, primero debe configurar el Id. de lote.</span><span class="sxs-lookup"><span data-stu-id="7964d-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
