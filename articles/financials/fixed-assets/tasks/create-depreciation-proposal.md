--- 
title: "Crear una propuesta de depreciación"
description: "En este procedimiento se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: ab5264a0f2c03655a3e8f23344f5233c1bfb6515
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="b9e33-103">Crear una propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="b9e33-103">Create a depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9e33-104">En este procedimiento se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="b9e33-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="b9e33-105">Esta tarea usa la empresa de prueba USMF y el rol de contable.</span><span class="sxs-lookup"><span data-stu-id="b9e33-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="b9e33-106">Crear propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="b9e33-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="b9e33-107">Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.</span><span class="sxs-lookup"><span data-stu-id="b9e33-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="b9e33-108">En el campo Nombre de diario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9e33-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b9e33-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9e33-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b9e33-110">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="b9e33-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="b9e33-111">Active la opción Resumir depreciación para resumir las depreciaciones mensuales en una línea de diario.</span><span class="sxs-lookup"><span data-stu-id="b9e33-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="b9e33-112">Por ejemplo, si el valor de fecha es el 31 de marzo de 2015, se genera la siguiente descripción: “Depreciación desde el 31 de enero de 2015”.</span><span class="sxs-lookup"><span data-stu-id="b9e33-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="b9e33-113">El campo Fecha de las líneas de diario propuestas se establece entonces en 31 de marzo de 2015.</span><span class="sxs-lookup"><span data-stu-id="b9e33-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="b9e33-114">La propuesta de depreciación se puede filtrar por activo, grupo de activos u otros criterios mediante la opción Filtro.</span><span class="sxs-lookup"><span data-stu-id="b9e33-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="b9e33-115">Cuando usa el formulario Crear propuestas de adquisición o depreciación para activos fijos, puede proponer la depreciación en lotes.</span><span class="sxs-lookup"><span data-stu-id="b9e33-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="b9e33-116">Esto se recomienda para propuestas más grandes que usarán más recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="b9e33-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="b9e33-117">Si selecciona la opción de lote, puede completar otras tareas durante ese tiempo.</span><span class="sxs-lookup"><span data-stu-id="b9e33-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="b9e33-118">Cuando se propone la depreciación de esta manera, la depreciación se calcula para los modelos de valor de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="b9e33-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="b9e33-119">Haga clic en Crear diario.</span><span class="sxs-lookup"><span data-stu-id="b9e33-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="b9e33-120">Revisar los movimientos de amortización</span><span class="sxs-lookup"><span data-stu-id="b9e33-120">Review depreciation entries</span></span>
1. <span data-ttu-id="b9e33-121">Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="b9e33-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="b9e33-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b9e33-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b9e33-123">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="b9e33-123">Click Lines.</span></span>
4. <span data-ttu-id="b9e33-124">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="b9e33-124">Click Post.</span></span>


