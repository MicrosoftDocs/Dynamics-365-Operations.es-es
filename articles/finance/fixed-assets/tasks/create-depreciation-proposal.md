---
title: Crear una propuesta de depreciación
description: En este tema se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos.
author: abruer
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 90c24e9d89c055ea95ca5f25cd85ef4042476a90
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187070"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="86e8f-103">Crear una propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="86e8f-103">Create a depreciation proposal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86e8f-104">En este tema se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="86e8f-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="86e8f-105">Esta tarea usa la empresa de prueba USMF y el rol de contable.</span><span class="sxs-lookup"><span data-stu-id="86e8f-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="86e8f-106">Crear una propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="86e8f-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="86e8f-107">En el Panel de exploración, vaya a **Módulos > Activos fijos > Entradas del diario > Crear propuesta de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="86e8f-108">En el campo **Nombre del diario**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="86e8f-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="86e8f-109">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="86e8f-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="86e8f-110">Active la opción **Resumir depreciación** para resumir las depreciaciones mensuales en una línea de diario.</span><span class="sxs-lookup"><span data-stu-id="86e8f-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="86e8f-111">Por ejemplo, si el valor de fecha es el 31 de marzo de 2015, se genera la siguiente descripción: “Depreciación desde el 31 de enero de 2015”.</span><span class="sxs-lookup"><span data-stu-id="86e8f-111">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="86e8f-112">El campo **Fecha** de las líneas de diario propuestas se establece entonces en 31 de marzo de 2015.</span><span class="sxs-lookup"><span data-stu-id="86e8f-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="86e8f-113">La propuesta de depreciación se puede filtrar por activo, grupo de activos u otros criterios mediante la opción **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="86e8f-114">Cuando usa el formulario **Crear propuestas de adquisición o depreciación para activos fijos**, puede proponer la depreciación en lotes.</span><span class="sxs-lookup"><span data-stu-id="86e8f-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="86e8f-115">Esto se recomienda para propuestas más grandes que usarán más recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="86e8f-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="86e8f-116">Si selecciona la opción de lote, puede completar otras tareas durante ese tiempo.</span><span class="sxs-lookup"><span data-stu-id="86e8f-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="86e8f-117">Cuando se propone la depreciación de esta manera, la depreciación se calcula para los modelos de valor de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="86e8f-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="86e8f-118">Seleccione **Crear diario**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="86e8f-119">Revisar los movimientos de amortización</span><span class="sxs-lookup"><span data-stu-id="86e8f-119">Review depreciation entries</span></span>
1. <span data-ttu-id="86e8f-120">En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="86e8f-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="86e8f-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="86e8f-122">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-122">Select **Lines**.</span></span>
4. <span data-ttu-id="86e8f-123">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="86e8f-123">Select **Post**.</span></span>

