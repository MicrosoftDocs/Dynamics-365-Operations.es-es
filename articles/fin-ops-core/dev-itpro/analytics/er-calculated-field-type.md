---
title: Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado
description: Este tema proporciona información sobre cómo usar el tipo de campo calculado para los orígenes de datos de ER.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 02d53f4326d8f31abf6ec7404575728837954bef
ms.sourcegitcommit: c9baf9a3b4552f0317b5ec87d252834f52df1b98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665619"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="5dcfb-103">Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5dcfb-104">Este tema explica cómo puede diseñar un origen de datos de informes electrónicos (ER) mediante el tipo **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="5dcfb-105">Este origen de datos puede contener una expresión del ER que, cuando se ejecuta, se puede controlar mediante los valores de los argumentos de parámetros que se configuran en un enlace que llama a este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="5dcfb-106">Al configurar llamadas con parámetros de este tipo de origen de datos, puede volver a usar un solo origen de datos en muchos enlaces, lo que reduce el número total de orígenes de datos que se deben configurar en distribuciones de modelos de ER o formatos de ER.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="5dcfb-107">También simplifica el componente de ER configurado, que reduce los costes de mantenimiento y el coste de uso de otros consumidores.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5dcfb-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5dcfb-108">Prerequisites</span></span>
<span data-ttu-id="5dcfb-109">Para completar los ejemplos de este tema, debe tener el acceso siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="5dcfb-110">Acceso a uno de estos roles:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="5dcfb-111">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5dcfb-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="5dcfb-112">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5dcfb-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="5dcfb-113">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="5dcfb-113">System administrator</span></span>

- <span data-ttu-id="5dcfb-114">Acceso a la instancia de los Regulatory Configuration Services (RCS) que se han aprovisionado para el mismo arrendatario que Finance and Operations, para uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="5dcfb-115">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5dcfb-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="5dcfb-116">Consultor funcional de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5dcfb-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="5dcfb-117">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="5dcfb-117">System administrator</span></span>

