---
title: Vuelva a establecer el data mart de informes financieros
description: "Este tema describe cómo restablecer el data mart de informes financieros."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: es-es
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="00a00-103">Vuelva a establecer el data mart de informes financieros</span><span class="sxs-lookup"><span data-stu-id="00a00-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="00a00-104">Este tema explica cómo restablecer el data mart de informes financieros para las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="00a00-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="00a00-105">Microsoft Dynamics 365 for Finance and Operations Financial Reporting versión 7.2.6.0 y posteriores</span><span class="sxs-lookup"><span data-stu-id="00a00-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="00a00-106">Microsoft Dynamics 365 for Finance and Operations Financial Reporting versión 7.0.10000.4 y posteriores</span><span class="sxs-lookup"><span data-stu-id="00a00-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="00a00-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (localmente)</span><span class="sxs-lookup"><span data-stu-id="00a00-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="00a00-108">Para obtener Finance and Operations Financial reporting versión 7.2.6.0, puede descargar el KB 4052514 de <https://support.microsoft.com/en-us/help/4052514>.</span><span class="sxs-lookup"><span data-stu-id="00a00-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="00a00-109">Restablecer el data mart de informes financieros de Finance and Operations Financial reporting versión 7.2.6.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="00a00-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="00a00-110">Restablecer el data mart de informes financieros desde el diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="00a00-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="00a00-111">Los pasos de este procedimiento se admiten en Finance and Operations Financial reporting versión 7.2.6.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="00a00-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="00a00-112">Si tiene una versión anterior, póngase en contacto con el equipo de asistencia técnica para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="00a00-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="00a00-113">En casos específicos, puede que tenga que restablecer el data mart del informe financiero.</span><span class="sxs-lookup"><span data-stu-id="00a00-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="00a00-114">Puede completar esta tarea en el cliente del diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="00a00-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="00a00-115">Aquí hay algunas escenarios donde puede que tenga que restablecer el data mart:</span><span class="sxs-lookup"><span data-stu-id="00a00-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="00a00-116">La base de datos de Finance and Operations se restauró, pero la base de datos de data mart no se restauró.</span><span class="sxs-lookup"><span data-stu-id="00a00-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="00a00-117">Ve datos incorrectos para un período.</span><span class="sxs-lookup"><span data-stu-id="00a00-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="00a00-118">La asistencia técnica le instruye para restablecer el data mart como parte de un paso de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="00a00-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="00a00-119">El reinicio de data mart se debe realizar únicamente cuando el volumen de procesamiento en la base de datos es pequeño.</span><span class="sxs-lookup"><span data-stu-id="00a00-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="00a00-120">El informe financiero no estará disponible durante el proceso de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="00a00-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="00a00-121">Restablecer el data mart</span><span class="sxs-lookup"><span data-stu-id="00a00-121">Reset the data mart</span></span>

