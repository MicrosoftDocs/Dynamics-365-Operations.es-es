---
title: Gestionar directivas de compra y venta de bajas
description: Puede permitir que los empleados compren y vendan bajas Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429022"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="bdbfb-103">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="bdbfb-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="bdbfb-104">Puede permitir que los empleados compren bajas creando una directiva de compra de bajas.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="bdbfb-105">Permitir que los empleados compren y vendan bajas</span><span class="sxs-lookup"><span data-stu-id="bdbfb-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="bdbfb-106">En la página **Parámetros de baja y ausencia**, seleccione **Sí** para **Permitir que los empleados compren bajas**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="bdbfb-107">Crear una directiva de compra de bajas</span><span class="sxs-lookup"><span data-stu-id="bdbfb-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="bdbfb-108">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="bdbfb-109">Seleccione **Política de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="bdbfb-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-110">Select **New**.</span></span>

4. <span data-ttu-id="bdbfb-111">Introduzca un **Nombre** y una **Descripción** para la directiva en **Directiva de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="bdbfb-112">Seleccione un **Tipo de directiva**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="bdbfb-113">Los tipos de directivas disponibles son **Importte** y **Horas por semana**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="bdbfb-114">Seleccione **Importe** para introducir un **Importe fijo** por los importes máximos que los empleados pueden comprar y vender.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="bdbfb-115">Si seleccionas **Horas por semana**, el tiempo de trabajo definido en el calendario de tiempo de trabajo asignado del empleado se utiliza para determinar el importe máximo de la directiva.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="bdbfb-116">Seleccione una **Fecha inicial** y una **Fecha final** para la directiva.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="bdbfb-117">Las solicitudes para comprar o vender bajas solo estarán disponibles para su envío durante este período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="bdbfb-118">En **Política de compra**, Seleccione **Equivalencia a tiempo completo** (FTE) para prorratear el importe máximo según el FTE definido en la posición del empleado.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="bdbfb-119">Si el tipo de política es **Importe**, introduzca un **Importe fijo máximo**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="bdbfb-120">Seleccione **Añadir** para agregar los tipos de baja para que los empleados compren bajas.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="bdbfb-121">Puede agregar varios tipos de bajas a la directiva.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="bdbfb-122">Introduzca los **Meses de servicio** para el tipo de baja, para permitir diferentes meses de servicio para determinar el importe máximo que un empleado puede comprar.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="bdbfb-123">Introduzca el **Importe máximo** para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="bdbfb-124">Introduzca la **Tarifa** con la que el empleado comprará la baja.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="bdbfb-125">Opcionalmente, introduzca el **Código de ingresos** a usar para comprar la baja.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="bdbfb-126">Opcionalmente, establezca si usar FTE para determinar el importe máximo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="bdbfb-127">Agregue la directiva de compra y venta de bajas a un plan de baja y ausencia</span><span class="sxs-lookup"><span data-stu-id="bdbfb-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="bdbfb-128">En la página **Baja y ausencia**, seleccione un plan de baja y ausencia.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="bdbfb-129">En **Reglas**, seleccione **Política de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="bdbfb-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdbfb-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdbfb-130">See also</span></span>

[<span data-ttu-id="bdbfb-131">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="bdbfb-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="bdbfb-132">Configurar tipos de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="bdbfb-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="bdbfb-133">Acumular planes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="bdbfb-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="bdbfb-134">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="bdbfb-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

