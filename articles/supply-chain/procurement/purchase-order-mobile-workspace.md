---
title: Área de trabajo de móvil de la aprobación del pedido de compra
description: Este tema proporciona información acerca del Espacio de trabajo móvil de la aprobación del pedido de compra, que le permite ver pedidos de compra y responder a ellos con acciones. Por ejemplo, puede aprobar o rechazar un pedido de compra.
author: mkirknel
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 33e5993f57a8c0248ac2e314f91cc40a2b355858
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653473"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="4c264-104">Área de trabajo de móvil de la aprobación del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="4c264-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c264-105">Este tema proporciona información sobre el espacio de trabajo móvil **Aprobación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="4c264-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="4c264-106">Este espacio de trabajo le permite ver pedidos de compra y responder a ellos con acciones.</span><span class="sxs-lookup"><span data-stu-id="4c264-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="4c264-107">Por ejemplo, puede aprobar o rechazar un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4c264-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="4c264-108">Información general</span><span class="sxs-lookup"><span data-stu-id="4c264-108">Overview</span></span> 
<span data-ttu-id="4c264-109">Los pedidos de compra que requieren aprobación pasan por un flujo de trabajo de aprobación.</span><span class="sxs-lookup"><span data-stu-id="4c264-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="4c264-110">El flujo de trabajo puede incluir varios pasos que requieren que una o más personas realicen una acción.</span><span class="sxs-lookup"><span data-stu-id="4c264-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="4c264-111">Por ejemplo, una persona puede tener que completar una tarea o aprobar el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4c264-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="4c264-112">El espacio de trabajo móvil **Aprobación de pedido de compra** le permite ver fácilmente y responder a los pedidos de compra desde el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="4c264-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="4c264-113">Este espacio de trabajo también le permite realizar las mismas acciones que el cliente web.</span><span class="sxs-lookup"><span data-stu-id="4c264-113">This workspace also lets you take the same workflow actions that you can take from the web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c264-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4c264-114">Prerequisites</span></span>
<span data-ttu-id="4c264-115">Los requisitos varían en función de la versión de Supply Chain Management que se haya implementado en su organización.</span><span class="sxs-lookup"><span data-stu-id="4c264-115">The prerequisites vary, depending on the version of Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-supply-chain-management"></a><span data-ttu-id="4c264-116">Requisitos previos si usa Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4c264-116">Prerequisites if you use Supply Chain Management</span></span> 
<span data-ttu-id="4c264-117">Si Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Aprobación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="4c264-117">If Supply Chain Management has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="4c264-118">Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="4c264-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="4c264-119">Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior</span><span class="sxs-lookup"><span data-stu-id="4c264-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="4c264-120">Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4c264-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4c264-121">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="4c264-121">Prerequisite</span></span></th>
<th><span data-ttu-id="4c264-122">Función</span><span class="sxs-lookup"><span data-stu-id="4c264-122">Role</span></span></th>
<th><span data-ttu-id="4c264-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c264-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4c264-124">Implementar 4017918 KB.</span><span class="sxs-lookup"><span data-stu-id="4c264-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="4c264-125">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="4c264-125">System administrator</span></span></td>
<td><span data-ttu-id="4c264-126">KB 4017918 es una actualización X++ o revisión de metadatos que contiene el espacio de trabajo móvil <strong>Aprobación del pedido de compra</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c264-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="4c264-127">Para implementar KB 4017918, el administrador del sistema debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4c264-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="4c264-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="4c264-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="4c264-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</span><span class="sxs-lookup"><span data-stu-id="4c264-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="4c264-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</span><span class="sxs-lookup"><span data-stu-id="4c264-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="4c264-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</span><span class="sxs-lookup"><span data-stu-id="4c264-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4c264-132">Publique el espacio de trabajo <strong>Aprobación del pedido de compra</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c264-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="4c264-133">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="4c264-133">System administrator</span></span></td>
<td><span data-ttu-id="4c264-134">Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</span><span class="sxs-lookup"><span data-stu-id="4c264-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="4c264-135">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="4c264-135">Download and install the mobile app</span></span>
<span data-ttu-id="4c264-136">Descargue e instale la aplicación móvil Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="4c264-136">Download and install the Finance and Operations mobile app:</span></span>

