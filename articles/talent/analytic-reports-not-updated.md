---
title: "Los informes de análisis no están actualizados"
description: "Este tema explica qué hacer si los cambios en los datos de un cliente no se muestran en los espacios de trabajo de un cliente."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 46f426a4b0012e87b4d9d21032870ac7fc33c4ae
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="a691b-103">Los informes de análisis no están actualizados</span><span class="sxs-lookup"><span data-stu-id="a691b-103">Analytic reports are not updated</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a691b-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="a691b-104">**Issue**</span></span>

<span data-ttu-id="a691b-105">Los cambios de los datos de un cliente no aparecen en las pestañas **Análisis** de las áreas de trabajo de un cliente.</span><span class="sxs-lookup"><span data-stu-id="a691b-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="a691b-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a691b-106">**Cause**</span></span>

<span data-ttu-id="a691b-107">De forma predeterminada, los informes de Microsoft Power BI se actualizan cada cuatro horas, de acuerdo con la programación del trabajo por lotes de medida de implementación.</span><span class="sxs-lookup"><span data-stu-id="a691b-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="a691b-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="a691b-108">**Resolution**</span></span>

<span data-ttu-id="a691b-109">Este problema podría ser simplemente una cuestión de control de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a691b-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="a691b-110">Siga estos pasos para iniciar el trabajo por lotes y actualizar las áreas de trabajo de análisis.</span><span class="sxs-lookup"><span data-stu-id="a691b-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="a691b-111">Abre la página **Trabajos por lotes** en **Administración del sistema \> Vínculos \> Trabajos por lotes \> Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="a691b-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="a691b-112">De manera alternativa, use Búsqueda y escriba **Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="a691b-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="a691b-113">Encuentre el trabajo **Implementación de medida** en la lista.</span><span class="sxs-lookup"><span data-stu-id="a691b-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="a691b-114">Seleccione **Editar** en la parte superior de la página, y establezca la fecha /hora inicial programada a un valor que actualice el análisis más cercano a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="a691b-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Trabajos por lotes](media/batch-jobs.png)
