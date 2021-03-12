---
title: Sincronizar clasificaciones de producto en Dynamics 365 Commerce
description: Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7318d53535a93352425f811ec90572e65aeb696
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006294"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a><span data-ttu-id="fac13-103">Sincronizar clasificaciones de producto en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fac13-103">Sync product ratings in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fac13-104">Este tema describe cómo sincronizar las clasificaciones de productos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fac13-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fac13-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="fac13-105">Overview</span></span>

<span data-ttu-id="fac13-106">Para consumir clasificaciones de productos en omnicanales, como en punto de venta (PDV) y en centros de llamadas, las clasificaciones de productos del servicio de clasificaciones y revisiones deben importarse en la base de datos de canal de Commerce.</span><span class="sxs-lookup"><span data-stu-id="fac13-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Commerce channel database.</span></span> <span data-ttu-id="fac13-107">Cuando las clasificaciones de productos se vuelven disponibles en omnicanales, pueden ayudar a los clientes indirectamente durante sus interacciones con socios de ventas.</span><span class="sxs-lookup"><span data-stu-id="fac13-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="fac13-108">Este tema describe las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="fac13-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="fac13-109">Configure **Trabajo de sincronización de clasificaciones de productos** como un trabajo por lotes para sincronizar clasificaciones de productos desde el **servicio de clasificaciones y revisiones**.</span><span class="sxs-lookup"><span data-stu-id="fac13-109">Configure **Product ratings sync job** as a batch job to synchronize product ratings from the **Ratings and Reviews service**.</span></span>
1. <span data-ttu-id="fac13-110">Compruebe que el trabajo por lotes para la sincronización de clasificación de productos fue correcto.</span><span class="sxs-lookup"><span data-stu-id="fac13-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="fac13-111">Haga que las clasificaciones de productos estén disponibles en PDV.</span><span class="sxs-lookup"><span data-stu-id="fac13-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a><span data-ttu-id="fac13-112">Configurar un trabajo por lotes para sincronizar clasificaciones de productos</span><span class="sxs-lookup"><span data-stu-id="fac13-112">Configure a batch job to synchronize product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fac13-113">Antes de comenzar, asegúrese de que la versión 10.0.6 o posterior de Dynamics 365 Commerce está instalada.</span><span class="sxs-lookup"><span data-stu-id="fac13-113">Before you start, make sure that version 10.0.6 or later of Dynamics 365 Commerce is installed.</span></span>

### <a name="initialize-the-commerce-scheduler"></a><span data-ttu-id="fac13-114">Inicializar el programador de Commerce</span><span class="sxs-lookup"><span data-stu-id="fac13-114">Initialize the commerce scheduler</span></span>

<span data-ttu-id="fac13-115">Para inicializar el programador de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fac13-115">To initialize the commerce scheduler, follow these steps.</span></span>

1. <span data-ttu-id="fac13-116">Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Inicializar programador de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="fac13-116">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Initialize commerce scheduler**.</span></span> <span data-ttu-id="fac13-117">Como alternativa, busque “Inicializar programador de Commerce”.</span><span class="sxs-lookup"><span data-stu-id="fac13-117">Alternatively, search for "Initialize commerce scheduler."</span></span>
1. <span data-ttu-id="fac13-118">En el cuadro de diálogo **Inicializar el programador de Commerce**, asegúrese de que la opción **Configuración de la existente Eliminar** está establecida en **No** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fac13-118">In the **Initialize commerce scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="fac13-119">Comprobar el trabajo subordinado de RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="fac13-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="fac13-120">Para comprobar que existe el trabajo subordinado **RetailProductRating**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fac13-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="fac13-121">Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Trabajos subordinados del programador**.</span><span class="sxs-lookup"><span data-stu-id="fac13-121">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="fac13-122">Como alternativa, busque “Trabajos subordinados del programador”.</span><span class="sxs-lookup"><span data-stu-id="fac13-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="fac13-123">En la lista de trabajos subordinados, encuentre o busque el trabajo subordinado **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="fac13-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="fac13-124">La ilustración siguiente muestra un ejemplo de los detalles del trabajo subordinado en Commerce.</span><span class="sxs-lookup"><span data-stu-id="fac13-124">The following illustration shows an example of the subjob details in Commerce.</span></span>

