---
title: Configurar deducciones
description: Usar deducciones en Microsoft Dynamics 365 Human Resources para determinar cuánto, si corresponde, deducir del sueldo de un empleado por cada prestación.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4a916ca2d0d47407ff0d8cc2cc7ca179ecb59bae
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803666"
---
# <a name="configure-deductions"></a><span data-ttu-id="0e657-103">Configurar deducciones</span><span class="sxs-lookup"><span data-stu-id="0e657-103">Configure deductions</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0e657-104">Usar deducciones en Microsoft Dynamics 365 Human Resources para determinar cuánto, si corresponde, deducir del sueldo de un empleado por cada prestación.</span><span class="sxs-lookup"><span data-stu-id="0e657-104">Use deductions in Microsoft Dynamics 365 Human Resources to determine how much, if any, to deduct from an employee’s paycheck for each benefit.</span></span> <span data-ttu-id="0e657-105">Las deducciones son efectivas a partir de una fecha, por lo que puede mantener un registro histórico de la información de la deducción.</span><span class="sxs-lookup"><span data-stu-id="0e657-105">Deductions are date-effective, so you can keep a historical record of deduction information.</span></span> 

1. <span data-ttu-id="0e657-106">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Deducciones**.</span><span class="sxs-lookup"><span data-stu-id="0e657-106">In the **Benefits management** workspace, under **Setup**, select **Deductions**.</span></span>

2. <span data-ttu-id="0e657-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0e657-107">Select **New**.</span></span>

3. <span data-ttu-id="0e657-108">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="0e657-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="0e657-109">Campo</span><span class="sxs-lookup"><span data-stu-id="0e657-109">Field</span></span> | <span data-ttu-id="0e657-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e657-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="0e657-111">**Deducción**</span><span class="sxs-lookup"><span data-stu-id="0e657-111">**Deduction**</span></span> | <span data-ttu-id="0e657-112">Un id. único que se utiliza para identificar la deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="0e657-112">A unique ID that is used to identify the benefit deduction.</span></span> |
   | <span data-ttu-id="0e657-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0e657-113">**Description**</span></span> | <span data-ttu-id="0e657-114">Una descripción de la deducción.</span><span class="sxs-lookup"><span data-stu-id="0e657-114">A description for the deduction.</span></span> |
   | <span data-ttu-id="0e657-115">**Vigente**</span><span class="sxs-lookup"><span data-stu-id="0e657-115">**Effective**</span></span> | <span data-ttu-id="0e657-116">La fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="0e657-116">The start date.</span></span> <span data-ttu-id="0e657-117">El valor predeterminado de la fecha actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="0e657-117">The default value is the current system date.</span></span> |
   | <span data-ttu-id="0e657-118">**Caducidad**</span><span class="sxs-lookup"><span data-stu-id="0e657-118">**Expiration**</span></span> | <span data-ttu-id="0e657-119">La fecha de finalización.</span><span class="sxs-lookup"><span data-stu-id="0e657-119">The end date.</span></span> <span data-ttu-id="0e657-120">El valor predeterminado es 12/31/2154, que significa nunca.</span><span class="sxs-lookup"><span data-stu-id="0e657-120">The default value is 12/31/2154, which signifies never.</span></span> |
   | <span data-ttu-id="0e657-121">**Título**</span><span class="sxs-lookup"><span data-stu-id="0e657-121">**Heading**</span></span> | <span data-ttu-id="0e657-122">El código de encabezado del sistema de nóminas que esta deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="0e657-122">The heading code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="0e657-123">Se utiliza cuando usa un proveedor de nómina externo.</span><span class="sxs-lookup"><span data-stu-id="0e657-123">This is used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="0e657-124">**Referencia del empleado para deducciones de nómina**</span><span class="sxs-lookup"><span data-stu-id="0e657-124">**Employee payroll deduction reference**</span></span> | <span data-ttu-id="0e657-125">Código de deducción del sistema de nóminas que esta deducción usará para la parte del empleado de la deducción al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="0e657-125">The deduction code from the payroll system that this deduction will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> |
   | <span data-ttu-id="0e657-126">**Partida de importe**</span><span class="sxs-lookup"><span data-stu-id="0e657-126">**Amount heading**</span></span> | <span data-ttu-id="0e657-127">El código de encabezado del sistema de nóminas que este importe de deducción usará para la parte de la deducción del empleado al procesar las prestaciones de la nómina.</span><span class="sxs-lookup"><span data-stu-id="0e657-127">The heading code from the payroll system that this deduction amount will use for the employee portion of the deduction when processing the benefits to payroll.</span></span> <span data-ttu-id="0e657-128">Normalmente, se utiliza cuando usa un proveedor de nómina externo.</span><span class="sxs-lookup"><span data-stu-id="0e657-128">This is normally used when you use a third-party payroll provider.</span></span> |
   | <span data-ttu-id="0e657-129">**Se puede eliminar**</span><span class="sxs-lookup"><span data-stu-id="0e657-129">**Can delete**</span></span> | <span data-ttu-id="0e657-130">Especifica si un valor exportado de Dynamics 365 for Finance and Operations puede hacer que el valor se elimine en el sistema de nómina.</span><span class="sxs-lookup"><span data-stu-id="0e657-130">Specifies whether an exported value from Dynamics 365 for Finance and Operations can cause the value to be deleted in the payroll system.</span></span> |
   | <span data-ttu-id="0e657-131">**Columnas emparejadas**</span><span class="sxs-lookup"><span data-stu-id="0e657-131">**Paired columns**</span></span> | <span data-ttu-id="0e657-132">Especifica si se debe exportar el encabezado y el importe de deducción en columnas adyacentes emparejadas al sistema de nómina.</span><span class="sxs-lookup"><span data-stu-id="0e657-132">Specifies whether to export heading and deduction amount in paired adjacent columns to the payroll system.</span></span> |
   | <span data-ttu-id="0e657-133">**Fecha de vigencia del cambio**</span><span class="sxs-lookup"><span data-stu-id="0e657-133">**Change effective date**</span></span> | <span data-ttu-id="0e657-134">La fecha en la que entrará en vigor el cambio de deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="0e657-134">The date when the benefit deduction change will become effective.</span></span> <span data-ttu-id="0e657-135">En esta fecha, el sistema cambiará automáticamente la deducción de prestaciones y actualizará todos los planes de prestaciones asociados con esta deducción, siempre que ejecute el proceso de **Actualización de cambio de deducción**.</span><span class="sxs-lookup"><span data-stu-id="0e657-135">On this date, the system automatically changes the benefit deduction and updates all benefit plans associated with this deduction, as long as you run **Deduction change update** processing.</span></span> |
   | <span data-ttu-id="0e657-136">**Cambio de deducción completado**</span><span class="sxs-lookup"><span data-stu-id="0e657-136">**Deduction change completed**</span></span> | <span data-ttu-id="0e657-137">La casilla de **Cambio de deducción completado** se seleccionará automáticamente una vez que el proceso de cambio de actualización de deducción haya completado los cambios de deducción de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="0e657-137">The **Deduction change completed** check box will be automatically selected once the benefit deduction changes have been completed by Deduction update change processing.</span></span> |
   
4. <span data-ttu-id="0e657-138">Para realizar un seguimiento y mantener los cambios en la configuración de la tasa de prestaciones, seleccione **Acciones** y luego seleccione **Mantener versiones**.</span><span class="sxs-lookup"><span data-stu-id="0e657-138">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="0e657-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e657-139">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]