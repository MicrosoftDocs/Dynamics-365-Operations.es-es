---
title: Crear y procesar una conformidad
description: Sírvase de este procedimiento para gestionar los casos de disconformidad, en función de un pedido de calidad existente.
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16ed11bce92920fe8240fc85f706a2ac6ab0a04b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572820"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="c34d7-103">Crear y procesar una conformidad</span><span class="sxs-lookup"><span data-stu-id="c34d7-103">Create and process a conformance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c34d7-104">Sírvase de este procedimiento para gestionar los casos de disconformidad, en función de un pedido de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="c34d7-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="c34d7-105">Puede ejecutar esta grabación en la empresa de demostración USMF, y puede utilizar los valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="c34d7-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="c34d7-106">Normalmente, este procedimiento lo realiza un empleado de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="c34d7-107">Como requisito previo, ejecute la grabación de tarea "Inspección de la calidad de las mercancías".</span><span class="sxs-lookup"><span data-stu-id="c34d7-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="c34d7-108">Para procesar la aprobación de un caso de disconformidad, el usuario que ejecuta la grabación de la tarea debe tener un valor "Nombre" asignado en la página Usuarios.</span><span class="sxs-lookup"><span data-stu-id="c34d7-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="c34d7-109">Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="c34d7-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="c34d7-110">Selección de un pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="c34d7-110">Select a quality order</span></span>
1. <span data-ttu-id="c34d7-111">Vaya a Pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="c34d7-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c34d7-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c34d7-113">Seleccione el pedido de calidad que se creó de la grabación de la tarea "Inspección de la calidad de las mercancías".</span><span class="sxs-lookup"><span data-stu-id="c34d7-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="c34d7-114">Creación de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="c34d7-114">Create a nonconformance</span></span>
1. <span data-ttu-id="c34d7-115">Haga clic en Consultas.</span><span class="sxs-lookup"><span data-stu-id="c34d7-115">Click Inquiries.</span></span>
2. <span data-ttu-id="c34d7-116">Haga clic en Disconformidades.</span><span class="sxs-lookup"><span data-stu-id="c34d7-116">Click Non conformances.</span></span>
3. <span data-ttu-id="c34d7-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c34d7-117">Click New.</span></span>
4. <span data-ttu-id="c34d7-118">En el campo Tipo de problema, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c34d7-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c34d7-119">Seleccione el problema que se encontró durante el proceso de inspección.</span><span class="sxs-lookup"><span data-stu-id="c34d7-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="c34d7-120">En el campo Tipo de problema, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c34d7-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c34d7-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c34d7-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c34d7-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c34d7-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c34d7-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c34d7-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="c34d7-124">Aprobación o rechazo de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="c34d7-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="c34d7-125">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="c34d7-125">Click Functions.</span></span>
2. <span data-ttu-id="c34d7-126">Haga clic en Aprobar disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="c34d7-127">Por ejemplo, apruebe la disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="c34d7-128">Las disconformidades aprobadas se pueden asociar con operaciones relacionadas para registrar trabajo realizado dentro del proceso de gestión de disconformidades y, como en esta grabación de tarea, el procesamiento de la gestión de correcciones.</span><span class="sxs-lookup"><span data-stu-id="c34d7-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="c34d7-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="c34d7-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="c34d7-130">Creación de una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="c34d7-130">Create a correction action</span></span>
1. <span data-ttu-id="c34d7-131">Haga clic en Correcciones.</span><span class="sxs-lookup"><span data-stu-id="c34d7-131">Click Corrections.</span></span>
2. <span data-ttu-id="c34d7-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c34d7-132">Click New.</span></span>
3. <span data-ttu-id="c34d7-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c34d7-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c34d7-134">En el campo Número de personal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c34d7-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c34d7-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c34d7-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c34d7-136">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="c34d7-136">Click Select.</span></span>
7. <span data-ttu-id="c34d7-137">Haga clic en Vincular.</span><span class="sxs-lookup"><span data-stu-id="c34d7-137">Click Attach.</span></span>
    * <span data-ttu-id="c34d7-138">Cree una nota sobre la corrección.</span><span class="sxs-lookup"><span data-stu-id="c34d7-138">Create a note about the correction.</span></span> <span data-ttu-id="c34d7-139">En este ejemplo, la acción es contactar con el proveedor para hablar del caso de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="c34d7-140">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c34d7-140">Click New.</span></span>
9. <span data-ttu-id="c34d7-141">Haga clic en Nota.</span><span class="sxs-lookup"><span data-stu-id="c34d7-141">Click Note.</span></span>
    * <span data-ttu-id="c34d7-142">Tenga en cuenta que, en función de la configuración del informe, se pueden imprimir distintos tipos de documentos en los informes relacionados con la gestión de la disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="c34d7-143">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c34d7-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="c34d7-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c34d7-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="c34d7-145">Mantenimiento de una corrección</span><span class="sxs-lookup"><span data-stu-id="c34d7-145">Maintain a correction</span></span>
1. <span data-ttu-id="c34d7-146">Haga clic en Marcar como finalizado.</span><span class="sxs-lookup"><span data-stu-id="c34d7-146">Click Mark complete.</span></span>
2. <span data-ttu-id="c34d7-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c34d7-147">Click OK.</span></span>
3. <span data-ttu-id="c34d7-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c34d7-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="c34d7-149">Cierre de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="c34d7-149">Close a nonconformance</span></span>
1. <span data-ttu-id="c34d7-150">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="c34d7-150">Click Functions.</span></span>
2. <span data-ttu-id="c34d7-151">Haga clic en Cerrar disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c34d7-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="c34d7-152">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="c34d7-152">Click Yes.</span></span>
4. <span data-ttu-id="c34d7-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c34d7-153">Close the page.</span></span>
5. <span data-ttu-id="c34d7-154">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c34d7-154">Close the page.</span></span>
