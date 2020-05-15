---
title: Diagnósticos de seguridad para las grabaciones de tareas
description: Este tema proporciona información sobre cómo analizar y administrar los requisitos de permisos de seguridad basados en una grabación de tareas.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: fada3abb9362426c7c9ec33f5d25552edf3ef630
ms.sourcegitcommit: 71fec2553158c332ce4d4bfcedc2c1ab58c1a1a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340684"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="7ad19-103">Diagnósticos de seguridad para las grabaciones de tareas</span><span class="sxs-lookup"><span data-stu-id="7ad19-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="7ad19-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7ad19-104">Before you begin</span></span>

<span data-ttu-id="7ad19-105">Este tema proporciona información sobre cómo analizar y administrar los requisitos de permisos de seguridad basados en una grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="7ad19-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="7ad19-106">Antes de completar los pasos de este tema, debe tener una grabación de tareas del proceso de negocio que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="7ad19-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="7ad19-107">Para registrar un proceso comercial, consulte [Recursos de grabación de tareas](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="7ad19-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="7ad19-108">Administrar la seguridad para la grabación de tareas</span><span class="sxs-lookup"><span data-stu-id="7ad19-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="7ad19-109">Vaya a **Administracion del sistema** > **Seguridad** > **Diagnóstico de seguridad para grabación de tareas**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="7ad19-110">Abra la tarea de grabación desde su ubicación.</span><span class="sxs-lookup"><span data-stu-id="7ad19-110">Open the task recording from its location.</span></span> <span data-ttu-id="7ad19-111">Seleccione **Abrir desde este PC** o **Abierto desde Lifecycle Services** y luego seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="7ad19-112">Esto abrirá la página **Detalles del elemento del menú de seguridad** que enumera los objetos de seguridad necesarios para el proceso.</span><span class="sxs-lookup"><span data-stu-id="7ad19-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="7ad19-113">Los elementos del menú **Acción** y **Salida** no están incluidos en la lista.</span><span class="sxs-lookup"><span data-stu-id="7ad19-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="7ad19-114">En el campo **Id. de usuario**, seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="7ad19-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="7ad19-115">Si el usuario no tiene permisos para algunos elementos del menú, el campo **Permisos que faltan** se actualizará a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Página de detalles del elemento del menú de seguridad](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="7ad19-117">Seleccione **Añadir referencia** para ver una lista de los objetos de seguridad, incluidos roles, deberes y privilegios que otorgan el permiso que falta.</span><span class="sxs-lookup"><span data-stu-id="7ad19-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="7ad19-118">Seleccione un objeto de seguridad en la lista:</span><span class="sxs-lookup"><span data-stu-id="7ad19-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="7ad19-119">Si **Papel** está seleccionado, seleccione **Agregar rol al usuario**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="7ad19-120">Esto abrirá la página **Asignar usuarios a roles**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="7ad19-121">Para obtener más información, consulte la página [Asignar usuarios a roles de seguridad](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7ad19-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="7ad19-122">Si está seleccionado **Derecho**, seleccione **Agregar derecho al rol**, seleccione los roles a los que se debe agregar el derecho y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="7ad19-123">Si está seleccionado **privilegio**, seleccione **Agregar privilegio a derechos**, seleccione los roles a los que se debe agregar el derecho y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ad19-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
