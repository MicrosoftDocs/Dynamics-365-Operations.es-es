---
title: Entrada y navegación de empleados optimizadas
description: La entrada de datos de los trabajadores en Dynamics 365 Talent se ha ampliado para permitir la entrada rápida para todos los empleados, del pasado, activos o del futuro. El modelo de navegación simplificado/consolidado se ha actualizado para buscar más rápidamente la información relacionada y ver y crear las actualizaciones necesarias.
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
ms.openlocfilehash: b73b420c2eb75077814fbfeb6cd17404c7efc11e
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2020
ms.locfileid: "4462532"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="1ef05-104">Entrada y navegación de empleados optimizadas</span><span class="sxs-lookup"><span data-stu-id="1ef05-104">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="1ef05-105">Dynamics 365 Talent permite la especificación eficaz de datos del empleado y del empleo.</span><span class="sxs-lookup"><span data-stu-id="1ef05-105">Dynamics 365 Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="1ef05-106">Puede actualizar rápidamente la información del historial de trabajo para empleados y contratistas del pasado, activos, y del futuro.</span><span class="sxs-lookup"><span data-stu-id="1ef05-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="1ef05-107">También puede permitir una experiencia simplificada de navegación para buscar rápidamente información relacionada y realizar los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="1ef05-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="1ef05-108">Esta funcionalidad ya está disponible en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="1ef05-108">This functionality is now available in all environments.</span></span> <span data-ttu-id="1ef05-109">Para activar esta característica, vaya a **Administración del sistema> Administración de características > Nuevo> Entrada de empleados optimizada > Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="1ef05-109">To turn this feature on, navigate to **System administration > Feature Management > New > Streamlined employee entry > Enable**.</span></span> <span data-ttu-id="1ef05-110">Esto habilitará estos cambios para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1ef05-110">This will enable these changes for all users.</span></span> <span data-ttu-id="1ef05-111">Puede desactivar esta opción en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="1ef05-111">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="1ef05-112">Opciones de vista</span><span class="sxs-lookup"><span data-stu-id="1ef05-112">View options</span></span>

