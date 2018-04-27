--- 
title: "Ampliar modelos de datos para usar archivos de gestión documental en salidas de formato"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un informe electrónico (ER) para usar los archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: bde8c612af22ba6bf4561732399fcf2cb1b5c9b3
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="9e41c-103">Ampliar modelos de datos para usar archivos de gestión documental en salidas de formato</span><span class="sxs-lookup"><span data-stu-id="9e41c-103">Extend data model to use Document Management files in format outputs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9e41c-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un informe electrónico (ER) para usar los archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="9e41c-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="9e41c-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="9e41c-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="9e41c-106">Para completar estos pasos, primero debe completar los pasos de la guía de tareas “ER Uso de los archivos de gestión de documentos en formatos de salida (Parte 1: Preparar el modelo de datos)”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="9e41c-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9e41c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="9e41c-108">Extienda el modelo de datos para mostrar los archivos de gestión de documentos</span><span class="sxs-lookup"><span data-stu-id="9e41c-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="9e41c-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9e41c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9e41c-110">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="9e41c-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9e41c-111">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="9e41c-112">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="9e41c-113">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="9e41c-113">Click Designer.</span></span>
6. <span data-ttu-id="9e41c-114">En el árbol, seleccione “Modelo de factura (InvoiceCustomer)”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="9e41c-115">Extenderemos este modelo de datos para exponer en él archivos que se hayan adjuntado a un pedido de ventas relacionado con una factura procesada electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="9e41c-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="9e41c-116">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e41c-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9e41c-117">En el campo Nombre, introduzca "Facturar adjuntos".</span><span class="sxs-lookup"><span data-stu-id="9e41c-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="9e41c-118">Facturar adjuntos</span><span class="sxs-lookup"><span data-stu-id="9e41c-118">Invoice attachments</span></span>  
9. <span data-ttu-id="9e41c-119">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9e41c-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="9e41c-120">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-120">Click Add.</span></span>
11. <span data-ttu-id="9e41c-121">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e41c-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9e41c-122">En el campo Nombre, introduzca "Contenido de archivo".</span><span class="sxs-lookup"><span data-stu-id="9e41c-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="9e41c-123">Contenido del archivo</span><span class="sxs-lookup"><span data-stu-id="9e41c-123">File content</span></span>  
13. <span data-ttu-id="9e41c-124">En el campo Tipo de artículo, seleccione "Contenedor".</span><span class="sxs-lookup"><span data-stu-id="9e41c-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="9e41c-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-125">Click Add.</span></span>
15. <span data-ttu-id="9e41c-126">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="9e41c-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="9e41c-127">En el campo Nombre, introduzca "Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="9e41c-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="9e41c-128">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="9e41c-128">File name</span></span>  
17. <span data-ttu-id="9e41c-129">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="9e41c-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="9e41c-130">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-data-sources"></a><span data-ttu-id="9e41c-131">Asigne los nuevos artículos del modelo de datos a los datos de origen de Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9e41c-131">Map new data model elements to Dynamics 365 for Finance and Operations data sources</span></span>
1. <span data-ttu-id="9e41c-132">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9e41c-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="9e41c-133">Use el Filtro rápido para filtrar el campo Definición con un valor de 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="9e41c-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="9e41c-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="9e41c-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="9e41c-135">Asignaremos nuevos elementos del modelo a los orígenes de datos adecuados.</span><span class="sxs-lookup"><span data-stu-id="9e41c-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="9e41c-136">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="9e41c-136">Click Designer.</span></span>
4. <span data-ttu-id="9e41c-137">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="9e41c-138">En el árbol, expanda “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="9e41c-139">En el árbol, seleccione “Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="9e41c-140">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-140">Click Edit.</span></span>
8. <span data-ttu-id="9e41c-141">En el campo Fórmula, introduzca "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="9e41c-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="9e41c-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="9e41c-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="9e41c-143">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-143">Click Save.</span></span>
10. <span data-ttu-id="9e41c-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-144">Close the page.</span></span>
11. <span data-ttu-id="9e41c-145">En el árbol, seleccione “Facturar adjuntos\Contenido de archivo”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="9e41c-146">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-146">Click Edit.</span></span>
13. <span data-ttu-id="9e41c-147">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="9e41c-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="9e41c-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="9e41c-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="9e41c-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-149">Click Save.</span></span>
15. <span data-ttu-id="9e41c-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-150">Close the page.</span></span>
16. <span data-ttu-id="9e41c-151">En el árbol, seleccione “Facturar adjuntos”.</span><span class="sxs-lookup"><span data-stu-id="9e41c-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="9e41c-152">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-152">Click Edit.</span></span>
18. <span data-ttu-id="9e41c-153">En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="9e41c-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="9e41c-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="9e41c-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="9e41c-155">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-155">Click Save.</span></span>
20. <span data-ttu-id="9e41c-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-156">Close the page.</span></span>
21. <span data-ttu-id="9e41c-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-157">Click Save.</span></span>
22. <span data-ttu-id="9e41c-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-158">Close the page.</span></span>
23. <span data-ttu-id="9e41c-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-159">Close the page.</span></span>
24. <span data-ttu-id="9e41c-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e41c-160">Close the page.</span></span>
25. <span data-ttu-id="9e41c-161">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="9e41c-161">Click Change status.</span></span>
26. <span data-ttu-id="9e41c-162">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="9e41c-162">Click Complete.</span></span>
27. <span data-ttu-id="9e41c-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9e41c-163">Click OK.</span></span>


