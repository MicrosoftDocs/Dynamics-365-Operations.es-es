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
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3d62e982d26afbec7ac04dd80592a73f4a3286f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968913"
---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="42ebf-103">Crear una propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="42ebf-103">Create a depreciation proposal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42ebf-104">En este tema se describe cómo funcionan las propuestas de lote de depreciación y se explica cómo proponer la depreciación para los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="42ebf-104">This topic describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="42ebf-105">Esta tarea usa la empresa de prueba USMF y el rol de contable.</span><span class="sxs-lookup"><span data-stu-id="42ebf-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-a-depreciation-proposal"></a><span data-ttu-id="42ebf-106">Crear una propuesta de depreciación</span><span class="sxs-lookup"><span data-stu-id="42ebf-106">Create a depreciation proposal</span></span>
1. <span data-ttu-id="42ebf-107">En el Panel de exploración, vaya a **Módulos > Activos fijos > Entradas del diario > Crear propuesta de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Create depreciation proposal**.</span></span>
2. <span data-ttu-id="42ebf-108">En el campo **Nombre del diario**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="42ebf-108">In the **Name of journal** field, select an option from the drop-down menu.</span></span>
3. <span data-ttu-id="42ebf-109">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="42ebf-109">In the **To date** field, enter a date.</span></span>

    - <span data-ttu-id="42ebf-110">Active la opción **Resumir depreciación** para resumir las depreciaciones mensuales en una línea de diario.</span><span class="sxs-lookup"><span data-stu-id="42ebf-110">Select the **Summarize depreciation** option to summarize monthly depreciations into one journal line.</span></span>  
    - <span data-ttu-id="42ebf-111">Por ejemplo, si el valor de fecha es el 31 de marzo de 2015, se genera la siguiente descripción: “Depreciación desde el 31 de enero de 2015”.</span><span class="sxs-lookup"><span data-stu-id="42ebf-111">For example, if the To date value is March 31, 2015, the following description is generated: "Depreciation since January 31, 2015."</span></span> <span data-ttu-id="42ebf-112">El campo **Fecha** de las líneas de diario propuestas se establece entonces en 31 de marzo de 2015.</span><span class="sxs-lookup"><span data-stu-id="42ebf-112">The **Date** field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    - <span data-ttu-id="42ebf-113">La propuesta de depreciación se puede filtrar por activo, grupo de activos u otros criterios mediante la opción **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-113">The depreciation proposal can be filtered by asset, asset group, or other criteria using the **Filter** option.</span></span>  
    - <span data-ttu-id="42ebf-114">Cuando usa el formulario **Crear propuestas de adquisición o depreciación para activos fijos**, puede proponer la depreciación en lotes.</span><span class="sxs-lookup"><span data-stu-id="42ebf-114">When you use the **Create acquisition or depreciation proposals for fixed assets** form, you can propose depreciation in batches.</span></span> <span data-ttu-id="42ebf-115">Esto se recomienda para propuestas más grandes que usarán más recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="42ebf-115">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="42ebf-116">Si selecciona la opción de lote, puede completar otras tareas durante ese tiempo.</span><span class="sxs-lookup"><span data-stu-id="42ebf-116">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="42ebf-117">Cuando se propone la depreciación de esta manera, la depreciación se calcula para los modelos de valor de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="42ebf-117">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  

4. <span data-ttu-id="42ebf-118">Seleccione **Crear diario**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-118">Select **Create journal**.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="42ebf-119">Revisar los movimientos de amortización</span><span class="sxs-lookup"><span data-stu-id="42ebf-119">Review depreciation entries</span></span>
1. <span data-ttu-id="42ebf-120">En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-120">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="42ebf-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="42ebf-121">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="42ebf-122">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-122">Select **Lines**.</span></span>
4. <span data-ttu-id="42ebf-123">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="42ebf-123">Select **Post**.</span></span>

