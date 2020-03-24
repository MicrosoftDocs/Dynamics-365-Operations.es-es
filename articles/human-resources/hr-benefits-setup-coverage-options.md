---
title: Crear opciones de cobertura
description: Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones, como Solo empleados para un plan médico o Sueldo x2 para un plan de seguro de vida.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092715"
---
# <a name="create-coverage-options"></a><span data-ttu-id="6a103-103">Crear opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="6a103-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="6a103-104">Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones, como Solo empleados para un plan médico o Sueldo x2 para un plan de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="6a103-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="6a103-105">Una vez definidas, las opciones de cobertura de prestaciones son reutilizables y puede asociar una opción con uno o más planes.</span><span class="sxs-lookup"><span data-stu-id="6a103-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="6a103-106">Una vez que se definen las opciones de cobertura, adjunte las opciones de cobertura a un tipo de plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6a103-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="6a103-107">El tipo de plan se asocia con un plan o programa de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6a103-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="6a103-108">Las opciones de cobertura asociadas con un tipo de plan estarán disponibles para todos los planes creados con ese tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="6a103-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="6a103-109">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="6a103-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="6a103-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6a103-110">Select **New**.</span></span>

3. <span data-ttu-id="6a103-111">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="6a103-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6a103-112">Campo</span><span class="sxs-lookup"><span data-stu-id="6a103-112">Field</span></span> | <span data-ttu-id="6a103-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a103-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6a103-114">**Opción de cobertura**</span><span class="sxs-lookup"><span data-stu-id="6a103-114">**Coverage option**</span></span> | <span data-ttu-id="6a103-115">Un nombre de opción de cobertura único.</span><span class="sxs-lookup"><span data-stu-id="6a103-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="6a103-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6a103-116">**Description**</span></span> | <span data-ttu-id="6a103-117">Una descripción de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="6a103-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="6a103-118">**Tipo de cobertura**</span><span class="sxs-lookup"><span data-stu-id="6a103-118">**Coverage code**</span></span> | <span data-ttu-id="6a103-119">Los códigos de cobertura asignan importes mínimos y máximos para cada tipo de persona cubierta idónea.</span><span class="sxs-lookup"><span data-stu-id="6a103-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="6a103-120">Un código de cobertura indica quién se ve afectado o el importe de cobertura permitido para un tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="6a103-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="6a103-121">Puede expresar el importe de la cobertura como un importe en dólares o un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="6a103-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="6a103-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6a103-122">For example:</span></span></br></br><span data-ttu-id="6a103-123">- **Emp+1**: para calificarse, el empleado debe tener un dependiente seleccionado (si se selecciona más de uno, ya no se califica).</span><span class="sxs-lookup"><span data-stu-id="6a103-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="6a103-124">- **Emp+familia**: para calificarse, el empleado debe tener al menos dos dependientes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6a103-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="6a103-125">**Número máximo**</span><span class="sxs-lookup"><span data-stu-id="6a103-125">**Maximum number**</span></span> | <span data-ttu-id="6a103-126">El número máximo de dependientes.</span><span class="sxs-lookup"><span data-stu-id="6a103-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="6a103-127">**Estado**</span><span class="sxs-lookup"><span data-stu-id="6a103-127">**Status**</span></span> | <span data-ttu-id="6a103-128">El estado de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="6a103-128">The status of the coverage option.</span></span> <span data-ttu-id="6a103-129">Si el estado de la opción de cobertura se establece en inactivo, la opción de cobertura no se puede seleccionar en los tipos de planes.</span><span class="sxs-lookup"><span data-stu-id="6a103-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="6a103-130">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="6a103-130">**Percent**</span></span> | <span data-ttu-id="6a103-131">El porcentaje del importe.</span><span class="sxs-lookup"><span data-stu-id="6a103-131">The percent amount.</span></span> <span data-ttu-id="6a103-132">Este campo solo está activo si se seleccionó Sueldo x % en el campo de código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="6a103-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="6a103-133">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="6a103-133">**Divisor**</span></span> | <span data-ttu-id="6a103-134">El divisor a usar en el cálculo cuando selecciona el código de cobertura Sueldo x %.</span><span class="sxs-lookup"><span data-stu-id="6a103-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="6a103-135">**Porcentaje mínimo**</span><span class="sxs-lookup"><span data-stu-id="6a103-135">**Percent minimum**</span></span> | <span data-ttu-id="6a103-136">El porcentaje mínimo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="6a103-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="6a103-137">**Porcentaje máximo**</span><span class="sxs-lookup"><span data-stu-id="6a103-137">**Percent maximum**</span></span> | <span data-ttu-id="6a103-138">El porcentaje máximo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="6a103-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="6a103-139">En **Opciones de idoneidad de contacto personal**, adjunte la opción de idoneidad de contactos personales correspondiente a cada opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="6a103-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="6a103-140">En **Autoservicio**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="6a103-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="6a103-141">Campo</span><span class="sxs-lookup"><span data-stu-id="6a103-141">Field</span></span> | <span data-ttu-id="6a103-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a103-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6a103-143">**Permitir importe de contribución del empleado**</span><span class="sxs-lookup"><span data-stu-id="6a103-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="6a103-144">Especifica si se permite a los empleados modificar el importe de la contribución en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6a103-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="6a103-145">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de contribución que el empleado introduce en el autoservicio de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6a103-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="6a103-146">**Permitir importe de cobertura del empleado**</span><span class="sxs-lookup"><span data-stu-id="6a103-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="6a103-147">Especifica si se permite a los empleados modificar el importe de la cobertura en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="6a103-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="6a103-148">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de cobertura que el empleado introduce en el autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="6a103-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="6a103-149">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a103-149">Select **Save**.</span></span> 
