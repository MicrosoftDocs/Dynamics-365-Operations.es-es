---
title: Crear opciones de cobertura
description: Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e1d5fc80d93e41626da8eb5bdf8f389fb0bd531
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466191"
---
# <a name="create-coverage-options"></a><span data-ttu-id="45866-103">Crear opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="45866-103">Create coverage options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="45866-104">Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="45866-105">Por ejemplo, las opciones de cobertura podrían incluir **Solo empleado** para un plan médico, o **2x salario** para un plan de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="45866-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="45866-106">Una vez definido, puede reutilizar las opciones de cobertura de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="45866-107">Puede asociar una opción con uno o más planes.</span><span class="sxs-lookup"><span data-stu-id="45866-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="45866-108">Después de definir las opciones de cobertura, adjunte las opciones de cobertura a un tipo de plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="45866-109">El tipo de plan se asocia con un plan o programa de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="45866-110">Las opciones de cobertura asociadas con un tipo de plan están disponibles para todos los planes creados con ese tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="45866-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="45866-111">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="45866-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="45866-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="45866-112">Select **New**.</span></span>

3. <span data-ttu-id="45866-113">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="45866-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="45866-114">Campo</span><span class="sxs-lookup"><span data-stu-id="45866-114">Field</span></span> | <span data-ttu-id="45866-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="45866-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="45866-116">**Opción de cobertura**</span><span class="sxs-lookup"><span data-stu-id="45866-116">**Coverage option**</span></span> | <span data-ttu-id="45866-117">Un nombre de opción de cobertura único.</span><span class="sxs-lookup"><span data-stu-id="45866-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="45866-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="45866-118">**Description**</span></span> | <span data-ttu-id="45866-119">Una descripción de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="45866-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="45866-120">**Tipo de cobertura**</span><span class="sxs-lookup"><span data-stu-id="45866-120">**Coverage code**</span></span> | <span data-ttu-id="45866-121">Los códigos de cobertura asignan importes mínimos y máximos para cada tipo de persona cubierta idónea.</span><span class="sxs-lookup"><span data-stu-id="45866-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="45866-122">Un código de cobertura indica quién se ve afectado o el importe de cobertura permitido para un tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="45866-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="45866-123">Puede expresar el importe de la cobertura como un importe en dólares o un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="45866-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="45866-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="45866-124">For example:</span></span></br></br><span data-ttu-id="45866-125">- **Emp+1**: para calificarse, el empleado debe tener un dependiente seleccionado (si se selecciona más de uno, ya no se califica).</span><span class="sxs-lookup"><span data-stu-id="45866-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="45866-126">- **Emp+familia**: para calificarse, el empleado debe tener al menos dos dependientes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="45866-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="45866-127">**Número máximo**</span><span class="sxs-lookup"><span data-stu-id="45866-127">**Maximum number**</span></span> | <span data-ttu-id="45866-128">El número máximo de dependientes.</span><span class="sxs-lookup"><span data-stu-id="45866-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="45866-129">**Estado**</span><span class="sxs-lookup"><span data-stu-id="45866-129">**Status**</span></span> | <span data-ttu-id="45866-130">El estado de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="45866-130">The status of the coverage option.</span></span> <span data-ttu-id="45866-131">Si el estado de la opción de cobertura se establece en inactivo, la opción de cobertura no se puede seleccionar en los tipos de planes.</span><span class="sxs-lookup"><span data-stu-id="45866-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="45866-132">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="45866-132">**Percent**</span></span> | <span data-ttu-id="45866-133">El porcentaje del importe.</span><span class="sxs-lookup"><span data-stu-id="45866-133">The percent amount.</span></span> <span data-ttu-id="45866-134">Este campo solo está activo si se seleccionó Sueldo x % en el campo de código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="45866-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="45866-135">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="45866-135">**Divisor**</span></span> | <span data-ttu-id="45866-136">El divisor a usar en el cálculo cuando selecciona el código de cobertura Sueldo x %.</span><span class="sxs-lookup"><span data-stu-id="45866-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="45866-137">**Porcentaje mínimo**</span><span class="sxs-lookup"><span data-stu-id="45866-137">**Percent minimum**</span></span> | <span data-ttu-id="45866-138">El porcentaje mínimo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="45866-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="45866-139">**Porcentaje máximo**</span><span class="sxs-lookup"><span data-stu-id="45866-139">**Percent maximum**</span></span> | <span data-ttu-id="45866-140">El porcentaje máximo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="45866-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="45866-141">En **Opciones de idoneidad de contacto personal**, adjunte la opción de idoneidad de contactos personales correspondiente a cada opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="45866-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="45866-142">En **Autoservicio**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="45866-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="45866-143">Campo</span><span class="sxs-lookup"><span data-stu-id="45866-143">Field</span></span> | <span data-ttu-id="45866-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="45866-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="45866-145">**Permitir importe de contribución del empleado**</span><span class="sxs-lookup"><span data-stu-id="45866-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="45866-146">Especifica si se permite a los empleados modificar el importe de la contribución en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="45866-147">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de contribución que el empleado introduce en el autoservicio de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="45866-148">**Permitir importe de cobertura del empleado**</span><span class="sxs-lookup"><span data-stu-id="45866-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="45866-149">Especifica si se permite a los empleados modificar el importe de la cobertura en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="45866-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="45866-150">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de cobertura que el empleado introduce en el autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="45866-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="45866-151">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="45866-151">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]