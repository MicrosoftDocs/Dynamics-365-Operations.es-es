--- 
title: "Ejecutar el formato para usar archivos de administración de documentos en las salidas de formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="007d9-103">Ejecutar el formato para usar archivos de administración de documentos en las salidas de formato para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="007d9-103">Run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="007d9-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="007d9-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="007d9-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="007d9-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="007d9-106">Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 3: crear formato)”.</span><span class="sxs-lookup"><span data-stu-id="007d9-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="007d9-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="007d9-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="007d9-108">Agregue los adjuntos necesarios para el pedido de ventas de una única factura</span><span class="sxs-lookup"><span data-stu-id="007d9-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="007d9-109">Vaya a Clientes > Facturas > Facturas de cliente abiertas.</span><span class="sxs-lookup"><span data-stu-id="007d9-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="007d9-110">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="007d9-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="007d9-111">Por ejemplo, filtre el campo Factura con un valor de "CIV-000148".</span><span class="sxs-lookup"><span data-stu-id="007d9-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="007d9-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="007d9-112">CIV-000148</span></span>  
3. <span data-ttu-id="007d9-113">Haga clic para seguir el enlace de la factura seleccionada.</span><span class="sxs-lookup"><span data-stu-id="007d9-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="007d9-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="007d9-114">CIV-000148</span></span>  
4. <span data-ttu-id="007d9-115">Haga clic para seguir el enlace en el campo Pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="007d9-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="007d9-116">000148</span><span class="sxs-lookup"><span data-stu-id="007d9-116">000148</span></span>  
5. <span data-ttu-id="007d9-117">En las Líneas o el campo de cabecera, seleccione la opción de Cabecera.</span><span class="sxs-lookup"><span data-stu-id="007d9-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="007d9-118">Seleccione el Encabezado para indicar que éste será el destino para agregar los adjuntos.</span><span class="sxs-lookup"><span data-stu-id="007d9-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="007d9-119">Haga clic en Vincular.</span><span class="sxs-lookup"><span data-stu-id="007d9-119">Click Attach.</span></span>
    * <span data-ttu-id="007d9-120">Agregue algunos archivos como adjuntos para este pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="007d9-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="007d9-121">Use los archivos de los tipos de documento admitidos por la gestión de documentos (con las extensiones de archivo DOCX, DPF, XML, JPG., etc.).</span><span class="sxs-lookup"><span data-stu-id="007d9-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="007d9-122">Examinar y seleccionar los archivos que se adjuntarán y que serán procesados con la factura relacionada en el mensaje electrónico de ER.</span><span class="sxs-lookup"><span data-stu-id="007d9-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="007d9-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="007d9-123">Click New.</span></span>
8. <span data-ttu-id="007d9-124">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="007d9-124">Click File.</span></span>
9. <span data-ttu-id="007d9-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="007d9-125">Click New.</span></span>
10. <span data-ttu-id="007d9-126">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="007d9-126">Click File.</span></span>
11. <span data-ttu-id="007d9-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="007d9-127">Close the page.</span></span>
12. <span data-ttu-id="007d9-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="007d9-128">Close the page.</span></span>
13. <span data-ttu-id="007d9-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="007d9-129">Close the page.</span></span>
14. <span data-ttu-id="007d9-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="007d9-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="007d9-131">Ejecute el informe diseñado para la factura seleccionada</span><span class="sxs-lookup"><span data-stu-id="007d9-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="007d9-132">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="007d9-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="007d9-133">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="007d9-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="007d9-134">En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="007d9-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="007d9-135">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="007d9-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="007d9-136">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="007d9-136">Click Run.</span></span>
6. <span data-ttu-id="007d9-137">Expanda los Registros para incluir la sección ().</span><span class="sxs-lookup"><span data-stu-id="007d9-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="007d9-138">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="007d9-138">Click Filter.</span></span>
8. <span data-ttu-id="007d9-139">Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="007d9-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="007d9-140">En campo Criterios, introduzca '000148'.</span><span class="sxs-lookup"><span data-stu-id="007d9-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="007d9-141">En los criterios del campo “Pedido de ventas”, introduzca el número de pedido 000148.</span><span class="sxs-lookup"><span data-stu-id="007d9-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="007d9-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="007d9-142">Click OK.</span></span>
11. <span data-ttu-id="007d9-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="007d9-143">Click OK.</span></span>
    * <span data-ttu-id="007d9-144">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="007d9-144">Review the generated output.</span></span> <span data-ttu-id="007d9-145">Tenga en cuenta que se ha creado un nodo XML por cada adjunto.</span><span class="sxs-lookup"><span data-stu-id="007d9-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="007d9-146">El contenido del adjunto se rellena al archivo de salida XML en formato de texto MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="007d9-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  


