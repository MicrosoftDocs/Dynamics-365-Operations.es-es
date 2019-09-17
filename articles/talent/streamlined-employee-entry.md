---
title: Entrada y navegación de empleados optimizadas
description: La entrada de datos de los trabajadores en Dynamics 365 for Talent se ha ampliado para permitir la entrada rápida para todos los empleados, del pasado, activos o del futuro. El modelo de navegación simplificado/consolidado se ha actualizado para buscar más rápidamente la información relacionada y ver y crear las actualizaciones necesarias.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: be0253ffc4396f36050ef02c51a20d378e44473d
ms.sourcegitcommit: 4176c333ce3f88c5c68e95bd47e5791d32365dd2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "1918221"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="bf337-104">Entrada y navegación de empleados optimizadas</span><span class="sxs-lookup"><span data-stu-id="bf337-104">Streamlined employee entry and navigation</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bf337-105">Dynamics 365 for Talent permite la especificación eficaz de datos del empleado y del empleo.</span><span class="sxs-lookup"><span data-stu-id="bf337-105">Dynamics 365 for Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="bf337-106">Puede actualizar rápidamente la información del historial de trabajo para empleados y contratistas del pasado, activos, y del futuro.</span><span class="sxs-lookup"><span data-stu-id="bf337-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="bf337-107">También puede permitir una experiencia simplificada de navegación para buscar rápidamente información relacionada y realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="bf337-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="bf337-108">Esta funcionalidad ya está disponible en los entornos de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="bf337-108">This functionality is now available in sandbox environments.</span></span> <span data-ttu-id="bf337-109">Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="bf337-109">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="bf337-110">Seleccione **Formulario y navegación de trabajador mejorado**.</span><span class="sxs-lookup"><span data-stu-id="bf337-110">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="bf337-111">Esto habilitará estos cambios para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bf337-111">This will enable these changes for all users.</span></span> <span data-ttu-id="bf337-112">Puede desactivar esta opción en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="bf337-112">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="bf337-113">Opciones de vista</span><span class="sxs-lookup"><span data-stu-id="bf337-113">View options</span></span>

<span data-ttu-id="bf337-114">Puede usar **Opciones de la vista** en el formulario Trabajador para seleccionar cualquier combinación de empleados y de contratistas de una sola lista.</span><span class="sxs-lookup"><span data-stu-id="bf337-114">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="bf337-115">Estas opciones le permiten ver trabajadores de entidades jurídicas o de la entidad jurídica a la que está conectadod actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf337-115">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="bf337-116">También puede ver los trabajadores activos, pendientes, y que yan salido, y puede limitar los resultados en función del tipo de trabajador (contratista o empleado.)</span><span class="sxs-lookup"><span data-stu-id="bf337-116">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="bf337-117">Si está habilitada la seguridad avanzada, sólo verá estos empleados y contratistas en las entidades jurídicas a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="bf337-117">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="bf337-118">Las columnas de la vista de lista cambian en función de sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="bf337-118">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="bf337-119">Por ejemplo, al visualizar los empleados que han salido, la fecha final y los códigos de motivo muestran como columnas adicionales en la lista.</span><span class="sxs-lookup"><span data-stu-id="bf337-119">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="bf337-120">[![Opciones de vista](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="bf337-120">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="bf337-121">Navegación y banner</span><span class="sxs-lookup"><span data-stu-id="bf337-121">Navigation and banner</span></span>

<span data-ttu-id="bf337-122">Un banner muestra información clave para cada trabajador.</span><span class="sxs-lookup"><span data-stu-id="bf337-122">A banner displays key information for each worker.</span></span> <span data-ttu-id="bf337-123">El banner para trabajadores activos muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="bf337-123">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="bf337-124">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="bf337-124">**Title**</span></span>
- <span data-ttu-id="bf337-125">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="bf337-125">**Department**</span></span>
- <span data-ttu-id="bf337-126">**Tipo de puesto**</span><span class="sxs-lookup"><span data-stu-id="bf337-126">**Position type**</span></span>
- <span data-ttu-id="bf337-127">**Tipo de trabajador**</span><span class="sxs-lookup"><span data-stu-id="bf337-127">**Worker type**</span></span>
- <span data-ttu-id="bf337-128">**Encargado**</span><span class="sxs-lookup"><span data-stu-id="bf337-128">**Manager**</span></span>
- <span data-ttu-id="bf337-129">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="bf337-129">**Legal entity**</span></span>

<span data-ttu-id="bf337-130">El banner para trabajadores que han salido muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="bf337-130">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="bf337-131">**Fecha de salida**</span><span class="sxs-lookup"><span data-stu-id="bf337-131">**Exited date**</span></span>
- <span data-ttu-id="bf337-132">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="bf337-132">**Reason**</span></span>

