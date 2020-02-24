---
title: Crear opciones de cobertura
description: ''
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010412"
---
# <a name="create-coverage-options"></a><span data-ttu-id="fb7f1-102">Crear opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="fb7f1-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="fb7f1-103">Las opciones de cobertura en Microsoft Dynamics 365 Human Resources son niveles de cobertura para la elección de un participante en un plan o programa de prestaciones, como Solo empleados para un plan médico o Sueldo x2 para un plan de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="fb7f1-104">Una vez definidas, las opciones de cobertura de prestaciones son reutilizables y puede asociar una opción con uno o más planes.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="fb7f1-105">Una vez que se definen las opciones de cobertura, adjunte las opciones de cobertura a un tipo de plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="fb7f1-106">El tipo de plan se asocia con un plan o programa de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="fb7f1-107">Las opciones de cobertura asociadas con un tipo de plan estarán disponibles para todos los planes creados con ese tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="fb7f1-108">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Opciones de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="fb7f1-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-109">Select **New**.</span></span>

3. <span data-ttu-id="fb7f1-110">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="fb7f1-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="fb7f1-111">Campo</span><span class="sxs-lookup"><span data-stu-id="fb7f1-111">Field</span></span> | <span data-ttu-id="fb7f1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb7f1-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fb7f1-113">**Opción de cobertura**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-113">**Coverage option**</span></span> | <span data-ttu-id="fb7f1-114">Un nombre de opción de cobertura único.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="fb7f1-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-115">**Description**</span></span> | <span data-ttu-id="fb7f1-116">Una descripción de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="fb7f1-117">**Tipo de cobertura**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-117">**Coverage code**</span></span> | <span data-ttu-id="fb7f1-118">Los códigos de cobertura asignan importes mínimos y máximos para cada tipo de persona cubierta idónea.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="fb7f1-119">Un código de cobertura indica quién se ve afectado o el importe de cobertura permitido para un tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="fb7f1-120">Puede expresar el importe de la cobertura como un importe en dólares o un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="fb7f1-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fb7f1-121">For example:</span></span></br></br><span data-ttu-id="fb7f1-122">- **Emp+1**: para calificarse, el empleado debe tener un dependiente seleccionado (si se selecciona más de uno, ya no se califica).</span><span class="sxs-lookup"><span data-stu-id="fb7f1-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="fb7f1-123">- **Emp+familia**: para calificarse, el empleado debe tener al menos dos dependientes seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="fb7f1-124">**Número máximo**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-124">**Maximum number**</span></span> | <span data-ttu-id="fb7f1-125">El número máximo de dependientes.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="fb7f1-126">**Estado**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-126">**Status**</span></span> | <span data-ttu-id="fb7f1-127">El estado de la opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-127">The status of the coverage option.</span></span> <span data-ttu-id="fb7f1-128">Si el estado de la opción de cobertura se establece en inactivo, la opción de cobertura no se puede seleccionar en los tipos de planes.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="fb7f1-129">**Porcentaje**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-129">**Percent**</span></span> | <span data-ttu-id="fb7f1-130">El porcentaje del importe.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-130">The percent amount.</span></span> <span data-ttu-id="fb7f1-131">Este campo solo está activo si se seleccionó Sueldo x % en el campo de código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="fb7f1-132">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-132">**Divisor**</span></span> | <span data-ttu-id="fb7f1-133">El divisor a usar en el cálculo cuando selecciona el código de cobertura Sueldo x %.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="fb7f1-134">**Porcentaje mínimo**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-134">**Percent minimum**</span></span> | <span data-ttu-id="fb7f1-135">El porcentaje mínimo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="fb7f1-136">**Porcentaje máximo**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-136">**Percent maximum**</span></span> | <span data-ttu-id="fb7f1-137">El porcentaje máximo cuando selecciona el código de cobertura Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="fb7f1-138">En **Opciones de idoneidad de contacto personal**, adjunte la opción de idoneidad de contactos personales correspondiente a cada opción de cobertura.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="fb7f1-139">En **Autoservicio**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="fb7f1-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="fb7f1-140">Campo</span><span class="sxs-lookup"><span data-stu-id="fb7f1-140">Field</span></span> | <span data-ttu-id="fb7f1-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb7f1-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fb7f1-142">**Permitir importe de contribución del empleado**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="fb7f1-143">Especifica si se permite a los empleados modificar el importe de la contribución en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fb7f1-144">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de contribución que el empleado introduce en el autoservicio de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="fb7f1-145">**Permitir importe de cobertura del empleado**</span><span class="sxs-lookup"><span data-stu-id="fb7f1-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="fb7f1-146">Especifica si se permite a los empleados modificar el importe de la cobertura en el autoservicio de prestaciones cuando seleccionan las prestaciones.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fb7f1-147">Si selecciona esta casilla, el sistema calculará los parámetros del plan de prestaciones en función del importe de cobertura que el empleado introduce en el autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="fb7f1-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fb7f1-148">Select **Save**.</span></span> 
