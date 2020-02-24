---
title: Configurar integración de Common Data Service
description: Puede activar o desactivar la integración entre Common Data Service y una instancia de Microsoft Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010440"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="16e6a-104">Configurar integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="16e6a-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="16e6a-105">Puede activar o desactivar la integración entre Common Data Service y una instancia de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="16e6a-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="16e6a-106">También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una entidad para ayudar a solucionar problemas de datos entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="16e6a-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="16e6a-107">Cuando desactiva la integración, los usuarios pueden realizar cambios en Human Resources o Common Data Service, pero esos cambios no se sincronizan entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="16e6a-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="16e6a-108">Por defecto, la integración entre Human Resources y Common Data Service está desactivada o activada, dependiendo de la presencia de datos de demostración en los entornos:</span><span class="sxs-lookup"><span data-stu-id="16e6a-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="16e6a-109">**Desactivada** para nuevos entornos que no incluyen datos de demostración</span><span class="sxs-lookup"><span data-stu-id="16e6a-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="16e6a-110">**Activada** para nuevos entornos que incluyen datos de demostración</span><span class="sxs-lookup"><span data-stu-id="16e6a-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="16e6a-111">Los nuevos entornos que incluyen datos de demostración comenzarán a sincronizarse cuando se aprovisionen.</span><span class="sxs-lookup"><span data-stu-id="16e6a-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="16e6a-112">Es posible que desee desactivar la integración en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="16e6a-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="16e6a-113">Está completando datos a través del Marco de gestión de datos y debe importar los datos varias veces para que estén en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="16e6a-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="16e6a-114">Hay problemas con los datos en Human Resources o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="16e6a-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="16e6a-115">Si desactiva la integración, puede eliminar un registro en un entorno sin eliminarlo en el otro.</span><span class="sxs-lookup"><span data-stu-id="16e6a-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="16e6a-116">Cuando vuelva a activar la integración, el registro en el entorno donde no se eliminó se sincronizará con el entorno donde se eliminó.</span><span class="sxs-lookup"><span data-stu-id="16e6a-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="16e6a-117">La sincronización comienza la próxima vez que se ejecuta el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="16e6a-118">Cuando desactive la integración de datos, asegúrese de no editar el mismo registro en ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="16e6a-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="16e6a-119">Cuando vuelva a activar la integración, el registro que editó por última vez se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="16e6a-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="16e6a-120">Por lo tanto, si no realizó los mismos cambios en el registro en ambos entornos, puede producirse la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="16e6a-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="16e6a-121">Acceder a la página de integración de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="16e6a-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="16e6a-122">En la instancia de Human Resources donde desea ver o configurar opciones para la integración con Common Data Service, seleccione la ventana **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="16e6a-123">[![Ventana Administración del sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="16e6a-124">Seleccione la ficha **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="16e6a-125">[![Pestaña Vínculos](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="16e6a-126">Debajo de **Integraciones**, seleccione **Configuración de Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="16e6a-127">[![Vínculo de configuración de Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="16e6a-128">Activar o desactivar la integración de datos entre Human Resources y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="16e6a-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="16e6a-129">Para activar la integración, establezca la opción **Permitir la integración con Common Data Service** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="16e6a-130">Cuando active la integración, los datos se sincronizarán la próxima vez que se ejecute el trabajo por lotes **La integración de Common Data Service omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="16e6a-131">Todos los datos deben estar disponibles después de que se complete el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="16e6a-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="16e6a-132">Para desactivar la integración, configure la opción como **No**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="16e6a-133">[![Activar o desactivar la integración de Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="16e6a-134">Ver los detalles de la integración de datos</span><span class="sxs-lookup"><span data-stu-id="16e6a-134">View data integration details</span></span>

<span data-ttu-id="16e6a-135">En la ficha desplegable **Administración** de la página **Integración de Common Data Service**, puede ver cómo se vinculan los registros entre Human Resources y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="16e6a-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="16e6a-136">Para ver los registros de una entidad, seleccione la entidad en el campo **Nombre de entidad CDS**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="16e6a-137">La cuadrícula muestra todos los registros que están vinculados a la entidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="16e6a-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="16e6a-138">[![Ver los registros de una entidad](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="16e6a-139">No todas las entidades de Common Data Service están incluidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="16e6a-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="16e6a-140">Solo las entidades que admiten el uso de campos personalizados aparecen en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="16e6a-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="16e6a-141">Hay nuevas entidades disponibles a través de lanzamientos continuos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="16e6a-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="16e6a-142">La cuadrícula incluye los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="16e6a-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="16e6a-143">**Nombre de entidad de CDS**: nombre de la entidad en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="16e6a-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="16e6a-144">**Referencia de entidad de CDS**: el identificador que Common Data Service utiliza para identificar un registro.</span><span class="sxs-lookup"><span data-stu-id="16e6a-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="16e6a-145">Este valor es equivalente a un valor **RecId** de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="16e6a-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="16e6a-146">Puede encontrar el identificador cuando abre la entidad de Common Data Service en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="16e6a-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="16e6a-147">**Nombre de la entidad de Human Resources**: la entidad que sincronizó los datos con Common Data Service por última vez.</span><span class="sxs-lookup"><span data-stu-id="16e6a-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="16e6a-148">La entidad puede tener el prefijo de Common Data Service u otro prefijo.</span><span class="sxs-lookup"><span data-stu-id="16e6a-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="16e6a-149">**Referencia de Human Resources**: el valor **RecId** que está asociado con el registro en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="16e6a-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="16e6a-150">**Eliminado de CDS**: un valor que indica si el registro se eliminó de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="16e6a-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="16e6a-151">Eliminar la asociación de un registro en Human Resources de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="16e6a-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="16e6a-152">Si experimenta problemas durante la sincronización de datos entre Human Resources y Common Data Service, puede resolverlos borrando el seguimiento y dejando que la tabla de seguimiento se vuelva a sincronizar.</span><span class="sxs-lookup"><span data-stu-id="16e6a-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="16e6a-153">Si elimina la asociación y luego cambia o elimina un registro en Common Data Service, los cambios no se sincronizarán con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="16e6a-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="16e6a-154">Si realiza cambios en Human Resources, se crea un nuevo registro de seguimiento y el registro se actualiza en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="16e6a-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="16e6a-155">Para eliminar la asociación de un registro entre Human Resources y Common Data Service, seleccione la entidad en el campo **Nombre de entidad CDS** y luego seleccione **Borrar información de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="16e6a-156">[![Borrar la información de seguimiento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="16e6a-157">Para ejecutar una sincronización completa en la entidad después de borrar el seguimiento, consulte el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="16e6a-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="16e6a-158">Sincronizar una entidad entre Human Resources y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="16e6a-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="16e6a-159">Use este procedimiento si los cambios de Common Data Service tardan demasiado en aparecer en Human Resources o si debe actualizar la tabla de seguimiento después de borrar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="16e6a-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="16e6a-160">Para ejecutar una sincronización completa en una entidad entre Human Resources y Common Data Service, seleccione la entidad en el campo **Nombre de entidad CDS** y luego seleccione **Sincronizar ahora**.</span><span class="sxs-lookup"><span data-stu-id="16e6a-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="16e6a-161">[![Ejecutar una sincronización completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="16e6a-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


