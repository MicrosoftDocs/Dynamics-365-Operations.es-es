---
title: Definiciones de informes en el diseñador de informes financieros
description: Este artículo proporciona información acerca de las definiciones de informes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7d5531112cfb803912849af3af785b2a69a79f3d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093423"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="8b004-103">Definiciones de informes en el diseñador de informes financieros</span><span class="sxs-lookup"><span data-stu-id="8b004-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b004-104">Este artículo proporciona información acerca de las definiciones de informes.</span><span class="sxs-lookup"><span data-stu-id="8b004-104">This article provides information about report definitions.</span></span> <span data-ttu-id="8b004-105">Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="8b004-106">Una definición de informe también proporciona opciones y ajustes para personalizar un informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="8b004-107">Una definición del informe es un componente de informe (o un bloque de creación) que utiliza una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="8b004-108">Una definición de informe también proporciona opciones y valores de configuración que puede usar para personalizar un informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="8b004-109">Después de definir definiciones de filas y de columnas, debe combinarlas en una definición del informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="8b004-110">En este momento, también define otros aspectos de las definiciones, como el nivel de detalle y la fecha del informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="8b004-111">Después, puede guardar y generar un informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-111">You can then save and generate a report.</span></span> <span data-ttu-id="8b004-112">Los informes financieros ofrecen los niveles de detalle siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b004-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="8b004-113">Financiero</span><span class="sxs-lookup"><span data-stu-id="8b004-113">Financial</span></span>
- <span data-ttu-id="8b004-114">Financiero y contable</span><span class="sxs-lookup"><span data-stu-id="8b004-114">Financial and Account</span></span>
- <span data-ttu-id="8b004-115">Financiero, contable y de transacciones</span><span class="sxs-lookup"><span data-stu-id="8b004-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="8b004-116">No obstante, según la forma en que se almacenan los datos en el sistema Microsoft Dynamics ERP, es posible que los detalles de transacción no estén disponibles en los informes.</span><span class="sxs-lookup"><span data-stu-id="8b004-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="8b004-117">Crear una definición del informe</span><span class="sxs-lookup"><span data-stu-id="8b004-117">Create a report definition</span></span>
1. <span data-ttu-id="8b004-118">En el diseñador de informes, en el menú **Archivo**, haga clic en **Nuevo** y luego seleccione **Definición del informe**.</span><span class="sxs-lookup"><span data-stu-id="8b004-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="8b004-119">Especifique la información adecuada en las pestañas **Informe**, **Salida y distribución**, **Encabezados y pies de página** y **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="8b004-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="8b004-120">Contenido de una definición del informe</span><span class="sxs-lookup"><span data-stu-id="8b004-120">Contents of a report definition</span></span>
<span data-ttu-id="8b004-121">La siguiente tabla describe las pestañas en una definición del informe y cómo se usa la información.</span><span class="sxs-lookup"><span data-stu-id="8b004-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="8b004-122">Pestaña</span><span class="sxs-lookup"><span data-stu-id="8b004-122">Tab</span></span></th>
<th><span data-ttu-id="8b004-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b004-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="8b004-124">Informe</span><span class="sxs-lookup"><span data-stu-id="8b004-124">Report</span></span></td>
<td><span data-ttu-id="8b004-125">Crear un informe, configurar un informe o modificar un informe existente.</span><span class="sxs-lookup"><span data-stu-id="8b004-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8b004-126">Salida y distribución</span><span class="sxs-lookup"><span data-stu-id="8b004-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="8b004-127">Cambiar el tipo de salida y destino del informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8b004-128">Encabezados y pies de página</span><span class="sxs-lookup"><span data-stu-id="8b004-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="8b004-129">Definir y aplicar formato a los encabezados y los pies de página para el informe.</span><span class="sxs-lookup"><span data-stu-id="8b004-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="8b004-130">Por ejemplo, puede agregar texto o imágenes al encabezado o al pie de página.</span><span class="sxs-lookup"><span data-stu-id="8b004-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="8b004-131">Los informes financieros admiten archivos .bmp, .jpg y .png para imágenes.</span><span class="sxs-lookup"><span data-stu-id="8b004-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="8b004-132">También puede agregar códigos de autotexto para insertar otra información, como el nombre de la empresa, el nombre del informe o el número de página.</span><span class="sxs-lookup"><span data-stu-id="8b004-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="8b004-133">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b004-133">Settings</span></span></td>
<td><span data-ttu-id="8b004-134">Especificar la configuración de la definición del informe, como los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="8b004-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="8b004-135">Formato e importes de redondeo</span><span class="sxs-lookup"><span data-stu-id="8b004-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="8b004-136">Formato de los informes de detalles</span><span class="sxs-lookup"><span data-stu-id="8b004-136">Format detail reports</span></span></li>
<li><span data-ttu-id="8b004-137">Formato de organigramas</span><span class="sxs-lookup"><span data-stu-id="8b004-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="8b004-138">Generar un informe de excepciones</span><span class="sxs-lookup"><span data-stu-id="8b004-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="8b004-139">Especificar conversión de divisa</span><span class="sxs-lookup"><span data-stu-id="8b004-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="8b004-140">Detalles del subtotal y de la cuenta de filtro</span><span class="sxs-lookup"><span data-stu-id="8b004-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="8b004-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8b004-141">Additional resources</span></span>

[<span data-ttu-id="8b004-142">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="8b004-142">Financial reporting</span></span>](financial-reporting-intro.md)
