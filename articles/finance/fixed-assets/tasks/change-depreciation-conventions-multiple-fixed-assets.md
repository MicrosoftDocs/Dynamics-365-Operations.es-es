---
title: Cambiar convenciones de depreciación para varios activos fijos
description: Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39930134782b40de05a92a6ad51c4f628f304a78
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447461"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="dd7ff-103">Cambiar convenciones de depreciación para varios activos fijos</span><span class="sxs-lookup"><span data-stu-id="dd7ff-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd7ff-104">Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="dd7ff-105">Esta guía de la tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="dd7ff-106">Vaya a Activos fijos > Tareas periódicas > Actualización masiva</span><span class="sxs-lookup"><span data-stu-id="dd7ff-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="dd7ff-107">En el campo Libro amortización, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="dd7ff-108">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="dd7ff-109">En el campo Colocado en inicio de servicio, inserte una fecha.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="dd7ff-110">En el campo Colocado en fin de servicio, inserte una fecha.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="dd7ff-111">Solo se actualizarán los activos que forman parte del libro de amortización seleccionado y que se han colocado en servicio entre estas fechas.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="dd7ff-112">En el campo Convención de amortizaciones actual, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="dd7ff-113">Solo se actualizarán los activos que tienen la convención de amortizaciones actual.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="dd7ff-114">En el campo Convención de amortizaciones nueva, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="dd7ff-115">Compruebe que el informe se imprima en el destino deseado.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="dd7ff-116">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="dd7ff-117">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-117">Click Filter.</span></span>
10. <span data-ttu-id="dd7ff-118">En la lista, seleccione el grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="dd7ff-119">En el campo Criterios, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="dd7ff-120">Seleccione el grupo de activos fijos que desee.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="dd7ff-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="dd7ff-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dd7ff-122">Click OK.</span></span>
15. <span data-ttu-id="dd7ff-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dd7ff-123">Click OK.</span></span>
    *  <span data-ttu-id="dd7ff-124">Los resultados del proceso se muestran en el informe de actualización masiva.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-124">Results of the process are shown on the Mass update report.</span></span>     

