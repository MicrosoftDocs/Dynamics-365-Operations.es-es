---
title: Crear contratos avanzados para facturación basada en progreso
description: Este tema explica cómo crear contratos de proyectos para que pueda generar facturas para los clientes, en función de un porcentaje del trabajo completado.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282847"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="9af62-103">Crear contratos avanzados para facturación basada en progreso</span><span class="sxs-lookup"><span data-stu-id="9af62-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="9af62-104">Este tema explica cómo crear contratos de proyectos para que pueda crear facturas para los clientes, en función de un porcentaje del trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="9af62-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="9af62-105">Los importes de factura de las categorías presupuestarias del trabajo que ha configurado para un proyecto se calculan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9af62-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="9af62-106">El tiempo de las facturas se configura al negociar el contrato de proyecto con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9af62-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="9af62-107">Use los procedimientos de este tema para configurar un contrato, un proyecto asociado y las reglas de facturación que calculan los importes de las facturas para las categorías presupuestarias de trabajo configuradas para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="9af62-108">Una vez que haya creado el contrato y el proyecto, puede configurar los detalles del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="9af62-109">Por ejemplo, puede definir las actividades y asignar trabajadores al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="9af62-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9af62-110">Example</span></span>

<span data-ttu-id="9af62-111">Su organización es una empresa de desarrollo de software.</span><span class="sxs-lookup"><span data-stu-id="9af62-111">Your organization is a software development firm.</span></span> <span data-ttu-id="9af62-112">Acuerda desarrollar un paquete de contabilidad de nóminas para un cliente por una cuota total de 20 000 USD.</span><span class="sxs-lookup"><span data-stu-id="9af62-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="9af62-113">Su organización acepta facturar al cliente a medida que se completan los porcentajes de trabajo específicos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="9af62-114">Configura las siguientes categorías de proyectos para el trabajo, de modo que pueda usarlas en el proceso de facturación:</span><span class="sxs-lookup"><span data-stu-id="9af62-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="9af62-115">Asesoría</span><span class="sxs-lookup"><span data-stu-id="9af62-115">Consulting</span></span>
- <span data-ttu-id="9af62-116">Diseño</span><span class="sxs-lookup"><span data-stu-id="9af62-116">Design</span></span>
- <span data-ttu-id="9af62-117">Instalación</span><span class="sxs-lookup"><span data-stu-id="9af62-117">Installation</span></span>

<span data-ttu-id="9af62-118">También configura reglas de facturación que calculan automáticamente los importes de las facturas por el porcentaje de trabajo del proyecto completado en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="9af62-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="9af62-119">El administrador de presupuestos crea un presupuesto para las categorías de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="9af62-120">El importe de trabajo completado se calcula automáticamente como un porcentaje de trabajo real en comparación con los importes presupuestados.</span><span class="sxs-lookup"><span data-stu-id="9af62-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9af62-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9af62-121">Prerequisites</span></span>

<span data-ttu-id="9af62-122">Antes de crear un proyecto que use reglas de facturación, debe configurar las secuencias numéricas para las reglas de facturación y un diario de tarifas que se utiliza para publicar facturas de progreso.</span><span class="sxs-lookup"><span data-stu-id="9af62-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="9af62-123">Vaya a **Administración de proyectos y contabilidad** \> **Configuración** \> **Parámetros de administración de proyectos y contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="9af62-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="9af62-124">En la página **Gestión de proyectos y parámetros contables**, en la pestaña **Secuencias numéricas**, configure la secuencia numérica que desea usar cuando se crean las reglas de facturación.</span><span class="sxs-lookup"><span data-stu-id="9af62-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="9af62-125">Vaya a **Integración en la contabilidad y gestión de proyectos** \> **Diarios** \> **Cuota**.</span><span class="sxs-lookup"><span data-stu-id="9af62-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="9af62-126">En la página **Diario de tarifas**, seleccione **Nuevo** e ingrese el nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="9af62-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="9af62-127">Crear un contrato para las facturaciones de progreso</span><span class="sxs-lookup"><span data-stu-id="9af62-127">Create a contract for progress billings</span></span>

