---
title: Optimice el rendimiento programando trabajos por lotes tras el horario laboral
description: Este tema explica cómo resolver problemas de rendimiento con Microsoft Dynamics 365 Human Resources programando trabajos por lotes de larga duración tras el horario laboral.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: f67b4b4c20345297f186c792fe2766c686e2ddbf
ms.sourcegitcommit: bdfc84aa7f607511981c0b2f20f03fabcb773510
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "3500514"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="c25a6-103">Optimice el rendimiento programando trabajos por lotes tras el horario laboral</span><span class="sxs-lookup"><span data-stu-id="c25a6-103">Optimize performance by scheduling batch jobs after hours</span></span>

## <a name="issue"></a><span data-ttu-id="c25a6-104">Emitir</span><span class="sxs-lookup"><span data-stu-id="c25a6-104">Issue</span></span>

<span data-ttu-id="c25a6-105">Microsoft Dynamics 365 Human Resources puede experimentar problemas de rendimiento si los trabajos por lotes de larga duración se ejecutan durante el horario comercial habitual.</span><span class="sxs-lookup"><span data-stu-id="c25a6-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="c25a6-106">Resolución</span><span class="sxs-lookup"><span data-stu-id="c25a6-106">Resolution</span></span>

<span data-ttu-id="c25a6-107">Programe los siguientes trabajos por lotes fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="c25a6-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="c25a6-108">También recomendamos revisar la frecuencia de los trabajos por lotes que se ejecutan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="c25a6-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="c25a6-109">Si es posible, reduzca la recurrencia del trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="c25a6-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="c25a6-110">En muchos casos, la frecuencia predeterminada es suficiente.</span><span class="sxs-lookup"><span data-stu-id="c25a6-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="c25a6-111">Los siguientes trabajos por lotes deben ejecutarse por la noche o tras las horas laborales.</span><span class="sxs-lookup"><span data-stu-id="c25a6-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="c25a6-112">Asegúrese de verificar la zona horaria para estos trabajos por lotes recurrentes.</span><span class="sxs-lookup"><span data-stu-id="c25a6-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="c25a6-113">Algunos trabajos por lotes pueden usar la hora estándar del Pacífico (PST).</span><span class="sxs-lookup"><span data-stu-id="c25a6-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="c25a6-114">Trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="c25a6-114">Batch job</span></span> | <span data-ttu-id="c25a6-115">Ocurrencia predeterminada</span><span class="sxs-lookup"><span data-stu-id="c25a6-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="c25a6-116">Limpieza del historial de trabajos por lotes</span><span class="sxs-lookup"><span data-stu-id="c25a6-116">Batch job history cleanup</span></span> | <span data-ttu-id="c25a6-117">1 vez al mes</span><span class="sxs-lookup"><span data-stu-id="c25a6-117">1 time per month</span></span> |
| <span data-ttu-id="c25a6-118">Limpieza de ubicación provisional de exportación</span><span class="sxs-lookup"><span data-stu-id="c25a6-118">Export staging cleanup</span></span> | <span data-ttu-id="c25a6-119">1 vez al día</span><span class="sxs-lookup"><span data-stu-id="c25a6-119">1 time per day</span></span> |
| <span data-ttu-id="c25a6-120">Sincronización de solicitud omitida de integración Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c25a6-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="c25a6-121">1 vez al día</span><span class="sxs-lookup"><span data-stu-id="c25a6-121">1 time per day</span></span> |
| <span data-ttu-id="c25a6-122">Trabajo del sistema de compresión de base de datos que necesita ejecutarse regularmente fuera del horario laboral</span><span class="sxs-lookup"><span data-stu-id="c25a6-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="c25a6-123">1 vez al día</span><span class="sxs-lookup"><span data-stu-id="c25a6-123">1 time per day</span></span> |
| <span data-ttu-id="c25a6-124">Trabajo del sistema de reconstrucción del índice de base de datos que necesita ejecutarse regularmente fuera del horario laboral</span><span class="sxs-lookup"><span data-stu-id="c25a6-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="c25a6-125">1 vez al día</span><span class="sxs-lookup"><span data-stu-id="c25a6-125">1 time per day</span></span> |

1. <span data-ttu-id="c25a6-126">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="c25a6-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="c25a6-127">En la barra **Buscar**, busque uno de los trabajos por lotes anteriores.</span><span class="sxs-lookup"><span data-stu-id="c25a6-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="c25a6-128">Seleccione **Funcionamiento en segundo plano** y después **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="c25a6-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Establezca la periodicidad](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="c25a6-130">En **Definir periodicidad**, establezca la **Fecha inicial** y **Hora de inicio** para tener lugar durante los fines de semana o fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="c25a6-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="c25a6-131">Seleccionar **Sin fecha final**.</span><span class="sxs-lookup"><span data-stu-id="c25a6-131">Select **No end date**.</span></span> 

   ![Defina la fecha y hora de la periodicidad](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="c25a6-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c25a6-133">Select **OK**.</span></span>

6. <span data-ttu-id="c25a6-134">Si hace falta, cambie cualquier otro parámetro en **Funcionamiento en segundo plano** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c25a6-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c25a6-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c25a6-135">Additional resources</span></span>

[<span data-ttu-id="c25a6-136">Optimizar el rendimiento con tareas automáticas de limpieza</span><span class="sxs-lookup"><span data-stu-id="c25a6-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)