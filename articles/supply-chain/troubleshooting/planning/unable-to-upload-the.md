---
title: No puede actualizar el coste unitario previsto cuando importa registros de previsión de la demanda
description: Cuando utiliza entidades de datos para importar registros de previsión de la demanda, el precio de coste de los registros existentes no se actualiza para que coincida con los datos importados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026885"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="6db20-103">No puede actualizar el coste unitario previsto cuando importa registros de previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="6db20-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="6db20-104">Número de KB: 4614109</span><span class="sxs-lookup"><span data-stu-id="6db20-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="6db20-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6db20-105">Symptoms</span></span>

<span data-ttu-id="6db20-106">Cuando utiliza entidades de datos para importar registros de previsión de la demanda, el valor **Coste unitario previsto** de los registros existentes no se actualiza para que coincida con los datos importados.</span><span class="sxs-lookup"><span data-stu-id="6db20-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="6db20-107">Causa</span><span class="sxs-lookup"><span data-stu-id="6db20-107">Cause</span></span>

<span data-ttu-id="6db20-108">**Coste unitario previsto** es un campo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6db20-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="6db20-109">El valor se basa en el coste unitario del producto y no se puede establecer directamente a través de la importación.</span><span class="sxs-lookup"><span data-stu-id="6db20-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="6db20-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="6db20-110">Resolution</span></span>

<span data-ttu-id="6db20-111">Debido a que el campo es de solo lectura, no puede importar valores en él.</span><span class="sxs-lookup"><span data-stu-id="6db20-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="6db20-112">El valor se calculará de acuerdo con la lógica empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="6db20-112">The value will be calculated according to the existing business logic.</span></span>
