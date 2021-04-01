---
title: Crear presupuestos de mantenimiento
description: En este tema se explica cómo crear un presupuesto de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 593a03e3317de5759427dfc61093530c4b7ef7e9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253503"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="7cec5-103">Crear presupuestos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="7cec5-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="7cec5-104">Los presupuestos de mantenimiento que se usan para proporcionar una visión general de los costes previstos para el mantenimiento preventivo.</span><span class="sxs-lookup"><span data-stu-id="7cec5-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="7cec5-105">Las líneas de presupuesto se calculan basándose en las líneas de la programación de mantenimiento con una fecha de inicio prevista durante el período presupuestario.</span><span class="sxs-lookup"><span data-stu-id="7cec5-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="7cec5-106">Los presupuestos de mantenimiento se basan en los tipos de coste que se usan en Administración de activos: **Preventivo**, **Correctivo** e **Inversión**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="7cec5-107">Los costes presupuestarios para el mantenimiento de la inversión se incluyen para los activos que estén activos y que tengan una fecha de sustitución durante el período presupuestario y un valor de sustitución relacionado.</span><span class="sxs-lookup"><span data-stu-id="7cec5-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="7cec5-108">Los costes presupuestarios para el mantenimiento correctivo se incluyen si se incluye una fecha correctiva pasada en el cálculo del presupuesto.</span><span class="sxs-lookup"><span data-stu-id="7cec5-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="7cec5-109">En ese caso, los costes correctivos de un período anterior se calculan para el mismo período futuro para el que se calcula el presupuesto de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="7cec5-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="7cec5-110">Crear un presupuesto de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="7cec5-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="7cec5-111">Seleccione **Administración de activos** \> **Consultas** \> **Presupuesto de mantenimiento** \> **Presupuesto**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="7cec5-112">Seleccione **Crear presupuesto**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="7cec5-113">En el campo **Presupuesto de mantenimiento**, especifique un Id. de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="7cec5-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="7cec5-114">En el campo **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="7cec5-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="7cec5-115">En la ficha desplegable **Período**, en los campos **Fecha inicial** y **Fecha final**, especifique las fechas de inicio y fin del período presupuestario.</span><span class="sxs-lookup"><span data-stu-id="7cec5-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="7cec5-116">Para incluir los costes de presupuesto correctivo que se calculan a partir de los costes reales de un período anterior, en el campo **Correctivo desde fecha**, especifique la fecha inicial del período desde el cual se deben incluir esos costes.</span><span class="sxs-lookup"><span data-stu-id="7cec5-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="7cec5-117">En función del nivel de detalle necesario en el presupuesto, establezca las opciones relevantes en las cinco pestañas desplegables **Agrupar por**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="7cec5-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-118">Select **OK**.</span></span>
8. <span data-ttu-id="7cec5-119">Seleccione **Líneas de presupuesto** para abrir la página **Líneas de presupuesto de mantenimiento**, donde podrá ver todas las líneas de presupuesto que se han creado para el período.</span><span class="sxs-lookup"><span data-stu-id="7cec5-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="7cec5-120">Para aprobar el presupuesto, selecciónelo en la página **Presupuestos de mantenimiento** y, a continuación, seleccione **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="7cec5-121">A continuación, en el cuadro **Aprobar el presupuesto**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="7cec5-122">Su nombre se especifica en el campo **Aprobado por** en la página **Presupuestos de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7cec5-123">Una vez que haya aprobado un presupuesto de mantenimiento, no puede volver a calcular o ajustar las líneas relacionadas en la página **Líneas de presupuesto de mantenimiento**, a menos que primero quite la aprobación.</span><span class="sxs-lookup"><span data-stu-id="7cec5-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="7cec5-124">Para quitar la aprobación de un presupuesto de mantenimiento, selecciónelo en la página **Presupuestos de mantenimiento** y, a continuación, seleccione **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="7cec5-125">A continuación, en el cuadro **Aprobar el presupuesto**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Presupuestos de mantenimiento](media/01-maintenance-budgets.png)

<span data-ttu-id="7cec5-127">También puede crear un nuevo presupuesto de mantenimiento copiando un presupuesto existente.</span><span class="sxs-lookup"><span data-stu-id="7cec5-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="7cec5-128">En la página **Presupuestos de mantenimiento**, seleccione el presupuesto que quiere copiar y, a continuación, seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="7cec5-129">Este es enfoque es práctico si, por ejemplo, ha creado un presupuesto para un mes y desea copiarlo a otros meses.</span><span class="sxs-lookup"><span data-stu-id="7cec5-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="7cec5-130">El presupuesto de mantenimiento calcula solo los costes del presupuesto según las líneas de la programación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="7cec5-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="7cec5-131">Para calcular los costes reales para el mismo período, puede realizar dicho cálculo en la página **Control de costes de activos**.</span><span class="sxs-lookup"><span data-stu-id="7cec5-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]