---
title: Importar datos históricos para previsiones de la demanda
description: Para obtener previsiones precisas de demanda necesita datos históricos de demanda por artículo o por clave de asignación de artículos. En este tema se explica cómo usar entidades de datos para importar datos históricos de la demanda desde cualquier sistema, de modo que tenga un historial más amplio de los datos de previsión de la demanda.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301659"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="81e95-104">Importar datos históricos para previsiones de la demanda</span><span class="sxs-lookup"><span data-stu-id="81e95-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81e95-105">Como ayuda para garantizar la precisión de las previsiones de demanda, debe tener todos los datos históricos de demanda que pueda obtener por artículo o por clave de asignación de artículos.</span><span class="sxs-lookup"><span data-stu-id="81e95-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="81e95-106">Si aún no ha importado los datos históricos de demanda, utilice la entidad de datos **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) de Dynamics 365 Supply Chain Management para importarlos.</span><span class="sxs-lookup"><span data-stu-id="81e95-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="81e95-107">En el espacio de trabajo **Administración de datos** podrá ver una descripción de todos los campos de la entidad.</span><span class="sxs-lookup"><span data-stu-id="81e95-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="81e95-108">Abra el espacio trabajo **Administración de datos** .</span><span class="sxs-lookup"><span data-stu-id="81e95-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="81e95-109">Seleccione el icono **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="81e95-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="81e95-110">Busque la lista de entidades para **Demanda externa histórica**.</span><span class="sxs-lookup"><span data-stu-id="81e95-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="81e95-111">Seleccione **Campos objetivo**.</span><span class="sxs-lookup"><span data-stu-id="81e95-111">Select **Target fields**.</span></span> <span data-ttu-id="81e95-112">Los siguientes campos de entidad son obligatorios: sitio (**DeliveringSiteId**), fecha (**DemandDate**), cantidad (**DemandQuantity**), y número de artículo (**ItemNumber**) o clave de asignación de artículos (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="81e95-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="81e95-113">Para usar la entidad de datos debe tener un archivo de Microsoft Excel o de valores separados por comas (CSV) que contenga los datos históricos de la demanda.</span><span class="sxs-lookup"><span data-stu-id="81e95-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="81e95-114">El siguiente ejemplo muestra cómo importar datos desde un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="81e95-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="81e95-115">Para obtener más información sobre cómo importar datos, incluido cómo limpiar datos después de una importación, consulte [Descripción general de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) y sus temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="81e95-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="81e95-116">Vea también [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="81e95-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]