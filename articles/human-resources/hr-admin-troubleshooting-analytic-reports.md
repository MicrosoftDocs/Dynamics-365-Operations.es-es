---
title: Solucionar problemas de informes analíticos
description: Este artículo explica qué hacer si los cambios en los datos de un cliente no se muestran en los espacios de trabajo de un cliente.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e0befe1a35aa46b2eabb4516559fe07ce27e9f18
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466673"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="94fad-103">Solucionar problemas de informes analíticos</span><span class="sxs-lookup"><span data-stu-id="94fad-103">Troubleshoot analytic reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="94fad-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="94fad-104">**Issue**</span></span>

<span data-ttu-id="94fad-105">Los cambios de los datos de un cliente no aparecen en las pestañas **Análisis** de las áreas de trabajo de un cliente.</span><span class="sxs-lookup"><span data-stu-id="94fad-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="94fad-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="94fad-106">**Cause**</span></span>

<span data-ttu-id="94fad-107">De forma predeterminada, los informes de Microsoft Power BI se actualizan cada cuatro horas, de acuerdo con la programación del trabajo por lotes de medida de implementación.</span><span class="sxs-lookup"><span data-stu-id="94fad-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="94fad-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="94fad-108">**Resolution**</span></span>

<span data-ttu-id="94fad-109">Este problema podría ser simplemente una cuestión de control de tiempo.</span><span class="sxs-lookup"><span data-stu-id="94fad-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="94fad-110">Siga estos pasos para iniciar el trabajo por lotes y actualizar las áreas de trabajo de análisis.</span><span class="sxs-lookup"><span data-stu-id="94fad-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="94fad-111">Abre la página **Trabajos por lotes** en **Administración del sistema \> Vínculos \> Trabajos por lotes \> Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="94fad-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="94fad-112">De manera alternativa, use Búsqueda y escriba **Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="94fad-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="94fad-113">Encuentre el trabajo **Implementación de medida** en la lista.</span><span class="sxs-lookup"><span data-stu-id="94fad-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="94fad-114">Seleccione **Editar** en la parte superior de la página, y establezca la fecha /hora inicial programada a un valor que actualice el análisis más cercano a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="94fad-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Trabajos por lotes](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]