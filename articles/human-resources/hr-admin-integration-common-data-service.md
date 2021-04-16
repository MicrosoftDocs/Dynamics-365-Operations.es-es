---
title: Configurar integración de Dataverse
description: Puede activar o desactivar la integración entre Microsoft Dataverse y Dynamics 365 Human Resources. También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una tabla para ayudar a solucionar problemas de datos entre los dos entornos.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 080f66e4e13df44a77f0499c6d69686f0e3d7021
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801200"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="e69e1-104">Configurar integración de Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e69e1-105">Puede activar o desactivar la integración entre Microsoft Dataverse y Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="e69e1-106">También puede ver los detalles de sincronización, borrar los datos de seguimiento y volver a sincronizar una tabla para ayudar a solucionar problemas de datos entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="e69e1-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="e69e1-107">Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="e69e1-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="e69e1-108">Cuando desactiva la integración, los usuarios pueden realizar cambios en Human Resources o Dataverse, pero esos cambios no se sincronizan entre los dos entornos.</span><span class="sxs-lookup"><span data-stu-id="e69e1-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="e69e1-109">De forma predeterminada, la integración entre Human Resources y Dataverse está desactivada.</span><span class="sxs-lookup"><span data-stu-id="e69e1-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="e69e1-110">Es posible que desee desactivar la integración en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="e69e1-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="e69e1-111">Está completando datos a través del Marco de gestión de datos y debe importar los datos varias veces para que estén en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="e69e1-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="e69e1-112">Hay problemas con los datos en Human Resources o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="e69e1-113">Si desactiva la integración, puede eliminar un registro en un entorno sin eliminarlo en el otro.</span><span class="sxs-lookup"><span data-stu-id="e69e1-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="e69e1-114">Cuando vuelva a activar la integración, el registro en el entorno donde no se eliminó se sincronizará con el entorno donde se eliminó.</span><span class="sxs-lookup"><span data-stu-id="e69e1-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="e69e1-115">La sincronización comienza la próxima vez que se ejecuta el trabajo por lotes **La integración de Dataverse omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="e69e1-116">Cuando desactive la integración de datos, asegúrese de no editar el mismo registro en ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="e69e1-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="e69e1-117">Cuando vuelva a activar la integración, el registro que editó por última vez se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="e69e1-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="e69e1-118">Por lo tanto, si no realizó los mismos cambios en el registro en ambos entornos, puede producirse la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="e69e1-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="e69e1-119">Acceder a la página de integración de Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="e69e1-120">En la instancia de Human Resources donde desea ver o configurar opciones para la integración con Dataverse, seleccione la ventana **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="e69e1-121">[![Ventana Administración del sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="e69e1-122">Seleccione la ficha **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="e69e1-123">[![Pestaña Vínculos](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="e69e1-124">Debajo de **Integraciones**, seleccione **Configuración de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="e69e1-125">[![Vínculo de configuración de Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="e69e1-126">Activar o desactivar la integración de datos entre Human Resources y Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="e69e1-127">Para activar la integración, establezca la opción **Habilitar la integración de Dataverse** en **Sí** en la página **Integración de Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e69e1-128">Cuando active la integración, los datos se sincronizarán la próxima vez que se ejecute el trabajo por lotes **La integración de Dataverse omitió la solicitud de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="e69e1-129">Todos los datos deben estar disponibles después de que se complete el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="e69e1-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="e69e1-130">Para desactivar la integración, configure la opción como **No**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="e69e1-131">[![Activar o desactivar la integración de Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="e69e1-132">Recomendamos encarecidamente desactivar la integración con Dataverse al realizar tareas de migración de datos.</span><span class="sxs-lookup"><span data-stu-id="e69e1-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="e69e1-133">Las grandes cargas de datos pueden afectar significativamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e69e1-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="e69e1-134">Por ejemplo, cargar 2000 trabajadores puede llevar varias horas cuando la integración está habilitada, y menos de una hora cuando está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e69e1-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="e69e1-135">Los números proporcionados en este ejemplo son solo para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="e69e1-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="e69e1-136">La cantidad exacta de tiempo que lleva importar registros puede variar mucho en función de muchos factores.</span><span class="sxs-lookup"><span data-stu-id="e69e1-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="e69e1-137">Ver los detalles de la integración de datos</span><span class="sxs-lookup"><span data-stu-id="e69e1-137">View data integration details</span></span>

