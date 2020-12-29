---
title: Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados
description: Este tema explica cómo puede ayudar a mejorar el rendimiento de las soluciones de generación de informes electrónicos (ER) agregando orígenes de datos de CAMPO CALCULADO parametrizados.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 940b696a06fb46bcd0557f059327cd4340448137
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681289"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="aa17f-103">Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados</span><span class="sxs-lookup"><span data-stu-id="aa17f-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa17f-104">Este tema explica cómo puede realizar [seguimientos de rendimiento](trace-execution-er-troubleshoot-perf.md) de formatos de [Informes electrónicos (ER)](general-electronic-reporting.md) que se ejecutan y luego utilizan la información de esos seguimientos para ayudar a mejorar el rendimiento mediante la configuración de orígenes de datos de **Campo calculado** parametrizados.</span><span class="sxs-lookup"><span data-stu-id="aa17f-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="aa17f-105">Como parte del proceso de diseño de las configuraciones de informes electrónicos (ER) para generar documentos electrónicos empresariales, se define el método que se usa para recuperar datos de la aplicación y para introducirlos en el resultado generado.</span><span class="sxs-lookup"><span data-stu-id="aa17f-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="aa17f-106">Al diseñar un origen de datos de ER parametrizado del tipo de **Campo calculado**, puede reducir la cantidad de llamadas a la base de datos y reducir significativamente el tiempo y el coste que implica recopilar los detalles de la ejecución del formato ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa17f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aa17f-107">Prerequisites</span></span>