<span data-ttu-id="9af62-128">Use este procedimiento para crear un contrato de proyecto para un proyecto de precio fijo.</span><span class="sxs-lookup"><span data-stu-id="9af62-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="9af62-129">Cree una factura de proyecto cuando el trabajo que se ha completado del proyecto alcance un porcentaje especificado.</span><span class="sxs-lookup"><span data-stu-id="9af62-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="9af62-130">Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Contratos de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9af62-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="9af62-131">En la página **Contratos de proyecto**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9af62-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="9af62-132">En el cuadro de diálogo **Nuevo contrato de proyecto**, establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9af62-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="9af62-133">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9af62-133">**Name**</span></span>
    - <span data-ttu-id="9af62-134">**Tipo de financiación**</span><span class="sxs-lookup"><span data-stu-id="9af62-134">**Funding type**</span></span>
    - <span data-ttu-id="9af62-135">**Fuente de financiación**</span><span class="sxs-lookup"><span data-stu-id="9af62-135">**Funding source**</span></span>
    - <span data-ttu-id="9af62-136">**Divisa de ventas**: de forma predeterminada, esta divisa se utiliza para las facturas de cliente asociadas al contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="9af62-137">Sin embargo, puede cambiar la divisa de ventas en una factura de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="9af62-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="9af62-138">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9af62-138">Select **OK**.</span></span> <span data-ttu-id="9af62-139">La información se copia en el encabezado de la página **Contratos de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="9af62-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="9af62-140">En la página **Contratos de proyectos**, complete el resto de la información requerida para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="9af62-141">Crear un proyecto para las facturaciones de progreso</span><span class="sxs-lookup"><span data-stu-id="9af62-141">Create a project for progress billings</span></span>

<span data-ttu-id="9af62-142">Siga estos pasos para crear un proyecto y todos los subproyectos asociados a un contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="9af62-143">Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="9af62-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="9af62-144">En la página **Todos los proyectos**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9af62-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="9af62-145">En el cuadro de diálogo **Nuevo proyecto**, en el campo **Tipo de proyecto**, seleccione **Tiempo y material**.</span><span class="sxs-lookup"><span data-stu-id="9af62-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="9af62-146">Seleccionar un grupo de proyectos.</span><span class="sxs-lookup"><span data-stu-id="9af62-146">Select a project group.</span></span> <span data-ttu-id="9af62-147">Un grupo de proyectos define la información de registro de los proyectos que se asignan al grupo.</span><span class="sxs-lookup"><span data-stu-id="9af62-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="9af62-148">Seleccione **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9af62-148">Select **Create project**.</span></span>
6. <span data-ttu-id="9af62-149">Después de crear el proyecto, defina la etapa del proyecto como **En proceso**.</span><span class="sxs-lookup"><span data-stu-id="9af62-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="9af62-150">Crear un presupuesto para un proyecto</span><span class="sxs-lookup"><span data-stu-id="9af62-150">Create a budget for a project</span></span>

<span data-ttu-id="9af62-151">Las categorías presupuestarias se usan para calcular automáticamente los importes de factura por el porcentaje de trabajo completado en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="9af62-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="9af62-152">Siga estos pasos para crear categorías de presupuesto para los costos estimados.</span><span class="sxs-lookup"><span data-stu-id="9af62-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="9af62-153">Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="9af62-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="9af62-154">En la página **Todos los proyectos**, seleccione y abra el proyecto que desee.</span><span class="sxs-lookup"><span data-stu-id="9af62-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="9af62-155">En la página **Proyectos**, en el Panel de acciones, en la pestaña **Plan**, en el grupo **Presupuesto**, seleccione **Presupuesto del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9af62-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="9af62-156">En la página **Presupuesto del proyecto**, especifique el coste estimado para cada categoría del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="9af62-157">Creación de reglas de facturación para las facturaciones de progreso</span><span class="sxs-lookup"><span data-stu-id="9af62-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="9af62-158">Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Contratos de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9af62-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="9af62-159">En la página **Contratos de proyectos**, seleccione y abra un contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="9af62-160">En la página del contrato del proyecto, en la ficha desplegable **Reglas de facturación**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9af62-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="9af62-161">En la página **Regla de facturación**, en el campo **Tipo de línea**, seleccione **Progreso**.</span><span class="sxs-lookup"><span data-stu-id="9af62-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="9af62-162">En la ficha desplegable **Detalles de línea de regla de facturación**, en el campo **Valor contractual**, especifique el valor total del contrato.</span><span class="sxs-lookup"><span data-stu-id="9af62-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="9af62-163">En el campo **Categoría**, seleccione la categoría en la que se registrará la transacción de cuota.</span><span class="sxs-lookup"><span data-stu-id="9af62-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="9af62-164">En el campo **Proyecto**, seleccione el proyecto que usa la regla de facturación.</span><span class="sxs-lookup"><span data-stu-id="9af62-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="9af62-165">Opcional: asigne la regla de facturación a otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="9af62-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="9af62-166">En la ficha desplegable **Proyecto**, en la sección **Proyectos disponibles**, seleccione un proyecto y luego seleccione el botón de flecha derecha para agregar el proyecto a la sección **Proyectos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="9af62-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="9af62-167">Opcional: calcule el importe porcentual que el cliente retiene de pagos en una factura.</span><span class="sxs-lookup"><span data-stu-id="9af62-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="9af62-168">En la ficha desplegable **Condiciones de retención de pago**, seleccione la fuente de financiación y, a continuación, en el campo **Porcentaje de retención**, especifique el porcentaje de retención.</span><span class="sxs-lookup"><span data-stu-id="9af62-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="9af62-169">Repita estos pasos para crear reglas de facturación adicionales para el contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9af62-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
