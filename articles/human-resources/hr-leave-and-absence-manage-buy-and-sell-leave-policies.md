---
title: Gestionar directivas de compra y venta de bajas
description: Puede permitir que los empleados compren y vendan bajas Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 491d1654bd219b487f95a1eb328e574114ec1f9f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051386"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="d5ccb-103">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="d5ccb-103">Manage buy and sell leave policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d5ccb-104">Puede permitir que los empleados compren y vendan bajas creando una directiva de compra y venta de bajas.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="d5ccb-105">Puede configurar estas políticas para utilizar el flujo de trabajo para las aprobaciones, establecer cantidades y tarifas máximas, y establecer tarifas de compra y venta.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="d5ccb-106">Permitir que los empleados compren y vendan bajas</span><span class="sxs-lookup"><span data-stu-id="d5ccb-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="d5ccb-107">En la página **Parámetros de permisos y ausencias**, seleccione **Sí** para **Permitir que los empleados compren bajas** y **Permitir que los empleados vendan bajas**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="d5ccb-108">Crear directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="d5ccb-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="d5ccb-109">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="d5ccb-110">Seleccione **Política de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="d5ccb-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-111">Select **New**.</span></span>

4. <span data-ttu-id="d5ccb-112">Introduzca un **Nombre** y una **Descripción** para la directiva en **Directiva de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="d5ccb-113">Seleccione un **Tipo de directiva**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="d5ccb-114">Los tipos de directivas disponibles son **Importte** y **Horas por semana**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="d5ccb-115">Seleccione **Importe** para introducir un **Importe fijo** por los importes máximos que los empleados pueden comprar y vender.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="d5ccb-116">Si seleccionas **Horas por semana**, el tiempo de trabajo definido en el calendario de tiempo de trabajo asignado del empleado se utiliza para determinar el importe máximo de la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="d5ccb-117">Seleccione una **Fecha inicial** y una **Fecha final** para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="d5ccb-118">Las solicitudes para comprar o vender bajas solo estarán disponibles para su envío durante este período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="d5ccb-119">Seleccione un **Id. de flujo de trabajo** para la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="d5ccb-120">Cualquier solicitud de compra y venta utilizará este flujo de trabajo para su revisión y aprobación.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="d5ccb-121">En **Política de compra**, Seleccione **Equivalencia a tiempo completo** (FTE) para prorratear el importe máximo según el FTE definido en la posición del empleado.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="d5ccb-122">Si el tipo de política es **Importe**, introduzca un **Importe fijo máximo**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="d5ccb-123">Seleccione **Añadir** para agregar los tipos de baja para que los empleados compren bajas.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="d5ccb-124">Puede agregar varios tipos de bajas a la directiva.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="d5ccb-125">Introduzca los **Meses de servicio** para el tipo de baja, para permitir diferentes meses de servicio para determinar el importe máximo que un empleado puede comprar.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="d5ccb-126">Introduzca el **Importe máximo** para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="d5ccb-127">Introduzca la **Tarifa** con la que el empleado comprará la baja.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="d5ccb-128">Opcionalmente, introduzca el **Código de ingresos** a usar para comprar la baja.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="d5ccb-129">Opcionalmente, establezca si usar FTE para determinar el importe máximo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="d5ccb-130">Para crear una directiva de venta, siga los pasos 8 a 14 de **Directiva de ventas**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="d5ccb-131">Agregue la directiva de compra y venta de bajas a un plan de baja y ausencia</span><span class="sxs-lookup"><span data-stu-id="d5ccb-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="d5ccb-132">En la página **Baja y ausencia**, seleccione un plan de baja y ausencia.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="d5ccb-133">En **Reglas**, seleccione **Política de compra y venta de bajas**.</span><span class="sxs-lookup"><span data-stu-id="d5ccb-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5ccb-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5ccb-134">See also</span></span>

[<span data-ttu-id="d5ccb-135">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="d5ccb-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="d5ccb-136">Configurar tipos de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="d5ccb-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="d5ccb-137">Acumular planes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="d5ccb-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="d5ccb-138">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="d5ccb-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]