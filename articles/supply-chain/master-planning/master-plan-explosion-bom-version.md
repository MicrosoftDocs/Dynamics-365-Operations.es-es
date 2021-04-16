---
title: Expansión de una versión de lista de materiales
description: En este artículo se explica un escenario de planificación maestra que implica la expansión de una versión de la lista de materiales (L. MAT.).
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 367b662a43b3c3255632f20aeb821b973b04d890
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833602"
---
# <a name="explosion-of-a-bom-version"></a><span data-ttu-id="0cc80-103">Expansión de una versión de lista de materiales</span><span class="sxs-lookup"><span data-stu-id="0cc80-103">Explosion of a BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cc80-104">En este artículo se explica un escenario de planificación maestra que implica la expansión de una versión de la lista de materiales (L. MAT.).</span><span class="sxs-lookup"><span data-stu-id="0cc80-104">This article explains a master planning scenario that involves explosion of a bill of materials (BOM) version.</span></span>

<span data-ttu-id="0cc80-105">Una expansión de demanda de una versión de lista de materiales (L. MAT.) crea una demanda de cada elemento de línea de lista de materiales en un sitio específico y, posiblemente, en un almacén específico.</span><span class="sxs-lookup"><span data-stu-id="0cc80-105">A demand explosion of a bill of materials (BOM) version creates a demand for each BOM line item at a specific site and, possibly, at a specific warehouse.</span></span> <span data-ttu-id="0cc80-106">Una lista de materiales específica de un sitio puede definir un almacén para cada línea de lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="0cc80-106">In a site-specific BOM, a specific warehouse can be defined for each BOM line.</span></span> <span data-ttu-id="0cc80-107">Además, para cada línea de lista de materiales, la configuración de las dimensiones de artículos determina si es preciso especificar el almacén.</span><span class="sxs-lookup"><span data-stu-id="0cc80-107">Additionally, for each BOM line, the item's dimension settings determine whether the warehouse is required.</span></span> <span data-ttu-id="0cc80-108">La demanda resultante para cada elemento de línea de lista de materiales se convierte, a su vez, en el punto de partida para expansiones de demandas adicionales.</span><span class="sxs-lookup"><span data-stu-id="0cc80-108">The resulting demand for each BOM line item then becomes the starting point for additional demand explosion.</span></span> <span data-ttu-id="0cc80-109">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cc80-109">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="0cc80-110">La dimensión Sitio es obligatoria y debe especificarse en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="0cc80-110">The site dimension is mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="0cc80-111">La dimensión Sitio es coherente.</span><span class="sxs-lookup"><span data-stu-id="0cc80-111">The site dimension is consistent.</span></span> <span data-ttu-id="0cc80-112">Por lo tanto, el sitio de menor nivel de demanda es equivalente al sitio de la transacción de demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="0cc80-112">Therefore, the site for lower-level demand is the same as the site on the initial demand transaction.</span></span>

<span data-ttu-id="0cc80-113">La ilustración siguiente muestra el proceso de expansión de la demanda de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="0cc80-113">The following illustration shows how the process for master planning demand explosion.</span></span> ![Expansión de la demanda con una versión de L. MAT](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a><span data-ttu-id="0cc80-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0cc80-115">Additional resources</span></span>
--------

[<span data-ttu-id="0cc80-116">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="0cc80-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)

[<span data-ttu-id="0cc80-117">Visión general de la planificación maestra y la funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="0cc80-117">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]