- [<span data-ttu-id="4c264-137">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="4c264-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="4c264-138">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="4c264-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="4c264-139">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="4c264-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="4c264-140">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="4c264-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="4c264-141">Especifique la dirección URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4c264-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="4c264-142">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="4c264-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="4c264-143">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="4c264-143">Enter your credentials.</span></span>
4. <span data-ttu-id="4c264-144">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="4c264-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="4c264-145">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="4c264-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Espacio de trabajo de aprobación del pedido de compra en la lista de espacios de trabajo disponibles](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="4c264-147">Visualización de los pedidos asignados al usuario</span><span class="sxs-lookup"><span data-stu-id="4c264-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="4c264-148">En el dispositivo móvil, seleccione el espacio de trabajo **Aprobación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="4c264-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="4c264-149">Seleccione **Pedidos asignados a mí** para ver todos los pedidos de compra para los que le han pedido tomar medidas en el flujo de trabajo de aprobación del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4c264-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="4c264-150">Seleccione un pedido.</span><span class="sxs-lookup"><span data-stu-id="4c264-150">Select an order.</span></span> <span data-ttu-id="4c264-151">En la página **Detalles de pedido** , verá la información y las líneas de encabezado del pedido.</span><span class="sxs-lookup"><span data-stu-id="4c264-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="4c264-152">También puede encontrar instrucciones de la tarea del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c264-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="4c264-153">Seleccione **Distribuciones contables** para abrir la página **Distribuciones contables para el encabezado**.</span><span class="sxs-lookup"><span data-stu-id="4c264-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="4c264-154">Vuelva a la página **Detalles de pedido** y seleccione una línea.</span><span class="sxs-lookup"><span data-stu-id="4c264-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="4c264-155">Desde los detalles de la línea de pedido, también puede explorar las distribuciones contables específicas de línea.</span><span class="sxs-lookup"><span data-stu-id="4c264-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="4c264-156">Realice una acción en el pedido de compra</span><span class="sxs-lookup"><span data-stu-id="4c264-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="4c264-157">Una vez que haya visualizado el pedido de compra que se le ha asignado y leído las instrucciones del flujo de trabajo, debe estar listo para tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="4c264-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="4c264-158">En el dispositivo móvil, seleccione el espacio de trabajo **Aprobación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="4c264-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="4c264-159">Seleccione **Pedidos asignados a mí** para ver todos los pedidos de compra para los que le han pedido tomar medidas en el flujo de trabajo de aprobación del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4c264-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="4c264-160">Seleccione un pedido y vea la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="4c264-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="4c264-161">Seleccione **Acciones** para mostrar las acciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="4c264-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="4c264-162">Las acciones disponibles dependen de la tarea que se le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="4c264-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="4c264-163">Acción de tarea</span><span class="sxs-lookup"><span data-stu-id="4c264-163">Task action</span></span>    | <span data-ttu-id="4c264-164">Acción de aprobación</span><span class="sxs-lookup"><span data-stu-id="4c264-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="4c264-165">Completo</span><span class="sxs-lookup"><span data-stu-id="4c264-165">Complete</span></span>       | <span data-ttu-id="4c264-166">Aprobar</span><span class="sxs-lookup"><span data-stu-id="4c264-166">Approve</span></span>          |
    | <span data-ttu-id="4c264-167">Devolución</span><span class="sxs-lookup"><span data-stu-id="4c264-167">Return</span></span>         | <span data-ttu-id="4c264-168">Rechazar</span><span class="sxs-lookup"><span data-stu-id="4c264-168">Reject</span></span>           |
    | <span data-ttu-id="4c264-169">Solicitar cambio</span><span class="sxs-lookup"><span data-stu-id="4c264-169">Request change</span></span> | <span data-ttu-id="4c264-170">Solicitar cambio</span><span class="sxs-lookup"><span data-stu-id="4c264-170">Request change</span></span>   |
    | <span data-ttu-id="4c264-171">Delegar</span><span class="sxs-lookup"><span data-stu-id="4c264-171">Delegate</span></span>       | <span data-ttu-id="4c264-172">Delegar</span><span class="sxs-lookup"><span data-stu-id="4c264-172">Delegate</span></span>         |

5. <span data-ttu-id="4c264-173">Seleccione la acción adecuada.</span><span class="sxs-lookup"><span data-stu-id="4c264-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="4c264-174">En la página **Completar tarea**, escriba un comentario.</span><span class="sxs-lookup"><span data-stu-id="4c264-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="4c264-175">Tenga en cuenta que si selecciona la acción **Delegar**, debe seleccionar un usuario en el que delegar la tarea.</span><span class="sxs-lookup"><span data-stu-id="4c264-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="4c264-176">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="4c264-176">Select **Done**.</span></span> <span data-ttu-id="4c264-177">Después de actualizar su espacio de trabajo, el pedido de compra ya no estará en su lista.</span><span class="sxs-lookup"><span data-stu-id="4c264-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 
