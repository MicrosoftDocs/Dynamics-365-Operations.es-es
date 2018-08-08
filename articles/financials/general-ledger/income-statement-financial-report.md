---
title: Informe financiero de informe de ingresos
description: "En este artículo se describen los informes predeterminados para las declaraciones de ingresos. También se describen los componentes asociados con este informe."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9105e1de86ed2834b04f75c7d08c4021402bcfda
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="440dc-104">Informe financiero de informe de ingresos</span><span class="sxs-lookup"><span data-stu-id="440dc-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="440dc-105">En este artículo se describen los informes predeterminados para las declaraciones de ingresos.</span><span class="sxs-lookup"><span data-stu-id="440dc-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="440dc-106">También se describen los componentes asociados con este informe.</span><span class="sxs-lookup"><span data-stu-id="440dc-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="440dc-107">Informe de ingresos predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="440dc-108">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-108">Default report</span></span>             | <span data-ttu-id="440dc-109">Qué hace</span><span class="sxs-lookup"><span data-stu-id="440dc-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="440dc-110">Informe de ingresos – predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-110">Income Statement – Default</span></span> | <span data-ttu-id="440dc-111">Ofrece una vista de la rentabilidad de la organización para el período actual y también para el ejercicio hasta la fecha.</span><span class="sxs-lookup"><span data-stu-id="440dc-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="440dc-112">Bloques de creación</span><span class="sxs-lookup"><span data-stu-id="440dc-112">Building blocks</span></span>
<span data-ttu-id="440dc-113">El informe financiero del informe de ingresos usa los siguientes bloques de creación.</span><span class="sxs-lookup"><span data-stu-id="440dc-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="440dc-114">Informe predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-114">Default report</span></span>             | <span data-ttu-id="440dc-115">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="440dc-115">Row definition</span></span>                     | <span data-ttu-id="440dc-116">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="440dc-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="440dc-117">Informe de ingresos - predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-117">Income Statement - Default</span></span> | <span data-ttu-id="440dc-118">Resumen de informe de ingresos - predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="440dc-119">Periódico y anual - predeterminado</span><span class="sxs-lookup"><span data-stu-id="440dc-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="440dc-120">Definición de filas</span><span class="sxs-lookup"><span data-stu-id="440dc-120">Row definition</span></span>

<span data-ttu-id="440dc-121">La definición de filas, Resumen de informe de ingresos - predeterminado, contiene una sección para cada parte de un extracto tradicional de ingresos.</span><span class="sxs-lookup"><span data-stu-id="440dc-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="440dc-122">La dimensión Categoría de cuenta principal se usa para crear esta definición de filas.</span><span class="sxs-lookup"><span data-stu-id="440dc-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="440dc-123">Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="440dc-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="440dc-124">Definición de columnas</span><span class="sxs-lookup"><span data-stu-id="440dc-124">Column Definition</span></span>

<span data-ttu-id="440dc-125">Las definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.</span><span class="sxs-lookup"><span data-stu-id="440dc-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="440dc-126">**Periódico y anual - tipos de columna predeterminadas:**</span><span class="sxs-lookup"><span data-stu-id="440dc-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="440dc-127">**DESC** : la descripción de la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="440dc-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="440dc-128">**FD**: datos financieros para el período actual</span><span class="sxs-lookup"><span data-stu-id="440dc-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="440dc-129">**FD**: datos financieros para el año hasta la fecha</span><span class="sxs-lookup"><span data-stu-id="440dc-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="440dc-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="440dc-130">Additional resources</span></span>
--------

[<span data-ttu-id="440dc-131">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="440dc-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="440dc-132">Ver informes financieros</span><span class="sxs-lookup"><span data-stu-id="440dc-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="440dc-133">Blog de informes financieros de Dynamics</span><span class="sxs-lookup"><span data-stu-id="440dc-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




