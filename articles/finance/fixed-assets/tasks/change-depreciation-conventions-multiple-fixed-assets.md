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
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c64e4f7117c4ca70236a02b4d36a88e9f2a9906
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210032"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="cff25-103">Cambiar convenciones de depreciación para varios activos fijos</span><span class="sxs-lookup"><span data-stu-id="cff25-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cff25-104">Esta tarea actualiza la convención de amortizaciones de un grupo de activos fijos especificado.</span><span class="sxs-lookup"><span data-stu-id="cff25-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="cff25-105">Esta guía de la tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="cff25-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="cff25-106">Vaya a Activos fijos > Tareas periódicas > Actualización masiva</span><span class="sxs-lookup"><span data-stu-id="cff25-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="cff25-107">En el campo Libro amortización, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cff25-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="cff25-108">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cff25-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cff25-109">En el campo Colocado en inicio de servicio, inserte una fecha.</span><span class="sxs-lookup"><span data-stu-id="cff25-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="cff25-110">En el campo Colocado en fin de servicio, inserte una fecha.</span><span class="sxs-lookup"><span data-stu-id="cff25-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="cff25-111">Solo se actualizarán los activos que forman parte del libro de amortización seleccionado y que se han colocado en servicio entre estas fechas.</span><span class="sxs-lookup"><span data-stu-id="cff25-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="cff25-112">En el campo Convención de amortizaciones actual, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cff25-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="cff25-113">Solo se actualizarán los activos que tienen la convención de amortizaciones actual.</span><span class="sxs-lookup"><span data-stu-id="cff25-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="cff25-114">En el campo Convención de amortizaciones nueva, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cff25-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="cff25-115">Compruebe que el informe se imprima en el destino deseado.</span><span class="sxs-lookup"><span data-stu-id="cff25-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="cff25-116">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="cff25-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="cff25-117">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="cff25-117">Click Filter.</span></span>
10. <span data-ttu-id="cff25-118">En la lista, seleccione el grupo de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cff25-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="cff25-119">En el campo Criterios, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cff25-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="cff25-120">Seleccione el grupo de activos fijos que desee.</span><span class="sxs-lookup"><span data-stu-id="cff25-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="cff25-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cff25-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="cff25-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cff25-122">Click OK.</span></span>
15. <span data-ttu-id="cff25-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cff25-123">Click OK.</span></span>
    *  <span data-ttu-id="cff25-124">Los resultados del proceso se muestran en el informe de actualización masiva.</span><span class="sxs-lookup"><span data-stu-id="cff25-124">Results of the process are shown on the Mass update report.</span></span>     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]