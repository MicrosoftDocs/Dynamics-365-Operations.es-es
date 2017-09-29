---
title: "Definiciones de informes en el diseñador de informes financieros"
description: "Este artículo proporciona información acerca de las definiciones de informes. Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. Una definición de informe también proporciona opciones y ajustes para personalizar un informe."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 96090a3ae15294d98d6207c8eb4a1e58429ca9eb
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="52d35-105">Definiciones de informes en el diseñador de informes financieros</span><span class="sxs-lookup"><span data-stu-id="52d35-105">Report definitions in financial report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="52d35-106">Este artículo proporciona información acerca de las definiciones de informes.</span><span class="sxs-lookup"><span data-stu-id="52d35-106">This article provides information about report definitions.</span></span> <span data-ttu-id="52d35-107">Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="52d35-108">Una definición de informe también proporciona opciones y ajustes para personalizar un informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="52d35-109">Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="52d35-110">Una definición de informe también proporciona opciones y configuración adicionales que puede usar para personalizar un informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="52d35-111">Después de definir definiciones de filas y de columnas, debe combinarlas en una definición del informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="52d35-112">En este momento, también define otros aspectos de las definiciones, como el nivel de detalle y la fecha del informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="52d35-113">Después, puede guardar y generar un informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-113">You can then save and generate a report.</span></span> <span data-ttu-id="52d35-114">Los informes financieros ofrecen los niveles de detalle siguientes:</span><span class="sxs-lookup"><span data-stu-id="52d35-114">Financial reporting offers the following levels of detail:</span></span>

-   <span data-ttu-id="52d35-115">Financiero</span><span class="sxs-lookup"><span data-stu-id="52d35-115">Financial</span></span>
-   <span data-ttu-id="52d35-116">Financiero y contable</span><span class="sxs-lookup"><span data-stu-id="52d35-116">Financial and Account</span></span>
-   <span data-ttu-id="52d35-117">Financiero, contable y de transacciones</span><span class="sxs-lookup"><span data-stu-id="52d35-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="52d35-118">Sin embargo, en función de cómo se almacenen los datos en el sistema de Microsoft Dynamics ERP, los detalles de transacción pueden no estar disponibles en los informes.</span><span class="sxs-lookup"><span data-stu-id="52d35-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="52d35-119">Crear una definición del informe</span><span class="sxs-lookup"><span data-stu-id="52d35-119">Create a report definition</span></span>
1.  <span data-ttu-id="52d35-120">En el diseñador de informes, en el menú **Archivo**, haga clic en **Nuevo** y luego seleccione **Definición del informe**.</span><span class="sxs-lookup"><span data-stu-id="52d35-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2.  <span data-ttu-id="52d35-121">Especifique la información adecuada en las pestañas **Informe**, **Salida y distribución**, **Encabezados y pies de página** y **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="52d35-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="52d35-122">Contenido de una definición del informe</span><span class="sxs-lookup"><span data-stu-id="52d35-122">Contents of a report definition</span></span>
<span data-ttu-id="52d35-123">La siguiente tabla describe las pestañas en una definición del informe y cómo se usa la información.</span><span class="sxs-lookup"><span data-stu-id="52d35-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52d35-124">Tabulación</span><span class="sxs-lookup"><span data-stu-id="52d35-124">Tab</span></span></th>
<th><span data-ttu-id="52d35-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="52d35-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="52d35-126">Informe</span><span class="sxs-lookup"><span data-stu-id="52d35-126">Report</span></span></td>
<td><span data-ttu-id="52d35-127">Crear un informe, configurar un informe o modificar un informe existente.</span><span class="sxs-lookup"><span data-stu-id="52d35-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52d35-128">Salida y distribución</span><span class="sxs-lookup"><span data-stu-id="52d35-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="52d35-129">Cambiar el tipo de salida y destino del informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="52d35-130">Encabezados y pies de página</span><span class="sxs-lookup"><span data-stu-id="52d35-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="52d35-131">Definir y aplicar formato a los encabezados y los pies de página para el informe.</span><span class="sxs-lookup"><span data-stu-id="52d35-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="52d35-132">Por ejemplo, puede agregar texto o imágenes al encabezado o al pie de página.</span><span class="sxs-lookup"><span data-stu-id="52d35-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="52d35-133">Los informes financieros admiten archivos .bmp, .jpg y .png para imágenes.</span><span class="sxs-lookup"><span data-stu-id="52d35-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="52d35-134">También puede agregar códigos de autotexto para insertar otra información, como el nombre de la empresa, el nombre del informe o el número de página.</span><span class="sxs-lookup"><span data-stu-id="52d35-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="52d35-135">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52d35-135">Settings</span></span></td>
<td><span data-ttu-id="52d35-136">Especificar la configuración de la definición del informe, como los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="52d35-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="52d35-137">Formato e importes de redondeo</span><span class="sxs-lookup"><span data-stu-id="52d35-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="52d35-138">Formato de los informes de detalles</span><span class="sxs-lookup"><span data-stu-id="52d35-138">Format detail reports</span></span></li>
<li><span data-ttu-id="52d35-139">Formato de organigramas</span><span class="sxs-lookup"><span data-stu-id="52d35-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="52d35-140">Generar un informe de excepciones</span><span class="sxs-lookup"><span data-stu-id="52d35-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="52d35-141">Especificar conversión de divisa</span><span class="sxs-lookup"><span data-stu-id="52d35-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="52d35-142">Detalles del subtotal y de la cuenta de filtro</span><span class="sxs-lookup"><span data-stu-id="52d35-142">Subtotal and filter account details</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="52d35-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52d35-143">See also</span></span>
--------

[<span data-ttu-id="52d35-144">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="52d35-144">Financial reporting</span></span>](financial-reporting-intro.md)




