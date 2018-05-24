---
title: "Importar datos históricos para previsiones de la demanda"
description: "Para obtener previsiones precisas de demanda necesita datos históricos de demanda por artículo o por clave de asignación de artículos. En este tema se explica cómo usar entidades de datos para importar datos históricos de la demanda desde cualquier sistema, de modo que tenga un historial más amplio de los datos de previsión de la demanda."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e7975003620d951717c66144c8d0521de0f69158
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="98cc1-104">Importar datos históricos para previsiones de la demanda</span><span class="sxs-lookup"><span data-stu-id="98cc1-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98cc1-105">Como ayuda para garantizar la precisión de las previsiones de demanda, debe tener todos los datos históricos de demanda que pueda obtener por artículo o por clave de asignación de artículos.</span><span class="sxs-lookup"><span data-stu-id="98cc1-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="98cc1-106">Si aún no ha importado los datos históricos de demanda, utilice la entidad de datos **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) de Microsoft Dynamics 365 for Finance and Operations para importarlos.</span><span class="sxs-lookup"><span data-stu-id="98cc1-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Microsoft Dynamics 365 for Finance and Operations to import it.</span></span>

<span data-ttu-id="98cc1-107">En el espacio de trabajo **Administración de datos** podrá ver una descripción de todos los campos de la entidad.</span><span class="sxs-lookup"><span data-stu-id="98cc1-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="98cc1-108">Abra el espacio trabajo **Administración de datos** .</span><span class="sxs-lookup"><span data-stu-id="98cc1-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="98cc1-109">Haga clic en el icono **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="98cc1-110">Busque la lista de entidades para **Demanda externa histórica**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="98cc1-111">Haga clic en **Campos objetivo**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-111">Click **Target fields**.</span></span> <span data-ttu-id="98cc1-112">Los siguientes campos de entidad son obligatorios: sitio (**DeliveringSiteId**), fecha (**DemandDate**), cantidad (**DemandQuantity**), y número de artículo (**ItemNumber**) o clave de asignación de artículos (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="98cc1-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="98cc1-113">Para usar la entidad de datos debe tener un archivo de Microsoft Excel o de valores separados por comas (CSV) que contenga los datos históricos de la demanda.</span><span class="sxs-lookup"><span data-stu-id="98cc1-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="98cc1-114">El siguiente ejemplo muestra cómo importar datos desde un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="98cc1-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="98cc1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98cc1-115">Example</span></span>

<span data-ttu-id="98cc1-116">Puede utilizar el siguiente archivo como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="98cc1-116">You can use the following file as an example.</span></span> <span data-ttu-id="98cc1-117">Descargue [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="98cc1-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="98cc1-118">Este archivo contiene los datos históricos de la demanda para el artículo D0001.</span><span class="sxs-lookup"><span data-stu-id="98cc1-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="98cc1-119">Contiene solo los siguientes campos obligatorios: sitio, cantidad y la fecha de la demanda.</span><span class="sxs-lookup"><span data-stu-id="98cc1-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="98cc1-120">Seleccione la empresa en la que desea importar los datos históricos.</span><span class="sxs-lookup"><span data-stu-id="98cc1-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="98cc1-121">Abra el espacio trabajo **Administración de datos** .</span><span class="sxs-lookup"><span data-stu-id="98cc1-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="98cc1-122">Haga clic en el icono **Importar**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="98cc1-123">Escriba un nombre para el proyecto de importación, como por ejemplo **Demanda histórica de importación para el artículo D0001**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="98cc1-124">En el campo **Formato de datos de origen**, seleccione el formato de archivo del archivo que está importando.</span><span class="sxs-lookup"><span data-stu-id="98cc1-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="98cc1-125">Para importar el archivo HistoricalDemandData para este ejemplo, seleccione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="98cc1-126">En el campo **Nombre de entidad**, seleccione **Demanda externa histórica**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="98cc1-127">Guarde el archivo en su equipo y, a continuación, cárguelo.</span><span class="sxs-lookup"><span data-stu-id="98cc1-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="98cc1-128">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-128">Click **Import**.</span></span>
9. <span data-ttu-id="98cc1-129">Se abre automáticamente la página **Resumen de la ejecución**.</span><span class="sxs-lookup"><span data-stu-id="98cc1-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="98cc1-130">Compruebe los datos importados en la página.</span><span class="sxs-lookup"><span data-stu-id="98cc1-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="98cc1-131">Una vez importados los datos históricos de la demanda, puede generar una previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="98cc1-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98cc1-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="98cc1-132">Additional resources</span></span>

[<span data-ttu-id="98cc1-133">Generar previsión estadística de línea base</span><span class="sxs-lookup"><span data-stu-id="98cc1-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)

