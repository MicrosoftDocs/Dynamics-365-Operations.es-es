---
title: Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda
description: Este artículo describe cómo excluir valores atípicos de los datos históricos que se usan para calcular una previsión de la demanda. Al excluir los valores atípicos se puede mejorar precisión de la previsión.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9dec963ed5abd6f77e82029a3ea5ba1a69d44e36
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436724"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="f4ee2-104">Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="f4ee2-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4ee2-105">Este artículo describe cómo excluir valores atípicos de los datos históricos que se usan para calcular una previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="f4ee2-106">Al excluir los valores atípicos se puede mejorar precisión de la previsión.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="f4ee2-107">Puede excluir valores atípicos para mejorar la precisión de la previsión.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="f4ee2-108">Esta tarea es opcional.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-108">This is an optional task.</span></span> <span data-ttu-id="f4ee2-109">Esta es una visión general del proceso:</span><span class="sxs-lookup"><span data-stu-id="f4ee2-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="f4ee2-110">Haga clic en **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Eliminación de valores atípicos** para abrir la página **Eliminación de valores atípicos**, donde puede usar una consulta para seleccionar las transacciones que desea excluir.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="f4ee2-111">Seleccione la empresa a la que se aplica la consulta y especifique un nombre y una descripción.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="f4ee2-112">El campo **Fecha de consulta** se establece automáticamente en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="f4ee2-113">Seleccione la casilla **Activo** para excluir de los datos históricos las transacciones que se encuentran mediante la consulta.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="f4ee2-114">Esta configuración se aplicará cuando cree una previsión de línea base.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="f4ee2-115">En la página **Consulta de eliminación de valores atípicos** puede agregar, quitar y seleccionar los criterios que definen las transacciones que se excluirán al calcular la previsión de línea base.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="f4ee2-116">Por ejemplo, seleccione un artículo o una transacción de pedido concreto que desee excluir.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="f4ee2-117">Haga clic en **Mostrar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-117">Click **Display transactions**.</span></span> <span data-ttu-id="f4ee2-118">La página **Transacciones de valores atípicos** enumera las transacciones que cumplen los criterios que se define en la consulta y que se excluyen de los datos históricos al calcular la previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="f4ee2-119">**Nota:** también puede crear una consulta basada en una pregunta existente.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="f4ee2-120">Seleccione la consulta que copiar y, a continuación, haga clic en **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="f4ee2-121">El campo **Fecha de consulta** identifica la versión.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="f4ee2-122">Puede usar la consulta tal cual, o puede hacer clic en **Editar consulta** para modificar los criterios.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="f4ee2-123">Puede modificar el nombre y la descripción de la nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="f4ee2-123">You can optionally modify the name and description of the new query.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f4ee2-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f4ee2-124">Additional resources</span></span>
--------

[<span data-ttu-id="f4ee2-125">Visión general de la previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="f4ee2-125">Demand forecasting overview</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="f4ee2-126">Supervisión de la precisión de previsión</span><span class="sxs-lookup"><span data-stu-id="f4ee2-126">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)



