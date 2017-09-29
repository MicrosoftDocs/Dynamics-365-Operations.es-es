---
title: "Solución de problemas de presupuesto"
description: "Este artículo proporciona respuestas a preguntas que puede que tenga cuando configure el presupuesto de puesto. Responde a preguntas frecuentes acerca de cómo crear elementos de costes presupuestarios, grupos de compensación y cuadrículas de compensación."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 421520fcd1b215a19c126ccea51b025977552448
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="position-budgeting-troubleshooting"></a><span data-ttu-id="6af59-104">Solución de problemas de presupuesto</span><span class="sxs-lookup"><span data-stu-id="6af59-104">Position budgeting troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6af59-105">Este artículo proporciona respuestas a preguntas que puede que tenga cuando configure el presupuesto de puesto.</span><span class="sxs-lookup"><span data-stu-id="6af59-105">This article provides answers to questions that you might have when you configure position budgeting.</span></span> <span data-ttu-id="6af59-106">Responde a preguntas frecuentes acerca de cómo crear elementos de costes presupuestarios, grupos de compensación y cuadrículas de compensación.</span><span class="sxs-lookup"><span data-stu-id="6af59-106">It addresses frequently asked questions about how to create budget cost elements, compensation groups, and compensation grids.</span></span> 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a><span data-ttu-id="6af59-107">¿Por qué no encuentro la página de puesto de previsión en Recursos humanos?</span><span class="sxs-lookup"><span data-stu-id="6af59-107">Why can’t I find the forecast position page in Human resources?</span></span>
---------------------------------------------------------------

<span data-ttu-id="6af59-108">Los puestos de previsión se han movido a Gestión presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="6af59-108">Forecast positions have been moved to Budgeting.</span></span>

