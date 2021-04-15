---
title: 'Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para utilizar archivos de administración de documentos (adjuntos) en la salida de informes electrónicos. (Parte 2)
author: NickSelin
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
ms.openlocfilehash: 1e79dd0a6c68aa6ba7b857c31c9159c68543d93b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754923"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="b40c7-104">Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)</span><span class="sxs-lookup"><span data-stu-id="b40c7-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b40c7-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un informe electrónico (ER) para usar los archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="b40c7-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="b40c7-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="b40c7-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="b40c7-107">Para completar estos pasos, primero debe completar los pasos de la guía de tareas “ER Uso de los archivos de gestión de documentos en formatos de salida (Parte 1: Preparar el modelo de datos)”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="b40c7-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="b40c7-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="b40c7-109">Extienda el modelo de datos para mostrar los archivos de gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="b40c7-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="b40c7-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="b40c7-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b40c7-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="b40c7-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b40c7-112">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="b40c7-113">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="b40c7-114">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="b40c7-114">Click Designer.</span></span>
6. <span data-ttu-id="b40c7-115">En el árbol, seleccione “Modelo de factura (InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="b40c7-116">Extenderemos este modelo de datos para exponer en él archivos que se hayan adjuntado a un pedido de ventas relacionado con una factura procesada electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="b40c7-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="b40c7-117">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b40c7-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="b40c7-118">En el campo Nombre, introduzca "Facturar adjuntos".</span><span class="sxs-lookup"><span data-stu-id="b40c7-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="b40c7-119">Facturar adjuntos</span><span class="sxs-lookup"><span data-stu-id="b40c7-119">Invoice attachments</span></span>  
9. <span data-ttu-id="b40c7-120">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="b40c7-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="b40c7-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-121">Click Add.</span></span>
11. <span data-ttu-id="b40c7-122">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b40c7-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="b40c7-123">En el campo Nombre, introduzca "Contenido de archivo".</span><span class="sxs-lookup"><span data-stu-id="b40c7-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="b40c7-124">Contenido del archivo</span><span class="sxs-lookup"><span data-stu-id="b40c7-124">File content</span></span>  
13. <span data-ttu-id="b40c7-125">En el campo Tipo de artículo, seleccione "Contenedor".</span><span class="sxs-lookup"><span data-stu-id="b40c7-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="b40c7-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-126">Click Add.</span></span>
15. <span data-ttu-id="b40c7-127">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b40c7-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="b40c7-128">En el campo Nombre, introduzca "Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="b40c7-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="b40c7-129">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="b40c7-129">File name</span></span>  
17. <span data-ttu-id="b40c7-130">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="b40c7-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="b40c7-131">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="b40c7-132">Asigne nuevos elementos de modelo de datos a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="b40c7-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="b40c7-133">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b40c7-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="b40c7-134">Use el Filtro rápido para filtrar el campo Definición con un valor de 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="b40c7-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="b40c7-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="b40c7-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="b40c7-136">Asignaremos nuevos elementos del modelo a los orígenes de datos adecuados.</span><span class="sxs-lookup"><span data-stu-id="b40c7-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="b40c7-137">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="b40c7-137">Click Designer.</span></span>
4. <span data-ttu-id="b40c7-138">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="b40c7-139">En el árbol, expanda “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="b40c7-140">En el árbol, seleccione “Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="b40c7-141">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-141">Click Edit.</span></span>
8. <span data-ttu-id="b40c7-142">En el campo Fórmula, introduzca "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="b40c7-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="b40c7-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="b40c7-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="b40c7-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-144">Click Save.</span></span>
10. <span data-ttu-id="b40c7-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-145">Close the page.</span></span>
11. <span data-ttu-id="b40c7-146">En el árbol, seleccione “Facturar adjuntos\Contenido de archivo”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="b40c7-147">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-147">Click Edit.</span></span>
13. <span data-ttu-id="b40c7-148">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="b40c7-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="b40c7-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="b40c7-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="b40c7-150">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-150">Click Save.</span></span>
15. <span data-ttu-id="b40c7-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-151">Close the page.</span></span>
16. <span data-ttu-id="b40c7-152">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="b40c7-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="b40c7-153">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-153">Click Edit.</span></span>
18. <span data-ttu-id="b40c7-154">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="b40c7-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="b40c7-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="b40c7-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="b40c7-156">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-156">Click Save.</span></span>
20. <span data-ttu-id="b40c7-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-157">Close the page.</span></span>
21. <span data-ttu-id="b40c7-158">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-158">Click Save.</span></span>
22. <span data-ttu-id="b40c7-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-159">Close the page.</span></span>
23. <span data-ttu-id="b40c7-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-160">Close the page.</span></span>
24. <span data-ttu-id="b40c7-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b40c7-161">Close the page.</span></span>
25. <span data-ttu-id="b40c7-162">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="b40c7-162">Click Change status.</span></span>
26. <span data-ttu-id="b40c7-163">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="b40c7-163">Click Complete.</span></span>
27. <span data-ttu-id="b40c7-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b40c7-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]