---
title: Registrar consumo
description: En este tema se explica cómo registrar el consumo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c9bbd51da23ea412bc124f932f73876a9506d47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436967"
---
# <a name="register-consumption"></a><span data-ttu-id="af0d9-103">Registrar consumo</span><span class="sxs-lookup"><span data-stu-id="af0d9-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="af0d9-104">Cuando se haya completado un trabajo de mantenimiento en una orden de trabajo, el paso siguiente es hacer los registros de consumo y registrar los diarios.</span><span class="sxs-lookup"><span data-stu-id="af0d9-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="af0d9-105">Puede hacer registros en los siguientes tipos de consumo: horas, artículos y gastos.</span><span class="sxs-lookup"><span data-stu-id="af0d9-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="af0d9-106">Los distintos tipos de consumo se registran en la página **Diarios de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="af0d9-107">La configuración del diario en **Administración de activos** se utiliza para crear y registrar diarios independientes para horas, artículos y gastos en el módulo **Gestión y contabilidad de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="af0d9-108">En algunos casos, es posible que pueda agregar o eliminar líneas de previsión en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-108">In some cases, you may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="af0d9-109">La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas del diario.</span><span class="sxs-lookup"><span data-stu-id="af0d9-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="af0d9-110">Lea más información sobre estados del ciclo de vida de la orden de trabajo y fases del proyecto relacionadas en [Previsiones, órdenes de trabajo y proyectos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="af0d9-110">Read more about work order lifecycle states and related project stages in [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="af0d9-111">Es posible configurar un registro automático de diarios en el estado de ciclo de vida de una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="af0d9-112">Consulte [Estados de ciclo de vida de orden de trabajo](../setup-for-work-orders/work-order-lifecycle-states.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="af0d9-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="af0d9-113">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="af0d9-114">Seleccione la orden de trabajo y haga clic en **Diarios**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-114">Select the work order, and click **Journals**.</span></span>

3. <span data-ttu-id="af0d9-115">Haga clic en **Copiar desde previsión** para transferir cualquier línea de previsión que pueda estar conectada con la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="af0d9-116">Puede seleccionar los tipos de consumo que desea transferir.</span><span class="sxs-lookup"><span data-stu-id="af0d9-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="af0d9-117">Si es necesario, puede agregar más líneas de consumo en la ficha desplegable pertinente haciendo clic en **Agregar línea** y rellenando los datos de la línea.</span><span class="sxs-lookup"><span data-stu-id="af0d9-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="af0d9-118">Haga clic en **Validar diarios** para validar las líneas de diario antes de registrarlo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="af0d9-119">Haga clic en **Registrar diarios** para registrar las líneas del diario.</span><span class="sxs-lookup"><span data-stu-id="af0d9-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="af0d9-120">Después de haber registrado los diarios de consumo, puede actualizar el estado del ciclo de vida del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-120">After you've posted the consumption journals, you can update the work order lifecycle state.</span></span> <span data-ttu-id="af0d9-121">Por ejemplo, para indicar que el pedido de trabajo se ha completado, puede actualizar al estado del ciclo de vida en “terminado”.</span><span class="sxs-lookup"><span data-stu-id="af0d9-121">For example, to indicate that the work order has been completed, you can update the lifecycle state to "Ended".</span></span>

    - <span data-ttu-id="af0d9-122">En el campo **Mostrar** situado en la parte superior de la página **Diarios de órdenes de trabajo**, seleccione las líneas del diario que desea ver: **Todas**, **No registradas** o **Registradas**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-122">In the **Show** field at the top of the **Work order journals** page, select which journal lines you want to see: **All**, **Not posted**, or **Posted**.</span></span> <span data-ttu-id="af0d9-123">Los diarios registrados tienen una marca de verificación en la casilla **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-123">Posted journals have a check mark in the **Posted** check box.</span></span>  
    - <span data-ttu-id="af0d9-124">Cuando se crean líneas de artículos en el diario de orden de trabajo, las dimensiones del producto y las dimensiones de seguimiento relacionadas con el artículo se transfieren automáticamente a la línea del diario.</span><span class="sxs-lookup"><span data-stu-id="af0d9-124">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="af0d9-125">La siguiente captura de pantalla muestra un ejemplo de los registros de horas y artículos en una orden de trabajo en **Diarios de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-125">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figura 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="af0d9-127">Horas divididas en órdenes de trabajo con varios trabajos de una orden trabajo</span><span class="sxs-lookup"><span data-stu-id="af0d9-127">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="af0d9-128">Si una orden de trabajo contiene varias tareas, puede registrar las horas de trabajo mediante la función **Horas divididas**, lo que significa que una línea de registro de horas se puede distribuir de forma equitativa en cada tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-128">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="af0d9-129">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-129">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="af0d9-130">Seleccione la orden de trabajo y haga clic en **Diarios**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-130">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="af0d9-131">Seleccione la línea de registro de horas que desea dividir y haga clic en **Horas divididas**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-131">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="af0d9-132">En el diálogo **Horas divididas en trabajos de mantenimiento de órdenes de trabajo**, el nombre del trabajador que está registrado se muestra automáticamente en el campo **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-132">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="af0d9-133">Si es necesario, puede seleccionar otro trabajador.</span><span class="sxs-lookup"><span data-stu-id="af0d9-133">If required, you can select another worker.</span></span>

