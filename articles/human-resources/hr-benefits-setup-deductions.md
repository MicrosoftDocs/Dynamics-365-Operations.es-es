---
title: Configurar deducciones
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
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010488"
---
# <a name="configure-deductions"></a><span data-ttu-id="363cb-102">Configurar deducciones</span><span class="sxs-lookup"><span data-stu-id="363cb-102">Configure deductions</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="363cb-103">Usar deducciones en Microsoft Dynamics 365 Human Resources para determinar cuánto, si corresponde, deducir del sueldo de un empleado por cada prestación.</span><span class="sxs-lookup"><span data-stu-id="363cb-103">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="363cb-104">Las deducciones son efectivas a partir de una fecha, por lo que puede mantener un registro histórico de la información de la deducción.</span><span class="sxs-lookup"><span data-stu-id="363cb-104">Deductions are date effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="363cb-105">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Deducciones**.</span><span class="sxs-lookup"><span data-stu-id="363cb-105">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="363cb-106">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="363cb-106">Select **New**.</span></span>

3. <span data-ttu-id="363cb-107">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="363cb-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="363cb-108">Campo</span><span class="sxs-lookup"><span data-stu-id="363cb-108">Field</span></span> | <span data-ttu-id="363cb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="363cb-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="363cb-110">Deducción</span><span class="sxs-lookup"><span data-stu-id="363cb-110">Deduction</span></span> | <span data-ttu-id="363cb-111">Un id. único que se utiliza para identificar la deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="363cb-111">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="363cb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="363cb-112">Description</span></span> | <span data-ttu-id="363cb-113">Una descripción de la deducción.</span><span class="sxs-lookup"><span data-stu-id="363cb-113">A description for the deduction.</span></span> |
   | <span data-ttu-id="363cb-114">Vigente</span><span class="sxs-lookup"><span data-stu-id="363cb-114">Effective</span></span> | <span data-ttu-id="363cb-115">La fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="363cb-115">The start date.</span></span> <span data-ttu-id="363cb-116">El valor predeterminado de la fecha actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="363cb-116">The default value is the current system date.</span></span> |
   | <span data-ttu-id="363cb-117">Caducidad</span><span class="sxs-lookup"><span data-stu-id="363cb-117">Expiration</span></span> | <span data-ttu-id="363cb-118">La fecha de finalización.</span><span class="sxs-lookup"><span data-stu-id="363cb-118">The end date.</span></span> <span data-ttu-id="363cb-119">El valor predeterminado es 12/31/2154, que significa nunca.</span><span class="sxs-lookup"><span data-stu-id="363cb-119">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="363cb-120">Título</span><span class="sxs-lookup"><span data-stu-id="363cb-120">Heading</span></span> | <span data-ttu-id="363cb-121">El código de encabezado del sistema de nóminas que esta deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="363cb-121">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="363cb-122">Se utiliza cuando usa un proveedor de nómina externo.</span><span class="sxs-lookup"><span data-stu-id="363cb-122">This is used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="363cb-123">Referencia del empleado para deducciones de nómina</span><span class="sxs-lookup"><span data-stu-id="363cb-123">Employee payroll deduction reference</span></span> | <span data-ttu-id="363cb-124">Código de deducción del sistema de nóminas que esta deducción usará para la parte del empleado de la deducción al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="363cb-124">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="363cb-125">Partida de importe</span><span class="sxs-lookup"><span data-stu-id="363cb-125">Amount heading</span></span> | <span data-ttu-id="363cb-126">El código de encabezado del sistema de nóminas que este importe de deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="363cb-126">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="363cb-127">Normalmente, se utiliza cuando usa un proveedor de nómina externo.</span><span class="sxs-lookup"><span data-stu-id="363cb-127">This is normally used when you use a third party payroll provider.</span></span> |
   | <span data-ttu-id="363cb-128">Se puede eliminar</span><span class="sxs-lookup"><span data-stu-id="363cb-128">Can delete</span></span> | <span data-ttu-id="363cb-129">Especifica si un valor exportado de Dynamics 365 for Finance and Operations puede hacer que el valor se elimine en el sistema de nómina.</span><span class="sxs-lookup"><span data-stu-id="363cb-129">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="363cb-130">Columnas emparejadas</span><span class="sxs-lookup"><span data-stu-id="363cb-130">Paired columns</span></span> | <span data-ttu-id="363cb-131">Especifica si se debe exportar el encabezado y el importe de deducción en columnas adyacentes emparejadas al sistema de nómina.</span><span class="sxs-lookup"><span data-stu-id="363cb-131">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="363cb-132">Fecha de vigencia del cambio</span><span class="sxs-lookup"><span data-stu-id="363cb-132">Change effective date</span></span> | <span data-ttu-id="363cb-133">La fecha en la que entrará en vigor el cambio de deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="363cb-133">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="363cb-134">En esta fecha, el sistema cambiará automáticamente la deducción de prestaciones y actualizará todos los planes de prestaciones asociados con esta deducción, siempre que ejecute el proceso de actualización de cambio de deducción.</span><span class="sxs-lookup"><span data-stu-id="363cb-134">On this date the system will automatically change the benefit deduction and update all benefit plans associated with this deduction, as long as you run Deduction change update processing.</span></span> |
   | <span data-ttu-id="363cb-135">Cambio de deducción completado</span><span class="sxs-lookup"><span data-stu-id="363cb-135">Deduction change completed</span></span> | <span data-ttu-id="363cb-136">La casilla de cambio de deducción completado se seleccionará automáticamente una vez que el proceso de cambio de actualización de deducción haya completado los cambios de deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="363cb-136">The Deduction change completed check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="363cb-137">Para realizar un seguimiento y mantener los cambios en la configuración de la tasa de prestaciones, seleccione **Acciones** y luego seleccione **Mantener versiones**.</span><span class="sxs-lookup"><span data-stu-id="363cb-137">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="363cb-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="363cb-138">Select **Save**.</span></span> 
