--- 
title: Procesar datos de origen y hacer un seguimiento
description: Todo el procesamiento de datos se ejecuta por trabajos.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7093338fd306e90df79a787f9de9861b3fe49dd5
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="71cd8-103">Procesar datos de origen y hacer un seguimiento</span><span class="sxs-lookup"><span data-stu-id="71cd8-103">Process and trace source data</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="71cd8-104">Todo el procesamiento de datos se ejecuta por trabajos.</span><span class="sxs-lookup"><span data-stu-id="71cd8-104">All data processing is run by jobs.</span></span> <span data-ttu-id="71cd8-105">Para cada trabajo y proveedor de datos, se crea un diario para documentar que se ejecutó el proceso y que las entradas se procesaran en el trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="71cd8-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="71cd8-106">Use este procedimiento para configurar un origen de datos y después para realizar un seguimiento del origen de un asiento de coste específico.</span><span class="sxs-lookup"><span data-stu-id="71cd8-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="71cd8-107">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="71cd8-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="71cd8-108">Para completar esta tarea, asegúrese de que reproduce las siguientes guías de tareas: “Crear un libro mayor de contabilidad de costes“, “Definir unidades de control de costes" y "Gestionar un origen de datos para el libro mayor de contabilidad de costes".</span><span class="sxs-lookup"><span data-stu-id="71cd8-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="71cd8-109">Vaya a Contabilidad de costes > Configuración de libro mayor > Libros mayores de contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="71cd8-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="71cd8-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="71cd8-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="71cd8-111">Seleccione el libro mayor de contabilidad de costes que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="71cd8-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="71cd8-112">Haga clic en Versiones reales.</span><span class="sxs-lookup"><span data-stu-id="71cd8-112">Click Actual versions.</span></span>
4. <span data-ttu-id="71cd8-113">En el panel de acciones, haga clic en Procesamiento de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="71cd8-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="71cd8-114">Haga clic en Diarios de transferencia de entradas de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="71cd8-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="71cd8-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="71cd8-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="71cd8-116">Haga clic en Entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="71cd8-116">Click Journal entries.</span></span>
8. <span data-ttu-id="71cd8-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="71cd8-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="71cd8-118">Haga clic en Entradas de costes.</span><span class="sxs-lookup"><span data-stu-id="71cd8-118">Click Cost entries.</span></span>
10. <span data-ttu-id="71cd8-119">Haga clic en Entrada de origen-</span><span class="sxs-lookup"><span data-stu-id="71cd8-119">Click Source entry.</span></span>
11. <span data-ttu-id="71cd8-120">En el panel de acciones, haga clic en Procesamiento de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="71cd8-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="71cd8-121">Haga clic en Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="71cd8-121">Click General ledger.</span></span>
13. <span data-ttu-id="71cd8-122">En el campo Periodo de calendario fiscal, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="71cd8-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="71cd8-123">Para este ejemplo, seleccione Período 9 de año fiscal 2017.</span><span class="sxs-lookup"><span data-stu-id="71cd8-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="71cd8-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="71cd8-124">Click OK.</span></span>


