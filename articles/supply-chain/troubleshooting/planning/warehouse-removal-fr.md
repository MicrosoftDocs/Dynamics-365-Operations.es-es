---
title: No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión
description: No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026884"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="ebc9b-103">No puede eliminar la dimensión de previsión de la demanda de almacén de las líneas de previsión</span><span class="sxs-lookup"><span data-stu-id="ebc9b-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="ebc9b-104">Número de KB: 4614408</span><span class="sxs-lookup"><span data-stu-id="ebc9b-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="ebc9b-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="ebc9b-105">Symptoms</span></span>

<span data-ttu-id="ebc9b-106">Este problema ocurre cuando la dimensión **Almacén** no está asignada en la pestaña **Dimensiones de previsión** de la página **Parámetros de previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="ebc9b-107">Sin embargo, la columna **Almacén** se muestra en la página **Previsión de la demanda** (**Planificacion maestra \> Previsión \> Entidad de previsión manual \> Líneas de previsión de la demanda**).</span><span class="sxs-lookup"><span data-stu-id="ebc9b-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="ebc9b-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="ebc9b-108">Resolution</span></span>

<span data-ttu-id="ebc9b-109">Los ajustes en la pestaña **Dimensiones de previsión** de la página **Parámetros de previsión de la demanda** no afecta a la página **Previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="ebc9b-110">Controlan la previsión de línea de base que se genera y se muestra en la previsión de la demanda ajustada.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="ebc9b-111">Sin embargo, no controlan las dimensiones que se requieren para el pronóstico de la demanda "real".</span><span class="sxs-lookup"><span data-stu-id="ebc9b-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="ebc9b-112">Al autorizar los registros que se muestran en la página **Previsión de la demanda ajustada**, puede convertirlos en entradas de previsión "reales" para un modelo de previsión.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="ebc9b-113">Después, ese modelo se puede utilizar para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="ebc9b-114">En la página **Previsión de la demanda**, las dimensiones de la previsión "real" que se muestran en las líneas de previsión de la demanda son parte de las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="ebc9b-115">(Este comportamiento se asemeja al comportamiento de las líneas de pedidos de ventas). Si su sistema no está configurado para usar **Almacén** como dimensión de inventario obligatoria, puede personalizar la página para ocultar la columna.</span><span class="sxs-lookup"><span data-stu-id="ebc9b-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
