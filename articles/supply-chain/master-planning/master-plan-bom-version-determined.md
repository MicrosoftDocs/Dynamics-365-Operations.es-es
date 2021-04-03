---
title: Determinar la versión de L. MAT.
description: En una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L. MAT válida en función del sitio.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6f1f1656f0ef04799b1ce6b397dac0f829e41c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251946"
---
# <a name="determine-the-bom-version"></a><span data-ttu-id="0a13c-103">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="0a13c-103">Determine the BOM version</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a13c-104">En una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L. MAT válida en función del sitio.</span><span class="sxs-lookup"><span data-stu-id="0a13c-104">During a demand explosion, if an item has a default order type of Production, the planning engine finds a valid BOM version based on the site.</span></span> 

<span data-ttu-id="0a13c-105">La dimensión del sitio se conoce siempre y se indica en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="0a13c-105">The site dimension is always known and is stated on the demand transaction.</span></span> <span data-ttu-id="0a13c-106">El siguiente proceso se usa para determinar la versión de L. MAT que utilizar:</span><span class="sxs-lookup"><span data-stu-id="0a13c-106">The following process is used to determine the BOM version to use:</span></span>

-   <span data-ttu-id="0a13c-107">Si hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa la L. MAT específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="0a13c-107">If there is a BOM version defined for the item at the demand site, the site-specific BOM is used.</span></span>
-   <span data-ttu-id="0a13c-108">Si no hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa una L. MAT general.</span><span class="sxs-lookup"><span data-stu-id="0a13c-108">If there is no site-specific BOM version defined for an item at the demand site, a general BOM is used.</span></span> <span data-ttu-id="0a13c-109">Una L. MAT general no indica un sitio, y es válida para varios sitios.</span><span class="sxs-lookup"><span data-stu-id="0a13c-109">A general BOM does not state a site, and it is valid for multiple sites.</span></span> <span data-ttu-id="0a13c-110">Si hay una L. MAT general, se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0a13c-110">If there is a general BOM, it is used.</span></span>
-   <span data-ttu-id="0a13c-111">Si no hay ninguna L. MAT. general que se pueda usar, la expansión de la demanda se detiene en este punto.</span><span class="sxs-lookup"><span data-stu-id="0a13c-111">If there is no general BOM version to use, the demand explosion stops at this point.</span></span>

<span data-ttu-id="0a13c-112">Una versión de L. MAT válida, tanto si es específica del sitio como si es general, debe cumplir los criterios necesarios para la fecha y la cantidad.</span><span class="sxs-lookup"><span data-stu-id="0a13c-112">A valid BOM version, whether site-specific or general, must meet the required criteria for date and quantity.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]