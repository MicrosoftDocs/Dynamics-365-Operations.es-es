---
title: Restringir la edición de información personal
description: Restrinja a los empleados para que no editen los detalles de los contactos en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d4785232dbb21c5f8a800497fb0cfd3c64dea2d8
ms.sourcegitcommit: 45d10d0c25b3ec585323709bb97ba1895b500429
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "5503045"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="aad1b-103">Restringir la edición de información personal</span><span class="sxs-lookup"><span data-stu-id="aad1b-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="aad1b-104">Este tema describe cómo restringir que los empleados editen los detalles de contacto en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aad1b-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="aad1b-105">Es posible que desee evitar que los empleados editen ciertos detalles de contacto, como la ubicación de su empresa o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="aad1b-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="aad1b-106">Para utilizar esta función, primero debe habilitar **(Vista previa) Impedir que los empleados agreguen o editen la dirección y la información de contacto para fines seleccionados** en Gestión de funciones.</span><span class="sxs-lookup"><span data-stu-id="aad1b-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="aad1b-107">Para obtener más información sobre la habilitación de características en vista previa, consulte [Administrar características](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="aad1b-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="aad1b-108">![Habilitar característica de vista previa](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="aad1b-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="aad1b-109">Elija la información que un empleado puede agregar o editar</span><span class="sxs-lookup"><span data-stu-id="aad1b-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="aad1b-110">En Human Resources, seleccione **Gestión de personal**, seleccione **Vínculos** y luego seleccione **Parámetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="aad1b-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Ir a Parámetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="aad1b-112">Sobre la página **Parámetros de recursos humanos**, seleccione la pestaña **Autoservicio para los empleados**.</span><span class="sxs-lookup"><span data-stu-id="aad1b-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Seleccione Autoservicio para empleados](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="aad1b-114">Sobre la pestaña **Autoservicio para los empleados**, desmarque toda la información en la sección **Dirección e información de contacto** que no desea que los empleados agreguen o editen.</span><span class="sxs-lookup"><span data-stu-id="aad1b-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="aad1b-115">En este ejemplo, hemos desmarcado la información de contacto de **Negocio**.</span><span class="sxs-lookup"><span data-stu-id="aad1b-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Restringir la edición de la información de contacto comercial](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="aad1b-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aad1b-117">Select **Save**.</span></span>

   ![Guardar cambios](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="aad1b-119">Experiencia del empleado</span><span class="sxs-lookup"><span data-stu-id="aad1b-119">Employee experience</span></span>

<span data-ttu-id="aad1b-120">Una vez que haya restringido a los empleados para que no agreguen o editen detalles de contacto, pueden ver la información, pero no pueden cambiarla.</span><span class="sxs-lookup"><span data-stu-id="aad1b-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="aad1b-121">En este ejemplo, donde los empleados no pueden editar datos de contacto de **Negocio**, aún pueden ver la información en el autoservicio del empleado:</span><span class="sxs-lookup"><span data-stu-id="aad1b-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Ver detalles de contacto comercial](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="aad1b-123">Sin embargo, cuando seleccionan los datos de contacto de la empresa, el panel **Editar dirección** aparece como de solo lectura y no pueden cambiar ninguno de los campos.</span><span class="sxs-lookup"><span data-stu-id="aad1b-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Los datos de contacto de la empresa se muestran como de solo lectura](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="aad1b-125">Además, si seleccionan **Agregar** para agregar una nueva dirección, no pueden seleccionar **Negocio** desde el cuadro desplegable **Objetivo**.</span><span class="sxs-lookup"><span data-stu-id="aad1b-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![El empleado no puede agregar una dirección comercial](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="aad1b-127">Los empleados obtienen la misma experiencia cuando seleccionan **Detalles de contacto** en la página **Informacion personal** y agregan una nueva dirección.</span><span class="sxs-lookup"><span data-stu-id="aad1b-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="aad1b-128">El cuadro desplegable **Objetivo** solo muestra los tipos de información que pueden agregar.</span><span class="sxs-lookup"><span data-stu-id="aad1b-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![El empleado no puede seleccionar Negocio en el menú desplegable Propósito](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="aad1b-130">**Detalles de contacto** ahora muestra **Objetivo** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="aad1b-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![El propósito se muestra en la cuadrícula de detalles de contacto](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="aad1b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aad1b-132">See also</span></span>

[<span data-ttu-id="aad1b-133">Visión general del autoservicio para empleado y director</span><span class="sxs-lookup"><span data-stu-id="aad1b-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="aad1b-134">Configurar parámetros de Human Resources</span><span class="sxs-lookup"><span data-stu-id="aad1b-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="aad1b-135">Editar información personal</span><span class="sxs-lookup"><span data-stu-id="aad1b-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)