<span data-ttu-id="00a00-122">Para restablecer el data mart, en el Diseñador de informes, en el menú **Herramientas** , seleccione **Restablecer data mart**.</span><span class="sxs-lookup"><span data-stu-id="00a00-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="00a00-123">El cuadro de diálogo que aparece tiene dos secciones: **Estadísticas** y **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="00a00-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="00a00-124">[![Cuadro de diálogo Restablecer el data mart](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="00a00-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="00a00-125">Intentos de integración</span><span class="sxs-lookup"><span data-stu-id="00a00-125">Integration attempts</span></span>

<span data-ttu-id="00a00-126">La cuadrícula **Intentos de integración** muestra el número de veces que el sistema ha intentado integrar transacciones.</span><span class="sxs-lookup"><span data-stu-id="00a00-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="00a00-127">El sistema sigue intentando integrar datos durante un período de días si los primeros intentos no tienen éxito.</span><span class="sxs-lookup"><span data-stu-id="00a00-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="00a00-128">Se sabrá que data mart debe ser restablecido es si el número de intentos es de 8 o más, y si hay muchas combinaciones de dimensiones o registros de transacción.</span><span class="sxs-lookup"><span data-stu-id="00a00-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="00a00-129">En esta situación, no se informará de los datos.</span><span class="sxs-lookup"><span data-stu-id="00a00-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="00a00-130">Estado de los datos</span><span class="sxs-lookup"><span data-stu-id="00a00-130">Data status</span></span>

<span data-ttu-id="00a00-131">La cuadrícula **Estado de los datos** proporciona una instantánea de las transacciones, de los tipos de cambio, y los valores de dimensión en el data mart.</span><span class="sxs-lookup"><span data-stu-id="00a00-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="00a00-132">Un gran número de registros obsoletos indican que se han producido numerosas actualizaciones de los registros.</span><span class="sxs-lookup"><span data-stu-id="00a00-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="00a00-133">Esta situación podría provocar tiempos de generación de informes más lentos.</span><span class="sxs-lookup"><span data-stu-id="00a00-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="00a00-134">Categorías de cuenta principal desalineadas</span><span class="sxs-lookup"><span data-stu-id="00a00-134">Misaligned main account categories</span></span>

<span data-ttu-id="00a00-135">Si utiliza una versión anterior a Microsoft Dynamics 365 for Finance and Operations Financial reporting versión 7.2.1, puede que tenga que restablecer el data mart si cambia el nombre de cuentas y mueve cuentas entre las categorías de cuenta.</span><span class="sxs-lookup"><span data-stu-id="00a00-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="00a00-136">Estas acciones pueden hacer que las categorías de cuenta principal tengan una alineación incorrecta.</span><span class="sxs-lookup"><span data-stu-id="00a00-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="00a00-137">El campo **Categorías de cuenta principal desalineada** muestra si está experimentando dicho problema.</span><span class="sxs-lookup"><span data-stu-id="00a00-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="00a00-138">Restablecer el data mart de Finance and Operations Financial reporting versión 7.2.6.0</span><span class="sxs-lookup"><span data-stu-id="00a00-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="00a00-139">Para restablecer el data mart de Finance and Operations Financial reporting versión 7.2.6.0 y versiones anteriores, en el cuadro de diálogo **Restablecer data mart** , seleccione la casilla de verificación **Restablecer data mart** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="00a00-140">Debe restablecer el data mart únicamente durante un tiempo de inactividad programado.</span><span class="sxs-lookup"><span data-stu-id="00a00-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="00a00-141">[![Cuadro de diálogo Restablecer el data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="00a00-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="00a00-142">Restablecer el data mart y seleccionar un motivo en Microsoft Dynamics 365 for Finance and Operations Financial reporting versión 7.3.0</span><span class="sxs-lookup"><span data-stu-id="00a00-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="00a00-143">Si determina que un reinicio de data mart es necesario, seleccione la casilla de verificación **Restaurar data mart** , y seleccione un motivo en el campo **Motivo**.</span><span class="sxs-lookup"><span data-stu-id="00a00-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="00a00-144">Las opciones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="00a00-144">The following options are available:</span></span>

- <span data-ttu-id="00a00-145">**Faltan datos o son incorrectos**: Basándose en las estadísticas, ha determinado que podrían faltar datos.</span><span class="sxs-lookup"><span data-stu-id="00a00-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="00a00-146">Antes de que pueda continuar, se recomienda que trabaje con el soporte para determinar la causa original.</span><span class="sxs-lookup"><span data-stu-id="00a00-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="00a00-147">**Restablecer base de datos**: la base de datos Finance and Operations se restauró, pero la base de datos del data mart de Financial reporting no se restauró.</span><span class="sxs-lookup"><span data-stu-id="00a00-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="00a00-148">**Otros**: está restableciendo el data mart por otro motivo.</span><span class="sxs-lookup"><span data-stu-id="00a00-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="00a00-149">Si le preocupa que haya un problema, póngase en contacto con Soporte para identificarlo.</span><span class="sxs-lookup"><span data-stu-id="00a00-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="00a00-150">Compruebe que todas las tareas existentes hayan terminado de integrarse antes de completar los pasos.</span><span class="sxs-lookup"><span data-stu-id="00a00-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="00a00-151">Puede ver el estado de la integración seleccionando &gt; **Herramientas** **Estado de integración**.</span><span class="sxs-lookup"><span data-stu-id="00a00-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="00a00-152">Borrar usuarios y empresas</span><span class="sxs-lookup"><span data-stu-id="00a00-152">Clear users and companies</span></span>

<span data-ttu-id="00a00-153">Seleccione la casilla de verificación **Borrar usuarios y empresas** si se restauró la base de datos, pero realizó cambios en usuarios o empresas.</span><span class="sxs-lookup"><span data-stu-id="00a00-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="00a00-154">En pocas ocasiones tendrá que seleccionar esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="00a00-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="00a00-155">Cuando esté listo para iniciar el proceso de restablecimiento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="00a00-156">Se le pedirá que confirme que está listo para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="00a00-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="00a00-157">Tenga en cuenta que el informe financiero no estará disponible durante el reinicio y la integración de datos inicial que se produce después.</span><span class="sxs-lookup"><span data-stu-id="00a00-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="00a00-158">Si desea revisar el estado de la integración, seleccione &gt; **Herramientas** **Estado de integración** para ver la última vez que la integración se ejecutó y el estado.</span><span class="sxs-lookup"><span data-stu-id="00a00-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="00a00-159">[![Permite ver el estado de la integración.](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="00a00-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="00a00-160">Restablecer el data mart de informes financieros de Finance and Operations Financial reporting versión 7.0.10000.4 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="00a00-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="00a00-161">Si se restablece la base de datos de Finance and Operations desde una copia de seguridad o copia de la base de datos de otro entorno, debe seguir los pasos de esta sección para ayudar a garantizar que el data mart del informe financiero usa correctamente la base de datos restaurada de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00a00-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="00a00-162">Los pasos de este proceso se admiten para Microsoft Dynamics AX application versión 7.0.1 (mayo de 2016) (compilación de la aplicación 7.0.1265.23014 y compilación de Financial reporting 7.0.10000.4) y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="00a00-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="00a00-163">Si tiene una versión anterior de Finance and Operations, contacte con nuestro equipo de soporte técnico para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="00a00-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="00a00-164">Exportar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="00a00-164">Export report definitions</span></span>

<span data-ttu-id="00a00-165">En primer lugar, siga estos pasos para exportar los diseños de informe desde el diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="00a00-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="00a00-166">En el Diseñador de informes, seleccione **Empresa** &gt; **Grupos de bloques de creación**.</span><span class="sxs-lookup"><span data-stu-id="00a00-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="00a00-167">Seleccione el grupo de bloques de creación para exportar y seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00a00-168">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="00a00-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="00a00-169">Seleccione las definiciones del informe que quiere exportar:</span><span class="sxs-lookup"><span data-stu-id="00a00-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="00a00-170">Para exportar todas las definiciones de informe y los bloques de creación asociados, seleccione **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="00a00-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="00a00-171">Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="00a00-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="00a00-172">Mantenga presionada la tecla Ctrl para seleccionar varios artículos de una pestaña. Al seleccionar los informes para exportar, las filas, columnas, árboles y conjuntos de dimensiones asociados se seleccionan también.</span><span class="sxs-lookup"><span data-stu-id="00a00-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="00a00-173">Seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-173">Select **Export**.</span></span>
5. <span data-ttu-id="00a00-174">Escriba un nombre de archivo y seleccione una ubicación segura en la que desea guardar las definiciones de informe exportadas.</span><span class="sxs-lookup"><span data-stu-id="00a00-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="00a00-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-175">Select **Save**.</span></span>

<span data-ttu-id="00a00-176">Puede copiar o cargar el archivo en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="00a00-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="00a00-177">De esta manera, el archivo se puede importar a un entorno diferente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="00a00-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="00a00-178">Para obtener información sobre el uso de una cuenta de almacenamiento de Microsoft Azure, consulte [transferir datos con el programa de línea de comandos de AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="00a00-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="00a00-179">Microsoft no proporciona una cuenta de almacenamiento como parte del contrato de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00a00-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="00a00-180">Debe comprar una cuenta almacenamiento o utilizar una cuenta de almacenamiento de una suscripción de Azure independiente.</span><span class="sxs-lookup"><span data-stu-id="00a00-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="00a00-181">Tenga en cuenta el comportamiento de la unidad D en las máquinas virtuales (VM) Azure.</span><span class="sxs-lookup"><span data-stu-id="00a00-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="00a00-182">No almacene permanentemente los grupos de bloques de creación exportados en la unidad D. Para obtener más información acerca de unidades temporales, consulte [Comprensión de la unidad temporal de Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="00a00-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="00a00-183">Detener servicios</span><span class="sxs-lookup"><span data-stu-id="00a00-183">Stop services</span></span>

<span data-ttu-id="00a00-184">Los servicios de Microsoft Windows siguientes tendrán conexiones abiertas con la base de datos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00a00-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="00a00-185">Por lo tanto, debe utilizar el escritorio remoto de Microsoft para conectarse con todos los equipos del entorno y utilizar services.msc para detener estos servicios.</span><span class="sxs-lookup"><span data-stu-id="00a00-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="00a00-186">Servicio de publicación de la World Wide Web (en todos los equipos Application Object Servers [AOS])</span><span class="sxs-lookup"><span data-stu-id="00a00-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="00a00-187">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="00a00-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="00a00-188">Servicio de proceso de Management Reporter 2012 (solo en equipos de Business Intelligence BI)</span><span class="sxs-lookup"><span data-stu-id="00a00-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="00a00-189">Restablecer</span><span class="sxs-lookup"><span data-stu-id="00a00-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="00a00-190">Descargue el último paquete de MinorVersionDataUpgrade.zip</span><span class="sxs-lookup"><span data-stu-id="00a00-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="00a00-191">Descargue el último paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="00a00-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="00a00-192">Para obtener instrucciones acerca de cómo encontrar y descargar la versión correcta de embalaje de la actualización de datos, vea[Descarga del paquete desplegable de la última actualización de datos](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="00a00-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="00a00-193">No se requiere una actualización para descargar el paquete de MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="00a00-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="00a00-194">Por tanto, solo tiene que seguir los pasos de la sección “Descarga de paquete desplegable de la última actualización de datos” de este tema.</span><span class="sxs-lookup"><span data-stu-id="00a00-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="00a00-195">Puede omitir el resto de pasos del tema.</span><span class="sxs-lookup"><span data-stu-id="00a00-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="00a00-196">Ejecute las secuencias de comandos en la base de datos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="00a00-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="00a00-197">Ejecute las secuencias de comandos siguientes en la base de datos de Finance and Operations (no en la base de datos del informe financiero):</span><span class="sxs-lookup"><span data-stu-id="00a00-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="00a00-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="00a00-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="00a00-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="00a00-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="00a00-200">Estas secuencias de comandos ayudan a garantizar que la configuración de usuarios, roles y seguimiento de cambios sea correcta.</span><span class="sxs-lookup"><span data-stu-id="00a00-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="00a00-201">Ejecutar un comando de Windows PowerShell para restablecer la base de datos</span><span class="sxs-lookup"><span data-stu-id="00a00-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="00a00-202">En el equipo de AOS, empiece como administrador de Microsoft Windows PowerShell y ejecute los comandos siguientes para restablecer la integración entre Finance and Operations y el informe financiero.</span><span class="sxs-lookup"><span data-stu-id="00a00-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="00a00-203">A continuación se indica una explicación de los parámetros del comando **Reset-DatamartIntegration** :</span><span class="sxs-lookup"><span data-stu-id="00a00-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="00a00-204">Los valores válidos de **-Reason** son **SERVICING**, **BADDATA**, y **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="00a00-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="00a00-205">El parámetro **-ReasonDetail** es de texto libre.</span><span class="sxs-lookup"><span data-stu-id="00a00-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="00a00-206">El motivo y el detalle del motivo se registrarán en telemetría/supervisión de entorno.</span><span class="sxs-lookup"><span data-stu-id="00a00-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="00a00-207">Tras ejecutar los comandos, se le pedirá que especifique **Y** para confirmar que desea restablecer la base de datos.</span><span class="sxs-lookup"><span data-stu-id="00a00-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="00a00-208">Restablecer servicios</span><span class="sxs-lookup"><span data-stu-id="00a00-208">Restart services</span></span>

<span data-ttu-id="00a00-209">Use services.msc para reiniciar los servicios que ha detenido anteriormente:</span><span class="sxs-lookup"><span data-stu-id="00a00-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="00a00-210">Servicio de publicación de la World Wide Web (en todos los equipos AOS)</span><span class="sxs-lookup"><span data-stu-id="00a00-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="00a00-211">Servicio de administración por lotes de Microsoft Dynamics 365 for Finance and Operations (solo en equipos AOS que no son privados)</span><span class="sxs-lookup"><span data-stu-id="00a00-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="00a00-212">Servicio de proceso de Management Reporter 2012 (en equipos de BI solamente)</span><span class="sxs-lookup"><span data-stu-id="00a00-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="00a00-213">Importar las definiciones de informe</span><span class="sxs-lookup"><span data-stu-id="00a00-213">Import report definitions</span></span>

<span data-ttu-id="00a00-214">Importe sus diseños de informe del Diseñador de informes, mediante el archivo creado durante la exportación.</span><span class="sxs-lookup"><span data-stu-id="00a00-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="00a00-215">En el Diseñador de informes, seleccione **Empresa** &gt; **Grupos de bloques de creación**.</span><span class="sxs-lookup"><span data-stu-id="00a00-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="00a00-216">Seleccione el grupo de bloques de creación para exportar y seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00a00-217">Para Finance and Operations, se admite solo un grupo de bloque de creación, **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="00a00-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="00a00-218">Seleccione el bloque de creación **Predeterminado** y seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="00a00-219">Seleccione el archivo que contiene las definiciones de informe exportadas y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="00a00-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="00a00-220">En el cuadro de diálogo **Importar**, seleccione las definiciones de informe que se van a importar:</span><span class="sxs-lookup"><span data-stu-id="00a00-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="00a00-221">Para importar todas las definiciones de informe y los bloques de creación asociados, seleccione **Seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="00a00-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="00a00-222">Para importar informes, filas, columnas, organigramas o grupos de dimensión específicos, seleccione los informes, las filas, las columnas, los organigramas o los grupos de dimensión que se deben importar y, a continuación, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="00a00-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="00a00-223">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="00a00-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="00a00-224">Restablecer el data mart de informes financieros de Finance and Operations (localmente)</span><span class="sxs-lookup"><span data-stu-id="00a00-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="00a00-225">Solicite a todos los usuarios que salgan del diseñador de informes y el área de informes financieros de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00a00-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="00a00-226">Ejecute la siguiente secuencia de comandos en la base de datos de informes financieros (MRDB).</span><span class="sxs-lookup"><span data-stu-id="00a00-226">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="00a00-227">Trunque o elimine todos los registros de la tabla FINANCIALREPORTS en la base de datos de Finance and Operations (AXDB).</span><span class="sxs-lookup"><span data-stu-id="00a00-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="00a00-228">Trunque o elimine todos los registros de la tabla FINANCIALREPORTVERSION, si esta tabla existe en la base de datos de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="00a00-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="00a00-229">Si la tabla no existe en la base de datos de Finance and Operations, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="00a00-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="00a00-230">Ejecute la secuencia de comandos **ResetDatamart.sql** en la base de datos de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="00a00-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="00a00-231">Este script deshabilita la integración de data mart, elimina todos los datos de data mart, y vuelve a permitir la integración de data mart.</span><span class="sxs-lookup"><span data-stu-id="00a00-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="00a00-232">Después de restablecimiento, puede comprobar manualmente la recarga de datos ejecutando la consulta siguiente en la base de datos de informes financieros.</span><span class="sxs-lookup"><span data-stu-id="00a00-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="00a00-233">Confirme que todas las filas tienen un valor **LastRunTime** , y que **StateType** está establecido en **5**.</span><span class="sxs-lookup"><span data-stu-id="00a00-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="00a00-234">Un valor **StateType** de **5** indica que los datos se recargaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="00a00-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="00a00-235">Un valor de **7** indica un estado erróneo.</span><span class="sxs-lookup"><span data-stu-id="00a00-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="00a00-236">En ocasiones, el mapa de la jerarquía organizativa tiene este estado la primera vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="00a00-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="00a00-237">Sin embargo, el estado erróneo debe resolverse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="00a00-237">However, the faulted state but should be automatically resolved.</span></span>