<span data-ttu-id="bf337-133">El banner para trabajadores pendientes muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="bf337-133">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="bf337-134">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="bf337-134">**Title**</span></span>
- <span data-ttu-id="bf337-135">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="bf337-135">**Department**</span></span>
- <span data-ttu-id="bf337-136">**Tipo de puesto**</span><span class="sxs-lookup"><span data-stu-id="bf337-136">**Position type**</span></span>
- <span data-ttu-id="bf337-137">**Encargado**</span><span class="sxs-lookup"><span data-stu-id="bf337-137">**Manager**</span></span>
- <span data-ttu-id="bf337-138">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="bf337-138">**Starting date**</span></span>
- <span data-ttu-id="bf337-139">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="bf337-139">**Legal entity**</span></span>

<span data-ttu-id="bf337-140">El panel de acciones de la página del trabajador se ha reorganizado para incluir menos opciones.</span><span class="sxs-lookup"><span data-stu-id="bf337-140">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="bf337-141">La información ahora se organiza en las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf337-141">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="bf337-142">Trabajo</span><span class="sxs-lookup"><span data-stu-id="bf337-142">Work</span></span>
- <span data-ttu-id="bf337-143">Persona</span><span class="sxs-lookup"><span data-stu-id="bf337-143">Person</span></span>
- <span data-ttu-id="bf337-144">Dejar</span><span class="sxs-lookup"><span data-stu-id="bf337-144">Leave</span></span>
- <span data-ttu-id="bf337-145">Compensación</span><span class="sxs-lookup"><span data-stu-id="bf337-145">Compensation</span></span>
- <span data-ttu-id="bf337-146">Prestaciones</span><span class="sxs-lookup"><span data-stu-id="bf337-146">Benefits</span></span>
- <span data-ttu-id="bf337-147">Conformidad</span><span class="sxs-lookup"><span data-stu-id="bf337-147">Compliance</span></span>

<span data-ttu-id="bf337-148">Además, una nueva pestaña **Vínculos** en la página principal del trabajador da a los usuarios una ubicación central para tener acceso a toda la información relacionada para un trabajador.</span><span class="sxs-lookup"><span data-stu-id="bf337-148">In addtion, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="bf337-149">Debido a estos cambios, puede mostrarse información en una ubicación diferente a la que está acostumbrado.</span><span class="sxs-lookup"><span data-stu-id="bf337-149">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="bf337-150">Por ejemplo, información de nómina que antes se mostraba en el formulario Trabajador ahora aparece en el panel de acciones en **Compensación > nómina**, y la pestaña **Información personal** ahora tiene un botón **Más información** para ocultar los campos a los que no se accede a menudo.</span><span class="sxs-lookup"><span data-stu-id="bf337-150">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="bf337-151">[![Pancarta](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="bf337-151">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="bf337-152">Historial laboral</span><span class="sxs-lookup"><span data-stu-id="bf337-152">Work history</span></span>

<span data-ttu-id="bf337-153">La pestaña **Historial de trabajo** muestra el historial de trabajo en todas las entidades jurídicas y está disponible para trabajadores y contratistas que han salido, están activos, o pendientes.</span><span class="sxs-lookup"><span data-stu-id="bf337-153">The **Work history** tab shows work history accross all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="bf337-154">Ahora puede ver todo el historial de trabajo a la vez para las entidades jurídicas a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="bf337-154">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="bf337-155">Además, puede editar información para cada una de las entradas del historial de trabajo sin cambiar el contexto de los datos.</span><span class="sxs-lookup"><span data-stu-id="bf337-155">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="bf337-156">Puede actualizar toda la información directamente en la página.</span><span class="sxs-lookup"><span data-stu-id="bf337-156">You can update all information directly on the page.</span></span> 

<span data-ttu-id="bf337-157">[![Historial laboral](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="bf337-157">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="bf337-158">Historial de puestos</span><span class="sxs-lookup"><span data-stu-id="bf337-158">Position history</span></span>

<span data-ttu-id="bf337-159">La pestaña **Puestos** en la página principal del trabajador proporciona una vista de todas las posiciones que se han tenido dentro de la organización, incluidas las asignaciones pasadas, presentes cualquier futura asignación.</span><span class="sxs-lookup"><span data-stu-id="bf337-159">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="bf337-160">También seguirá pudiendo acceder directamente al historial de puestos del trabajador en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="bf337-160">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="bf337-161">[![Puestos](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="bf337-161">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>

