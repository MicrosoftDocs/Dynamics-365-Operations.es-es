---
title: Página principal de aplicación móvil
description: Este tema describe la aplicación Finance and Operations y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización.
author: sericks007
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 219bb1b5ac8360acf267fb792b8e23f961096abc
ms.sourcegitcommit: bbb64b3475eef155b3f9d1bdc440545da8a7182f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2019
ms.locfileid: "2553077"
---
# <a name="mobile-app-home-page"></a><span data-ttu-id="8ae5b-103">Página principal de aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="8ae5b-103">Mobile app home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ae5b-104">Este tema describe la aplicación Finance and Operations y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-104">This topic describes the Finance and Operations Operations mobile app and provides links to resources that can help you implement it in your organization.</span></span>

<a name="overview"></a><span data-ttu-id="8ae5b-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="8ae5b-105">Overview</span></span>
--------

<span data-ttu-id="8ae5b-106">La aplicación móvil permite a su organización tener los procesos de negocio disponibles en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-106">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="8ae5b-107">Una vez que el administrador de TI habilita los espacios de trabajo móviles para su organización, los usuarios pueden iniciar sesión en la aplicación e inmediatamente comenzar a trabajar con procesos empresariales en sus dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-107">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="8ae5b-108">La aplicación móvil incluye las siguientes características que pueden ayudarle a aumentar la productividad:</span><span class="sxs-lookup"><span data-stu-id="8ae5b-108">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="8ae5b-109">Los usuarios pueden ver, editar, y realizar acciones en datos empresariales, incluso si tienen conectividad de red intermitente o sus dispositivos móviles están completamente sin conexión.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-109">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="8ae5b-110">Cuando un dispositivo restablece una conexión de red, las operaciones de datos sin conexión se sincronizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-110">When a device reestablishes a network connection, offline data operations are automatically synchronized.</span></span>
- <span data-ttu-id="8ae5b-111">Las administraciones o los desarrolladores de TI pueden crear y publicar espacios de trabajo móviles adaptados para la organización.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-111">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="8ae5b-112">La aplicación utiliza los activos codificados existentes.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-112">The app uses your existing code assets.</span></span> <span data-ttu-id="8ae5b-113">Por lo tanto, no tiene tener que volver a implementar los procedimientos de validación, la lógica de negocios, o la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-113">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="8ae5b-114">Las administraciones o los desarrolladores de TI fácilmente puede diseñar espacios de trabajo móviles mediante el diseñador de espacios de trabajo interactivo que se incluye en el cliente web.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-114">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="8ae5b-115">Los administradores o los desarrolladores de TI pueden opcionalmente optimizar las capacidades sin conexión de los espacios de trabajo usando el marco de extensibilidad de la lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-115">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="8ae5b-116">Dado que los datos continúan con su procesamiento mientras el dispositivo está desconectado, los escenarios móviles siguen siendo ricos y fluidos, aunque los dispositivos no tengan conectividad de red constante.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-116">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="8ae5b-117">Elementos de la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="8ae5b-117">Elements of the mobile app</span></span>
<span data-ttu-id="8ae5b-118">La exploración en la aplicación móvil consiste en cuatro conceptos básicos: el panel de información, los espacios de trabajo, las páginas, y las acciones.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-118">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="8ae5b-119">[![Conceptos de navegación en la aplicación móvil](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="8ae5b-119">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="8ae5b-120">Al iniciar la aplicación, vaya al **panel de información**.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-120">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="8ae5b-121">En el panel, puede ver una lista de **espacios de trabajo** que ya sea han publicado.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-121">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="8ae5b-122">En cada espacio de trabajo, puede ver una lista de las **páginas** que están disponibles para dicho espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-122">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="8ae5b-123">Tras estar una página, puede realizar varias acciones.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-123">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="8ae5b-124">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="8ae5b-124">Here are some examples:</span></span>

    - <span data-ttu-id="8ae5b-125">Ver datos detallados.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-125">View detailed data.</span></span>
    - <span data-ttu-id="8ae5b-126">Navegue a otras páginas, puede navegar a otras páginas para buscar datos relacionados, como líneas o detalles de entidad.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-126">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="8ae5b-127">Vea una lista **acciones** disponibles para dicha página.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-127">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="8ae5b-128">Las acciones le permiten crear o editar datos existentes.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-128">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="8ae5b-129">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="8ae5b-129">Implementation process</span></span>
