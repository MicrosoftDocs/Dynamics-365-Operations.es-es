---
title: Optimizar el rendimiento con tareas automáticas de limpieza
description: Este tema explica cómo resolver algunos problemas de rendimiento con Microsoft Dynamics 365 Talent limpiando el historial de trabajos por lotes.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 1e9d237817024800ad9880ec58db3505ac1c493f
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2027093"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="69630-103">Optimizar el rendimiento con tareas automáticas de limpieza</span><span class="sxs-lookup"><span data-stu-id="69630-103">Optimize performance with auto cleanup tasks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69630-104">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="69630-104">**Issue**</span></span>

<span data-ttu-id="69630-105">Microsoft Dynamics 365 Talent pueden experimentar problemas de rendimiento si el historial de trabajos por lotes crece demasiado.</span><span class="sxs-lookup"><span data-stu-id="69630-105">Microsoft Dynamics 365 Talent can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="69630-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="69630-106">**Cause**</span></span>

<span data-ttu-id="69630-107">Los trabajos por lotes que se ejecutan con frecuencia pueden llevar al crecimiento insostenible del historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="69630-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="69630-108">Esto puede provocar problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69630-108">This can cause performance issues.</span></span> 

<span data-ttu-id="69630-109">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="69630-109">**Resolution**</span></span>

<span data-ttu-id="69630-110">Programe una tarea automática para limpiar el historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="69630-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="69630-111">Se recomienda configurar la tarea para ejecutarse semanalmente, pero puede querer ejecutar la limpieza con más o menos frecuencia dependiendo de su entorno.</span><span class="sxs-lookup"><span data-stu-id="69630-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="69630-112">El procedimiento siguiente contiene nuestros valores recomendados, pero puede cambiar estos según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="69630-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="69630-113">En Talent, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="69630-113">In Talent, select **System administration**.</span></span>

2. <span data-ttu-id="69630-114">En la barra **Buscar**, especifique **Limpieza del historial de trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="69630-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Busque limpieza de historial de trabajos por lotes](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="69630-116">En el **Límite de historial (días)**, especifique **30**.</span><span class="sxs-lookup"><span data-stu-id="69630-116">In **History limit (days)**, enter **30**.</span></span>

   ![Establezca el límite del historial en 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="69630-118">Seleccione **Funcionamiento en segundo plano** y después seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="69630-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Establezca la periodicidad](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="69630-120">En **Definir frecuencia**, establezca la **Fecha inicial** y **Hora de inicio** para producir durante los fines de semana o fuera del horario de oficina y después seleccione **SIN FECHA DE FINALIZACIÓN**.</span><span class="sxs-lookup"><span data-stu-id="69630-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Defina la fecha y hora de la periodicidad](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="69630-122">En **PATRÓN DE PERIODICIDAD**, seleccione **Días** y establezca **REPETICIÓN DESPUÉS DEL INTERVALO ESPECIFICADO** **7**.</span><span class="sxs-lookup"><span data-stu-id="69630-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Establezca la limpieza para repetirse semanalmente](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="69630-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69630-124">Select **OK**.</span></span>

8. <span data-ttu-id="69630-125">Modifique cualquier otro parámetro en **Funcionamiento en segundo plano** según sea necesario y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69630-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

