---
title: Crear y procesar una conformidad
description: Este tema explica cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bf20ed737707b7cf99023e3c78489caf4a68eab
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383628"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="7a527-103">Crear y procesar una conformidad</span><span class="sxs-lookup"><span data-stu-id="7a527-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7a527-104">Este tema explica cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="7a527-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="7a527-105">Puede ejecutar esta grabación en la empresa de demostración USMF, y puede utilizar los valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="7a527-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="7a527-106">Normalmente, este procedimiento lo realiza un empleado de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="7a527-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="7a527-107">Como requisito previo, complete las instrucciones en [Inspección de la calidad de las mercancías](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="7a527-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="7a527-108">Para procesar la aprobación de un caso de disconformidad, el usuario que ejecuta la grabación de la tarea debe tener un valor "Nombre" asignado en la página Usuarios.</span><span class="sxs-lookup"><span data-stu-id="7a527-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="7a527-109">Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="7a527-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="7a527-110">Selección de un pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="7a527-110">Select a quality order</span></span>
1. <span data-ttu-id="7a527-111">En el panel de navegación, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="7a527-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="7a527-112">En la lista, seleccione el pedido de calidad que se creó en [Inspección de la calidad de las mercancías](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="7a527-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="7a527-113">Creación de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="7a527-113">Create a nonconformance</span></span>
1. <span data-ttu-id="7a527-114">En el panel Acciones, seleccione **Consultas**.</span><span class="sxs-lookup"><span data-stu-id="7a527-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="7a527-115">Seleccione **No conformidades**.</span><span class="sxs-lookup"><span data-stu-id="7a527-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="7a527-116">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a527-116">Select **New**.</span></span>
4. <span data-ttu-id="7a527-117">En el menú desplegable del campo **Tipo de problema**, seleccione el problema encontrado durante el proceso de inspección.</span><span class="sxs-lookup"><span data-stu-id="7a527-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="7a527-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a527-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="7a527-119">Aprobación o rechazo de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="7a527-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="7a527-120">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="7a527-120">Select **Functions**.</span></span>
2. <span data-ttu-id="7a527-121">Seleccione **Aprobar la no conformidad**.</span><span class="sxs-lookup"><span data-stu-id="7a527-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="7a527-122">Por ejemplo, apruebe la disconformidad.</span><span class="sxs-lookup"><span data-stu-id="7a527-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="7a527-123">Las disconformidades aprobadas se pueden asociar con operaciones relacionadas para registrar trabajo realizado dentro del proceso de gestión de disconformidades y, como en este tema, el procesamiento de la gestión de correcciones.</span><span class="sxs-lookup"><span data-stu-id="7a527-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="7a527-124">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7a527-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="7a527-125">Creación de una acción de corrección</span><span class="sxs-lookup"><span data-stu-id="7a527-125">Create a correction action</span></span>
1. <span data-ttu-id="7a527-126">Seleccione **Correcciones**.</span><span class="sxs-lookup"><span data-stu-id="7a527-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="7a527-127">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a527-127">Select **New**.</span></span>
3. <span data-ttu-id="7a527-128">En el campo **Número de personal** de la nueva fila, seleccione el registro deseado desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="7a527-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="7a527-129">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="7a527-129">Click **Select**.</span></span>
5. <span data-ttu-id="7a527-130">Seleccione **Adjuntar**.</span><span class="sxs-lookup"><span data-stu-id="7a527-130">Select **Attach**.</span></span> <span data-ttu-id="7a527-131">Cree una nota sobre la corrección.</span><span class="sxs-lookup"><span data-stu-id="7a527-131">Create a note about the correction.</span></span> <span data-ttu-id="7a527-132">En este ejemplo, la acción es contactar con el proveedor para hablar del caso de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="7a527-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="7a527-133">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a527-133">Select **New**.</span></span>
7. <span data-ttu-id="7a527-134">Seleccione **Nota**.</span><span class="sxs-lookup"><span data-stu-id="7a527-134">Select **Note**.</span></span> <span data-ttu-id="7a527-135">En función de la configuración del informe, se pueden imprimir distintos tipos de documentos en los informes relacionados con la gestión de la disconformidad.</span><span class="sxs-lookup"><span data-stu-id="7a527-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="7a527-136">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7a527-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="7a527-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7a527-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="7a527-138">Mantenimiento de una corrección</span><span class="sxs-lookup"><span data-stu-id="7a527-138">Maintain a correction</span></span>
1. <span data-ttu-id="7a527-139">Seleccione **Marcar como finalizado**.</span><span class="sxs-lookup"><span data-stu-id="7a527-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="7a527-140">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a527-140">Select **OK**.</span></span>
3. <span data-ttu-id="7a527-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7a527-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="7a527-142">Cierre de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="7a527-142">Close a nonconformance</span></span>
1. <span data-ttu-id="7a527-143">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="7a527-143">Select **Functions**.</span></span>
2. <span data-ttu-id="7a527-144">Seleccione **Cerrar la no conformidad**.</span><span class="sxs-lookup"><span data-stu-id="7a527-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="7a527-145">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7a527-145">Select **Yes**.</span></span>
4. <span data-ttu-id="7a527-146">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="7a527-146">Close the pages.</span></span>
