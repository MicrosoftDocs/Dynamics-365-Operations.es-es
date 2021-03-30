---
title: Importar datos históricos para previsiones de la demanda
description: Para obtener previsiones precisas de demanda necesita datos históricos de demanda por artículo o por clave de asignación de artículos. En este tema se explica cómo usar entidades de datos para importar datos históricos de la demanda desde cualquier sistema, de modo que tenga un historial más amplio de los datos de previsión de la demanda.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d415895bd05b9ab1a2311ab69cc3757047df91db
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204625"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="57dd9-104">Importar datos históricos para previsiones de la demanda</span><span class="sxs-lookup"><span data-stu-id="57dd9-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57dd9-105">Como ayuda para garantizar la precisión de las previsiones de demanda, debe tener todos los datos históricos de demanda que pueda obtener por artículo o por clave de asignación de artículos.</span><span class="sxs-lookup"><span data-stu-id="57dd9-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="57dd9-106">Si aún no ha importado los datos históricos de demanda, utilice la entidad de datos **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) de Dynamics 365 Supply Chain Management para importarlos.</span><span class="sxs-lookup"><span data-stu-id="57dd9-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="57dd9-107">En el espacio de trabajo **Administración de datos** podrá ver una descripción de todos los campos de la entidad.</span><span class="sxs-lookup"><span data-stu-id="57dd9-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="57dd9-108">Abra el espacio trabajo **Administración de datos** .</span><span class="sxs-lookup"><span data-stu-id="57dd9-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="57dd9-109">Seleccione el icono **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="57dd9-110">Busque la lista de entidades para **Demanda externa histórica**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="57dd9-111">Seleccione **Campos objetivo**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-111">Select **Target fields**.</span></span> <span data-ttu-id="57dd9-112">Los siguientes campos de entidad son obligatorios: sitio (**DeliveringSiteId**), fecha (**DemandDate**), cantidad (**DemandQuantity**), y número de artículo (**ItemNumber**) o clave de asignación de artículos (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="57dd9-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="57dd9-113">Para usar la entidad de datos debe tener un archivo de Microsoft Excel o de valores separados por comas (CSV) que contenga los datos históricos de la demanda.</span><span class="sxs-lookup"><span data-stu-id="57dd9-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="57dd9-114">El siguiente ejemplo muestra cómo importar datos desde un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="57dd9-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="57dd9-115">Para obtener más información sobre cómo importar datos, incluido cómo limpiar datos después de una importación, consulte [Descripción general de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) y sus temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="57dd9-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="57dd9-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57dd9-116">Example</span></span>

<span data-ttu-id="57dd9-117">Puede utilizar el siguiente archivo como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="57dd9-117">You can use the following file as an example.</span></span> <span data-ttu-id="57dd9-118">Descargue [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span><span class="sxs-lookup"><span data-stu-id="57dd9-118">Download the [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span></span> <span data-ttu-id="57dd9-119">Este archivo contiene los datos históricos de la demanda para el artículo D0001.</span><span class="sxs-lookup"><span data-stu-id="57dd9-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="57dd9-120">Contiene solo los siguientes campos obligatorios: sitio, cantidad y la fecha de la demanda.</span><span class="sxs-lookup"><span data-stu-id="57dd9-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="57dd9-121">Seleccione la empresa en la que desea importar los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="57dd9-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="57dd9-122">Abra el espacio trabajo **Administración de datos** .</span><span class="sxs-lookup"><span data-stu-id="57dd9-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="57dd9-123">Seleccione el icono **Importar**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="57dd9-124">Escriba un nombre para el proyecto de importación, como por ejemplo **Demanda histórica de importación para el artículo D0001**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="57dd9-125">En el campo **Formato de datos de origen**, seleccione el formato de archivo del archivo que está importando.</span><span class="sxs-lookup"><span data-stu-id="57dd9-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="57dd9-126">Para importar el archivo HistoricalDemandData para este ejemplo, seleccione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="57dd9-127">En el campo **Nombre de entidad**, seleccione **Demanda externa histórica**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="57dd9-128">Guarde el archivo en su equipo y, a continuación, cárguelo.</span><span class="sxs-lookup"><span data-stu-id="57dd9-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="57dd9-129">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-129">Select **Import**.</span></span>
9. <span data-ttu-id="57dd9-130">Se abre automáticamente la página **Resumen de la ejecución**.</span><span class="sxs-lookup"><span data-stu-id="57dd9-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="57dd9-131">Compruebe los datos importados en la página.</span><span class="sxs-lookup"><span data-stu-id="57dd9-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="57dd9-132">Una vez importados los datos históricos de la demanda, puede generar una previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="57dd9-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="57dd9-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="57dd9-133">Additional resources</span></span>

[<span data-ttu-id="57dd9-134">Generar previsión estadística de línea base</span><span class="sxs-lookup"><span data-stu-id="57dd9-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="57dd9-135">Visión general de los trabajos de exportación e importación de datos</span><span class="sxs-lookup"><span data-stu-id="57dd9-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]