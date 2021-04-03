---
title: Optimizar el rendimiento con tareas automáticas de limpieza
description: Este artículo explica cómo resolver algunos problemas de rendimiento con Microsoft Dynamics 365 Human Resources limpiando el historial de trabajos por lotes.
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
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 8fef2152f7c65a6678e6cb94da8ea2bbe99ea51d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466697"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="8372a-103">Optimizar el rendimiento con tareas automáticas de limpieza</span><span class="sxs-lookup"><span data-stu-id="8372a-103">Optimize performance with auto cleanup tasks</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8372a-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="8372a-104">**Issue**</span></span>

<span data-ttu-id="8372a-105">Microsoft Dynamics 365 Human Resources pueden experimentar problemas de rendimiento si el historial de trabajos por lotes crece demasiado.</span><span class="sxs-lookup"><span data-stu-id="8372a-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="8372a-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="8372a-106">**Cause**</span></span>

<span data-ttu-id="8372a-107">Los trabajos por lotes que se ejecutan con frecuencia pueden llevar al crecimiento insostenible del historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="8372a-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="8372a-108">Esto puede provocar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8372a-108">This can cause performance issues.</span></span> 

<span data-ttu-id="8372a-109">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="8372a-109">**Resolution**</span></span>

<span data-ttu-id="8372a-110">Programe una tarea automática para limpiar el historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="8372a-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="8372a-111">Se recomienda configurar la tarea para ejecutarse semanalmente, pero puede querer ejecutar la limpieza con más o menos frecuencia dependiendo de su entorno.</span><span class="sxs-lookup"><span data-stu-id="8372a-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="8372a-112">El procedimiento siguiente contiene nuestros valores recomendados, pero puede cambiar estos según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="8372a-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="8372a-113">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="8372a-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="8372a-114">En la barra **Buscar**, especifique **Limpieza del historial de trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="8372a-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Busque limpieza de historial de trabajos por lotes](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="8372a-116">En el **Límite de historial (días)**, especifique **30**.</span><span class="sxs-lookup"><span data-stu-id="8372a-116">In **History limit (days)**, enter **30**.</span></span>

   ![Establezca el límite del historial en 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="8372a-118">Seleccione **Funcionamiento en segundo plano** y después seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="8372a-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Establezca la periodicidad](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="8372a-120">En **Definir frecuencia**, establezca la **Fecha inicial** y **Hora de inicio** para producir durante los fines de semana o fuera del horario de oficina y después seleccione **SIN FECHA DE FINALIZACIÓN**.</span><span class="sxs-lookup"><span data-stu-id="8372a-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Defina la fecha y hora de la periodicidad](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="8372a-122">En **PATRÓN DE PERIODICIDAD**, seleccione **Días** y establezca **REPETICIÓN DESPUÉS DEL INTERVALO ESPECIFICADO** **7**.</span><span class="sxs-lookup"><span data-stu-id="8372a-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Establezca la limpieza para repetirse semanalmente](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="8372a-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8372a-124">Select **OK**.</span></span>

8. <span data-ttu-id="8372a-125">Modifique cualquier otro parámetro en **Funcionamiento en segundo plano** según sea necesario y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8372a-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]