<span data-ttu-id="5dcfb-118">Debe descargar y también almacenar localmente los archivos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-118">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="5dcfb-119">**Contenido**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-119">**Content**</span></span>                           | <span data-ttu-id="5dcfb-120">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-120">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="5dcfb-121">Configuración del modelo datos de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dcfb-121">Sample ER data model configuration</span></span>    | [<span data-ttu-id="5dcfb-122">Modelo para aprender llamadas con parámetros.versión.1.xml</span><span class="sxs-lookup"><span data-stu-id="5dcfb-122">Model to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| <span data-ttu-id="5dcfb-123">Configuración de metadatos de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dcfb-123">Sample ER metadata configuration</span></span>      | [<span data-ttu-id="5dcfb-124">Metadatos para aprender llamadas con parámetros.versión.1.xml</span><span class="sxs-lookup"><span data-stu-id="5dcfb-124">Metadata to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| <span data-ttu-id="5dcfb-125">Configuración del modelo de mapeado de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dcfb-125">Sample ER model mapping configuration</span></span> | [<span data-ttu-id="5dcfb-126">Asignación para aprender llamadas con parámetros.versión.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="5dcfb-126">Mapping to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="5dcfb-127">Configuración de formato de ER de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dcfb-127">Sample ER format configuration</span></span>        | [<span data-ttu-id="5dcfb-128">Formato para aprender llamadas con parámetros.versión.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="5dcfb-128">Format to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="5dcfb-129">Iniciar sesión en su instancia de RCS</span><span class="sxs-lookup"><span data-stu-id="5dcfb-129">Sign in to your RCS instance</span></span>
<span data-ttu-id="5dcfb-130">En este ejemplo, creará una configuración para la empresa del ejemplo, Litware, Inc. First, en RCS, tiene que completar estos pasos, en el procedimiento [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="5dcfb-130">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="5dcfb-131">En el panel predeterminado, seleccione **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-131">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="5dcfb-132">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-132">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="5dcfb-133">Importe las configuraciones descargadas al RCS en la siguiente secuencia: modelo de datos, metadatos, distribución de modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-133">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="5dcfb-134">Realice los pasos siguientes para cada configuración de ER:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-134">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="5dcfb-135">Seleccione **Intercambiar.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-135">Select **Exchange.**</span></span>
    2. <span data-ttu-id="5dcfb-136">Seleccione **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-136">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="5dcfb-137">Seleccione **Examinar** y seleccione la configuración necesaria de ER en formato XML.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-137">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="5dcfb-138">Seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-138">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="5dcfb-139">Revise la solución de ER proporcionada</span><span class="sxs-lookup"><span data-stu-id="5dcfb-139">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="5dcfb-140">Revisión de la distribución del modelo</span><span class="sxs-lookup"><span data-stu-id="5dcfb-140">Review model mapping</span></span>

1. <span data-ttu-id="5dcfb-141">En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-141">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="5dcfb-142">Seleccione **Asignación para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-142">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="5dcfb-143">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-143">Select **Designer**.</span></span>
4. <span data-ttu-id="5dcfb-144">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-144">Select **Designer**.</span></span>  
   
    <span data-ttu-id="5dcfb-145">Esta distribución del modelo de ER está diseñada para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-145">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="5dcfb-146">Obtener la lista de códigos de impuestos (origen de datos**Impuestos**) que residen en la tabla **TaxTable**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-146">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="5dcfb-147">Obtener la lista de transacciones de impuestos (origen de datos**Impuestos**) que residen en la tabla **TaxTable**:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-147">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="5dcfb-148">Agrupar la lista de transacciones capturadas (origen de datos**Gr**) por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-148">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="5dcfb-149">Calcular las transacciones agrupadas que siguen valores agregados por código de impuestos:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-149">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="5dcfb-150">Sumar los valores de la base fiscal.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-150">Sum of tax base values.</span></span>
            - <span data-ttu-id="5dcfb-151">Sumar los valores de las tasas.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-151">Sum of tax values.</span></span>
            - <span data-ttu-id="5dcfb-152">Sumar el valor mínimo del índice de impuestos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-152">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="5dcfb-153">La distribución de modelo en esta configuración implementa el modelo de datos base de todos los formatos ER creados para este modelo y ejecutados en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-153">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="5dcfb-154">Como consecuencia, el contenido de los orígenes de datos **Impuesto** y **Gr** se expone para los formatos de ER como orígenes de datos abstractos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-154">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Página de diseñador de distribución de modelo que muestra los orígenes de datos Impuesto y Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="5dcfb-156">Cierre la página **Diseñador de distribución del modelo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-156">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="5dcfb-157">Cierre la página **Distribución del modelo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-157">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="5dcfb-158">Formato de revisión</span><span class="sxs-lookup"><span data-stu-id="5dcfb-158">Review format</span></span>

1. <span data-ttu-id="5dcfb-159">En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-159">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="5dcfb-160">Seleccione **Formato para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-160">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="5dcfb-161">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-161">Select **Designer**.</span></span> <span data-ttu-id="5dcfb-162">Este formato de ER está diseñado para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-162">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="5dcfb-163">Genere un extracto impositivo en formato XML.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-163">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="5dcfb-164">Mostrar los siguientes niveles de impuestos en el extracto de impuestos: regular, reducido, y ninguno.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-164">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="5dcfb-165">Actuales varois detalles en cada nivel de impuestos y tener un número distinto de detalles en cada nivel.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-165">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Página de diseñador de formato](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="5dcfb-167">Seleccione **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-167">Select **Mapping**.</span></span>
5. <span data-ttu-id="5dcfb-168">Expanda las entradas **Modelo**, **Datos,** y **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-168">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="5dcfb-169">El campo calculado **Model.Data.Summary.Level** contiene la expresión que devuelve el código del nivel de impuestos (**Regular**, **Reducido**, **Ninguno,** o **Otro**) como valor de texto para cualquier código de impuestos que se puede recuperar del origen de datos **Model.Data.Summary** en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-169">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![La página del diseñador del formato que muestra los detalles del modelo de datos Model para aprender las llamadas con parámetros](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="5dcfb-171">Expanda **Model**.**Data2**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-171">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="5dcfb-172">Expanda **Model**.**Data2Summary2**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-172">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="5dcfb-173">El origen de datos **Model**.**Data2.Summary2** está configurado para agrupar los detalles de transacción del origen de datos **Model.Data.Summary** por el nivel de impuestos (devuelto por el campo calculado **Model.Data.Summary.Level** ) y calcular las agregaciones.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-173">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![Página del diseñador del formato que muestra los detalles del origen de datos Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="5dcfb-175">Revise los campos calculados **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, y **Model**.**Data2.Level3.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-175">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="5dcfb-176">Estos campos calculados se usan para filtrar la lista de registros de **Model**.**Data2.Summary2** y devolver solamente los registros que representan un nivel determinado de los impuestos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-176">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="5dcfb-177">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-177">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="5dcfb-178">Crear un formato derivado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-178">Create a derived format</span></span>
<span data-ttu-id="5dcfb-179">Puede mejorar el formato proporcionado agregando un campo calculado para filtrar el nivel impositivo requerido en lugar de utilizar los tres campos existentes: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** y **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-179">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="5dcfb-180">El nivel necesario de impuestos se puede especificar en la ubicación donde se llamará a este nuevo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-180">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="5dcfb-181">En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-181">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="5dcfb-182">Seleccione **Formato para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-182">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="5dcfb-183">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-183">Select **Create configuration**.</span></span>
4. <span data-ttu-id="5dcfb-184">Seleccione **Derivar de nombre: Formato para aprender las llamadas con parámetros, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-184">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="5dcfb-185">En el campo **Nombre**, introduzca **Formato para aprender llamadas con parámetros (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-185">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="5dcfb-186">Seleccione **Crear configuración.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-186">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="5dcfb-187">Configurar un campo calculado con parámetros que devuelve una lista de registros</span><span class="sxs-lookup"><span data-stu-id="5dcfb-187">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="5dcfb-188">Empezar a agregar un nuevo campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-188">Start adding a new calculated field</span></span>

1. <span data-ttu-id="5dcfb-189">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-189">Select **Designer**.</span></span>
2. <span data-ttu-id="5dcfb-190">Seleccione **Expandir o contraer/** para expandir todos los elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-190">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="5dcfb-191">Seleccione **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-191">Select **Mapping**.</span></span>
4. <span data-ttu-id="5dcfb-192">Expanda el elemento **Model**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-192">Expand the **Model** item.</span></span>
5. <span data-ttu-id="5dcfb-193">Seleccione **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-193">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="5dcfb-194">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-194">Select **Add**.</span></span>
7. <span data-ttu-id="5dcfb-195">Seleccione **Funciones\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-195">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="5dcfb-196">En el campo **Nombre**, especifique **Niveles**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-196">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="5dcfb-197">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-197">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="5dcfb-198">Definir un parámetro para agregar un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-198">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="5dcfb-199">Seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-199">Select **Parameters**.</span></span>
2. <span data-ttu-id="5dcfb-200">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-200">Select **New**.</span></span>
3. <span data-ttu-id="5dcfb-201">En el campo **Nombre**, introduzca **Nivel impositivo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-201">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="5dcfb-202">En el campo **Tipo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-202">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="5dcfb-203">Solo los tipos de datos primitivos se pueden utilizar para especificar el tipo de argumento de parámetros.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-203">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="5dcfb-204">Por lo tanto, los tipos **Lista de registro**, **registro**, y **Enumeración** no se pueden usar con este propósito.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-204">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="5dcfb-205">El número máximo de parámetros que se pueden especificar para un solo campo calculado es 8.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-205">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista de orígenes de datos de parámetros](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="5dcfb-207">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-207">Select **OK**.</span></span>

<span data-ttu-id="5dcfb-208">Si agrega este parámetro, especifica la condición que debe existir en lugar de llamar a este campo calculado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-208">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="5dcfb-209">Cuando llama a este campo calculado, debe especificar argumento del parámetro **Nivel impositivo** como valor con el formato **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-209">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="5dcfb-210">Asegúrese de definir parámetros solo para los campos calculados que residen en un contenedor ( **Lista de registros**, **registro**, o **Contenedor**).</span><span class="sxs-lookup"><span data-stu-id="5dcfb-210">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="5dcfb-211">El parámetro configurado está disponible en la lista de orígenes de datos de este campo calculado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-211">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="5dcfb-212">Puede agregar el parámetro a la expresión configurada seleccionando **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-212">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Campo del origen de datos](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="5dcfb-214">Definir una expresión para agregar un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-214">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="5dcfb-215">En el campo **Fórmula**, escriba:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-215">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="5dcfb-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="5dcfb-217">Seleccione el parámetro **Nivel impositivo** en la lista de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-217">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="5dcfb-218">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-218">Select **Add data source**.</span></span>
4. <span data-ttu-id="5dcfb-219">En el campo **Fórmula**, finalice la expresión como:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-219">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="5dcfb-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="5dcfb-221">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-221">Select **Save**.</span></span>

    ![Información del campo de origen de datos](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="5dcfb-223">Cierre la página **Diseñador de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-223">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="5dcfb-224">Terminar de agregar un nuevo campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-224">Finish adding a new calculated field</span></span>

- <span data-ttu-id="5dcfb-225">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-225">Select **OK**.</span></span>

<span data-ttu-id="5dcfb-226">En la página **Diseñador de formato**, el campo calculado configurado con parámetros **Niveles** requiere un argumento **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-226">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Lista ampliada de niveles del campo calculado](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="5dcfb-228">Use el campo calculado configurado para vincular elementos del formato</span><span class="sxs-lookup"><span data-stu-id="5dcfb-228">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="5dcfb-229">Seleccione **Model.Data2.Levels** para seleccionar el campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-229">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="5dcfb-230">Seleccione el elemento de formato **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-230">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="5dcfb-231">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-231">Select **Bind**.</span></span>
4. <span data-ttu-id="5dcfb-232">Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level1**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados del elemento del formato seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-232">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="5dcfb-233">La vinculación aplicada se ha creado como una llamada del campo calculado con parámetros.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-233">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="5dcfb-234">De forma predeterminada, el nombre del elemento de formato vinculado se usa como argumento para el campo calculado con parámetros en las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-234">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="5dcfb-235">El campo calculado se configura para usar un único parámetro.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-235">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="5dcfb-236">El tipo de datos de este parámetro se define como **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-236">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="5dcfb-237">Cuando el nombre del elemento de formato vinculado está en blanco, el nombre del origen de datos de este elemento se usa en el vínculo aplicado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-237">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="5dcfb-238">Seleccione el elemento de formato **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-238">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="5dcfb-239">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-239">Select **Bind**.</span></span>
7. <span data-ttu-id="5dcfb-240">Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level2**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados en el elemento del formato seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-240">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="5dcfb-241">Seleccione el elemento de formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-241">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="5dcfb-242">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-242">Select **Bind**.</span></span>
10. <span data-ttu-id="5dcfb-243">Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level3**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados en el elemento del formato seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-243">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="5dcfb-244">Cuando se especifica el argumento del campo calculado con parámetros para el elemento XML que representa el nivel de impuestos (por ejemplo, **Model.Data2.Levels ("Reduced")** como valor de texto), no es necesario hacer lo mismo para atributos XML anidados -sus vínculos heredarán automáticamente el valor del argumento definido en el nivel principal (**Model.Data2.Levels.aggregated.Base**, no **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="5dcfb-244">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="5dcfb-245">Las llamadas periódicas de cualquier campo calculado con parámetros no se admiten.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-245">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="5dcfb-246">Puede seleccionar **Editar fórmula** y cambiar el argumento aplicado de forma predeterminada del campo calculado con parámetros del vínculo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-246">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="5dcfb-247">Si falta este argumento, puede producir errores en tiempo de ejecución — se informa a los usuarios sobre esta situación cuando se valida el formato actual.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-247">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Notificación de aviso de validación](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="5dcfb-249">Configurar un campo calculado con parámetros para devolver un registro</span><span class="sxs-lookup"><span data-stu-id="5dcfb-249">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="5dcfb-250">Cuando un campo calculado con parámetros devuelve un registro, necesita admitir el vínculo de campos individuales de este registro para dar formato a elementos.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-250">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="5dcfb-251">En casos como éste no habrá vinculación principal que contenga el valor de un argumento para llamar a un campo calculado con parámetros —este valor debe definirse en la vinculación del campo de un único registro.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-251">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="5dcfb-252">Empezar a agregar un nuevo campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-252">Start adding a new calculated field</span></span>

1. <span data-ttu-id="5dcfb-253">Seleccione **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-253">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="5dcfb-254">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-254">Select **Add**.</span></span>
3. <span data-ttu-id="5dcfb-255">Seleccione **Funciones\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-255">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="5dcfb-256">En el campo **Nombre**, especifique **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-256">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="5dcfb-257">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-257">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="5dcfb-258">Definir un parámetro para agregar un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-258">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="5dcfb-259">Seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-259">Select **Parameters**.</span></span>
2. <span data-ttu-id="5dcfb-260">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-260">Select **New**.</span></span>
3. <span data-ttu-id="5dcfb-261">En el campo **Nombre**, introduzca **Nivel impositivo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-261">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="5dcfb-262">En el campo **Tipo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-262">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="5dcfb-263">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-263">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="5dcfb-264">Definir una expresión para agregar un campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-264">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="5dcfb-265">En el campo **Fórmula**, introduzca lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-265">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="5dcfb-266">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-266">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="5dcfb-267">Seleccione el parámetro **Nivel impositivo**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-267">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="5dcfb-268">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-268">Select **Add data source**.</span></span>
4. <span data-ttu-id="5dcfb-269">En el campo **Fórmula**, anexe **'Taxation Level'))** a lo que especificó en el paso 1 para finalizar la expresión a:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-269">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="5dcfb-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="5dcfb-271">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-271">Select **Save**.</span></span>
6. <span data-ttu-id="5dcfb-272">Cierre la página **Diseñador de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-272">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="5dcfb-273">Terminar de agregar un nuevo campo calculado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-273">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="5dcfb-274">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-274">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="5dcfb-275">Use el campo calculado configurado para vincular elementos del formato</span><span class="sxs-lookup"><span data-stu-id="5dcfb-275">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="5dcfb-276">Expanda **Model.Data2.LevelRecord** para seleccionar el campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-276">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="5dcfb-277">Expanda el contenedor **Model.Data2.LevelRecord.aggregated** del campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-277">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="5dcfb-278">Seleccione el campo **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-278">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="5dcfb-279">Seleccione el elemento de formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-279">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="5dcfb-280">Seleccione **Desenlazar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-280">Select **Unbind**.</span></span>
6. <span data-ttu-id="5dcfb-281">Seleccione el elemento de formato **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-281">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="5dcfb-282">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-282">Select **Bind**.</span></span>
8. <span data-ttu-id="5dcfb-283">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-283">Select **Edit formula**.</span></span>
9. <span data-ttu-id="5dcfb-284">Cambie la expresión a **Model.Data2.LevelRecord("None").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-284">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Expresión actualizada](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="5dcfb-286">Quite los campos calculados que no se utilizan</span><span class="sxs-lookup"><span data-stu-id="5dcfb-286">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="5dcfb-287">Seleccione **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-287">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="5dcfb-288">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-288">Select **Delete**.</span></span>
3. <span data-ttu-id="5dcfb-289">Seleccione **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-289">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="5dcfb-290">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-290">Select **Delete**.</span></span>
5. <span data-ttu-id="5dcfb-291">Seleccione **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-291">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="5dcfb-292">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-292">Select **Delete**.</span></span>
7. <span data-ttu-id="5dcfb-293">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-293">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5dcfb-294">Se reusó el mismo campo calculado **Model.Data2.Levels** varias veces en vínculos de formato.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-294">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="5dcfb-295">Es mucho más fácil utilizar y mantener un único campo calculado en lugar de hacerlo para varios campos similares.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-295">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="5dcfb-296">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-296">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="5dcfb-297">Completar la versión ajustada de un formato derivado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-297">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="5dcfb-298">En la ficha desplegable **Versiones**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-298">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="5dcfb-299">Seleccione **Completar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-299">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="5dcfb-300">Exportar la versión completada de un formato derivado</span><span class="sxs-lookup"><span data-stu-id="5dcfb-300">Export completed version of a derived format</span></span>

1. <span data-ttu-id="5dcfb-301">Seleccione el formato **Formato para aprender llamadas con parámetros (personalizado)** en el árbol de las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-301">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="5dcfb-302">En la ficha desplegable **Versiones**, seleccione la versión 1.1.1 completa.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-302">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="5dcfb-303">Seleccione **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-303">Select **Exchange**.</span></span>
4. <span data-ttu-id="5dcfb-304">Seleccione **Exportar como archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-304">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="5dcfb-305">Almacene la configuración descargada localmente, en formato XML.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-305">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="5dcfb-306">Probar los formatos de ER</span><span class="sxs-lookup"><span data-stu-id="5dcfb-306">Test ER formats</span></span> 
<span data-ttu-id="5dcfb-307">Puede ejecutar los formatos de ER inicial y mejorado para asegurarse de que funcionan los campos calculados con parámetros configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-307">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="5dcfb-308">Importar configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="5dcfb-308">Import ER configurations</span></span>
<span data-ttu-id="5dcfb-309">Puede importar las configuraciones revisadas de RCS mediante el repositorio de ER del tipo **RCS**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-309">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="5dcfb-310">Si ya ha revisado los pasos en el tema, utilice el tema [Importar configuraciones de informes electrónicos (ER) desde Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use el repositorio de ER configurado para importar las configuraciones tratadas anteriormente en este tema a su entorno.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-310">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="5dcfb-311">De lo contrario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-311">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="5dcfb-312">Seleccione la empresa **DEMF** y en el panel predeterminado, seleccione **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-312">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="5dcfb-313">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-313">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="5dcfb-314">Importe las configuraciones desde el Centro de descarga de Microsoft en la siguiente secuencia: modelo de datos, distribución de modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-314">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="5dcfb-315">Realice los pasos siguientes para cada configuración de ER:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-315">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="5dcfb-316">Seleccione **Intercambiar.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-316">Select **Exchange.**</span></span>
    2. <span data-ttu-id="5dcfb-317">Seleccione **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-317">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="5dcfb-318">Seleccione **Examinar** para seleccionar la configuración necesaria de ER en formato XML.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-318">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="5dcfb-319">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-319">Select **OK**.</span></span>

4. <span data-ttu-id="5dcfb-320">Importe la versión 1.1.1 completada de RCS de formato **Formato para aprender llamadas con parámetros (personalizado)**:</span><span class="sxs-lookup"><span data-stu-id="5dcfb-320">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="5dcfb-321">Seleccione **Intercambiar.**</span><span class="sxs-lookup"><span data-stu-id="5dcfb-321">Select **Exchange.**</span></span>
    2. <span data-ttu-id="5dcfb-322">Seleccione **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-322">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="5dcfb-323">Seleccione **Examinar** para seleccionar el archivo almacenado localmente **Formato para aprender las llamadas con parámetros (personalizado)** en formato XML.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-323">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="5dcfb-324">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-324">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="5dcfb-325">Ejecutar los formatos de ER</span><span class="sxs-lookup"><span data-stu-id="5dcfb-325">Run ER formats</span></span>

1. <span data-ttu-id="5dcfb-326">En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-326">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="5dcfb-327">Seleccione **Formato para aprender llamadas con parámetros**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-327">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="5dcfb-328">Seleccione **Ejecutar** en la cinta de opciones superior.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-328">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="5dcfb-329">Guarde la salida generada localmente.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-329">Save the locally generated output.</span></span>
5. <span data-ttu-id="5dcfb-330">Seleccione **Formato para aprender llamadas con parámetros (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-330">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="5dcfb-331">Seleccione **Ejecutar** en la cinta de opciones superior.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-331">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="5dcfb-332">Guarde la salida generada localmente.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-332">Save the generated output locally.</span></span> 
8. <span data-ttu-id="5dcfb-333">Compare el contenido de las salidas generadas.</span><span class="sxs-lookup"><span data-stu-id="5dcfb-333">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5dcfb-334">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5dcfb-334">Additional resources</span></span>
[<span data-ttu-id="5dcfb-335">Diseñador de fórmulas en los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="5dcfb-335">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