5. <span data-ttu-id="af0d9-134">Seleccione una categoría para el registro de horas en el campo **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-134">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="af0d9-135">Inserte el número de horas de trabajo que se van a dividir en el campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-135">Insert number of work hours to be split in the **Hours** field.</span></span>

    ![Figura 2](media/02-consumption.png)

7. <span data-ttu-id="af0d9-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af0d9-137">Click **OK**.</span></span>

<span data-ttu-id="af0d9-138">*Ejemplo:* en la siguiente captura de pantalla se muestran las líneas de diario para una orden de trabajo que contiene tres tareas.</span><span class="sxs-lookup"><span data-stu-id="af0d9-138">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="af0d9-139">La primera línea, que contiene tres horas de trabajo, se ha dividido, y una hora de trabajo se registra en cada tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-139">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="af0d9-140">Una vez creadas las tres líneas de registro de horas, decida qué hacer con la línea de registro de horas original (la primera línea del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="af0d9-140">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="af0d9-141">Puede conservarla tal cual o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="af0d9-141">You can keep it as is or delete it.</span></span> 

![Figura 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="af0d9-143">Dimensiones financieras en los registros de consumo</span><span class="sxs-lookup"><span data-stu-id="af0d9-143">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="af0d9-144">Al hacer registros de consumo, las dimensiones financieras relacionadas con los distintos tipos de registro se agregan a los registros en una secuencia específica.</span><span class="sxs-lookup"><span data-stu-id="af0d9-144">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

- <span data-ttu-id="af0d9-145">*Registros de horas y gastos:* en primer lugar, se agregan las dimensiones financieras del encabezado del diario, si existen.</span><span class="sxs-lookup"><span data-stu-id="af0d9-145">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="af0d9-146">A continuación, se agregan las dimensiones financieras del proyecto de orden de trabajo relacionado.</span><span class="sxs-lookup"><span data-stu-id="af0d9-146">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="af0d9-147">Finalmente, se agregan las dimensiones financieras del recurso (trabajador).</span><span class="sxs-lookup"><span data-stu-id="af0d9-147">Finally, financial dimensions from the resource (worker) are added.</span></span>

- <span data-ttu-id="af0d9-148">*Registros de artículos:* en primer lugar, se agregan las dimensiones financieras del encabezado del diario, si existen.</span><span class="sxs-lookup"><span data-stu-id="af0d9-148">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="af0d9-149">Después, se agregan las dimensiones financieras del proyecto de orden de trabajo relacionado.</span><span class="sxs-lookup"><span data-stu-id="af0d9-149">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="af0d9-150">A continuación, se agregan las dimensiones financieras del sitio.</span><span class="sxs-lookup"><span data-stu-id="af0d9-150">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="af0d9-151">Finalmente, se agregan las dimensiones financieras del artículo.</span><span class="sxs-lookup"><span data-stu-id="af0d9-151">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="af0d9-152">Para los tres tipos de registro, se valida la combinación de dimensiones financieras y se dejan en blanco las combinaciones no válidas.</span><span class="sxs-lookup"><span data-stu-id="af0d9-152">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="af0d9-153">Esta es la configuración estándar con otras aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="af0d9-153">This is standard setup with other Finance and Operations apps.</span></span>

