---
title: Ver el historial de flujo de trabajo
description: Este tema describe los pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16c6594161f1fecd36183a6b8f2c798f52d70a9c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189807"
---
# <a name="view-workflow-history"></a><span data-ttu-id="818e1-103">Ver el historial de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="818e1-103">View workflow history</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="818e1-104">Este tema describe los pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe.</span><span class="sxs-lookup"><span data-stu-id="818e1-104">This topic describes the steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="818e1-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="818e1-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="818e1-106">Vaya a **Panel de exploración > Módulos > Común > Preguntas > Flujo de trabajo > Historial de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="818e1-106">Go to **Navigation pane > Modules > Common > Inquiries > Workflow > Workflow history**.</span></span>
    - <span data-ttu-id="818e1-107">Utilice este formulario para ver el estado de un documento que se ha enviado al sistema de flujo de trabajo para procesarlo y aprobarlo.</span><span class="sxs-lookup"><span data-stu-id="818e1-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    - <span data-ttu-id="818e1-108">El **Id. de la instancia** es el código de identificación de la instancia de flujo de trabajo que está procesando, o ha procesado, el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-108">The **Instance ID** is the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="818e1-109">El **Estado** es el estado del flujo de trabajo del documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-109">The **Status** is the workflow status of the document.</span></span>  
    - <span data-ttu-id="818e1-110">El **ID del flujo de trabajo** es el código de identificación del flujo de trabajo que está procesando, o ha procesado, el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-110">The **Workflow ID** is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="818e1-111">El **Documento** es el código de identificación del documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-111">The **Document** is the identification code of the document.</span></span>  
    - <span data-ttu-id="818e1-112">El **Tipo de documento** es el tipo de documento que se envió para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="818e1-112">The **Document type** is the type of document that was submitted for processing.</span></span>  
    - <span data-ttu-id="818e1-113">**Flujo de trabajo** es el nombre del flujo de trabajo que está procesando, o ha procesado, el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-113">The **Workflow** is the name of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="818e1-114">**Versión** es el número de versión del flujo de trabajo que está procesando, o ha procesado, el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-114">The **Version** is the version number of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="818e1-115">La **Fecha y hora de creación** es la fecha y hora en que se envió el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-115">The **Created date and time** is the date and time that the document was submitted.</span></span>  
    - <span data-ttu-id="818e1-116">El **Tiempo transcurrido** es el tiempo que ha pasado desde que se envió el documento.</span><span class="sxs-lookup"><span data-stu-id="818e1-116">The **Elapsed time** is the time that has passed since the document was submitted.</span></span>  
    - <span data-ttu-id="818e1-117">El botón de **Reanudar** le permite que reanudar el proceso del flujo de trabajo para el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="818e1-117">The **Resume** button allows you to resume the workflow process for the selected document.</span></span>  
    - <span data-ttu-id="818e1-118">El botón **Recuperar** le permite recuperar el documento seleccionado para que no sea procesado.</span><span class="sxs-lookup"><span data-stu-id="818e1-118">The **Recall** button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="818e1-119">En la lista, seleccione el vínculo de la fila deseada.</span><span class="sxs-lookup"><span data-stu-id="818e1-119">In the list, select the link in the desired row.</span></span>
    - <span data-ttu-id="818e1-120">Asegúrese de que la sección **Elementos de trabajo** está expandida.</span><span class="sxs-lookup"><span data-stu-id="818e1-120">Make sure the **Work items** section is expanded.</span></span> <span data-ttu-id="818e1-121">En esta sección puede ver los elementos de trabajo que se están asociados al documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="818e1-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="818e1-122">Por ejemplo, es posible que haya completado una tarea, o que el documento se haya aprobado.</span><span class="sxs-lookup"><span data-stu-id="818e1-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    - <span data-ttu-id="818e1-123">El botón **Reasignar** abrirá un cuadro de diálogo en el que se puede reasignar un elemento de trabajo a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="818e1-123">The **Reassign** button will open a dialog box where you can reassign a work item to another user.</span></span>  
    - <span data-ttu-id="818e1-124">Asegúrese de que la sección **Detalles de seguimiento** está expandida.</span><span class="sxs-lookup"><span data-stu-id="818e1-124">Make sure the **Tracking details** section is expanded.</span></span> <span data-ttu-id="818e1-125">En esta sección puede ver el historial del flujo de trabajo del documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="818e1-125">In this section you can view the workflow history of the selected document.</span></span>  