<span data-ttu-id="1ef05-113">Puede usar **Opciones de la vista** en el formulario Trabajador para seleccionar cualquier combinación de empleados y de contratistas de una sola lista.</span><span class="sxs-lookup"><span data-stu-id="1ef05-113">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="1ef05-114">Estas opciones le permiten ver trabajadores de entidades jurídicas o de la entidad jurídica a la que está conectadod actualmente.</span><span class="sxs-lookup"><span data-stu-id="1ef05-114">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="1ef05-115">También puede ver los trabajadores activos, pendientes, y que yan salido, y puede limitar los resultados en función del tipo de trabajador (contratista o empleado.)</span><span class="sxs-lookup"><span data-stu-id="1ef05-115">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="1ef05-116">Si está habilitada la seguridad avanzada, sólo verá estos empleados y contratistas en las entidades jurídicas a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="1ef05-116">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="1ef05-117">Las columnas de la vista de lista cambian en función de sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="1ef05-117">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="1ef05-118">Por ejemplo, al visualizar los empleados que han salido, la fecha final y los códigos de motivo muestran como columnas adicionales en la lista.</span><span class="sxs-lookup"><span data-stu-id="1ef05-118">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="1ef05-119">[![Opciones de vista](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="1ef05-119">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="1ef05-120">Navegación y banner</span><span class="sxs-lookup"><span data-stu-id="1ef05-120">Navigation and banner</span></span>

<span data-ttu-id="1ef05-121">Un banner muestra información clave para cada trabajador.</span><span class="sxs-lookup"><span data-stu-id="1ef05-121">A banner displays key information for each worker.</span></span> <span data-ttu-id="1ef05-122">El banner para trabajadores activos muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="1ef05-122">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="1ef05-123">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="1ef05-123">**Title**</span></span>
- <span data-ttu-id="1ef05-124">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="1ef05-124">**Department**</span></span>
- <span data-ttu-id="1ef05-125">**Tipo de puesto**</span><span class="sxs-lookup"><span data-stu-id="1ef05-125">**Position type**</span></span>
- <span data-ttu-id="1ef05-126">**Tipo de trabajador**</span><span class="sxs-lookup"><span data-stu-id="1ef05-126">**Worker type**</span></span>
- <span data-ttu-id="1ef05-127">**Encargado**</span><span class="sxs-lookup"><span data-stu-id="1ef05-127">**Manager**</span></span>
- <span data-ttu-id="1ef05-128">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="1ef05-128">**Legal entity**</span></span>

<span data-ttu-id="1ef05-129">El banner para trabajadores que han salido muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="1ef05-129">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="1ef05-130">**Fecha de salida**</span><span class="sxs-lookup"><span data-stu-id="1ef05-130">**Exited date**</span></span>
- <span data-ttu-id="1ef05-131">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="1ef05-131">**Reason**</span></span>

<span data-ttu-id="1ef05-132">El banner para trabajadores pendientes muestra los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="1ef05-132">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="1ef05-133">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="1ef05-133">**Title**</span></span>
- <span data-ttu-id="1ef05-134">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="1ef05-134">**Department**</span></span>
- <span data-ttu-id="1ef05-135">**Tipo de puesto**</span><span class="sxs-lookup"><span data-stu-id="1ef05-135">**Position type**</span></span>
- <span data-ttu-id="1ef05-136">**Encargado**</span><span class="sxs-lookup"><span data-stu-id="1ef05-136">**Manager**</span></span>
- <span data-ttu-id="1ef05-137">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="1ef05-137">**Starting date**</span></span>
- <span data-ttu-id="1ef05-138">**Entidad jurídica**</span><span class="sxs-lookup"><span data-stu-id="1ef05-138">**Legal entity**</span></span>

<span data-ttu-id="1ef05-139">El panel de acciones de la página del trabajador se ha reorganizado para incluir menos opciones.</span><span class="sxs-lookup"><span data-stu-id="1ef05-139">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="1ef05-140">La información ahora se organiza en las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ef05-140">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="1ef05-141">Trabajo</span><span class="sxs-lookup"><span data-stu-id="1ef05-141">Work</span></span>
- <span data-ttu-id="1ef05-142">Persona</span><span class="sxs-lookup"><span data-stu-id="1ef05-142">Person</span></span>
- <span data-ttu-id="1ef05-143">Salir</span><span class="sxs-lookup"><span data-stu-id="1ef05-143">Leave</span></span>
- <span data-ttu-id="1ef05-144">Compensación</span><span class="sxs-lookup"><span data-stu-id="1ef05-144">Compensation</span></span>
- <span data-ttu-id="1ef05-145">Beneficios</span><span class="sxs-lookup"><span data-stu-id="1ef05-145">Benefits</span></span>
- <span data-ttu-id="1ef05-146">Conformidad</span><span class="sxs-lookup"><span data-stu-id="1ef05-146">Compliance</span></span>

<span data-ttu-id="1ef05-147">Además, una nueva pestaña **Vínculos** en la página principal del trabajador da a los usuarios una ubicación central para tener acceso a toda la información relacionada para un trabajador.</span><span class="sxs-lookup"><span data-stu-id="1ef05-147">In addition, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="1ef05-148">Debido a estos cambios, puede mostrarse información en una ubicación diferente a la que está acostumbrado.</span><span class="sxs-lookup"><span data-stu-id="1ef05-148">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="1ef05-149">Por ejemplo, información de nómina que antes se mostraba en el formulario Trabajador ahora aparece en el panel de acciones en **Compensación > nómina**, y la pestaña **Información personal** ahora tiene un botón **Más información** para ocultar los campos a los que no se accede a menudo.</span><span class="sxs-lookup"><span data-stu-id="1ef05-149">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="1ef05-150">[![Pancarta](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="1ef05-150">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="1ef05-151">Historial laboral</span><span class="sxs-lookup"><span data-stu-id="1ef05-151">Work history</span></span>

<span data-ttu-id="1ef05-152">La pestaña **Historial de trabajo** muestra el historial de trabajo en todas las entidades jurídicas y está disponible para trabajadores y contratistas que han salido, están activos, o pendientes.</span><span class="sxs-lookup"><span data-stu-id="1ef05-152">The **Work history** tab shows work history across all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="1ef05-153">Ahora puede ver todo el historial de trabajo a la vez para las entidades jurídicas a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="1ef05-153">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="1ef05-154">Además, puede editar información para cada una de las entradas del historial de trabajo sin cambiar el contexto de los datos.</span><span class="sxs-lookup"><span data-stu-id="1ef05-154">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="1ef05-155">Puede actualizar toda la información directamente en la página.</span><span class="sxs-lookup"><span data-stu-id="1ef05-155">You can update all information directly on the page.</span></span> 

<span data-ttu-id="1ef05-156">[![Historial laboral](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="1ef05-156">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="1ef05-157">Historial de puestos</span><span class="sxs-lookup"><span data-stu-id="1ef05-157">Position history</span></span>

<span data-ttu-id="1ef05-158">La pestaña **Puestos** en la página principal del trabajador proporciona una vista de todas las posiciones que se han tenido dentro de la organización, incluidas las asignaciones pasadas, presentes cualquier futura asignación.</span><span class="sxs-lookup"><span data-stu-id="1ef05-158">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="1ef05-159">También seguirá pudiendo acceder directamente al historial de puestos del trabajador en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="1ef05-159">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="1ef05-160">[![Puestos](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="1ef05-160">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>

