---
title: Configurar flujos de trabajo de aprobación de arrendamiento
description: El tema explica cómo configurar un flujo de trabajo de aprobación que se ejecutará cuando se cree un nuevo arrendamiento.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1eaa2f5cc191ec93c30f4f10a662a87e501a341d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249590"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="cad03-103">Configurar flujos de trabajo de aprobación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="cad03-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cad03-104">El tema explica cómo configurar un flujo de trabajo de aprobación que se ejecutará cuando se cree un nuevo arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="cad03-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="cad03-105">Para obtener información sobre cómo utilizar el flujo de trabajo, consulte [Utilizar flujos de trabajo de aprobación de arrendamiento](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="cad03-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="cad03-106">Vaya a **Arrendamiento de activos \> Configuración \> Flujo de trabajo de arrendamientos**.</span><span class="sxs-lookup"><span data-stu-id="cad03-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="cad03-107">En la página **Flujo de trabajo de arrendamiento**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="cad03-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="cad03-108">En el cuadro de diálogo que aparece, en **Tipo de flujo de trabajo**, seleccione el vínculo **Flujo de trabajo de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="cad03-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="cad03-109">Se abre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cad03-109">The application is opened.</span></span> <span data-ttu-id="cad03-110">Después de que se ejecute, inicie sesión en Azure Active Directory (Azure AD) para ser redirigido a la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cad03-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="cad03-111">Arrastre el elemento **Aprobación de flujo de trabajo de arrendamiento** al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cad03-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="cad03-112">Conecte un nodo desde **Inicio** a **Aprobación de flujo de trabajo de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="cad03-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="cad03-113">A continuación, conecte **Aprobación del flujo de trabajo de arrendamiento** a **Fin**.</span><span class="sxs-lookup"><span data-stu-id="cad03-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="cad03-114">Haga doble clic en **Aprobación de flujo de trabajo de arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="cad03-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="cad03-115">Seleccione **Propiedades**, y luego, en **Configuración básica**, introduzca un nombre para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cad03-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="cad03-116">En esta página, también puede establecer más parámetros para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cad03-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="cad03-117">Si ha activado **Acciones automáticas**, el sistema tomará automáticamente una acción específica.</span><span class="sxs-lookup"><span data-stu-id="cad03-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="cad03-118">Se pueden enviar notificaciones si se especifican en la pestaña **Notificaciones**. En la pestaña **Configuración avanzada**, puede especificar un aprobador final, establecer un límite de tiempo y designar acciones específicas que deben completarse.</span><span class="sxs-lookup"><span data-stu-id="cad03-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="cad03-119">Cuando haya terminado de configurar los parámetros del flujo de trabajo, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cad03-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="cad03-120">Seleccione **Paso 1** y luego **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cad03-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="cad03-121">En **Configuración básica**, introduzca un nombre para el paso, cree una línea de asunto para la aprobación y especifique las instrucciones para la aprobación.</span><span class="sxs-lookup"><span data-stu-id="cad03-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="cad03-122">En la página **Asignación**, seleccione el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="cad03-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="cad03-123">Para asignar usuarios específicos a la aprobación, seleccione **Usuario**, seleccione los usuarios que aprueban los arrendamientos y luego seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cad03-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="cad03-124">Seleccione **Guardar y cerrar** para crear el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cad03-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="cad03-125">Luego, cuando se le solicite, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cad03-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="cad03-126">En la página **Crear flujo de trabajo de arrendamiento**, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cad03-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="cad03-127">Seleccione el nuevo flujo de trabajo y luego seleccione **Versiones**.</span><span class="sxs-lookup"><span data-stu-id="cad03-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="cad03-128">Luego seleccione **Activar** para asegurarse de que el flujo de trabajo esté activo.</span><span class="sxs-lookup"><span data-stu-id="cad03-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="cad03-129">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="cad03-129">Select **Close**.</span></span> <span data-ttu-id="cad03-130">Aparece la nueva versión activa.</span><span class="sxs-lookup"><span data-stu-id="cad03-130">The new active version appears.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]