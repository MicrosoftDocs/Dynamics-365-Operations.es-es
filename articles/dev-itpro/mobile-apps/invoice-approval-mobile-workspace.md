---
title: "Espacio de trabajo móvil Aprobaciones de facturas"
description: "Este tema proporciona información sobre del espacio de trabajo móvil Aprobaciones de facturas. Este espacio de trabajo proporciona una lista de facturas que se le han asignado a través del proceso de flujo de trabajo del encabezado de factura de proveedor."
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: af673f076f684500b6ca84d04c01f7f773d65cd6
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="5defd-104">Espacio de trabajo móvil Aprobaciones de facturas</span><span class="sxs-lookup"><span data-stu-id="5defd-104">Invoice approvals mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5defd-105">Este tema proporciona información sobre del espacio de trabajo móvil **Aprobaciones de facturas**.</span><span class="sxs-lookup"><span data-stu-id="5defd-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="5defd-106">Este espacio de trabajo proporciona una lista de facturas que se le han asignado a través del proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5defd-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="5defd-107">Este espacio de trabajo móvil se debe usar con la aplicación móvil Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="5defd-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="5defd-108">Información general</span><span class="sxs-lookup"><span data-stu-id="5defd-108">Overview</span></span>

<span data-ttu-id="5defd-109">El espacio de trabajo móvil **Aprobaciones de facturas** permite a los empleados y directores de proveedores ver las facturas que se les han asignado como parte del proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5defd-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="5defd-110">Puede ver la información de la factura e incluso los detalles de la línea y la distribución, que le ayudarán a tomar decisiones informadas de aprobación.</span><span class="sxs-lookup"><span data-stu-id="5defd-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="5defd-111">En el espacio de trabajo, puede tomar medidas para mover la factura por el proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5defd-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5defd-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5defd-112">Prerequisites</span></span>

<span data-ttu-id="5defd-113">Para poder usar este espacio de trabajo móvil, antes debe satisfacer los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="5defd-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5defd-114">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="5defd-114">Prerequisite</span></span></th>
<th><span data-ttu-id="5defd-115">Función</span><span class="sxs-lookup"><span data-stu-id="5defd-115">Role</span></span></th>
<th><span data-ttu-id="5defd-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5defd-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5defd-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julio 2017), debe haberse implementando en la organización.</span><span class="sxs-lookup"><span data-stu-id="5defd-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="5defd-118">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="5defd-118">System administrator</span></span></td>
<td><span data-ttu-id="5defd-119">Consulte <a href="../deployment/deploy-demo-environment.md">Implementar un entorno de demostración</a>.</span><span class="sxs-lookup"><span data-stu-id="5defd-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="5defd-120">El espacio de trabajo móvil <strong>Aprobaciones de facturas</strong> debe publicarse.</span><span class="sxs-lookup"><span data-stu-id="5defd-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="5defd-121">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="5defd-121">System administrator</span></span></td>
<td><span data-ttu-id="5defd-122">Consulte <a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</span><span class="sxs-lookup"><span data-stu-id="5defd-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="5defd-123">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="5defd-123">Download and install the mobile app</span></span>

<span data-ttu-id="5defd-124">Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="5defd-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="5defd-125">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="5defd-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="5defd-126">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="5defd-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="5defd-127">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="5defd-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="5defd-128">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="5defd-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="5defd-129">Escriba la dirección URL de Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5defd-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="5defd-130">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="5defd-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="5defd-131">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="5defd-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="5defd-132">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="5defd-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="5defd-133">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="5defd-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="5defd-134">[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="5defd-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="5defd-135">Aprobar facturas mediante el espacio de trabajo móvil Aprobaciones de facturas</span><span class="sxs-lookup"><span data-stu-id="5defd-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="5defd-136">En el dispositivo móvil, seleccione el espacio de trabajo **Aprobaciones de facturas**.</span><span class="sxs-lookup"><span data-stu-id="5defd-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="5defd-137">Seleccione la factura que le ha sido asignada por el proceso de flujo de trabajo del encabezado de factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="5defd-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="5defd-138">En la página **Detalles de la factura**, revise la información de encabezado de factura, como la información del proveedor y la fecha.</span><span class="sxs-lookup"><span data-stu-id="5defd-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="5defd-139">Seleccione una línea de la factura para ver su información más detallada en la vista **Detalles de línea de factura**.</span><span class="sxs-lookup"><span data-stu-id="5defd-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="5defd-140">En la vista **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar las distribuciones de la línea.</span><span class="sxs-lookup"><span data-stu-id="5defd-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="5defd-141">Aquí puede ver la contabilidad para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="5defd-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="5defd-142">La información que se muestra incluye las dimensiones financieras y la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="5defd-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="5defd-143">En la página **Detalles de línea de factura**, seleccione la **Distribuciones** para mostrar todas las distribuciones.</span><span class="sxs-lookup"><span data-stu-id="5defd-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="5defd-144">Aquí puede ver la contabilidad para la toda la factura.</span><span class="sxs-lookup"><span data-stu-id="5defd-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="5defd-145">La información que se muestra incluye las dimensiones financieras y las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="5defd-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="5defd-146">Seleccione **Datos adjuntos** para ver las notas o los archivo que están asociadas a la factura.</span><span class="sxs-lookup"><span data-stu-id="5defd-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="5defd-147">En la página **Detalles de la factura**, seleccione la acción del flujo de trabajo adecuado para completar el proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="5defd-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="5defd-148">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5defd-148">Select **Done**.</span></span>

