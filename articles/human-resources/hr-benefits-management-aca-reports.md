---
title: Generar informes de la Ley de Cuidado de salud asequible en la Administración de prestaciones
description: Estos temas describen cómo la Administración de prestaciones ayuda a rastrear la información notificada en el Formulario 1095-B y el Formulario 1095-C para la orden del empresario de la Ley de Cuidado de salud asequible (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2e4b250f4a059719067a9e19bbf3ce4aecc9bb1f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114192"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="a609a-103">Genere informes de ACA en la administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="a609a-103">Generate ACA reports in Benefits management</span></span>

<span data-ttu-id="a609a-104">La Administración de prestaciones ayuda a rastrear la información notificada en el Formulario 1095-B y el Formulario 1095-C para la orden del empresario de la Ley de Cuidado de salud asequible (ACA).</span><span class="sxs-lookup"><span data-stu-id="a609a-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="a609a-105">Al igual que la capacidad de los informes de ACA en el antiguo espacio de trabajo **Prestaciones**, esta funcionalidad solo se aplica a las entidades jurídicas de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a609a-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="a609a-106">Para usar esta funcionalidad, primero debe activar la **Administración avanzada de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="a609a-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="a609a-107">Para obtener más información, incluidas advertencias importantes sobre la Administración de prestaciones, consulte [Habilitar o deshabilitar la Administración de prestaciones](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="a609a-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a609a-108">Solo puede utilizar los informes de ACA desde el espacio de trabajo **Administración de prestaciones** o el antiguo espacio de trabajo **Prestaciones**, pero no desde ambos.</span><span class="sxs-lookup"><span data-stu-id="a609a-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="a609a-109">Por ejemplo, si cambió a Administración de prestaciones, los informes de ACA solo estarán disponibles en el espacio de trabajo **Administración de prestaciones**, no en el antiguo espacio de trabajo **Prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="a609a-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="a609a-110">Si cambia a Administración de prestaciones en la mitad de un año de inscripción, debe configurar correctamente los datos de los empleados para todo el año en Administración de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="a609a-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="a609a-111">De esta manera, se asegurará de recibir informes precisos durante todo el año.</span><span class="sxs-lookup"><span data-stu-id="a609a-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="a609a-112">Introducción</span><span class="sxs-lookup"><span data-stu-id="a609a-112">Getting started</span></span>

<span data-ttu-id="a609a-113">Para rastrear la información de los formularios 1095, primero hay que crear uno o más grupos de cobertura de Cuidado de salud asequible.</span><span class="sxs-lookup"><span data-stu-id="a609a-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="a609a-114">Estos grupos indican la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a609a-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="a609a-115">La oferta de cobertura que se le brindó a un empleado</span><span class="sxs-lookup"><span data-stu-id="a609a-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="a609a-116">La parte del empleado de la prima mensual de menor coste, si el coste es superior al umbral de pobreza federal</span><span class="sxs-lookup"><span data-stu-id="a609a-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="a609a-117">El puerto seguro que utiliza el empresario, si corresponde</span><span class="sxs-lookup"><span data-stu-id="a609a-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="a609a-118">Los grupos de cobertura de Cuidado de salud asequible le ayudan a administrar esta información para varios registros de empleados que tienen las mismas condiciones.</span><span class="sxs-lookup"><span data-stu-id="a609a-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="a609a-119">Puede asignar grupos fácilmente a uno o más empleados.</span><span class="sxs-lookup"><span data-stu-id="a609a-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="a609a-120">Crear o editar un grupo de cobertura de Cuidado de salud asequible</span><span class="sxs-lookup"><span data-stu-id="a609a-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="a609a-121">En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Seleccionar un grupo de cobertura de Cuidado de salud asequible](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="a609a-123">Seleccione **Nuevo** para crear un nuevo grupo de cobertura de Cuidado de salud asequible o **Editar** para cambiar un grupo existente.</span><span class="sxs-lookup"><span data-stu-id="a609a-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Seleccionar Nuevo o Editar](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="a609a-125">Establezca los campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a609a-125">Set the following fields.</span></span>

    | <span data-ttu-id="a609a-126">Campo</span><span class="sxs-lookup"><span data-stu-id="a609a-126">Field</span></span> | <span data-ttu-id="a609a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="a609a-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="a609a-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="a609a-128">Name</span></span> | <span data-ttu-id="a609a-129">Escriba un nombre para el grupo.</span><span class="sxs-lookup"><span data-stu-id="a609a-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="a609a-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="a609a-130">Description</span></span> | <span data-ttu-id="a609a-131">Escriba una descripción del grupo.</span><span class="sxs-lookup"><span data-stu-id="a609a-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="a609a-132">Oferta de cobertura</span><span class="sxs-lookup"><span data-stu-id="a609a-132">Offer of coverage</span></span> | <span data-ttu-id="a609a-133">La cobertura que se ofrece a los empleados, su cónyuge o pareja, y sus dependientes.</span><span class="sxs-lookup"><span data-stu-id="a609a-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="a609a-134">Parte de coste del empleado</span><span class="sxs-lookup"><span data-stu-id="a609a-134">Employee share of cost</span></span> | <span data-ttu-id="a609a-135">El importe del que el empleado es responsable.</span><span class="sxs-lookup"><span data-stu-id="a609a-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="a609a-136">Safe Harbor de la sección 4980H aplicable</span><span class="sxs-lookup"><span data-stu-id="a609a-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="a609a-137">El código 4980H de puerto seguro o ayuda para transición.</span><span class="sxs-lookup"><span data-stu-id="a609a-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="a609a-138">Mes de inicio del plan</span><span class="sxs-lookup"><span data-stu-id="a609a-138">Plan start month</span></span> | <span data-ttu-id="a609a-139">Seleccione el mes del calendario en el que comienza el año de su plan de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="a609a-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="a609a-140">Grupo válido desde</span><span class="sxs-lookup"><span data-stu-id="a609a-140">Group valid from</span></span> | <span data-ttu-id="a609a-141">La primera fecha en la que este registro es válido.</span><span class="sxs-lookup"><span data-stu-id="a609a-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="a609a-142">Grupo válido hasta</span><span class="sxs-lookup"><span data-stu-id="a609a-142">Group valid through</span></span> | <span data-ttu-id="a609a-143">La última fecha en la que este registro es válido.</span><span class="sxs-lookup"><span data-stu-id="a609a-143">The last date when this record is valid.</span></span> <span data-ttu-id="a609a-144">Si no hay fecha de vencimiento, introduzca **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="a609a-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Crear un grupo de cobertura](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="a609a-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="a609a-147">Asignar varios empleados a un grupo de cobertura de Cuidado de salud asequible</span><span class="sxs-lookup"><span data-stu-id="a609a-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="a609a-148">En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="a609a-149">Seleccione el grupo al que desea asignar empleados.</span><span class="sxs-lookup"><span data-stu-id="a609a-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="a609a-150">Seleccione **Asignación masiva**.</span><span class="sxs-lookup"><span data-stu-id="a609a-150">Select **Mass assignment**.</span></span>

    ![Seleccionar asignación masiva](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="a609a-152">Seleccione empleados de la lista y, a continuación, seleccione **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Asignar empleados seleccionados a un grupo](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="a609a-154">Mantener varias versiones de opciones de cobertura</span><span class="sxs-lookup"><span data-stu-id="a609a-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="a609a-155">Puede mantener varias versiones de cualquier grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="a609a-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="a609a-156">Cuando algo cambia en su organización o las prestaciones que se ofrecen, puede mantener actualizada la información del grupo sin tener que crear un grupo nuevo y reasignar empleados a dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="a609a-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="a609a-157">Una vez que haya creado grupos de cobertura de Cuidado de salud asequible, puede realizar una asignación masiva de empleados a estos grupos.</span><span class="sxs-lookup"><span data-stu-id="a609a-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="a609a-158">También puede asignar empleados individualmente a grupos e indicar si se realiza un seguimiento y notificación de la información de ACA.</span><span class="sxs-lookup"><span data-stu-id="a609a-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="a609a-159">Si no tiene que hacer un seguimiento y notificación de la información de ACA para un empleado, puede establecer la opción **Notificar cobertura** en **No**.</span><span class="sxs-lookup"><span data-stu-id="a609a-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="a609a-160">Por ejemplo, es posible que tenga empleados a tiempo parcial que no requieren informes de ACA.</span><span class="sxs-lookup"><span data-stu-id="a609a-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="a609a-161">Reemplazar los valores predeterminados para un empleado</span><span class="sxs-lookup"><span data-stu-id="a609a-161">Override default values for an employee</span></span>

<span data-ttu-id="a609a-162">Para los empleados que están asignados a un grupo de cobertura de Cuidado de salud asequible, puede cambiar las siguientes opciones para cualquier mes que requiera valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="a609a-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="a609a-163">Oferta de cobertura</span><span class="sxs-lookup"><span data-stu-id="a609a-163">Offer of coverage</span></span>
- <span data-ttu-id="a609a-164">Parte de coste del empleado</span><span class="sxs-lookup"><span data-stu-id="a609a-164">Employee share of cost</span></span>
- <span data-ttu-id="a609a-165">Safe Harbor de la sección 4980H aplicable</span><span class="sxs-lookup"><span data-stu-id="a609a-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="a609a-166">Para los informes de ACA de 2020, debe notificar los códigos postales del trabajo y del hogar en el Formulario 1095-C.</span><span class="sxs-lookup"><span data-stu-id="a609a-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="a609a-167">Los valores se rellenan automáticamente a partir de las ubicaciones activas actuales.</span><span class="sxs-lookup"><span data-stu-id="a609a-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="a609a-168">Si alguna de las ubicaciones varió en algún momento del año, debe reemplazar el valor.</span><span class="sxs-lookup"><span data-stu-id="a609a-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="a609a-169">El campo **Código postal** (línea 17) del informe 1095-C solo debe rellenarse si el código **Oferta de cobertura** contiene **1L** a **1Q**, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a609a-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="a609a-170">**1L, 1M o 1N:** el código postal de la residencia principal</span><span class="sxs-lookup"><span data-stu-id="a609a-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="a609a-171">**1O, 1P, 1Q:** el código postal principal del trabajo</span><span class="sxs-lookup"><span data-stu-id="a609a-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="a609a-172">Para introducir excepciones para cualquier valor de un grupo de Cuidado de salud asequible, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a609a-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="a609a-173">En el espacio de trabajo **Administración de personal**, seleccione **Vínculos** y, a continuación, seleccione **Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="a609a-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="a609a-174">Seleccione el empleado en la lista.</span><span class="sxs-lookup"><span data-stu-id="a609a-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="a609a-175">En la pestaña **Empleo**, en la sección **Más información**, seleccione **Cobertura de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Cambiar las opciones de un empleado](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="a609a-177">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-177">Select **Edit**.</span></span>
5. <span data-ttu-id="a609a-178">Para cada mes que requiera cambios, active la casilla **Sobrescribir la configuración predeterminada** y cambie los otros valores según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a609a-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Reemplazar los valores predeterminados](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="a609a-180">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="a609a-181">Notificar cobertura de atención sanitaria</span><span class="sxs-lookup"><span data-stu-id="a609a-181">Report health care coverage</span></span>

<span data-ttu-id="a609a-182">Debe realizar un seguimiento de cualquier cobertura de atención sanitaria autoasegurada y patrocinada por el empresario para los empleados de tiempo completo y parcial.</span><span class="sxs-lookup"><span data-stu-id="a609a-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="a609a-183">Incluya a cada empleado, junto con sus dependientes, en el informe 1095-C para los meses en que estaban cubiertos.</span><span class="sxs-lookup"><span data-stu-id="a609a-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="a609a-184">Para indicar si se debe informar un plan de prestaciones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a609a-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="a609a-185">En el espacio de trabajo **Administración de prestaciones**, seleccione **Planes de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="a609a-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="a609a-186">Seleccione el plan de beneficios del que va a informar.</span><span class="sxs-lookup"><span data-stu-id="a609a-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="a609a-187">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-187">Select **Edit**.</span></span>
4. <span data-ttu-id="a609a-188">Establezca la opción **Se informa por la Ley de Reportado Cuidado de salud asequible** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a609a-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Notificar cobertura de cuidad cuidado de salud](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="a609a-190">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-190">Select **Save**.</span></span>

<span data-ttu-id="a609a-191">Si un empleado elige cobertura de atención médica para un dependiente, el período de cobertura del dependiente se determina por la fecha de inscripción o eliminación.</span><span class="sxs-lookup"><span data-stu-id="a609a-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="a609a-192">Las fechas de cobertura para dependientes se calculan automáticamente según el período en el que el dependiente fue apto y estuvo activo en un plan durante el año de inscripción.</span><span class="sxs-lookup"><span data-stu-id="a609a-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="a609a-193">Generar los formularios 1095-B y 1095-C</span><span class="sxs-lookup"><span data-stu-id="a609a-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="a609a-194">Puede generar los formularios 1095-B y 1095-C de ACA y distribuirlos a cada uno de sus empleados.</span><span class="sxs-lookup"><span data-stu-id="a609a-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="a609a-195">También puede generar electrónicamente el Formulario 1095-C y los archivos de transmisión 1094-C correspondientes para enviarlos a la agencia tributaria.</span><span class="sxs-lookup"><span data-stu-id="a609a-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="a609a-196">En el espacio de trabajo **Administración de prestaciones**, seleccione **Formulario 1095-B de ACA** o **Formulario 1095-C de ACA**.</span><span class="sxs-lookup"><span data-stu-id="a609a-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="a609a-197">Cambie los parámetros según sea necesario y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a609a-198">Si imprime formularios 1095-C para más de 500 empleados, recibirá más de un archivo PDF.</span><span class="sxs-lookup"><span data-stu-id="a609a-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="a609a-199">Le recomendamos que aumente el valor del campo **Tamaño máximo de archivo en megabytes** en la página **Parámetros de la administración de documentos** a **150**.</span><span class="sxs-lookup"><span data-stu-id="a609a-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="a609a-200">(Para abrir rápidamente esa página, puede usar el campo de búsqueda en la barra de navegación).</span><span class="sxs-lookup"><span data-stu-id="a609a-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Cambiar el tamaño máximo de archivo](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="a609a-202">Para comprobar el estado de los informes y verlos, utilice el campo de búsqueda en la barra de navegación para abrir la página **Trabajos de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a609a-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Búsqueda de la página de trabajos de informes electrónicos](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="a609a-204">Seleccione el informe que desea ver y, a continuación, seleccione **Mostrar archivos**.</span><span class="sxs-lookup"><span data-stu-id="a609a-204">Select the report to view, and then select **Show files**.</span></span>

    ![Mostrar archivos](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="a609a-206">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a609a-206">Select **Open**.</span></span>

    ![Abrir un archivo](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="a609a-208">En la barra de notificaciones que aparece en la parte inferior de la ventana del explorador, abra el archivo zip y seleccione el informe.</span><span class="sxs-lookup"><span data-stu-id="a609a-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="a609a-209">Puede ver o imprimir el archivo PDF.</span><span class="sxs-lookup"><span data-stu-id="a609a-209">You can view or print the PDF file.</span></span>

    ![Formulario 1095-C de ejemplo](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="a609a-211">Ver información de cobertura de ACA</span><span class="sxs-lookup"><span data-stu-id="a609a-211">View ACA coverage information</span></span>

<span data-ttu-id="a609a-212">La página **Cobertura de cuidado de salud asequible del trabajador** muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a609a-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="a609a-213">Empleados asignados a cada grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="a609a-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="a609a-214">Empleados que no se tienen que incluir en un informe</span><span class="sxs-lookup"><span data-stu-id="a609a-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="a609a-215">Empleados no asignados</span><span class="sxs-lookup"><span data-stu-id="a609a-215">Unassigned employees</span></span>

<span data-ttu-id="a609a-216">Para ver esta información, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a609a-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="a609a-217">En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de cobertura de cuidado de salud asequible del trabajador**.</span><span class="sxs-lookup"><span data-stu-id="a609a-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="a609a-218">En el campo **Nombre del grupo**, seleccione un grupo.</span><span class="sxs-lookup"><span data-stu-id="a609a-218">In the **Group name** field, select a group.</span></span>

    ![Ver la cobertura de ACA](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="a609a-220">Si alguno de los valores predeterminados del grupo de cobertura de Cuidado de salud asequible se han anulado, aparecerá un asterisco junto al valor que se cambió.</span><span class="sxs-lookup"><span data-stu-id="a609a-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="a609a-221">Si los valores para los 12 meses son iguales y no se han reemplazado, el valor se imprimirá en la columna **Todos los 12 meses**.</span><span class="sxs-lookup"><span data-stu-id="a609a-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="a609a-222">Puede ver a los empleados que están marcados como empleados de los que no hay que informar según la ACA y que no requieren un Formulario 1095-C.</span><span class="sxs-lookup"><span data-stu-id="a609a-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="a609a-223">En el campo **Filtrar por**, seleccione **No se informa para Ley de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="a609a-224">Puede ver los empleados que no están asignados a un grupo o que están asignados a un grupo caducado.</span><span class="sxs-lookup"><span data-stu-id="a609a-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="a609a-225">En el campo **Filtrar por**, seleccione **Grupo sin asignar o caducado**.</span><span class="sxs-lookup"><span data-stu-id="a609a-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="a609a-226">Exportar a Excel</span><span class="sxs-lookup"><span data-stu-id="a609a-226">Export to Excel</span></span>

<span data-ttu-id="a609a-227">Para exportar cualquiera de las listas a Microsoft Excel, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a609a-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="a609a-228">Seleccione el botón **Abrir en Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="a609a-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="a609a-229">Seleccione **Tabla temporal de Human Resources de HCM para uso interno**.</span><span class="sxs-lookup"><span data-stu-id="a609a-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="a609a-230">Seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="a609a-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="a609a-231">Ver dependientes declarables según la ACA</span><span class="sxs-lookup"><span data-stu-id="a609a-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="a609a-232">Si tiene que informar sobre las personas cubiertas porque proporciona cobertura autoasegurada, puede ver los dependientes cubiertos por los planes de prestaciones marcados como **Se informa para Ley de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="a609a-233">En el panel de acciones, seleccione **Ver cobertura de dependientes**.</span><span class="sxs-lookup"><span data-stu-id="a609a-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Ver la cobertura de dependientes](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="a609a-235">Se muestra la información de cobertura para los dependientes del empleado.</span><span class="sxs-lookup"><span data-stu-id="a609a-235">Coverage information for the employee's dependents is shown.</span></span>

![Cobertura de dependientes](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="a609a-237">La página muestra solo los planes de prestaciones que están marcados como **Se informa para Ley de Cuidado de salud asequible**.</span><span class="sxs-lookup"><span data-stu-id="a609a-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>
