---
title: Configurar integración de Common Data Service
description: Puede activar o desactivar la integración entre Common Data Service y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9ee4715526e18b33ae4b7e90b081ed5868bb19c
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527941"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="fdc52-104">Configurar integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fdc52-104">Configure Common Data Service integration</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="fdc52-105">Puede activar o desactivar la integración entre Common Data Service y Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="fdc52-106">También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="fdc52-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="fdc52-107">Cuando desactiva la integración, los usuarios pueden realizar cambios en Human Resources o Common Data Service, pero esos cambios no se sincronizan entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="fdc52-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="fdc52-108">De forma predeterminada, la integración entre Human Resources y Common Data Service está desactivada.</span><span class="sxs-lookup"><span data-stu-id="fdc52-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="fdc52-109">Es posible que desee desactivar la integración en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="fdc52-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="fdc52-110">Está completando datos a través del Marco de gestión de datos y debe importar los datos varias veces para que estén en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="fdc52-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="fdc52-111">Hay problemas con los datos en Human Resources o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fdc52-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="fdc52-112">Si desactiva la integración, puede eliminar un registro en un entorno sin eliminarlo en el otro.</span><span class="sxs-lookup"><span data-stu-id="fdc52-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="fdc52-113">Cuando vuelva a activar la integración, el registro en el entorno donde no se eliminó se sincronizará con el entorno donde se eliminó.</span><span class="sxs-lookup"><span data-stu-id="fdc52-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="fdc52-114">La sincronización comienza la próxima vez que se ejecuta el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="fdc52-115">Cuando desactive la integración de datos, asegúrese de no editar el mismo registro en ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="fdc52-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="fdc52-116">Cuando vuelva a activar la integración, el registro que editó por última vez se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="fdc52-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="fdc52-117">Por lo tanto, si no realizó los mismos cambios en el registro en ambos entornos, puede producirse la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="fdc52-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="fdc52-118">Acceder a la página de integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fdc52-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="fdc52-119">En la instancia de Human Resources donde desea ver o configurar opciones para la integración con Common Data Service, seleccione la ventana **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="fdc52-120">[![Ventana Administración del sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="fdc52-121">Seleccione la ficha **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="fdc52-122">[![Pestaña Vínculos](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="fdc52-123">Debajo de **Integraciones**, seleccione **Configuración de Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="fdc52-124">[![Vínculo de configuración de Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="fdc52-125">Activar o desactivar la integración de datos entre Human Resources y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fdc52-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="fdc52-126">Para activar la integración, establezca la opción **Permitir la integración con Common Data Service** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fdc52-127">Cuando active la integración, los datos se sincronizarán la próxima vez que se ejecute el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="fdc52-128">Todos los datos deben estar disponibles después de que se complete el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="fdc52-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="fdc52-129">Para desactivar la integración, configure la opción como **No**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="fdc52-130">[![Activar o desactivar la integración de Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

> [!WARNING]
> <span data-ttu-id="fdc52-131">Recomendamos encarecidamente desactivar la integración con Common Data Service al realizar tareas de migración de datos.</span><span class="sxs-lookup"><span data-stu-id="fdc52-131">We strongly recommend turning off Common Data Service integration while performing data migration tasks.</span></span> <span data-ttu-id="fdc52-132">Las grandes cargas de datos pueden afectar significativamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fdc52-132">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="fdc52-133">Por ejemplo, cargar 2000 trabajadores puede llevar varias horas cuando la integración está habilitada, y menos de una hora cuando está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fdc52-133">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="fdc52-134">Los números proporcionados en este ejemplo son solo para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="fdc52-134">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="fdc52-135">La cantidad exacta de tiempo que lleva importar registros puede variar mucho en función de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="fdc52-135">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="fdc52-136">Ver los detalles de la integración de datos</span><span class="sxs-lookup"><span data-stu-id="fdc52-136">View data integration details</span></span>

<span data-ttu-id="fdc52-137">En la ficha desplegable **Administración** de la página **Integración de Common Data Service**, puede ver cómo se vinculan los registros entre Human Resources y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fdc52-137">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="fdc52-138">Para ver los registros de una entidad, seleccione la entidad en el campo **Nombre de entidad CDS**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-138">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="fdc52-139">La cuadrícula muestra todos los registros que están vinculados a la entidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fdc52-139">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="fdc52-140">[![Ver los registros de una entidad](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-140">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="fdc52-141">No todas las entidades de Common Data Service están incluidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="fdc52-141">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="fdc52-142">Solo las entidades que admiten el uso de campos personalizados aparecen en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fdc52-142">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="fdc52-143">Hay nuevas entidades disponibles a través de lanzamientos continuos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-143">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="fdc52-144">La cuadrícula incluye los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="fdc52-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="fdc52-145">**Nombre de entidad de CDS**: nombre de la entidad en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fdc52-145">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="fdc52-146">**Referencia de entidad de CDS**: el identificador que Common Data Service utiliza para identificar un registro.</span><span class="sxs-lookup"><span data-stu-id="fdc52-146">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="fdc52-147">Este valor es equivalente a un valor **RecId** de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="fdc52-148">Puede encontrar el identificador cuando abre la entidad de Common Data Service en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="fdc52-148">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="fdc52-149">**Nombre de la entidad de Human Resources**: la entidad que sincronizó los datos con Common Data Service por última vez.</span><span class="sxs-lookup"><span data-stu-id="fdc52-149">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="fdc52-150">La entidad puede tener el prefijo de Common Data Service u otro prefijo.</span><span class="sxs-lookup"><span data-stu-id="fdc52-150">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="fdc52-151">**Referencia de Human Resources**: el valor **RecId** que está asociado con el registro en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="fdc52-152">**Eliminado de CDS**: un valor que indica si el registro se eliminó de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fdc52-152">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="fdc52-153">Eliminar la asociación de un registro en Human Resources de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fdc52-153">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="fdc52-154">Si experimenta problemas durante la sincronización de datos entre Human Resources y Common Data Service, puede resolverlos borrando el seguimiento y dejando que la tabla de seguimiento se vuelva a sincronizar.</span><span class="sxs-lookup"><span data-stu-id="fdc52-154">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="fdc52-155">Si elimina la asociación y luego cambia o elimina un registro en Common Data Service, los cambios no se sincronizarán con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-155">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="fdc52-156">Si realiza cambios en Human Resources, se crea un nuevo registro de seguimiento y el registro se actualiza en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="fdc52-156">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="fdc52-157">Para eliminar la asociación de un registro entre Human Resources y Common Data Service, seleccione la entidad en el campo **Nombre de entidad CDS** y luego seleccione **Borrar información de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-157">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="fdc52-158">[![Borrar la información de seguimiento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-158">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="fdc52-159">Para ejecutar una sincronización completa en la entidad después de borrar el seguimiento, consulte el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fdc52-159">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="fdc52-160">Sincronizar una entidad entre Human Resources y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="fdc52-160">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="fdc52-161">Use este procedimiento cuando:</span><span class="sxs-lookup"><span data-stu-id="fdc52-161">Use this procedure when:</span></span>

- <span data-ttu-id="fdc52-162">Cambios de Common Data Service tardan demasiado en aparecer en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fdc52-162">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="fdc52-163">Debe actualizar la tabla de seguimiento después de borrar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fdc52-163">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="fdc52-164">Para ejecutar una sincronización completa en una entidad entre Human Resources y Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="fdc52-164">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="fdc52-165">Seleccione la entidad en el campo **Nombre de entidad CDS**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-165">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="fdc52-166">Seleccione **Sincronizar ahora**.</span><span class="sxs-lookup"><span data-stu-id="fdc52-166">Select **Sync now**.</span></span>

<span data-ttu-id="fdc52-167">[![Ejecutar una sincronización completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="fdc52-167">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


