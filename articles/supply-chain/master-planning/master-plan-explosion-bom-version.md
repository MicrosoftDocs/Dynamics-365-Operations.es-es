---
title: "Expansión de una versión de lista de materiales"
description: "En este artículo se explica un escenario de planificación maestra que implica la expansión de una versión de la lista de materiales (L. MAT.)."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f8c633e09103c45aff5614270a94a3bfe4fc5e20
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="f8c05-103">Expansión de una versión de lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f8c05-103">Explosion of a BOM version</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f8c05-104">En este artículo se explica un escenario de planificación maestra que implica la expansión de una versión de la lista de materiales (L. MAT.).</span><span class="sxs-lookup"><span data-stu-id="f8c05-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="f8c05-105">Una expansión de demanda de una versión de lista de materiales (L. MAT.) crea una demanda de cada elemento de línea de lista de materiales en un sitio específico y, posiblemente, en un almacén específico.</span><span class="sxs-lookup"><span data-stu-id="f8c05-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="f8c05-106">Una lista de materiales específica de un sitio puede definir un almacén para cada línea de lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="f8c05-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="f8c05-107">Además, para cada línea de lista de materiales, la configuración de las dimensiones de artículos determina si es preciso especificar el almacén.</span><span class="sxs-lookup"><span data-stu-id="f8c05-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="f8c05-108">La demanda resultante para cada elemento de línea de lista de materiales se convierte, a su vez, en el punto de partida para expansiones de demandas adicionales.</span><span class="sxs-lookup"><span data-stu-id="f8c05-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="f8c05-109">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f8c05-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f8c05-110">La dimensión Sitio es obligatoria y debe especificarse en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="f8c05-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f8c05-111">La dimensión Sitio es coherente.</span><span class="sxs-lookup"><span data-stu-id="f8c05-111">The site dimension is consistent.</span></span> <span data-ttu-id="f8c05-112">Por lo tanto, el sitio de menor nivel de demanda es equivalente al sitio de la transacción de demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="f8c05-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="f8c05-113">La ilustración siguiente muestra el proceso de expansión de la demanda de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="f8c05-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Expansión de la demanda con una versión de L. MAT](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a><span data-ttu-id="f8c05-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8c05-115">See also</span></span>
--------

[<span data-ttu-id="f8c05-116">Planificación maestra: cómo se establece la versión de la lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f8c05-116">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="f8c05-117">Planificación maestra y funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="f8c05-117">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)




