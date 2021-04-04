---
title: 'Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para utilizar archivos de administración de documentos (adjuntos) en la salida de informes electrónicos. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559782"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="25972-104">Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)</span><span class="sxs-lookup"><span data-stu-id="25972-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25972-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un informe electrónico (ER) para usar los archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="25972-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="25972-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="25972-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="25972-107">Para completar estos pasos, primero debe completar los pasos de la guía de tareas “ER Uso de los archivos de gestión de documentos en formatos de salida (Parte 1: Preparar el modelo de datos)”.</span><span class="sxs-lookup"><span data-stu-id="25972-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="25972-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="25972-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="25972-109">Extienda el modelo de datos para mostrar los archivos de gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="25972-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="25972-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="25972-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="25972-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="25972-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="25972-112">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="25972-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="25972-113">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.</span><span class="sxs-lookup"><span data-stu-id="25972-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="25972-114">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="25972-114">Click Designer.</span></span>
6. <span data-ttu-id="25972-115">En el árbol, seleccione “Modelo de factura (InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="25972-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="25972-116">Extenderemos este modelo de datos para exponer en él archivos que se hayan adjuntado a un pedido de ventas relacionado con una factura procesada electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="25972-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="25972-117">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="25972-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="25972-118">En el campo Nombre, introduzca "Facturar adjuntos".</span><span class="sxs-lookup"><span data-stu-id="25972-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="25972-119">Facturar adjuntos</span><span class="sxs-lookup"><span data-stu-id="25972-119">Invoice attachments</span></span>  
9. <span data-ttu-id="25972-120">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="25972-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="25972-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="25972-121">Click Add.</span></span>
11. <span data-ttu-id="25972-122">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="25972-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="25972-123">En el campo Nombre, introduzca "Contenido de archivo".</span><span class="sxs-lookup"><span data-stu-id="25972-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="25972-124">Contenido del archivo</span><span class="sxs-lookup"><span data-stu-id="25972-124">File content</span></span>  
13. <span data-ttu-id="25972-125">En el campo Tipo de artículo, seleccione "Contenedor".</span><span class="sxs-lookup"><span data-stu-id="25972-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="25972-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="25972-126">Click Add.</span></span>
15. <span data-ttu-id="25972-127">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="25972-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="25972-128">En el campo Nombre, introduzca "Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="25972-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="25972-129">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="25972-129">File name</span></span>  
17. <span data-ttu-id="25972-130">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="25972-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="25972-131">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="25972-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="25972-132">Asigne nuevos elementos de modelo de datos a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="25972-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="25972-133">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25972-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="25972-134">Use el Filtro rápido para filtrar el campo Definición con un valor de 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="25972-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="25972-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="25972-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="25972-136">Asignaremos nuevos elementos del modelo a los orígenes de datos adecuados.</span><span class="sxs-lookup"><span data-stu-id="25972-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="25972-137">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="25972-137">Click Designer.</span></span>
4. <span data-ttu-id="25972-138">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="25972-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="25972-139">En el árbol, expanda “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="25972-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="25972-140">En el árbol, seleccione “Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="25972-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="25972-141">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="25972-141">Click Edit.</span></span>
8. <span data-ttu-id="25972-142">En el campo Fórmula, introduzca "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="25972-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="25972-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="25972-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="25972-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="25972-144">Click Save.</span></span>
10. <span data-ttu-id="25972-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-145">Close the page.</span></span>
11. <span data-ttu-id="25972-146">En el árbol, seleccione “Facturar adjuntos\Contenido de archivo”.</span><span class="sxs-lookup"><span data-stu-id="25972-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="25972-147">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="25972-147">Click Edit.</span></span>
13. <span data-ttu-id="25972-148">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="25972-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="25972-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="25972-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="25972-150">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="25972-150">Click Save.</span></span>
15. <span data-ttu-id="25972-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-151">Close the page.</span></span>
16. <span data-ttu-id="25972-152">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="25972-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="25972-153">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="25972-153">Click Edit.</span></span>
18. <span data-ttu-id="25972-154">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="25972-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="25972-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="25972-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="25972-156">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="25972-156">Click Save.</span></span>
20. <span data-ttu-id="25972-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-157">Close the page.</span></span>
21. <span data-ttu-id="25972-158">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="25972-158">Click Save.</span></span>
22. <span data-ttu-id="25972-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-159">Close the page.</span></span>
23. <span data-ttu-id="25972-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-160">Close the page.</span></span>
24. <span data-ttu-id="25972-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25972-161">Close the page.</span></span>
25. <span data-ttu-id="25972-162">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="25972-162">Click Change status.</span></span>
26. <span data-ttu-id="25972-163">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="25972-163">Click Complete.</span></span>
27. <span data-ttu-id="25972-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="25972-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]