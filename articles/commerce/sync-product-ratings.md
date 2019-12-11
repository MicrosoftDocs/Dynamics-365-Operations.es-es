---
title: Sincronizar clasificaciones de producto en Dynamics 365 Retail
description: Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698174"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a><span data-ttu-id="68218-103">Sincronizar clasificaciones de producto en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="68218-103">Sync product ratings in Dynamics 365 Retail</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="68218-104">Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="68218-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="68218-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="68218-105">Overview</span></span>

<span data-ttu-id="68218-106">Para consumir clasificaciones de productos en omnicanales, como en punto de venta (PDV) y en centros de llamadas, las clasificaciones de productos del servicio de clasificaciones y revisiones deben importarse en la base de datos de canal de Retail.</span><span class="sxs-lookup"><span data-stu-id="68218-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Retail channel database.</span></span> <span data-ttu-id="68218-107">Cuando las clasificaciones de productos se vuelven disponibles en omnicanales, pueden ayudar a los clientes indirectamente durante sus interacciones con socios de ventas.</span><span class="sxs-lookup"><span data-stu-id="68218-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="68218-108">Este tema describe las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="68218-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="68218-109">Configurar un trabajo por lotes de Retail para importar clasificaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="68218-109">Configure a Retail batch job to import product ratings.</span></span>
1. <span data-ttu-id="68218-110">Compruebe que el trabajo por lotes para la sincronización de clasificación de productos fue correcto.</span><span class="sxs-lookup"><span data-stu-id="68218-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="68218-111">Haga que las clasificaciones de productos estén disponibles en PDV.</span><span class="sxs-lookup"><span data-stu-id="68218-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a><span data-ttu-id="68218-112">Configurar un trabajo por lotes de Retail para importar clasificaciones de productos</span><span class="sxs-lookup"><span data-stu-id="68218-112">Configure a Retail batch job to import product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68218-113">Antes de comenzar, asegúrese de que la versión 10.0.6 o posterior de Retail está instalada.</span><span class="sxs-lookup"><span data-stu-id="68218-113">Before you start, make sure that version 10.0.6 or later of Retail is installed.</span></span>

### <a name="initialize-the-retail-scheduler"></a><span data-ttu-id="68218-114">Inicializar el Programador de tareas Retail</span><span class="sxs-lookup"><span data-stu-id="68218-114">Initialize the retail scheduler</span></span>

<span data-ttu-id="68218-115">Para inicializar el Programador de tareas Retail, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68218-115">To initialize the retail scheduler, follow these steps.</span></span>

1. <span data-ttu-id="68218-116">Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Inicializar el Programador de tareas Retail**.</span><span class="sxs-lookup"><span data-stu-id="68218-116">Go to **Retail \> Headquarters setup \> Retail scheduler \> Initialize retail scheduler**.</span></span> <span data-ttu-id="68218-117">Como alternativa, busque “Inicializar el Programador de tareas Retail”.</span><span class="sxs-lookup"><span data-stu-id="68218-117">Alternatively, search for "Initialize retail scheduler."</span></span>
1. <span data-ttu-id="68218-118">En el cuadro de diálogo **Inicializar el Programador de tareas Retail**, asegúrese de que la opción **Configuración de la existente Eliminar** está establecida en **No** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68218-118">In the **Initialize retail scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="68218-119">Comprobar el trabajo subordinado de RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="68218-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="68218-120">Para comprobar que existe el trabajo subordinado **RetailProductRating**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68218-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="68218-121">Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Trabajos subordinados del programador**.</span><span class="sxs-lookup"><span data-stu-id="68218-121">Go to **Retail \> Headquarters setup \> Retail scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="68218-122">Como alternativa, busque “Trabajos subordinados del programador”.</span><span class="sxs-lookup"><span data-stu-id="68218-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="68218-123">En la lista de trabajos subordinados, encuentre o busque el trabajo subordinado **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="68218-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="68218-124">La ilustración siguiente muestra un ejemplo de los detalles del trabajo subordinado en Retail.</span><span class="sxs-lookup"><span data-stu-id="68218-124">The following illustration shows an example of the subjob details in Retail.</span></span>

