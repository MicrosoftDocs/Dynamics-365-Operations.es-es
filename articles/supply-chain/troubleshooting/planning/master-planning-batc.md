---
title: No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados
description: No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049489"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="04b17-103">No puede filtrar elementos de planificación maestra por sus valores de grupo de cobertura relacionados</span><span class="sxs-lookup"><span data-stu-id="04b17-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="04b17-104">Número de KB: 4612572</span><span class="sxs-lookup"><span data-stu-id="04b17-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="04b17-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="04b17-105">Symptoms</span></span>

<span data-ttu-id="04b17-106">Desea filtrar los artículos que se incluirán en un trabajo por lotes de planificación maestra, según los valores de los registros relacionados de la tabla de cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="04b17-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="04b17-107">(Por ejemplo, desea filtrar elementos por su **Proveedor** y / o valor de **Grupo de cobertura**).</span><span class="sxs-lookup"><span data-stu-id="04b17-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="04b17-108">La configuración del filtro para el trabajo por lotes le permite crear una combinación desde la tabla **Artículos** a la tabla **Cobertura de artículos** y, a continuación, especifique los valores de campo de la tabla de cobertura de elementos en su consulta.</span><span class="sxs-lookup"><span data-stu-id="04b17-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="04b17-109">Sin embargo, después de completar esta configuración, el sistema aún crea órdenes planificadas para toda la cobertura de artículos, no solo para los artículos que coinciden con los valores de campo especificados de la tabla de cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="04b17-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="04b17-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="04b17-110">Resolution</span></span>

<span data-ttu-id="04b17-111">El filtro de trabajo por lotes solo puede filtrar por elementos.</span><span class="sxs-lookup"><span data-stu-id="04b17-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="04b17-112">Aunque puede agregar una combinación a la tabla **Cobertura de artículos**, la configuración de filtro que realice en esa tabla no afectará el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="04b17-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="04b17-113">En runtime, el sistema ejecuta la planificación para todos los grupos de cobertura y todas las variaciones que tienen los artículos filtrados.</span><span class="sxs-lookup"><span data-stu-id="04b17-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="04b17-114">Una vez que un elemento ya está incluido en la ejecución, los grupos de cobertura incluidos en el filtro de elementos a no afectarán el resultado de la planificación.</span><span class="sxs-lookup"><span data-stu-id="04b17-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
