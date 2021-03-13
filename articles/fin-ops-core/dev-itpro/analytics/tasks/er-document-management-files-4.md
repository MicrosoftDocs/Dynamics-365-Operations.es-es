---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 4: Ejecución del formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos para utilizar archivos de administración de documentos en la salida de informes electrónicos. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d437b31b8a55f345ebc3567bc8c6a2c5ecfd2eec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092525"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="3616e-104">Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 4: Ejecución del formato)</span><span class="sxs-lookup"><span data-stu-id="3616e-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3616e-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="3616e-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="3616e-106">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="3616e-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="3616e-107">Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 3: crear formato)”.</span><span class="sxs-lookup"><span data-stu-id="3616e-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="3616e-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3616e-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="3616e-109">Agregue los adjuntos necesarios para el pedido de ventas de una única factura</span><span class="sxs-lookup"><span data-stu-id="3616e-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="3616e-110">Vaya a Clientes > Facturas > Facturas de cliente abiertas.</span><span class="sxs-lookup"><span data-stu-id="3616e-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="3616e-111">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="3616e-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3616e-112">Por ejemplo, filtre el campo Factura con un valor de "CIV-000148".</span><span class="sxs-lookup"><span data-stu-id="3616e-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="3616e-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="3616e-113">CIV-000148</span></span>  
3. <span data-ttu-id="3616e-114">Haga clic para seguir el enlace de la factura seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3616e-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="3616e-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="3616e-115">CIV-000148</span></span>  
4. <span data-ttu-id="3616e-116">Haga clic para seguir el enlace en el campo Pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="3616e-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="3616e-117">000148</span><span class="sxs-lookup"><span data-stu-id="3616e-117">000148</span></span>  
5. <span data-ttu-id="3616e-118">En las Líneas o el campo de cabecera, seleccione la opción de Cabecera.</span><span class="sxs-lookup"><span data-stu-id="3616e-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="3616e-119">Seleccione el Encabezado para indicar que éste será el destino para agregar los adjuntos.</span><span class="sxs-lookup"><span data-stu-id="3616e-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="3616e-120">Haga clic en Vincular.</span><span class="sxs-lookup"><span data-stu-id="3616e-120">Click Attach.</span></span>
    * <span data-ttu-id="3616e-121">Agregue algunos archivos como adjuntos para este pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="3616e-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="3616e-122">Use los archivos de los tipos de documento admitidos por la gestión de documentos (con las extensiones de archivo DOCX, DPF, XML, JPG., etc.).</span><span class="sxs-lookup"><span data-stu-id="3616e-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="3616e-123">Examinar y seleccionar los archivos que se adjuntarán y que serán procesados con la factura relacionada en el mensaje electrónico de ER.</span><span class="sxs-lookup"><span data-stu-id="3616e-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="3616e-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3616e-124">Click New.</span></span>
8. <span data-ttu-id="3616e-125">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="3616e-125">Click File.</span></span>
9. <span data-ttu-id="3616e-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3616e-126">Click New.</span></span>
10. <span data-ttu-id="3616e-127">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="3616e-127">Click File.</span></span>
11. <span data-ttu-id="3616e-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3616e-128">Close the page.</span></span>
12. <span data-ttu-id="3616e-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3616e-129">Close the page.</span></span>
13. <span data-ttu-id="3616e-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3616e-130">Close the page.</span></span>
14. <span data-ttu-id="3616e-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3616e-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="3616e-132">Ejecute el informe diseñado para la factura seleccionada</span><span class="sxs-lookup"><span data-stu-id="3616e-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="3616e-133">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="3616e-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3616e-134">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="3616e-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="3616e-135">En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="3616e-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="3616e-136">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="3616e-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="3616e-137">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="3616e-137">Click Run.</span></span>
6. <span data-ttu-id="3616e-138">Expanda los Registros para incluir la sección ().</span><span class="sxs-lookup"><span data-stu-id="3616e-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="3616e-139">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="3616e-139">Click Filter.</span></span>
8. <span data-ttu-id="3616e-140">Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="3616e-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="3616e-141">En campo Criterios, introduzca '000148'.</span><span class="sxs-lookup"><span data-stu-id="3616e-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="3616e-142">En los criterios del campo “Pedido de ventas”, introduzca el número de pedido 000148.</span><span class="sxs-lookup"><span data-stu-id="3616e-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="3616e-143">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="3616e-143">Click OK.</span></span>
11. <span data-ttu-id="3616e-144">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="3616e-144">Click OK.</span></span>
    * <span data-ttu-id="3616e-145">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="3616e-145">Review the generated output.</span></span> <span data-ttu-id="3616e-146">Tenga en cuenta que se ha creado un nodo XML por cada adjunto.</span><span class="sxs-lookup"><span data-stu-id="3616e-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="3616e-147">El contenido del adjunto se rellena al archivo de salida XML en formato de texto MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="3616e-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  