- <span data-ttu-id="aa17f-108">Para completar los ejemplos de este tema, debe tener acceso a uno de los siguientes [roles](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="aa17f-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="aa17f-109">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="aa17f-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="aa17f-110">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="aa17f-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="aa17f-111">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="aa17f-111">System administrator</span></span>

- <span data-ttu-id="aa17f-112">La empresa debe establecerse en **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="aa17f-113">Siga los pasos del [Apéndice 1](#appendix1) de este tema para descargar los componentes de la solución ER de Microsoft de ejemplo que se requieren para completar los ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="aa17f-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="aa17f-114">Siga los pasos en el [Apéndice 2](#appendix2) de este tema para configurar el conjunto mínimo de parámetros de ER que se requiere para usar el marco de ER para ayudar a mejorar el rendimiento de la solución de Microsoft ER de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa17f-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="aa17f-115">Importar la solución de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-115">Import the sample ER solution</span></span>

<span data-ttu-id="aa17f-116">Supongamos que debe diseñar una nueva solución de ER para generar un nuevo informe que muestra las transacciones de proveedor.</span><span class="sxs-lookup"><span data-stu-id="aa17f-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="aa17f-117">Actualmente, puede buscar las transacciones de un proveedor seleccionado en la página **Transacciones de proveedor** (vaya **Proveedores** \> **Proveedores** \> **Todos los proveedores**, seleccione un proveedor y, a continuación, en el panel de acciones, en la pestaña **Proveedor**, en el grupo **Transacciones**, seleccione **Transacciones**).</span><span class="sxs-lookup"><span data-stu-id="aa17f-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="aa17f-118">Sin embargo, desea tener todas las transacciones de proveedor juntas en un documento electrónico en formato XML.</span><span class="sxs-lookup"><span data-stu-id="aa17f-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="aa17f-119">Esta solución consistirá en varias configuraciones de ER que contienen el modelo de datos requeridos, la asignación modelo, y los componentes del formato.</span><span class="sxs-lookup"><span data-stu-id="aa17f-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="aa17f-120">El primer paso es importar la solución ER de ejemplo para generar un informe de transacciones del proveedor.</span><span class="sxs-lookup"><span data-stu-id="aa17f-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="aa17f-121">Iniciar sesión en la instancia de Microsoft Dynamics 365 Finance que se ha aprovisionado para su empresa.</span><span class="sxs-lookup"><span data-stu-id="aa17f-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="aa17f-122">En este tema, usted creará y modificará las configuraciones de ER necesarias para la empresa de ejemplo, **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="aa17f-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="aa17f-123">Asegúrese de que este proveedor de configuración se han agregado a la instancia de Finance y se marca como activo.</span><span class="sxs-lookup"><span data-stu-id="aa17f-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="aa17f-124">Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="aa17f-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="aa17f-125">En el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes** .</span><span class="sxs-lookup"><span data-stu-id="aa17f-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="aa17f-126">En la página **Configuraciones** importe las configuraciones de ER que ha descargado como requisito previo en el Finance, en el orden siguiente: modelo de datos, asignación modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="aa17f-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="aa17f-127">Para cada configuración, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="aa17f-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="aa17f-128">En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="aa17f-129">Seleccione **Exploración** y seleccione seleccionar el archivo adecuado para la configuración de ER en formato XML.</span><span class="sxs-lookup"><span data-stu-id="aa17f-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="aa17f-130">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-130">Select **OK**.</span></span>

![Configuraciones importadas en la página Configuraciones](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="aa17f-132">Revisar la solución de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="aa17f-133">Revisar la asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="aa17f-133">Review the model mapping</span></span>

1. <span data-ttu-id="aa17f-134">En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de mejora del rendimiento** y seleccione **Asignación de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="aa17f-135">En el panel de acciones, haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="aa17f-136">En la página **Asignación de modelo a origen de datos** en el Panel acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="aa17f-137">Esta distribución del modelo de ER está diseñada para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa17f-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="aa17f-138">Obtener la lista de transacciones de proveedores que están almacenadas en la tabla VendTrans (origen de datos **Trans**).</span><span class="sxs-lookup"><span data-stu-id="aa17f-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="aa17f-139">Para cada transacción, obtenga, de la tabla VendTable, el registro de un proveedor para el que se registró la transacción (origen de datos **\#Vend**).</span><span class="sxs-lookup"><span data-stu-id="aa17f-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa17f-140">Los orígenes de datos **\#Vend** están configurados para obtener el registro de proveedor correspondiente mediante el uso de la relación existente de muchos a uno **\@.'\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="aa17f-141">La distribución de modelo en esta configuración implementa el modelo de datos base de todos los formatos ER creados para este modelo y ejecutados en Finance.</span><span class="sxs-lookup"><span data-stu-id="aa17f-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="aa17f-142">Por lo tanto, el contenido de los orígenes de datos **Trans** se expone para los formatos de ER como orígenes de datos **modelo** abstractos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Origen de datos Trans en la página del diseñador de asignación de modelo](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="aa17f-144">Cierre la página **Diseñador de distribución del modelo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="aa17f-145">Cierre la página **Asignación de modelo a origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="aa17f-146">Formato de revisión</span><span class="sxs-lookup"><span data-stu-id="aa17f-146">Review format</span></span>

1. <span data-ttu-id="aa17f-147">En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de mejora del rendimiento** y seleccione **Formato de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="aa17f-148">En el panel de acciones, haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="aa17f-149">En la página **Diseñador de formato**, en la pestaña **Asignación**, seleccione **Expander/Contraer**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="aa17f-150">Expanda los elementos **Modelo**, **Datos,** y **Transacción**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="aa17f-151">Este formato ER está diseñado para generar un informe de transacciones de proveedores en formato XML.</span><span class="sxs-lookup"><span data-stu-id="aa17f-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Formatear orígenes de datos y vínculos configurados de elementos de formato en la página del diseñador de formato](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="aa17f-153">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="aa17f-154">Ejecute la solución de ER de ejemplo para realizar un seguimiento de la ejecución</span><span class="sxs-lookup"><span data-stu-id="aa17f-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="aa17f-155">Supongamos que haya terminado de diseñar de la primera versión de la solución de ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="aa17f-156">Ahora desea probar la solución en su instancia de Finance and Operations y analizar el rendimiento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa17f-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="aa17f-157">Activar el seguimiento del rendimiento de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="aa17f-158">Seleccione la compañía **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="aa17f-159">Siga los pasos en [Activar el seguimiento de rendimiento de ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para generar un seguimiento de rendimiento mientras se ejecuta un formato ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![Cuadro de diálogo parámetros de usuario](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="aa17f-161">Ejecutar formato del ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-161">Run the ER format</span></span>

1. <span data-ttu-id="aa17f-162">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="aa17f-163">En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Formato de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="aa17f-164">En el panel de acciones, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="aa17f-165">Utilizar el seguimiento de rendimiento para analizar el rendimiento de la asignación de modelos</span><span class="sxs-lookup"><span data-stu-id="aa17f-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="aa17f-166">En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="aa17f-167">En el panel de acciones, haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="aa17f-168">En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="aa17f-169">En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="aa17f-170">Seleccione el seguimiento más reciente que se generó y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="aa17f-171">La nueva información está ahora disponible para algunos artículos de orígenes de datos de la asignación del modelo actual:</span><span class="sxs-lookup"><span data-stu-id="aa17f-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="aa17f-172">El tiempo real empleado que se usó para obtener datos mediante el origen de datos</span><span class="sxs-lookup"><span data-stu-id="aa17f-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="aa17f-173">El mismo tiempo expresado como un porcentaje de tiempo total que se ha dedicado a ejecutar toda la distribución del modelo</span><span class="sxs-lookup"><span data-stu-id="aa17f-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Detalles del tiempo de ejecución en la página del diseñador de asignación de modelos](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="aa17f-175">La cuadrícula **Estadísticas de rendimiento** muestra que el origen de datos **Trans** llama a la tabla VendTrans una vez.</span><span class="sxs-lookup"><span data-stu-id="aa17f-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="aa17f-176">El valor **\[265\]\[Q: 265\]** del origen de datos **Trans** indica que se han obtenido 265 transacciones de proveedores de la tabla de la aplicación y se han devuelto al modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="aa17f-177">Los **Estadísticas de rendimiento** también muestran que la asignación de modelos actual duplica las solicitudes de la base de datos mientras que el origen de datos **\#Vend** se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="aa17f-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="aa17f-178">Es se produce por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="aa17f-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="aa17f-179">La tabla de proveedores se llama dos veces para cada una de las 265 transacciones de proveedores iteradas, para un total de 530 llamadas:</span><span class="sxs-lookup"><span data-stu-id="aa17f-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="aa17f-180">Se realiza una llamada para especificar el número de cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="aa17f-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="aa17f-181">Se realiza una llamada para especificar el nombre del proveedor.</span><span class="sxs-lookup"><span data-stu-id="aa17f-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="aa17f-182">Se llama a la tabla de proveedores para cada transacción de proveedor iterada, aunque las transacciones obtenidas se hayan registrado solo para cinco proveedores.</span><span class="sxs-lookup"><span data-stu-id="aa17f-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="aa17f-183">De las 530 llamadas, 525 son duplicadas.</span><span class="sxs-lookup"><span data-stu-id="aa17f-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="aa17f-184">La siguiente ilustración muestra el mensaje que recibe sobre llamadas duplicadas (solicitudes de base de datos).</span><span class="sxs-lookup"><span data-stu-id="aa17f-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Mensaje sobre solicitudes duplicadas a la base de datos en la página de diseñador de la distribución del modelo](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="aa17f-186">Del tiempo total de ejecución de la asignación de modelos (aproximadamente ocho segundos), observe que más del 80 por ciento (aproximadamente seis segundos) se ha dedicado a recuperar valores de la tabla de aplicación VendTable.</span><span class="sxs-lookup"><span data-stu-id="aa17f-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="aa17f-187">Ese porcentaje es demasiado grande para dos atributos de cinco proveedores, en comparación con el volumen de información de la tabla de aplicaciones de VendTrans.</span><span class="sxs-lookup"><span data-stu-id="aa17f-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="aa17f-188">Para reducir la cantidad de llamadas que se realizan para obtener los detalles del proveedor para cada transacción y mejorar el rendimiento de la asignación de modelos puede usar el almacenamiento en caché para el origen de datos **\#Vend**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="aa17f-189">El origen de datos **Trans\\\#Vend** se almacenará en caché en el ámbito de la transacción actual del origen de datos **Trans** en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa17f-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="aa17f-190">Al almacenar en caché el origen de datos **\#Vend**, reduce el número de llamadas duplicadas de 525 a 260, pero no elimina por completo la duplicación.</span><span class="sxs-lookup"><span data-stu-id="aa17f-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="aa17f-191">Para eliminar por completo la duplicación, puede configurar un nuevo origen de datos parametrizado del tipo de **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="aa17f-192">Mejorar la distribución del de modelo según la información de seguimiento de la ejecución</span><span class="sxs-lookup"><span data-stu-id="aa17f-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="aa17f-193">Modificar la lógica de la distribución del modelo</span><span class="sxs-lookup"><span data-stu-id="aa17f-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="aa17f-194">Siga estos pasos para utilizar el almacenamiento en caché y un origen de datos del tipo de **Campo calculado**, para ayudar a prevenir llamadas duplicadas a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="aa17f-195">En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="aa17f-196">En el panel de acciones, haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="aa17f-197">En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="aa17f-198">En la página **Diseñador de asignación de modelos**, siga estos pasos para agregar un origen de datos del tipo **Registros de tabla** para acceder a los registros en la tabla de aplicación VendTable:</span><span class="sxs-lookup"><span data-stu-id="aa17f-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="aa17f-199">En el panel **Tipos de origen de datos**, expanda **Dynamics 365 for Operations** y seleccione **Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="aa17f-200">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="aa17f-201">En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Vend**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="aa17f-202">En el campo **Tabla**, escriba **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="aa17f-203">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-203">Select **OK**.</span></span>

5. <span data-ttu-id="aa17f-204">Puede parametrizar llamadas a orígenes de datos del tipo de **Campo calculado** solo si esos orígenes de datos residen en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa17f-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="aa17f-205">Por lo tanto, siga estos pasos para agregar una fuente de datos del tipo **Contenedor vacío** para contener un nuevo origen de datos parametrizado del tipo **Campo calculado**:</span><span class="sxs-lookup"><span data-stu-id="aa17f-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="aa17f-206">En el panel **Tipos de origen de datos**, expanda **General** y seleccione **Vaciar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="aa17f-207">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="aa17f-208">En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Box**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="aa17f-209">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-209">Select **OK**.</span></span>

    ![Origen de datos Box en la página del diseñador de asignación de modelo](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="aa17f-211">Siga estos pasos para agregar un origen de datos parametrizado del tipo **Campo calculado**:</span><span class="sxs-lookup"><span data-stu-id="aa17f-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="aa17f-212">En el panel **Origen de datos**, seleccione **Box**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="aa17f-213">En el panel **Tipos de origen de datos**, expanda **Funciones**, y seleccione **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="aa17f-214">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-214">Select **Add**.</span></span>
    4. <span data-ttu-id="aa17f-215">En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Vend**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="aa17f-216">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="aa17f-217">En la página **Diseñador de fórmulas**, seleccione **Parámetros** para especificar los parámetros que deben proporcionarse cuando se llama a este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="aa17f-218">En el cuadro de diálogo **Parámetros**, seleccione los **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="aa17f-219">En el campo **Nombre**, escriba **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="aa17f-220">En el campo **Tipo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="aa17f-221">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-221">Select **OK**.</span></span>
    11. <span data-ttu-id="aa17f-222">En el campo **Fórmula**, especifique **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="aa17f-223">Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="aa17f-224">Seleccione **Aceptar** para agregar el nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="aa17f-225">Siga estos pasos para marcar el origen de datos agregado como almacenada en caché durante la ejecución:</span><span class="sxs-lookup"><span data-stu-id="aa17f-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="aa17f-226">En el panel **Orígenes de datos**, seleccione **Box\\Vend**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="aa17f-227">Seleccione **Memoria caché**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa17f-228">El origen de datos **Box\\Vend** se almacenará en caché en el ámbito de las transacciones de todos los proveedores del origen de datos **Trans** en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa17f-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="aa17f-229">Siga estos pasos para actualizar el origen de datos anidado **Trans\\\#Vend** para que utilice el origen de datos **Box\\Vend**:</span><span class="sxs-lookup"><span data-stu-id="aa17f-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="aa17f-230">En el panel **Orígenes de datos**, expanda **Trans**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="aa17f-231">Selecciona el origen de datos **Trans\\\#Vend** y luego seleccione **Editar** \> **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="aa17f-232">En la página **Diseñador de fórmulas**, en el campo **Fórmula**, especifique **Box.Vend (\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="aa17f-233">Seleccione **Guardar** y después, cierre la página **Diseñador de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="aa17f-234">Seleccione **Aceptar** para completar sus cambios en el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aa17f-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="aa17f-235">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-235">Select **Save**.</span></span>

    ![Origen de datos Vend en la página del diseñador de asignación de modelo](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="aa17f-237">Cierre la página **Diseñador de distribución del modelo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="aa17f-238">Cierre la página **Distribuciones del modelo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="aa17f-239">Complete la versión modificada de la distribución del modelo de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="aa17f-240">En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione la versión **1.2** de la configuración del **Seguimiento de la mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="aa17f-241">Seleccione **Cambiar estado** \> **Completar** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="aa17f-242">Ejecute la solución modificada de ER para realizar un seguimiento de la ejecución</span><span class="sxs-lookup"><span data-stu-id="aa17f-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="aa17f-243">Repita los pasos de la sección anterior [Ejecutar formato del ER](#run-format) en este tema para generar un nuevo seguimiento del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="aa17f-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="aa17f-244">Utilizar el seguimiento de rendimiento para analizar los ajustes en la asignación de modelos</span><span class="sxs-lookup"><span data-stu-id="aa17f-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="aa17f-245">En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="aa17f-246">En el panel de acciones, haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="aa17f-247">En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="aa17f-248">En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="aa17f-249">Seleccione el seguimiento más reciente que se generó y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="aa17f-250">Observe que los ajustes que realizó en la distribución de modelo han eliminado las consultas duplicadas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="aa17f-251">El número de llamadas a las tablas de base de datos y de orígenes de datos para esta distribución de modelo también se ha reducido.</span><span class="sxs-lookup"><span data-stu-id="aa17f-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Realizar un seguimiento de la información en la página del diseñador de asignación de modelo 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="aa17f-253">El tiempo total de ejecución se ha reducido unas 20 veces (de unos 8 segundos a unos 400 milisegundos).</span><span class="sxs-lookup"><span data-stu-id="aa17f-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="aa17f-254">Por lo tanto, el rendimiento de la solución completa de ER ha mejorado.</span><span class="sxs-lookup"><span data-stu-id="aa17f-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Realizar un seguimiento de la información en la página del diseñador de asignación de modelo 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="aa17f-256">Apéndice 1: Descargar los componentes de la solución Microsoft ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="aa17f-257">Debe descargar y también almacenar los siguientes archivos y guardarlos localmente.</span><span class="sxs-lookup"><span data-stu-id="aa17f-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="aa17f-258">Archivo</span><span class="sxs-lookup"><span data-stu-id="aa17f-258">File</span></span>                                        | <span data-ttu-id="aa17f-259">Contenido</span><span class="sxs-lookup"><span data-stu-id="aa17f-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="aa17f-260">Mejora del rendimiento model.version.1</span><span class="sxs-lookup"><span data-stu-id="aa17f-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="aa17f-261">Configuración del modelo datos de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-261">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="aa17f-262">Mejora del rendimiento mapping.version.1.1</span><span class="sxs-lookup"><span data-stu-id="aa17f-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="aa17f-263">Configuración del modelo de mapeado de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-263">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="aa17f-264">Mejora del rendimiento format.version.1.1</span><span class="sxs-lookup"><span data-stu-id="aa17f-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="aa17f-265">Configuración de formato de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa17f-265">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="aa17f-266">Apéndice 2: Configurar el marco ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="aa17f-267">Antes de que pueda comenzar a utilizar el marco de ER para mejorar el rendimiento de la solución de Microsoft ER de ejemplo, debe configurar el conjunto mínimo de parámetros de ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="aa17f-268">Configurar los parámetros de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-268">Configure ER parameters</span></span>

1. <span data-ttu-id="aa17f-269">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="aa17f-270">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="aa17f-271">En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="aa17f-272">En la pestaña **Adjuntos**, establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa17f-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="aa17f-273">En el campo **Configuraciones**, seleccione el tipo **Archivo** para el **DEMF** de la empresa.</span><span class="sxs-lookup"><span data-stu-id="aa17f-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="aa17f-274">En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="aa17f-275">Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="aa17f-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="aa17f-276">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="aa17f-277">Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="aa17f-278">El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito.</span><span class="sxs-lookup"><span data-stu-id="aa17f-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="aa17f-279">Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="aa17f-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="aa17f-280">Solo el propietario de una configuración de ER puede editarla.</span><span class="sxs-lookup"><span data-stu-id="aa17f-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="aa17f-281">Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="aa17f-282">Revise la lista de proveedores de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="aa17f-283">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="aa17f-284">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="aa17f-285">En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos.</span><span class="sxs-lookup"><span data-stu-id="aa17f-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="aa17f-286">Revise el contenido de esta página.</span><span class="sxs-lookup"><span data-stu-id="aa17f-286">Review the contents of this page.</span></span> <span data-ttu-id="aa17f-287">Si un registro para **Litware, Inc.** ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="aa17f-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="aa17f-288">Añada una nueva configuración para el proveedor de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="aa17f-289">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="aa17f-290">En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="aa17f-291">En la página **Proveedores de configuración**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="aa17f-292">En el campo **Nombre**, introduzca **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="aa17f-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="aa17f-293">En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="aa17f-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="aa17f-294">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="aa17f-295">Activar un proveedor de configuración de ER</span><span class="sxs-lookup"><span data-stu-id="aa17f-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="aa17f-296">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="aa17f-297">En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.</span><span class="sxs-lookup"><span data-stu-id="aa17f-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="aa17f-298">Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="aa17f-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa17f-299">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aa17f-299">Additional resources</span></span>

- [<span data-ttu-id="aa17f-300">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="aa17f-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="aa17f-301">Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="aa17f-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="aa17f-302">Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado</span><span class="sxs-lookup"><span data-stu-id="aa17f-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)
