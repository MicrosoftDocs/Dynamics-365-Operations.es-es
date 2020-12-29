---
title: Modificar formatos al aplicar de nuevo plantillas de Excel
description: Para completar estos pasos en este procedimiento, primero debe completar el procedimiento - Diseñar una configuración de ER para generar informes en formato OPENXML”.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5b1bc5f227a0944c513dee2c12a5042decde872
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684244"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="cd1be-103">Modificar formatos al aplicar de nuevo plantillas de Excel</span><span class="sxs-lookup"><span data-stu-id="cd1be-103">Modify formats by reapplying Excel templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd1be-104">Para completar estos pasos en este procedimiento, primero debe completar el procedimiento - Diseñar una configuración de ER para generar informes en formato OPENXML”.</span><span class="sxs-lookup"><span data-stu-id="cd1be-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="cd1be-105">Este procedimiento explica cómo modificar una configuración de formado del informe electrónico (ER) aplicando de nuevo una plantilla de Microsoft Excel que ha sido modificada.</span><span class="sxs-lookup"><span data-stu-id="cd1be-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="cd1be-106">En este procedimiento, importará una plantilla modificade de Excel a la configuración de formato ER que ha sido creado por la empresa de ejemplo, Litware, Inc. y después generar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="cd1be-107">Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="cd1be-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="cd1be-108">Estos pasos se pueden completar mediante el conjunto de datos de GBSI.</span><span class="sxs-lookup"><span data-stu-id="cd1be-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="cd1be-109">Antes de empezar, descargue y guarde el archivo, SampleVendPaymWsReport2.xlsx, que se muestra en el tema de Ayuda, modifique el formato electrónico del informe reaplicando una plantilla de Excel (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="cd1be-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="cd1be-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="cd1be-111">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo.</span><span class="sxs-lookup"><span data-stu-id="cd1be-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="cd1be-112">Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="cd1be-112">If you don't see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="cd1be-113">Seleccionar formato del ER</span><span class="sxs-lookup"><span data-stu-id="cd1be-113">Select the ER format</span></span>
1. <span data-ttu-id="cd1be-114">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="cd1be-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="cd1be-115">En el árbol, expanda "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="cd1be-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="cd1be-116">En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="cd1be-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="cd1be-117">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-117">Click Attachments.</span></span>
    * <span data-ttu-id="cd1be-118">Tenga en cuenta que el archivo de Excel SampleVendPaymWsReport.xlsx se usa actualmente como plantilla para el procesamiento del diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="cd1be-119">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="cd1be-119">Click Open.</span></span>
    * <span data-ttu-id="cd1be-120">Haga clic en Abrir para explorar el diseño de la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="cd1be-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="cd1be-121">Revisar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="cd1be-121">Review the template.</span></span> <span data-ttu-id="cd1be-122">Tenga en cuenta que actualmente incluye los detalles siguientes para cada línea de pago: número de cuenta de proveedor, nombre del proveedor, banco, número de ruta, número de cuenta, débito, crédito y divisa.</span><span class="sxs-lookup"><span data-stu-id="cd1be-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="cd1be-123">Para este ejemplo, deseamos ampliar esta lista agregando los detalles acerca de la fecha de pago.</span><span class="sxs-lookup"><span data-stu-id="cd1be-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="cd1be-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cd1be-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="cd1be-125">Volver a aplicar una nueva plantilla de Excel al formato del ER</span><span class="sxs-lookup"><span data-stu-id="cd1be-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="cd1be-126">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="cd1be-126">Click Designer.</span></span>
    * <span data-ttu-id="cd1be-127">Abra la versión de borrador del formato de ER para su edición.</span><span class="sxs-lookup"><span data-stu-id="cd1be-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="cd1be-128">En el panel de acciones, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="cd1be-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="cd1be-129">Haga clic en Actualización desde Excel.</span><span class="sxs-lookup"><span data-stu-id="cd1be-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="cd1be-130">Haga clic en la “Actualizar plantilla" y seleccione el archivo SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="cd1be-130">Click 'Update template', and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="cd1be-131">Haga clic Actualizar plantilla y busque el archivo descargado anteriormente SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="cd1be-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="cd1be-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cd1be-132">Click OK.</span></span>
    * <span data-ttu-id="cd1be-133">Se aplica la plantilla de SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="cd1be-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="cd1be-134">La estructura del formato del ER se sincroniza con el contenido de la plantilla, cuyos artículos se agregan al formato del ER.</span><span class="sxs-lookup"><span data-stu-id="cd1be-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="cd1be-135">Cualquier elemento existente en el formato del ER que no se incluyan en la plantilla se quita de la definición del formato.</span><span class="sxs-lookup"><span data-stu-id="cd1be-135">Any existing elements in the ER format that aren't included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="cd1be-136">En el árbol, seleccione "Excel".</span><span class="sxs-lookup"><span data-stu-id="cd1be-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="cd1be-137">Tenga en cuenta que el campo Plantilla ahora contiene una referencia a la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="cd1be-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="cd1be-138">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-138">Click Attachments.</span></span>
7. <span data-ttu-id="cd1be-139">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="cd1be-139">Click Open.</span></span>
    * <span data-ttu-id="cd1be-140">Haga clic en Abrir para explorar el diseño de la plantilla de Excel modificada.</span><span class="sxs-lookup"><span data-stu-id="cd1be-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="cd1be-141">Revisar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="cd1be-141">Review the template.</span></span> <span data-ttu-id="cd1be-142">Tenga en cuenta que ahora incluye una línea para la fecha de pago.</span><span class="sxs-lookup"><span data-stu-id="cd1be-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="cd1be-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cd1be-143">Close the page.</span></span>
9. <span data-ttu-id="cd1be-144">En el árbol, expanda "Excel".</span><span class="sxs-lookup"><span data-stu-id="cd1be-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="cd1be-145">En el árbol, expanda 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="cd1be-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="cd1be-146">En el árbol, seleccione "Excel\LíneasPago\FechaPago".</span><span class="sxs-lookup"><span data-stu-id="cd1be-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="cd1be-147">Tenga en cuenta que el formato del ER ahora contiene un elemento más.</span><span class="sxs-lookup"><span data-stu-id="cd1be-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="cd1be-148">Se han agregado una celda, PaymDate, a la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="cd1be-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="cd1be-149">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="cd1be-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="cd1be-150">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="cd1be-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="cd1be-151">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="cd1be-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="cd1be-152">En el árbol, seleccione modelo\Pagos\Fecha de la transacción(TransactionDate).</span><span class="sxs-lookup"><span data-stu-id="cd1be-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="cd1be-153">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="cd1be-153">Click Bind.</span></span>
    * <span data-ttu-id="cd1be-154">Especifique qué datos se agregan a la nueva celda en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cd1be-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="cd1be-155">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="cd1be-155">Click Save.</span></span>
18. <span data-ttu-id="cd1be-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cd1be-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="cd1be-157">Habilitar la versión de borrador modificada del formato del ER para su uso en el procesamiento del diario de pagos</span><span class="sxs-lookup"><span data-stu-id="cd1be-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="cd1be-158">En el panel de acciones, haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="cd1be-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="cd1be-159">Haga clic en Parámetros de usuario.</span><span class="sxs-lookup"><span data-stu-id="cd1be-159">Click User parameters.</span></span>
3. <span data-ttu-id="cd1be-160">Seleccione Sí en el campo Parámetros de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cd1be-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="cd1be-161">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cd1be-161">Click OK.</span></span>
5. <span data-ttu-id="cd1be-162">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cd1be-162">Click Edit.</span></span>
6. <span data-ttu-id="cd1be-163">Seleccione Sí en el campo Borrador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cd1be-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="cd1be-164">Usar la versión de borrador modificada del formato del ER para el procesamiento del diario de pagos</span><span class="sxs-lookup"><span data-stu-id="cd1be-164">Use the modified draft version of the ER format for payment journal processing</span></span>

<span data-ttu-id="cd1be-165">Revise la hoja de cálculo creada, incluido el nuevo detalle de líneas de pago – fecha de pago.</span><span class="sxs-lookup"><span data-stu-id="cd1be-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  