![Detalles del trabajo subordinado de RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="fac13-126">Si no encuentra el trabajo subordinado **RetailProductRating**, es posible que ya haya ejecutado el trabajo **Sincronizar clasificaciones de producto** y el trabajo **1040 CDX** antes de haber inicializado el programador Commerce.</span><span class="sxs-lookup"><span data-stu-id="fac13-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the Commerce scheduler.</span></span> <span data-ttu-id="fac13-127">En este caso, siga estos pasos para ejecutar el trabajo **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="fac13-127">In this case, follow these steps to run the **Full data sync** job.</span></span>

> 1. <span data-ttu-id="fac13-128">Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canales**.</span><span class="sxs-lookup"><span data-stu-id="fac13-128">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span> <span data-ttu-id="fac13-129">Como alternativa, busque “Base de datos de canales”.</span><span class="sxs-lookup"><span data-stu-id="fac13-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="fac13-130">Seleccione la base de datos de canal que se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="fac13-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="fac13-131">En el panel de acciones, seleccione **Sincronización de datos completa**.</span><span class="sxs-lookup"><span data-stu-id="fac13-131">On the action pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="fac13-132">En el cuadro de diálogo desplegable **Seleccionar una programación de distribución**, seleccione **1040 - productos** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fac13-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="fac13-133">Repita los pasos del procedimiento anterior para comprobar que se ha creado el trabajo subordinado **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="fac13-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="fac13-134">Importar clasificaciones de productos</span><span class="sxs-lookup"><span data-stu-id="fac13-134">Import product ratings</span></span>

<span data-ttu-id="fac13-135">Para importar clasificaciones de productos en Commerce desde el servicio de clasificaciones y revisiones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fac13-135">To import product ratings into Commerce from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="fac13-136">Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de tareas Retail \> Sincronizar trabajo de clasificaciones de productos**.</span><span class="sxs-lookup"><span data-stu-id="fac13-136">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="fac13-137">Como alternativa, busque “Sincronizar trabajo de clasificaciones de productos”.</span><span class="sxs-lookup"><span data-stu-id="fac13-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="fac13-138">En el cuadro de diálogo **Extraer clasificaciones de productos**, en la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="fac13-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="fac13-139">En el cuadro de diálogo **Definir periodicidad**, configure un patrón de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="fac13-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="fac13-140">(El valor sugerido es dos horas). No programe una periodicidad inferior a una hora.</span><span class="sxs-lookup"><span data-stu-id="fac13-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="fac13-141">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fac13-141">Select **OK**.</span></span>
1. <span data-ttu-id="fac13-142">Establezca la opción **Procesamiento por lotes** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fac13-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="fac13-143">Este valor ayuda a garantizar que podrá auditar los registros y comprobar el estado de las ejecuciones de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="fac13-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="fac13-144">Seleccione **Aceptar** para programar el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="fac13-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="fac13-145">La ilustración siguiente muestra un ejemplo de la configuración de trabajos por lotes en Commerce.</span><span class="sxs-lookup"><span data-stu-id="fac13-145">The following illustration shows an example of batch job configuration in Commerce.</span></span>

![Configuración del trabajo por lotes de Sincronizar clasificaciones de productos](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="fac13-147">Comprobar que el trabajo por lotes para la sincronización de la clasificación de productos fue correcto</span><span class="sxs-lookup"><span data-stu-id="fac13-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="fac13-148">Para comprobar que el trabajo por lotes **Sincronizar clasificaciones de productos** fue correcto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fac13-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="fac13-149">Vaya a **Retail y Commerce \> Administrador del sistema \> Consultas \> Trabajos por lotes** o, si usa una referencia de almacén (SKU) solo de Commerce, **Retail y Commerce \> Consultas e informes \> Trabajos por lotes** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fac13-149">Go to **Retail and Commerce \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Commerce-only stock keeping unit (SKU), **Retail and Commerce \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="fac13-150">Como alternativa, busque “Trabajos por lotes”.</span><span class="sxs-lookup"><span data-stu-id="fac13-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="fac13-151">Para ver los detalles del trabajo por lotes, en la lista de trabajos por lotes, en la columna **Descripción del trabajo**, busque una descripción que contenga “Extraer clasificaciones de productos”.</span><span class="sxs-lookup"><span data-stu-id="fac13-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="fac13-152">Seleccione el id. de trabajo para ver los detalles del trabajo por lotes, como la fecha u hora inicial programada y el texto de periodicidad.</span><span class="sxs-lookup"><span data-stu-id="fac13-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="fac13-153">La ilustración siguiente se muestra un ejemplo de los detalles del trabajo por lotes en Commerce cuando el trabajo por lotes se programa para que ejecutarse en intervalos de dos horas.</span><span class="sxs-lookup"><span data-stu-id="fac13-153">The following illustration shows an example of the batch job details in Commerce when the batch job is scheduled to run at two-hour intervals.</span></span>

![Detalles del trabajo por lotes de Sincronizar clasificaciones de producto](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="fac13-155">Hacer que las clasificaciones de productos estén disponibles en PDV</span><span class="sxs-lookup"><span data-stu-id="fac13-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="fac13-156">La solución de clasificaciones y revisiones en Dynamics 365 Commerce es una solución de omnicanal.</span><span class="sxs-lookup"><span data-stu-id="fac13-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="fac13-157">Sin embargo, las clasificaciones de productos no se muestran en PDV de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fac13-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="fac13-158">Para ayudar a los clientes de tiendas a ver las clasificaciones y las revisiones cuando les ayudan los socios de ventas, debe activar las clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="fac13-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="fac13-159">Para activar clasificaciones de productos en el PDV, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fac13-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="fac13-160">Vaya a **Retail y Commerce \> Configuración de Commerce \> Parámetros \> Parámetros de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="fac13-160">Go to **Retail and Commerce \> Commerce setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="fac13-161">Como alternativa, busque "Parámetros de Commerce”.</span><span class="sxs-lookup"><span data-stu-id="fac13-161">Alternatively, search for "Commerce parameters."</span></span>
1. <span data-ttu-id="fac13-162">En la pestaña **Parámetros de configuración**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fac13-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="fac13-163">Escriba un nombre como **RatingsAndReviews.EnableProductRatingsForRetailStores** y establezca el valor en **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="fac13-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="fac13-164">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fac13-164">Select **Save**.</span></span>
1. <span data-ttu-id="fac13-165">Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="fac13-165">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span> <span data-ttu-id="fac13-166">Como alternativa, busque “Programación de distribución”.</span><span class="sxs-lookup"><span data-stu-id="fac13-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="fac13-167">En la lista de trabajos, seleccione **1110** (**Configuración global**) y después seleccione **Ejecutar ahora**.</span><span class="sxs-lookup"><span data-stu-id="fac13-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="fac13-168">Una vez que el trabajo se haya ejecutado correctamente, compruebe que las clasificaciones de productos se mostrarán ahora en PDV.</span><span class="sxs-lookup"><span data-stu-id="fac13-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="fac13-169">La ilustración siguiente muestra un ejemplo de la configuración de los parámetros de Commerce para activar las clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="fac13-169">The following illustration shows an example of the configuration of the Commerce parameters to turn on product ratings at the POS.</span></span>

![Configuración de los parámetros de Commerce para las clasificaciones de productos en PDV](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="fac13-171">En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en el PDV.</span><span class="sxs-lookup"><span data-stu-id="fac13-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Clasificaciones de productos en el PDV](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="fac13-173">En la siguiente ilustración se muestra un ejemplo de clasificaciones de productos en los canales del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fac13-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Clasificaciones de productos en un canal de centro de llamadas](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="fac13-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fac13-175">Additional resources</span></span>

[<span data-ttu-id="fac13-176">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="fac13-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="fac13-177">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="fac13-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="fac13-178">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="fac13-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="fac13-179">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="fac13-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
