---
title: Actualizar costes estándar en un entorno de fabricación
description: Este artículo proporciona orientación acerca de cómo actualizar los costes estándar en un entorno de no fabricación.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66d08888e426c55fc775a1f2505772bca45e7802
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842138"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="6b0f4-103">Actualizar costes estándar en un entorno de fabricación</span><span class="sxs-lookup"><span data-stu-id="6b0f4-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b0f4-104">Este artículo proporciona orientación acerca de cómo actualizar los costes estándar en un entorno de no fabricación.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="6b0f4-105">Las actualizaciones pueden reflejar nuevos artículos, categorías de coste o fórmulas de cálculo de costes indirectos.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="6b0f4-106">También pueden reflejar correcciones y cambios de coste.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="6b0f4-107">El tipo de actualización afecta a los pasos que debe completar para actualizar los costes estándar, tal como se muestra en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6b0f4-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="6b0f4-108">Especifica los cambios en el coste estándar esperados para los artículos comprados y, a continuación, cambia el estado de los registros de costes de artículos a **Activo** en la fecha adecuada.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="6b0f4-109">Sin embargo, no vuelve a calcular los costes de los artículos fabricados que usan artículos comprados.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="6b0f4-110">Especifica los costes estándar para un nuevo artículo comprado, pero no vuelve a calcular los costes de los artículos fabricados que tienen una versión de la lista de materiales (L. MAT) que contiene el nuevo artículo comprado como componente.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="6b0f4-111">Corrige o cambia el coste de un artículo comprado o cambia el grupo de costes asignado a un artículo comprado y vuelve a calcular el coste de todos los artículos fabricados que tienen una versión de L. MAT que contiene el artículo comprado como componente.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="6b0f4-112">Cambia el coste de una categoría de coste y calcula el coste de todos los artículos fabricados que tienen una versión de ruta que contiene operaciones de enrutamiento que usan la categoría de coste.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="6b0f4-113">Cambia las categorías de costes asignadas a las operaciones de rutas o el grupo de costes asignado a las categorías de costes.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="6b0f4-114">A continuación calcula el coste de todos los artículos fabricados que tienen una versión de ruta que contiene operaciones de enrutamiento que usan la categoría de coste.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="6b0f4-115">Cambia una fórmula de cálculo de costes indirectos y calcula el coste de todos los artículos fabricados que se verán afectados por el cambio.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="6b0f4-116">Cambia o agrega un sitio de fabricación para un artículo fabricado y calcula el coste fabricado del artículo para el sitio.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="6b0f4-117">Calcula, o vuelve a calcular, el coste de un artículo fabricado y vuelve a calcular el coste de todos los artículos fabricados que tienen una versión de L. MAT que contiene el artículo fabricado como componente.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="6b0f4-118">Calcula los costes de un nuevo artículo fabricado en función de su información de L. MAT y ruta definidas, aprobadas y activas.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="6b0f4-119">Cada caso requiere una consideración cuidadosa sobre cómo se deben actualizar los costes estándar.</span><span class="sxs-lookup"><span data-stu-id="6b0f4-119">Each case requires careful consideration about how to update standard costs.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]