![Detalles del trabajo subordinado de RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="68218-126">Si no encuentra el trabajo subordinado **RetailProductRating**, es posible que ya haya ejecutado el trabajo **Sincronizar clasificaciones de producto** y el trabajo **1040 CDX** antes de haber inicializado el Programador de tareas Retail.</span><span class="sxs-lookup"><span data-stu-id="68218-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the retail scheduler.</span></span> <span data-ttu-id="68218-127">En este caso, siga estos pasos para ejecutar el trabajo **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="68218-127">In this case, follow these steps to run the **Full data sync** job.</span></span>
>
> 1. <span data-ttu-id="68218-128">Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Base de datos de canales**.</span><span class="sxs-lookup"><span data-stu-id="68218-128">Go to **Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span> <span data-ttu-id="68218-129">Como alternativa, busque “Base de datos de canales”.</span><span class="sxs-lookup"><span data-stu-id="68218-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="68218-130">Seleccione la base de datos de canal que se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="68218-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="68218-131">En el panel de acciones, seleccione **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="68218-131">On the Action Pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="68218-132">En el cuadro de diálogo desplegable **Seleccionar una programación de distribución**, seleccione **1040 - productos** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68218-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="68218-133">Repita los pasos del procedimiento anterior para comprobar que se ha creado el trabajo subordinado **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="68218-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="68218-134">Importar clasificaciones de productos</span><span class="sxs-lookup"><span data-stu-id="68218-134">Import product ratings</span></span>

<span data-ttu-id="68218-135">Para importar clasificaciones de productos en Retail desde el servicio de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68218-135">To import product ratings into Retail from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="68218-136">Vaya a **Retail \> Configuración de sede central \> Programador de tareas Retail \> Sincronizar trabajo de clasificaciones de productos**.</span><span class="sxs-lookup"><span data-stu-id="68218-136">Go to **Retail \> Headquarters setup \> Retail scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="68218-137">Como alternativa, busque “Sincronizar trabajo de clasificaciones de productos”.</span><span class="sxs-lookup"><span data-stu-id="68218-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="68218-138">En el cuadro de diálogo **Extraer clasificaciones de productos**, en la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="68218-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="68218-139">En el cuadro de diálogo **Definir periodicidad**, configure un patrón de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="68218-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="68218-140">(El valor sugerido es dos horas). No programe una periodicidad inferior a una hora.</span><span class="sxs-lookup"><span data-stu-id="68218-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="68218-141">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68218-141">Select **OK**.</span></span>
1. <span data-ttu-id="68218-142">Establezca la opción **Procesamiento por lotes** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="68218-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="68218-143">Este valor ayuda a garantizar que podrá auditar los registros y comprobar el estado de las ejecuciones de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="68218-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="68218-144">Seleccione **Aceptar** para programar el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="68218-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="68218-145">La ilustración siguiente muestra un ejemplo de la configuración de trabajos por lotes en Retail.</span><span class="sxs-lookup"><span data-stu-id="68218-145">The following illustration shows an example of batch job configuration in Retail.</span></span>

![Configuración del trabajo por lotes de Sincronizar clasificaciones de productos](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="68218-147">Comprobar que el trabajo por lotes para la sincronización de la clasificación de productos fue correcto</span><span class="sxs-lookup"><span data-stu-id="68218-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="68218-148">Para comprobar que el trabajo por lotes **Sincronizar clasificaciones de productos** fue correcto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68218-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="68218-149">Vaya a **Retail \> Administrador del sistema \> Consultas \> Trabajos por lotes** o, si usa una referencia de almacén (SKU) solo de Retail, **Retail \> Consultas e informes \> Trabajos por lotes** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="68218-149">Go to **Retail \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Retail-only stock keeping unit (SKU), **Retail \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="68218-150">Como alternativa, busque “Trabajos por lotes”.</span><span class="sxs-lookup"><span data-stu-id="68218-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="68218-151">Para ver los detalles del trabajo por lotes, en la lista de trabajos por lotes, en la columna **Descripción del trabajo**, busque una descripción que contenga “Extraer clasificaciones de productos”.</span><span class="sxs-lookup"><span data-stu-id="68218-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="68218-152">Seleccione el id. de trabajo para ver los detalles del trabajo por lotes, como la fecha u hora inicial programada y el texto de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="68218-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="68218-153">La ilustración siguiente se muestra un ejemplo de los detalles del trabajo por lotes en Retail cuando el trabajo por lotes se programa para que ejecutarse en intervalos de dos horas.</span><span class="sxs-lookup"><span data-stu-id="68218-153">The following illustration shows an example of the batch job details in Retail when the batch job is scheduled to run at two-hour intervals.</span></span>

![Detalles del trabajo por lotes de Sincronizar clasificaciones de producto](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="68218-155">Hacer que las clasificaciones de productos estén disponibles en PDV</span><span class="sxs-lookup"><span data-stu-id="68218-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="68218-156">La solución de clasificaciones y revisiones en Dynamics 365 Commerce es una solución de omnicanal.</span><span class="sxs-lookup"><span data-stu-id="68218-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="68218-157">Sin embargo, las clasificaciones de productos no se muestran en PDV de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="68218-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="68218-158">Para ayudar a los clientes de tiendas a ver las clasificaciones y las revisiones cuando les ayudan los socios de ventas, debe activar las clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="68218-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="68218-159">Para activar clasificaciones de productos en el PDV, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68218-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="68218-160">Vaya a **Retail \> Configuración de Retail \> Parámetros \> Parámetros comerciales**.</span><span class="sxs-lookup"><span data-stu-id="68218-160">Go to **Retail \> Retail setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="68218-161">Como alternativa, busque "Parámetros comerciales”.</span><span class="sxs-lookup"><span data-stu-id="68218-161">Alternatively, search for "Retail parameters."</span></span>
1. <span data-ttu-id="68218-162">En la pestaña **Parámetros de configuración**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="68218-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="68218-163">Escriba un nombre como **RatingsAndReviews.EnableProductRatingsForRetailStores** y establezca el valor en **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="68218-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="68218-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68218-164">Select **Save**.</span></span>
1. <span data-ttu-id="68218-165">Vaya a **Retail \> TI de Retail \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="68218-165">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span> <span data-ttu-id="68218-166">Como alternativa, busque “Programación de distribución”.</span><span class="sxs-lookup"><span data-stu-id="68218-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="68218-167">En la lista de trabajos, seleccione **1110** (**Configuración global**) y después seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="68218-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="68218-168">Una vez que el trabajo se haya ejecutado correctamente, compruebe que las clasificaciones de productos se mostrarán ahora en PDV.</span><span class="sxs-lookup"><span data-stu-id="68218-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="68218-169">La ilustración siguiente muestra un ejemplo de la configuración de los parámetros de Retail para activar las clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="68218-169">The following illustration shows an example of the configuration of the Retail parameters to turn on product ratings at the POS.</span></span>

![Configuración de los parámetros de Retail para las clasificaciones de productos en PDV](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="68218-171">En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="68218-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Clasificaciones de productos en el PDV](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="68218-173">En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en los canales del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="68218-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Clasificaciones de productos en un canal de centro de llamadas](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="68218-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="68218-175">Additional resources</span></span>

[<span data-ttu-id="68218-176">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="68218-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="68218-177">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="68218-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="68218-178">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="68218-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="68218-179">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="68218-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