## <a name="why-cant-i-delete-a-budget-cost-element"></a><span data-ttu-id="6af59-109">¿Por qué no puedo eliminar un elemento de coste presupuestario?</span><span class="sxs-lookup"><span data-stu-id="6af59-109">Why can’t I delete a budget cost element?</span></span>
<span data-ttu-id="6af59-110">No puede eliminar un elemento de coste presupuestario asignado a un puesto de previsión.</span><span class="sxs-lookup"><span data-stu-id="6af59-110">You can’t delete a budget cost element that is assigned to a forecast position.</span></span> <span data-ttu-id="6af59-111">Para poder eliminar un elemento de coste presupuestario, debe quitarlo de todas las posiciones de previsión.</span><span class="sxs-lookup"><span data-stu-id="6af59-111">Before you can delete a budget cost element, you must remove it from all forecast positions.</span></span> <span data-ttu-id="6af59-112">**Sugerencia:** Para encontrar todos los puestos a los que está asignado un elemento de coste presupuestario, seleccione el elemento de coste en la página **Elementos de coste presupuestario** y, a continuación, haga clic en **Actualizar puestos**.</span><span class="sxs-lookup"><span data-stu-id="6af59-112">**Tip:** To find all the positions that a budget cost element is assigned to, select the cost element on the **Budget cost elements** page, and then click **Update positions**.</span></span> <span data-ttu-id="6af59-113">Los puestos que usan el elemento de coste se muestran en la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="6af59-113">The positions that use the cost element are listed in the upper grid.</span></span>

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a><span data-ttu-id="6af59-114">¿Cómo puedo quitar un elemento de coste de varios puestos de previsión sin abrirlos todos?</span><span class="sxs-lookup"><span data-stu-id="6af59-114">How can I remove a cost element from multiple forecast positions without opening each one?</span></span>
<span data-ttu-id="6af59-115">No es posible eliminar un elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="6af59-115">You can’t remove a cost element.</span></span> <span data-ttu-id="6af59-116">Sin embargo, si cambia la fecha de inicio y final de modo que se encuentren fuera de las fechas del ciclo de planificación presupuestaria, el elemento de coste ya no se asignará a los puestos de previsión de dicho ciclo de planificación presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="6af59-116">However, if you change the start and end dates so that they are outside the budget planning cycle dates, the cost element will no longer be assigned to the forecast positions in that budget planning cycle.</span></span> <span data-ttu-id="6af59-117">Para realizar este cambio, abra el elemento de coste presupuestario y, a continuación, en la ficha desplegable **Cálculo de costes**, haga clic en **Modificar fechas** y cambiar la fecha de vigencia o la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="6af59-117">To make this change, open the budget cost element, and then, on the **Cost calculation** FastTab, click **Change dates**, and change the effective date or expiration date.</span></span> <span data-ttu-id="6af59-118">Haga clic en **Aceptar** para actualizar automáticamente todos los puestos de previsión a los que está asignado el elemento de costes.</span><span class="sxs-lookup"><span data-stu-id="6af59-118">Then click **OK** to automatically update all forecast positions that the cost element is assigned to.</span></span> <span data-ttu-id="6af59-119">**Sugerencia:** Si usa este método, tenga en cuenta que quita el elemento de coste presupuestario de **todos** los puestos de previsión en los que la fecha inicial y final ya no esté dentro del intervalo adecuado.</span><span class="sxs-lookup"><span data-stu-id="6af59-119">**Tip:** If you use this method, be aware that it removes the budget cost element from **all** forecast positions where the start and end dates are no longer within the appropriate range.</span></span> <span data-ttu-id="6af59-120">Si esto no es lo que quiere hacer, debe abrir cada puesto de previsión del que desee quitar el elemento de coste presupuestario y realizar manualmente el cambio.</span><span class="sxs-lookup"><span data-stu-id="6af59-120">If this effect isn't what you intend, you must open each forecast position that you want to remove the budget cost element from and manually make the change.</span></span>

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a><span data-ttu-id="6af59-121">¿Por qué no puedo especificar un importe anual en la ficha desplegable de cálculo de costes para el elemento de coste presupuestario?</span><span class="sxs-lookup"><span data-stu-id="6af59-121">Why can’t I enter an annual amount on the Cost calculation FastTab for the budget cost element?</span></span>
<span data-ttu-id="6af59-122">No se puede especificar un importe anual si hay elementos de coste presupuestario en la ficha desplegable **Base de cálculo** porque el sistema requiere un porcentaje para calcular el valor.</span><span class="sxs-lookup"><span data-stu-id="6af59-122">You can’t enter an annual amount if there are budget cost elements on the **Calculation basis** FastTab, because the system requires a percentage in order to calculate the value.</span></span> <span data-ttu-id="6af59-123">Para cambiar el valor, elimine todos los elementos de coste presupuestario de la ficha **Base de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="6af59-123">To change the value, remove all budget cost elements from the **Calculation basis** FastTab.</span></span>

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a><span data-ttu-id="6af59-124">¿Por qué no puedo cambiar el tipo de coste presupuestario de ganancia a otro tipo?</span><span class="sxs-lookup"><span data-stu-id="6af59-124">Why can’t I change the budget cost type from earning to another budget cost type?</span></span>
<span data-ttu-id="6af59-125">Algunos elementos de coste presupuestario usan el elemento de coste ganancia como base de cálculo.</span><span class="sxs-lookup"><span data-stu-id="6af59-125">Some budget cost elements use the earning cost element as a calculation basis.</span></span> <span data-ttu-id="6af59-126">Para cambiar el campo **Tipo de coste presupuestario**, elimine el elemento de coste de ganancias de la ficha desplegable **Base de cálculo** de todos los elementos de coste presupuestario.</span><span class="sxs-lookup"><span data-stu-id="6af59-126">To change the **Budget cost type** field, remove the earning cost element from the **Calculation basis** FastTab of all budget cost elements.</span></span>

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a><span data-ttu-id="6af59-127">¿Por qué no puedo cambiar la fecha de las líneas del elemento de coste presupuestario para un elemento de coste presupuestario?</span><span class="sxs-lookup"><span data-stu-id="6af59-127">Why can’t I change the date on budget cost element lines for a budget cost element?</span></span>
<span data-ttu-id="6af59-128">No puede cambiar la fecha en la línea de elemento de coste presupuestario cuando se usa un elemento de coste presupuestario para un puesto de previsión.</span><span class="sxs-lookup"><span data-stu-id="6af59-128">You can’t change the date on the budget cost element line when a budget cost element is used by a forecast position.</span></span> <span data-ttu-id="6af59-129">Esta limitación ayuda a garantizar que los puestos de previsión están siempre dentro de las directrices del elemento de coste presupuestario.</span><span class="sxs-lookup"><span data-stu-id="6af59-129">This limitation helps guarantee that the forecast positions are always within the guidelines of the budget cost element.</span></span> <span data-ttu-id="6af59-130">Para cambiar la fecha, en la ficha desplegable **Cálculo de costes**, haga clic en **Modificar fechas** y especifique las nuevas fechas.</span><span class="sxs-lookup"><span data-stu-id="6af59-130">To change the date, on the **Cost calculation** FastTab, click **Change dates**, and enter the new dates.</span></span> <span data-ttu-id="6af59-131">A continuación, haga clic en **Aceptar** para actualizar los puestos a los que está asignado el elemento de costes.</span><span class="sxs-lookup"><span data-stu-id="6af59-131">Then click **OK** to update the positions that the cost element is assigned to.</span></span>

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a><span data-ttu-id="6af59-132">¿Por qué no puedo cambiar los costes de un elemento de coste presupuestario en la página Grupo de compensación?</span><span class="sxs-lookup"><span data-stu-id="6af59-132">Why can’t I change the costs for a budget cost element on the Compensation group page?</span></span>
<span data-ttu-id="6af59-133">Solo puede crear y modificar elementos de coste presupuestario en la página **Elementos de coste presupuestario**.</span><span class="sxs-lookup"><span data-stu-id="6af59-133">You can create and change budget cost elements only on the **Budget cost elements** page.</span></span>

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a><span data-ttu-id="6af59-134">¿Por qué recibo un mensaje de error cuando cambio las fechas para un elemento de coste en un puesto de previsión?</span><span class="sxs-lookup"><span data-stu-id="6af59-134">Why do I receive an error message when I change the dates for a cost element on a forecast position?</span></span>
<span data-ttu-id="6af59-135">Las fechas de la línea del elemento de coste de puesto de previsión deben estar dentro de los intervalos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6af59-135">The dates on the forecast position cost element line must be within the following ranges:</span></span>

-   <span data-ttu-id="6af59-136">Las fechas de activación y jubilación del puesto.</span><span class="sxs-lookup"><span data-stu-id="6af59-136">The activation and retirement dates of the position.</span></span>
-   <span data-ttu-id="6af59-137">Las fechas de activación y vencimiento del elemento de coste presupuestario.</span><span class="sxs-lookup"><span data-stu-id="6af59-137">The activation and expiration dates of the budget cost element.</span></span>
-   <span data-ttu-id="6af59-138">Las fechas de inicio y fin del ciclo presupuestario asociado al proceso de planificación presupuestaria del puesto de previsión.</span><span class="sxs-lookup"><span data-stu-id="6af59-138">The start and end dates of the budget cycle that is associated with the budget planning process of the forecast position.</span></span>





