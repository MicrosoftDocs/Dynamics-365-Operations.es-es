---
title: Introducir aptitudes
description: Las obras y los gerentes pueden introducir aptitudes en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076614"
---
# <a name="enter-skills"></a><span data-ttu-id="d774e-103">Introducir aptitudes</span><span class="sxs-lookup"><span data-stu-id="d774e-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d774e-104">Puede especificar aptitudes objetivo o aptitudes reales para trabajadores, candidatos o contactos en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d774e-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d774e-105">Una aptitud objetivo es una aptitud una persona tiene previsto lograr.</span><span class="sxs-lookup"><span data-stu-id="d774e-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="d774e-106">Una aptitud real es una aptitud que una persona tiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="d774e-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="d774e-107">Cree un flujo de trabajo para aprobar automáticamente las aptitudes</span><span class="sxs-lookup"><span data-stu-id="d774e-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="d774e-108">Para introducir aptitudes sin requerir aprobación, debe crear un flujo de trabajo para aprobar automáticamente las aptitudes.</span><span class="sxs-lookup"><span data-stu-id="d774e-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="d774e-109">Las aptitudes ingresadas por los trabajadores siempre requieren la aprobación del gerente.</span><span class="sxs-lookup"><span data-stu-id="d774e-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="d774e-110">Este flujo de trabajo solo aprueba automáticamente las aptitudes introducidas por los gerentes en nombre de sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="d774e-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="d774e-111">En el espacio de trabajo **Administración de personal**, seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="d774e-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="d774e-112">En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="d774e-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="d774e-113">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d774e-113">Select **New**.</span></span>

4. <span data-ttu-id="d774e-114">En el panel **Crear flujo de trabajo**, seleccione **Aptitudes del trabajador**.</span><span class="sxs-lookup"><span data-stu-id="d774e-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="d774e-115">[![Seleccione el flujo de trabajo de aptitudes del trabajador](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="d774e-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="d774e-116">En el diálogo **¿Abrir este archivo?**, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d774e-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="d774e-117">Cuando se le solicite, introduzca sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="d774e-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="d774e-118">En el editor de flujo de trabajo, seleccione el elemento de flujo de trabajo **Aprobar aptitudes** y arrástrelo al lienzo.</span><span class="sxs-lookup"><span data-stu-id="d774e-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="d774e-119">[![Seleccione el elemento de flujo de trabajo Aprobar aptitudes](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="d774e-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="d774e-120">Conecte el elemento **Comienzo** al elemento **Aprobar aptitudes 1**, y luego conecte el elemento **Aprobar aptitudes 1** al elemento **Final**.</span><span class="sxs-lookup"><span data-stu-id="d774e-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="d774e-121">Es posible que deba desplazarse hacia abajo para ver el elemento **Final**.</span><span class="sxs-lookup"><span data-stu-id="d774e-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="d774e-122">Puede arrastrarlo más cerca de los otros elementos.</span><span class="sxs-lookup"><span data-stu-id="d774e-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="d774e-123">[![Conectar elementos del flujo de trabajo](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="d774e-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="d774e-124">Haga doble clic en el elemento de flujo de trabajo **Aprobar aptitudes 1** y, a continuación, haga clic con el botón derecho en el elemento **Paso 1**.</span><span class="sxs-lookup"><span data-stu-id="d774e-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="d774e-125">Haga clic con el botón secundario en el elemento **Paso 1** y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d774e-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="d774e-126">En la ventana **Propiedades**, seleccione **Condición** en la barra de navegación de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d774e-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="d774e-127">Seleccione **Ejecutar este paso únicamente si se cumplen las condiciones siguientes**.</span><span class="sxs-lookup"><span data-stu-id="d774e-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="d774e-128">Seleccione **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="d774e-128">Select **Add condition**.</span></span> <span data-ttu-id="d774e-129">Tras **Dónde**, seleccione **Aptitudes de autoservicio de los empleados** y luego seleccione **Aptitudes de autoservicio de los empleados.**.</span><span class="sxs-lookup"><span data-stu-id="d774e-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="d774e-130">Tras **es**, seleccione **campo** y luego seleccione **Relación de usuario a persona.**.</span><span class="sxs-lookup"><span data-stu-id="d774e-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="d774e-131">[![Especificar condición](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="d774e-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="d774e-132">Seleccione **Asignación** en la barra de navegación de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="d774e-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="d774e-133">En la pestaña **Tipo de asignación**, seleccione **Jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="d774e-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="d774e-134">En la pestaña **Selección de jerarquía**, en el campo **Tipo de jerarquía:**, seleccione **Jerarquía gerencial**.</span><span class="sxs-lookup"><span data-stu-id="d774e-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="d774e-135">[![Especificar jerarquía gerencial](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="d774e-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="d774e-136">Seleccione **Cerrar**, seleccione **Flujo de trabajo** en la ruta de navegación del lienzo y, a continuación, seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d774e-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="d774e-137">Para obtener más información sobre crear flujos de trabajo, consulte [Visión general del sistema de flujos de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d774e-137">For more information about creating workflows, see [Workflow system overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="d774e-138">Introducir aptitudes para un trabajador</span><span class="sxs-lookup"><span data-stu-id="d774e-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="d774e-139">Seleccione un trabajador.</span><span class="sxs-lookup"><span data-stu-id="d774e-139">Select a worker.</span></span>

2. <span data-ttu-id="d774e-140">En la barra de acciones de la página **Trabajador**, seleccione **Persona** y luego seleccione **Aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="d774e-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="d774e-141">En la página **Aptitudes**, complete los siguientes campos para cada aptitud:</span><span class="sxs-lookup"><span data-stu-id="d774e-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="d774e-142">**Aptitud**: seleccione una aptitud.</span><span class="sxs-lookup"><span data-stu-id="d774e-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="d774e-143">**Tipo de nivel**: seleccione **Actual** para una aptitud que el trabajador ya tiene, o seleccione **Objetivo** para una aptitud en la que el trabajador está trabajando.</span><span class="sxs-lookup"><span data-stu-id="d774e-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="d774e-144">**Nivel**: seleccione un nivel para la aptitud del trabajador.</span><span class="sxs-lookup"><span data-stu-id="d774e-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="d774e-145">**Fecha de nivel**: seleccione una fecha en la herramienta calendario.</span><span class="sxs-lookup"><span data-stu-id="d774e-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="d774e-146">**Examinador**: si corresponde, seleccione un examinador de la lista.</span><span class="sxs-lookup"><span data-stu-id="d774e-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="d774e-147">Puede filtrar su búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d774e-147">You can filter your search.</span></span>
   - <span data-ttu-id="d774e-148">**Años de experiencia**: introduzca los años de experiencia.</span><span class="sxs-lookup"><span data-stu-id="d774e-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="d774e-149">**Verificado**: si se verifica la habilidad, marque la casilla.</span><span class="sxs-lookup"><span data-stu-id="d774e-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="d774e-150">**Verificada por**: introduzca el nombre del verificador.</span><span class="sxs-lookup"><span data-stu-id="d774e-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="d774e-151">Cuando haya terminado de introducir habilidades, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d774e-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d774e-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d774e-152">See also</span></span>

[<span data-ttu-id="d774e-153">Configurar aptitudes</span><span class="sxs-lookup"><span data-stu-id="d774e-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="d774e-154">Asignar aptitudes</span><span class="sxs-lookup"><span data-stu-id="d774e-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]