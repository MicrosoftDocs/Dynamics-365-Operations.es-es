---
title: Contenido en Power BI de Real frente a presupuesto
description: "Este tema describe el contenido en Power BI de Real frente a presupuesto Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido."
author: ryansandness
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 2a0ad5af4e4d7da09690331dc9d1a51d2e97a664
ms.contentlocale: es-es
ms.lasthandoff: 12/01/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="fe2aa-104">Contenido en Power BI de Real frente a presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="fe2aa-105">Este tema describe el contenido en Microsoft Power BI de **Real frente a presupuesto**</span><span class="sxs-lookup"><span data-stu-id="fe2aa-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="fe2aa-106">Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="fe2aa-107">Información general</span><span class="sxs-lookup"><span data-stu-id="fe2aa-107">Overview</span></span>

<span data-ttu-id="fe2aa-108">El contenido en Power BI de **Real rente a presupuesto** se creó para aquellas personas que son responsables de supervisar los valores reales frente al presupuesto en su organización.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="fe2aa-109">El contenido en Power BI de **Real frente a presupuesto** proporciona visibilidad en las desviaciones de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="fe2aa-110">Puede analizar el presupuesto para el año actual por categoría de cuenta, código de presupuesto, cuenta principal, descripciones de la cuenta principal o período fiscal para obtener una mejor comprensión de los motivos que producen las desviaciones.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="fe2aa-111">Acceso al contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="fe2aa-111">Accessing the Power BI content</span></span>
<span data-ttu-id="fe2aa-112">Los informes del contenido de Power BI **Valor real frente a presupuesto** se muestran en los espacios de trabajo **Presupuestos y previsiones de libro mayor** y **CFO**.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="fe2aa-113">Informes que se incluyen en el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="fe2aa-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="fe2aa-114">La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Real frente a presupuesto**.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="fe2aa-115">Informe</span><span class="sxs-lookup"><span data-stu-id="fe2aa-115">Report</span></span>                      | <span data-ttu-id="fe2aa-116">Métricas</span><span class="sxs-lookup"><span data-stu-id="fe2aa-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="fe2aa-117">Gastos reales frente a gastos de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="fe2aa-118">Total de gastos este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-118">Total expenses this year</span></span></li><li><span data-ttu-id="fe2aa-119">Total de gastos de presupuesto este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="fe2aa-120">Ingresos reales frente a ingresos de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="fe2aa-121">Ingresos totales este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-121">Total revenue this year</span></span></li><li><span data-ttu-id="fe2aa-122">Total de ingresos de presupuesto este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="fe2aa-123">Gastos</span><span class="sxs-lookup"><span data-stu-id="fe2aa-123">Expense</span></span>                     | <ul><li><span data-ttu-id="fe2aa-124">Total de gastos este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-124">Total expenses this year</span></span></li><li><span data-ttu-id="fe2aa-125">Objetivo de gastos en función de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="fe2aa-126">Ingresos</span><span class="sxs-lookup"><span data-stu-id="fe2aa-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="fe2aa-127">Ingresos totales este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-127">Total revenue this year</span></span></li><li><span data-ttu-id="fe2aa-128">Objetivo de ingresos en función de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="fe2aa-129">Ingresos netos</span><span class="sxs-lookup"><span data-stu-id="fe2aa-129">Net income</span></span>                  | <ul><li><span data-ttu-id="fe2aa-130">Ingresos netos este año</span><span class="sxs-lookup"><span data-stu-id="fe2aa-130">Net income this year</span></span></li><li><span data-ttu-id="fe2aa-131">Objetivo de ingresos netos en función de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="fe2aa-132">Ampliar el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="fe2aa-132">Extending the Power BI content</span></span>
<span data-ttu-id="fe2aa-133">Mediante los paquetes de contenido disponibles en Microsoft Dynamics Lifecycle Services (LCS), puede ofrecer análisis muy buenos a las personas que no inician sesión en Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="fe2aa-134">Puede modificar estos paquetes de contenido para que incluyan otros informes o representaciones visuales y, a continuación, publicar los paquetes de contenidos en el inquilino de Power BI.com para su análisis.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="fe2aa-135">Puede encontrar el contenido en Power BI de **Real frente a presupuesto** en la biblioteca de activos compartidos de LCS.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="fe2aa-136">Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="fe2aa-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="fe2aa-137">Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).</span><span class="sxs-lookup"><span data-stu-id="fe2aa-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="fe2aa-138">Comprensión del modelo de datos y de las entidades</span><span class="sxs-lookup"><span data-stu-id="fe2aa-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="fe2aa-139">Entidad</span><span class="sxs-lookup"><span data-stu-id="fe2aa-139">Entity</span></span>                    | <span data-ttu-id="fe2aa-140">Contenido</span><span class="sxs-lookup"><span data-stu-id="fe2aa-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="fe2aa-141">Actividades de contabilidad general</span><span class="sxs-lookup"><span data-stu-id="fe2aa-141">General Ledger Activities</span></span> | <span data-ttu-id="fe2aa-142">Importes de transacción de contabilidad general</span><span class="sxs-lookup"><span data-stu-id="fe2aa-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="fe2aa-143">Actividades de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-143">Budget Activities</span></span>         | <span data-ttu-id="fe2aa-144">Importes de transacción para el registro presupuestario</span><span class="sxs-lookup"><span data-stu-id="fe2aa-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="fe2aa-145">Cuentas principales</span><span class="sxs-lookup"><span data-stu-id="fe2aa-145">Main Accounts</span></span>             | <span data-ttu-id="fe2aa-146">Cuentas principales para filtrar informes</span><span class="sxs-lookup"><span data-stu-id="fe2aa-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="fe2aa-147">Calendarios fiscales</span><span class="sxs-lookup"><span data-stu-id="fe2aa-147">Fiscal Calendars</span></span>          | <span data-ttu-id="fe2aa-148">Calendarios fiscales para filtrar informes</span><span class="sxs-lookup"><span data-stu-id="fe2aa-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="fe2aa-149">Libros mayores</span><span class="sxs-lookup"><span data-stu-id="fe2aa-149">Ledgers</span></span>                   | <span data-ttu-id="fe2aa-150">Libros mayores que se pueden usar para filtrar el informe en la contabilidad actual</span><span class="sxs-lookup"><span data-stu-id="fe2aa-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="fe2aa-151">Códigos de presupuesto</span><span class="sxs-lookup"><span data-stu-id="fe2aa-151">Budget Codes</span></span>              | <span data-ttu-id="fe2aa-152">Códigos presupuestarios para filtrar informes</span><span class="sxs-lookup"><span data-stu-id="fe2aa-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="fe2aa-153">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="fe2aa-153">Legal Entities</span></span>            | <span data-ttu-id="fe2aa-154">Entidades jurídicas que se pueden usar para filtrar el informe para la entidad jurídica actual</span><span class="sxs-lookup"><span data-stu-id="fe2aa-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