<span data-ttu-id="8ae5b-130">La ilustración siguiente muestra el proceso para implementar ambos espacios de trabajo móviles que proporciona Microsoft y los espacios de trabajo móviles personalizados.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-130">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

<span data-ttu-id="8ae5b-131">[![Proceso de implementación de aplicaciones móviles](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span><span class="sxs-lookup"><span data-stu-id="8ae5b-131">[![Mobile apps implementation process](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span></span>

<span data-ttu-id="8ae5b-132">La siguiente tabla incluye vínculos a los recursos que pueden ayudarle a implementar ambos espacios de trabajo móviles que proporciona Microsoft y los espacios de trabajo móviles personalizados.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-132">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="8ae5b-133">Los números de la primera columna corresponden a los pasos numerados de la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-133">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ae5b-134">Paso</span><span class="sxs-lookup"><span data-stu-id="8ae5b-134">Step</span></span></th>
<th><span data-ttu-id="8ae5b-135">Función</span><span class="sxs-lookup"><span data-stu-id="8ae5b-135">Role</span></span></th>
<th><span data-ttu-id="8ae5b-136">Acción</span><span class="sxs-lookup"><span data-stu-id="8ae5b-136">Action</span></span></th>
<th><span data-ttu-id="8ae5b-137">Recursos para ayudarle a completar la acción</span><span class="sxs-lookup"><span data-stu-id="8ae5b-137">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8ae5b-138">1</span><span class="sxs-lookup"><span data-stu-id="8ae5b-138">1</span></span></td>
<td><span data-ttu-id="8ae5b-139">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8ae5b-139">System administrator</span></span></td>
<td><span data-ttu-id="8ae5b-140">Implemente aplicaciones Finance and Operations en su organización.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-140">Implement Finance and Operations apps in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="8ae5b-141">Si aún no ha implementado una versión de Microsoft Dynamics 365, vea <a href="../deployment/deploy-demo-environment.md">Implementar un entorno de demostración</a>.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-141">If you haven&#39;t yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="8ae5b-142">Para ver una lista de espacios de trabajo móviles se pueden utilizar, vea <a href="mobile-workspaces-released.md">Espacios de trabajo móviles recientemente liberados</a>.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-142">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ae5b-143">2</span><span class="sxs-lookup"><span data-stu-id="8ae5b-143">2</span></span></td>
<td><span data-ttu-id="8ae5b-144">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8ae5b-144">System administrator</span></span></td>
<td><span data-ttu-id="8ae5b-145"><strong>Si está usando Microsoft Dynamics 365 for Operations versión 1611:</strong> descargue e instale KB que permitan espacios de trabajo móviles proporcionados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-145"><strong>If you&#39;re using Microsoft Dynamics 365 for Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="8ae5b-146">Consulte los temas siguientes para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="8ae5b-146">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="8ae5b-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Espacios de trabajo móviles de control de costes</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="8ae5b-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Espacio de trabajo móvil de inventario disponible</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="8ae5b-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espacios de trabajo móviles de pedidos de ventas</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="8ae5b-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espacio de trabajo de móvil de colaboración de proveedor</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="8ae5b-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Espacio de trabajo móvil de entrada de tiempo de proyecto</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="8ae5b-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Espacio de trabajo móvil de gestión de gastos</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ae5b-153">3</span><span class="sxs-lookup"><span data-stu-id="8ae5b-153">3</span></span></td>
<td><span data-ttu-id="8ae5b-154">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8ae5b-154">System administrator</span></span></td>
<td><span data-ttu-id="8ae5b-155">Publique los espacios de trabajo móviles que se proporcionan en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-155">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="8ae5b-156"><a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>
</span><span class="sxs-lookup"><span data-stu-id="8ae5b-156"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ae5b-157">4</span><span class="sxs-lookup"><span data-stu-id="8ae5b-157">4</span></span></td>
<td><span data-ttu-id="8ae5b-158">Desarrollador o fabricante de software independiente (ISV)</span><span class="sxs-lookup"><span data-stu-id="8ae5b-158">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="8ae5b-159">Use la plataforma móvil para crear espacios de trabajo móviles personalizados.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-159">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="8ae5b-160"><a href="platform/mobile-platform-home-page.md">Plataforma móvil</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-160"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ae5b-161">5</span><span class="sxs-lookup"><span data-stu-id="8ae5b-161">5</span></span></td>
<td><span data-ttu-id="8ae5b-162">ISV</span><span class="sxs-lookup"><span data-stu-id="8ae5b-162">ISV</span></span></td>
<td><span data-ttu-id="8ae5b-163">Cree un paquete desplegable que contenga espacios de trabajo móviles personalizados, y cargue el paquete en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8ae5b-163">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="8ae5b-164"><a href="../deployment/create-apply-deployable-package.md">Crear un paquete implementable</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-164"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ae5b-165">6</span><span class="sxs-lookup"><span data-stu-id="8ae5b-165">6</span></span></td>
<td><span data-ttu-id="8ae5b-166">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8ae5b-166">System administrator</span></span></td>
<td><span data-ttu-id="8ae5b-167">Aplique el paquete desplegable que contiene los espacios de trabajo personalizados que proporciona el proveedor de software independiente (ISV).</span><span class="sxs-lookup"><span data-stu-id="8ae5b-167">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="8ae5b-168"><a href="../deployment/apply-deployable-package-system.md">Aplicar un paquete implementable</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-168"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ae5b-169">7</span><span class="sxs-lookup"><span data-stu-id="8ae5b-169">7</span></span></td>
<td><span data-ttu-id="8ae5b-170">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="8ae5b-170">System administrator</span></span></td>
<td><span data-ttu-id="8ae5b-171">Publique los espacios de trabajo personalizados que proporciona el ISV.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-171">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="8ae5b-172"><a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-172"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8ae5b-173">8</span><span class="sxs-lookup"><span data-stu-id="8ae5b-173">8</span></span></td>
<td><span data-ttu-id="8ae5b-174">Usuario</span><span class="sxs-lookup"><span data-stu-id="8ae5b-174">User</span></span></td>
<td><span data-ttu-id="8ae5b-175">Descargar e instalar la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-175">Download and install the mobile app.</span></span></td>
<td><span data-ttu-id="8ae5b-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662"> Aplicación Finance and Operations para Android</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations app for Android</a></span></span><BR/><span data-ttu-id="8ae5b-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Aplicación Finance and Operations para iOS</a></span><span class="sxs-lookup"><span data-stu-id="8ae5b-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations app for iOS</a></span></span><BR/>
<span data-ttu-id="8ae5b-178">(Windows puede no admitido)</span><span class="sxs-lookup"><span data-stu-id="8ae5b-178">(Windows Phone unsupported)</span></span>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8ae5b-179">9</span><span class="sxs-lookup"><span data-stu-id="8ae5b-179">9</span></span></td>
<td><span data-ttu-id="8ae5b-180">Usuario</span><span class="sxs-lookup"><span data-stu-id="8ae5b-180">User</span></span></td>
<td><span data-ttu-id="8ae5b-181">Inicie sesión y utilice la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="8ae5b-182">La aplicación incluye los espacios de trabajo móviles que ha publicado el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="8ae5b-183">Para ver una lista de espacios de trabajo móviles que proporciona Microsoft, vea <a href="mobile-workspaces-released.md">Espacios de trabajo móviles recientemente liberados</a>.</span><span class="sxs-lookup"><span data-stu-id="8ae5b-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>
