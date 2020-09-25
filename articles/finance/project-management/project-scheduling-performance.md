---
title: Rendimiento de la programación de recursos del proyecto
description: Este tema proporciona información sobre cómo mejorar el rendimiento de la programación de los recursos para una gran cantidad de proyectos.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760659"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="6a614-103">Rendimiento de la programación de recursos del proyecto</span><span class="sxs-lookup"><span data-stu-id="6a614-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="6a614-104">Los problemas de rendimiento relacionados con la programación de recursos pueden ocurrir cuando el número de proyectos llega a miles.</span><span class="sxs-lookup"><span data-stu-id="6a614-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="6a614-105">Para mejorar el rendimiento de la programación de los recursos, hay una función disponible que permite a los usuarios reducir el tiempo que lleva iniciar el formulario de disponibilidad de recursos.</span><span class="sxs-lookup"><span data-stu-id="6a614-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="6a614-106">Específicamente, esto elimina el proceso de sincronización de acumulación de capacidad de recursos y utiliza la tabla **ResProjectResource** para acelerar la búsqueda de recursos.</span><span class="sxs-lookup"><span data-stu-id="6a614-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="6a614-107">Tenga en cuenta que la tabla **ResRollup** la tabla ya no se utilizará.</span><span class="sxs-lookup"><span data-stu-id="6a614-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a614-108">Si existe una dependencia del proceso de sincronización de acumulación de capacidad de recursos o de la tabla **ResProjectResource**, no utilice esta función.</span><span class="sxs-lookup"><span data-stu-id="6a614-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="6a614-109">Habilitar la mejora del rendimiento de la programación de recursos</span><span class="sxs-lookup"><span data-stu-id="6a614-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="6a614-110">Para habilitar la mejora del rendimiento de la programación de recursos, complete los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="6a614-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="6a614-111">Vaya a **Administración de características** > **Todas** y en la lista de características, ubique **Habilitar la función de mejora del rendimiento de la programación de recursos del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a614-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="6a614-112">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="6a614-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a614-113">Si no puede encontrar la función en la lista, seleccione **Buscar actualizaciones** para actualizar la lista.</span><span class="sxs-lookup"><span data-stu-id="6a614-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="6a614-114">Actualice su navegador y luego vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Recursos del proyecto** > **Sincronizar la capacidad de los calendarios de recursos en todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="6a614-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="6a614-115">Establezca **Eliminar registros de capacidad existentes** en **Sí** para eliminar los datos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a614-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="6a614-116">Si desea generar datos incrementales, establezca la opción en **No**.</span><span class="sxs-lookup"><span data-stu-id="6a614-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="6a614-117">En el campo **Código de período**, seleccione el período en el que se deben generar los datos.</span><span class="sxs-lookup"><span data-stu-id="6a614-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="6a614-118">Si selecciona un código de período, no es necesario definir una fecha de inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="6a614-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="6a614-119">Si deja el campo **Código de período** en blanco, seleccione las fechas de inicio y finalización específicas para generar datos.</span><span class="sxs-lookup"><span data-stu-id="6a614-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="6a614-120">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a614-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="6a614-121">Esto distribuirá datos generales a la tabla **ResCalendarCapacity** en todas las empresas de su entorno, por lo que el trabajo por lotes solo debe ejecutarse en una entidad legal.</span><span class="sxs-lookup"><span data-stu-id="6a614-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="6a614-122">Los datos de este trabajo por lotes son necesarios para calcular la capacidad de recursos a través del calendario asociado.</span><span class="sxs-lookup"><span data-stu-id="6a614-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="6a614-123">Vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Recursos del proyecto** > **Completar los recursos del proyecto en todas las empresas** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a614-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="6a614-124">Este es el script de actualización de datos para datos generales en las tablas **ResProjectResource**, **ResCalendarDateTimeRange** y **ResEffectiveDateTimeRange**.</span><span class="sxs-lookup"><span data-stu-id="6a614-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="6a614-125">Los valores para el campo **PSAPRojSchedRole.RootActivity** también se actualizan.</span><span class="sxs-lookup"><span data-stu-id="6a614-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="6a614-126">Si no se ejecuta, recibirá una advertencia cuando intente ejecutar operaciones de programación de recursos.</span><span class="sxs-lookup"><span data-stu-id="6a614-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="6a614-127">Deshabilitar la mejora del rendimiento de la programación de recursos</span><span class="sxs-lookup"><span data-stu-id="6a614-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="6a614-128">Vaya a **Administración de características** > **Todas** y busque **Habilitar la función de mejora del rendimiento de la programación de recursos del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a614-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="6a614-129">Seleccione la característica y luego seleccione el botón **Deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="6a614-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="6a614-130">Actualice su navegador.</span><span class="sxs-lookup"><span data-stu-id="6a614-130">Refresh your browser.</span></span>
4. <span data-ttu-id="6a614-131">Vaya a **Administración de proyectos y contabilidad** > **Periódico** > **Sincronización de capacidad** > **Sincronizar acumulaciones de capacidad de recursos**.</span><span class="sxs-lookup"><span data-stu-id="6a614-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="6a614-132">En la página **Sincronización de acumulación de capacidad**, establezca **Eliminar registros de capacidad existentes** en **Sí** para eliminar los datos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6a614-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="6a614-133">Si desea generar datos incrementales, establezca la opción en **No**.</span><span class="sxs-lookup"><span data-stu-id="6a614-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="6a614-134">En el campo **Código de período**, seleccione el período en el que se deben generar los datos.</span><span class="sxs-lookup"><span data-stu-id="6a614-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="6a614-135">Si selecciona un código de período, no es necesario definir una fecha de inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="6a614-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="6a614-136">Si deja el campo **Código de período** en blanco, seleccione las fechas de inicio y finalización específicas para generar datos.</span><span class="sxs-lookup"><span data-stu-id="6a614-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="6a614-137">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a614-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a614-138">Esto distribuirá datos generales a la tabla **ResRollup** en todas las empresas de su entorno, por lo que el trabajo por lotes solo debe ejecutarse en una entidad legal.</span><span class="sxs-lookup"><span data-stu-id="6a614-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="6a614-139">Este trabajo por lotes es necesario para todas las vistas de **Disponibilidad de recursos**.</span><span class="sxs-lookup"><span data-stu-id="6a614-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="6a614-140">Si este trabajo por lotes no se ejecuta, los datos de **ResRollup** se generarán sobre la marcha, lo que puede llevar tiempo.</span><span class="sxs-lookup"><span data-stu-id="6a614-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>
