---
title: El peso debe ser positivo.
description: El peso debe ser positivo.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924312"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="549e3-103">El peso debe ser positivo.</span><span class="sxs-lookup"><span data-stu-id="549e3-103">Weight must be positive</span></span>

<span data-ttu-id="549e3-104">Código de error: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="549e3-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="549e3-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="549e3-105">Symptoms</span></span>

<span data-ttu-id="549e3-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="549e3-106">The system shows the following error message:</span></span>

> <span data-ttu-id="549e3-107">El peso debe ser positivo.</span><span class="sxs-lookup"><span data-stu-id="549e3-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="549e3-108">Causa</span><span class="sxs-lookup"><span data-stu-id="549e3-108">Cause</span></span>

<span data-ttu-id="549e3-109">El campo **Peso bruto** está configurado en *0* (cero) o un valor negativo.</span><span class="sxs-lookup"><span data-stu-id="549e3-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="549e3-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="549e3-110">Resolution</span></span>

<span data-ttu-id="549e3-111">Para especificar un peso, siga uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="549e3-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="549e3-112">En el campo **Peso bruto**, establezca un valor.</span><span class="sxs-lookup"><span data-stu-id="549e3-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="549e3-113">Luego seleccione una unidad en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="549e3-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="549e3-114">Seleccione **Obtener el peso del sistema** para calcular el valor **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="549e3-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
