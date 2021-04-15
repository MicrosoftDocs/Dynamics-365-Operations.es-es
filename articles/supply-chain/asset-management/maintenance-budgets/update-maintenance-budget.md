---
title: Actualizar presupuestos de mantenimiento
description: En este tema se explica cómo actualizar un presupuesto de mantenimiento en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 01620e1cca17d3c2b08b3abcdf9a4482693f0409
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809839"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="01944-103">Actualizar presupuestos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="01944-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="01944-104">La página **Líneas de presupuesto de mantenimiento** muestra todas las líneas de presupuesto que se han creado para el presupuesto seleccionado en la página **Presupuestos de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="01944-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="01944-105">(Para obtener más información, consulte [Crear presupuestos de mantenimiento](create-maintenance-budget.md).) Puede volver a calcular y ajustar las líneas de presupuesto de mantenimiento hasta que se apruebe el presupuesto de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="01944-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="01944-106">Una vez que haya pasado el periodo del presupuesto y se hayan registrado los costes en Administración de activos, también puede actualizar las líneas de presupuesto con los costes reales.</span><span class="sxs-lookup"><span data-stu-id="01944-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="01944-107">Volver a calcular un presupuesto de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="01944-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="01944-108">Puede volver a calcular un presupuesto de mantenimiento en la página **Líneas de presupuesto de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="01944-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="01944-109">Cuando vuelva a calcular un presupuesto de mantenimiento, se eliminan las líneas de presupuesto existentes y se hace un nuevo cálculo.</span><span class="sxs-lookup"><span data-stu-id="01944-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="01944-110">En la página **Líneas de presupuesto de mantenimiento**, seleccione **Volver a calcular**.</span><span class="sxs-lookup"><span data-stu-id="01944-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="01944-111">En el cuadro de diálogo **Volver a calcular el presupuesto**, realice los cambios necesarios para el nuevo cálculo y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01944-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="01944-112">Se crean nuevas líneas de presupuesto en función de los valores que establezca.</span><span class="sxs-lookup"><span data-stu-id="01944-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="01944-113">Ajustar líneas de presupuesto</span><span class="sxs-lookup"><span data-stu-id="01944-113">Adjust budget lines</span></span>

<span data-ttu-id="01944-114">En lugar de volver a calcular todo el presupuesto de mantenimiento, puede ajustar las líneas seleccionadas que están relacionadas con los costes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="01944-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="01944-115">En la página **Líneas de presupuesto de mantenimiento**, seleccione las líneas para actualizar el coste presupuestario.</span><span class="sxs-lookup"><span data-stu-id="01944-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="01944-116">Seleccione **Ajustar**.</span><span class="sxs-lookup"><span data-stu-id="01944-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="01944-117">Para agregar un importe a las líneas seleccionadas, seleccione la casilla **Agregar coste** e introduzca el valor en el campo **Agregar valor**.</span><span class="sxs-lookup"><span data-stu-id="01944-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="01944-118">Para multiplicar el coste presupuestario en las líneas de presupuesto seleccionadas por un factor, seleccione la casilla **Multiplicar coste** e introduzca el factor en el campo **Multiplicar valor**.</span><span class="sxs-lookup"><span data-stu-id="01944-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="01944-119">Por ejemplo, si introduce **1,2** en el campo **Multiplicar valor**, aumentará el coste presupuestario en las líneas seleccionadas en un 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="01944-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="01944-120">Si introduce **0,7**, reducirá el coste presupuestario en las líneas seleccionadas en un 30 por ciento.</span><span class="sxs-lookup"><span data-stu-id="01944-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="01944-121">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01944-121">Select **OK**.</span></span>

<span data-ttu-id="01944-122">Las líneas de presupuesto seleccionadas se actualizan en función de los valores definidos en el paso 3 o 4.</span><span class="sxs-lookup"><span data-stu-id="01944-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="01944-123">Actualizar costes reales</span><span class="sxs-lookup"><span data-stu-id="01944-123">Update actual costs</span></span>

<span data-ttu-id="01944-124">Una vez que hayan pasado las fechas en las líneas de presupuesto y se hayan registrado los costes reales en Administración de activos, puede actualizar los costes reales en el presupuesto de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="01944-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="01944-125">En la página **Líneas de presupuesto de mantenimiento**, seleccione **Actualizar coste**.</span><span class="sxs-lookup"><span data-stu-id="01944-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="01944-126">En el cuadro de diálogo **Calcular coste real**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="01944-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="01944-127">Los campos **Coste real** en las líneas de presupuesto se actualizan si se han registrado los costes reales.</span><span class="sxs-lookup"><span data-stu-id="01944-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="01944-128">Se podrán generar nuevas líneas de presupuesto si se han creado nuevos tipos de activos desde que creó el presupuesto, y si esos tipos de activos se han utilizado en los activos para los que se han creado órdenes de trabajo y para los que se han registrado costes relacionados.</span><span class="sxs-lookup"><span data-stu-id="01944-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="01944-129">Las nuevas líneas de presupuesto muestran solo los costes reales, ya que no se calculó ningún coste presupuestario para ellas.</span><span class="sxs-lookup"><span data-stu-id="01944-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="01944-130">Para obtener una visión general de los costes reales divididos en costes preventivos, correctivos y de inversión, puede hacer un cálculo para el mismo período en la página **Control de costes del activo**.</span><span class="sxs-lookup"><span data-stu-id="01944-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="01944-131">Agregar líneas de presupuesto manualmente</span><span class="sxs-lookup"><span data-stu-id="01944-131">Manually add budget lines</span></span>

<span data-ttu-id="01944-132">En la página **Líneas de presupuesto de mantenimiento**, puede agregar manualmente una nueva línea de presupuesto seleccionando **Nueva** y haciendo selecciones en la línea.</span><span class="sxs-lookup"><span data-stu-id="01944-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="01944-133">A continuación se muestran algunos ejemplos de situaciones en las que este enfoque podría ser de utilidad:</span><span class="sxs-lookup"><span data-stu-id="01944-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="01944-134">Sabe que la restauración de algunos activos se encuentra actualmente en la fase de planificación, pero los trabajos relacionados aún no se han creado en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="01944-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="01944-135">Sin embargo, desea que se incluyan los costes presupuestarios para esos trabajos en el presupuesto de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="01944-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="01944-136">Se han creado nuevos activos o tipos de activos desde que hizo el presupuesto de mantenimiento, pero los planes de mantenimiento aún no se han configurado en esos activos o tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="01944-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="01944-137">Sin embargo, desea que se incluyan los costes presupuestarios para esos tipos de activos en el presupuesto de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="01944-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]