<span data-ttu-id="e69e1-138">En la ficha desplegable **Administración** de la página **Integración de Microsoft Dataverse**, puede ver cómo se vinculan las filas entre Human Resources y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="e69e1-139">Para ver las filas de una tabla, seleccione la tabla en el campo **Tabla de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="e69e1-140">La cuadrícula muestra todas las filas que están vinculadas a la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e69e1-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="e69e1-141">No todas las tablas de Dataverse están incluidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="e69e1-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="e69e1-142">Solo las tablas que admiten el uso de campos personalizados aparecen en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e69e1-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="e69e1-143">Hay nuevas tablas disponibles a través de lanzamientos continuos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="e69e1-144">La cuadrícula incluye los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e69e1-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="e69e1-145">**Tabla de Dataverse**: nombre de la tabla en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="e69e1-146">**Referencia de tabla de Dataverse**: el identificador que Dataverse usa para identificar un registro.</span><span class="sxs-lookup"><span data-stu-id="e69e1-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="e69e1-147">Este valor es equivalente a un valor **RecId** de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="e69e1-148">Puede encontrar el identificador abriendo la tabla de Dataverse en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e69e1-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="e69e1-149">**Nombre de la entidad de Human Resources**: la entidad de Human Resources que sincronizó los datos con Dataverse por última vez.</span><span class="sxs-lookup"><span data-stu-id="e69e1-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="e69e1-150">La entidad puede tener el prefijo de Dataverse u otro prefijo.</span><span class="sxs-lookup"><span data-stu-id="e69e1-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="e69e1-151">**Referencia de Human Resources**: el valor **RecId** que está asociado con el registro en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="e69e1-152">**Eliminada de Dataverse**: valor que indica si la fila se ha eliminado de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="e69e1-153">Los registros de Human Resources se corresponden con filas de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="e69e1-154">Eliminar la asociación de un registro de Human Resources desde una fila de Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="e69e1-155">Si experimenta problemas durante la sincronización de datos entre Human Resources y Dataverse, puede resolverlos borrando el seguimiento y dejando que la tabla de seguimiento se vuelva a sincronizar.</span><span class="sxs-lookup"><span data-stu-id="e69e1-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="e69e1-156">Si quita la asociación y luego cambia o elimina una fila en Dataverse, los cambios no se sincronizarán con Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="e69e1-157">Si realiza cambios en Human Resources, se crea un nuevo registro de seguimiento y la fila se actualiza en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e69e1-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="e69e1-158">Para quitar la asociación de un registro de Human Resources con una fila de Dataverse, seleccione la tabla en el campo **Tabla de Dataverse** y active **Borrar información de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="e69e1-159">[![Borrar la información de seguimiento](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="e69e1-160">Para ejecutar una sincronización completa en la tabla después de borrar el seguimiento, consulte el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e69e1-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="e69e1-161">Sincronizar una tabla entre Human Resources y Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="e69e1-162">Use este procedimiento cuando:</span><span class="sxs-lookup"><span data-stu-id="e69e1-162">Use this procedure when:</span></span>

- <span data-ttu-id="e69e1-163">Cambios de Dataverse tardan demasiado en aparecer en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e69e1-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="e69e1-164">Debe actualizar la tabla de seguimiento después de borrar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e69e1-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="e69e1-165">Para ejecutar una sincronización completa en una tabla entre Human Resources y Dataverse:</span><span class="sxs-lookup"><span data-stu-id="e69e1-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="e69e1-166">Seleccione la tabla en el campo **Tabla de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="e69e1-167">Seleccione **Sincronizar ahora**.</span><span class="sxs-lookup"><span data-stu-id="e69e1-167">Select **Sync now**.</span></span>

<span data-ttu-id="e69e1-168">[![Ejecutar una sincronización completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="e69e1-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="e69e1-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e69e1-169">See also</span></span>

[<span data-ttu-id="e69e1-170">Tablas de Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="e69e1-171">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="e69e1-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="e69e1-172">Preguntas frecuentes sobre tablas virtuales para Human Resources</span><span class="sxs-lookup"><span data-stu-id="e69e1-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="e69e1-173">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="e69e1-173">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="e69e1-174">Actualizaciones de terminología</span><span class="sxs-lookup"><span data-stu-id="e69e1-174">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]