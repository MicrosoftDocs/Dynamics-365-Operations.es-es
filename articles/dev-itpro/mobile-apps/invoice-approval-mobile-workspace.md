---
title: Espacio de trabajo móvil Aprobaciones de facturas
description: Este tema proporciona información sobre del espacio de trabajo móvil Aprobaciones de facturas. Este espacio de trabajo proporciona una lista de facturas que se le han asignado a través del proceso de flujo de trabajo del encabezado de factura de proveedor.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ff726670e0fd7566a74e6def73555a7c53b86f97
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "327007"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="0e508-104">Espacio de trabajo móvil Aprobaciones de facturas</span><span class="sxs-lookup"><span data-stu-id="0e508-104">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e508-105">Este tema proporciona información sobre del espacio de trabajo móvil **Aprobaciones de facturas**.</span><span class="sxs-lookup"><span data-stu-id="0e508-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="0e508-106">Este espacio de trabajo proporciona una lista de facturas que se le han asignado a través del proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0e508-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="0e508-107">Este espacio de trabajo móvil se debe usar con la aplicación Microsoft Dynamics 365 for Unified Operations mobile.</span><span class="sxs-lookup"><span data-stu-id="0e508-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="0e508-108">Información general</span><span class="sxs-lookup"><span data-stu-id="0e508-108">Overview</span></span>

<span data-ttu-id="0e508-109">El espacio de trabajo móvil **Aprobaciones de facturas** permite a los empleados y directores de proveedores ver las facturas que se les han asignado como parte del proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0e508-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="0e508-110">Puede ver la información de la factura e incluso los detalles de la línea y la distribución, que le ayudarán a tomar decisiones informadas de aprobación.</span><span class="sxs-lookup"><span data-stu-id="0e508-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="0e508-111">En el espacio de trabajo, puede tomar medidas para mover la factura por el proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e508-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0e508-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0e508-112">Prerequisites</span></span>

<span data-ttu-id="0e508-113">Para poder usar este espacio de trabajo móvil, antes debe satisfacer los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="0e508-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0e508-114">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="0e508-114">Prerequisite</span></span></th>
<th><span data-ttu-id="0e508-115">Función</span><span class="sxs-lookup"><span data-stu-id="0e508-115">Role</span></span></th>
<th><span data-ttu-id="0e508-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e508-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0e508-117">Microsoft Dynamics 365 for Finance and Operations debe ser implementado en su organización.</span><span class="sxs-lookup"><span data-stu-id="0e508-117">Microsoft Dynamics 365 for Finance and Operations must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="0e508-118">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="0e508-118">System administrator</span></span></td>
<td><span data-ttu-id="0e508-119">Consulte <a href="../deployment/deploy-demo-environment.md">Implementar un entorno de demostración</a>.</span><span class="sxs-lookup"><span data-stu-id="0e508-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="0e508-120">El espacio de trabajo móvil <strong>Aprobaciones de facturas</strong> debe publicarse.</span><span class="sxs-lookup"><span data-stu-id="0e508-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="0e508-121">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="0e508-121">System administrator</span></span></td>
<td><span data-ttu-id="0e508-122">Consulte <a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</span><span class="sxs-lookup"><span data-stu-id="0e508-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="0e508-123">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="0e508-123">Download and install the mobile app</span></span>

<span data-ttu-id="0e508-124">Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="0e508-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="0e508-125">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="0e508-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="0e508-126">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="0e508-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="0e508-127">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="0e508-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="0e508-128">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="0e508-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="0e508-129">Especifique la dirección URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e508-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="0e508-130">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="0e508-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="0e508-131">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="0e508-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="0e508-132">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="0e508-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="0e508-133">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="0e508-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="0e508-134">[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="0e508-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="0e508-135">Aprobar facturas mediante el espacio de trabajo móvil Aprobaciones de facturas</span><span class="sxs-lookup"><span data-stu-id="0e508-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="0e508-136">En el dispositivo móvil, seleccione el espacio de trabajo **Aprobaciones de facturas**.</span><span class="sxs-lookup"><span data-stu-id="0e508-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="0e508-137">Seleccione la factura que le ha sido asignada por el proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="0e508-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="0e508-138">En la página **Detalles de la factura**, revise la información de encabezado de factura, como la información del proveedor y la fecha.</span><span class="sxs-lookup"><span data-stu-id="0e508-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="0e508-139">Seleccione una línea de la factura para ver su información más detallada en la vista **Detalles de línea de factura**.</span><span class="sxs-lookup"><span data-stu-id="0e508-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="0e508-140">En la vista **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar las distribuciones de la línea.</span><span class="sxs-lookup"><span data-stu-id="0e508-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="0e508-141">Aquí puede ver la contabilidad para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="0e508-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="0e508-142">La información que se muestra incluye las dimensiones financieras y la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="0e508-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="0e508-143">En la página **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar todas las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="0e508-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="0e508-144">Aquí puede ver la contabilidad para la toda la factura.</span><span class="sxs-lookup"><span data-stu-id="0e508-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="0e508-145">La información que se muestra incluye las dimensiones financieras y las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="0e508-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="0e508-146">Seleccione **Datos adjuntos** para ver las notas o los archivo que están asociadas a la factura.</span><span class="sxs-lookup"><span data-stu-id="0e508-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="0e508-147">En la página **Detalles de la factura**, seleccione la acción del flujo de trabajo adecuado para completar el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="0e508-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="0e508-148">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="0e508-148">Select **Done**.</span></span>
