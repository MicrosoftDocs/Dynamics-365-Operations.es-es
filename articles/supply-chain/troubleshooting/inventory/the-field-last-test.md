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
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="f57e6-103">El campo Fecha de la última prueba no se actualiza cuando se crean varios pedidos de calidad</span><span class="sxs-lookup"><span data-stu-id="f57e6-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="f57e6-104">Número de KB: 4612803</span><span class="sxs-lookup"><span data-stu-id="f57e6-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="f57e6-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="f57e6-105">Symptoms</span></span>

<span data-ttu-id="f57e6-106">El campo **Fecha de la última prueba** no se actualiza cuando se crean varios pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="f57e6-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="f57e6-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="f57e6-107">Resolution</span></span>

<span data-ttu-id="f57e6-108">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="f57e6-108">The system is behaving as designed.</span></span> <span data-ttu-id="f57e6-109">La última fecha de prueba no está relacionada con pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="f57e6-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="f57e6-110">Almacena la fecha en la que los productos terminados se compraron o fabricaron por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f57e6-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="f57e6-111">Esta fecha se utiliza para calcular la fecha recomendada de vida útil.</span><span class="sxs-lookup"><span data-stu-id="f57e6-111">This date is used to calculate the shelf life advice date.</span></span>
