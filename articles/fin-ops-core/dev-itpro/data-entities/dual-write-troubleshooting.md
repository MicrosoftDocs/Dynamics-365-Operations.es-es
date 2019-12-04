---
title: Guía de solución de problemas para integración de datos
description: Este tema proporciona información para solución de problemas de integración de datos entre aplicaciones de Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 35c0a1e6342008bc2ee6ff25a1663e199c8cb985
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771034"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="f2142-103">Guía de solución de problemas para integración de datos</span><span class="sxs-lookup"><span data-stu-id="f2142-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="f2142-104">Habilitar los registros de seguimiento de complementos en Common Data Service e inspeccionar los detalles del error en el complemento de escritura dual</span><span class="sxs-lookup"><span data-stu-id="f2142-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2142-105">Si tiene un problema o un error durante la sincronización de la escritura dual, siga estos pasos para inspeccionar los errores en el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f2142-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="f2142-106">Antes de que pueda inspeccionar los errores, debe habilitar los registros de seguimiento de complementos.</span><span class="sxs-lookup"><span data-stu-id="f2142-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="f2142-107">Para obtener instrucciones, consulte la sección "Ver registros de seguimiento" de [Tutorial: Escribir y registrar complementos](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="f2142-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="f2142-108">Ahora ya puede inspeccionar errores.</span><span class="sxs-lookup"><span data-stu-id="f2142-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="f2142-109">Inicie sesión en Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="f2142-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="f2142-110">Seleccione el botón **Configuración** (símbolo de engranaje) y, a continuación, seleccione **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="f2142-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="f2142-111">En el menú **Configuración** , seleccione **Personalización \> Registro de seguimiento de complementos**.</span><span class="sxs-lookup"><span data-stu-id="f2142-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="f2142-112">Seleccione **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** como nombre del tipo para mostrar los detalles de error.</span><span class="sxs-lookup"><span data-stu-id="f2142-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="f2142-113">Inspeccione los errores de sincronización de escritura dual</span><span class="sxs-lookup"><span data-stu-id="f2142-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="f2142-114">Siga estos pasos para inspeccionar errores durante las pruebas.</span><span class="sxs-lookup"><span data-stu-id="f2142-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="f2142-115">Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f2142-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="f2142-116">Abra el proyecto de LCS para el que quiere realizar la prueba de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="f2142-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="f2142-117">Seleccione **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="f2142-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="f2142-118">Cree una conexión al escritorio remoto para la máquina virtual (VM) de la aplicación mediante el uso de la cuenta local que se muestra en el LCS.</span><span class="sxs-lookup"><span data-stu-id="f2142-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="f2142-119">Abra el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="f2142-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="f2142-120">Vaya **Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.</span><span class="sxs-lookup"><span data-stu-id="f2142-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="f2142-121">Se muestran los errores y los detalles.</span><span class="sxs-lookup"><span data-stu-id="f2142-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="f2142-122">Desvincular un entorno Common Data Service de la aplicación y vincular otro entorno</span><span class="sxs-lookup"><span data-stu-id="f2142-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="f2142-123">Para actualizar los vínculos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f2142-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="f2142-124">Vaya al entorno de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2142-124">Go to the application environment.</span></span>
2. <span data-ttu-id="f2142-125">Abra Administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f2142-125">Open Data Management.</span></span>
3. <span data-ttu-id="f2142-126">Seleccione **Vínculo a CDS para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f2142-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="f2142-127">Seleccione todas las asignaciones que se están ejecutando y, a continuación, seleccione **Detener**.</span><span class="sxs-lookup"><span data-stu-id="f2142-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="f2142-128">Seleccione todas las asignaciones y, a continuación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f2142-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2142-129">La opción **Eliminar** no está disponible si se selecciona la plantilla **CustomerV3-Account**.</span><span class="sxs-lookup"><span data-stu-id="f2142-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="f2142-130">Anule la selección de esta plantilla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f2142-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="f2142-131">**CustomerV3-Account** es una antigua plantilla y funciona con la solución Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="f2142-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="f2142-132">Dado que el lanzamiento es global, aparecerá en todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="f2142-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="f2142-133">Seleccione **Desvincular entorno**.</span><span class="sxs-lookup"><span data-stu-id="f2142-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="f2142-134">Seleccione **Sí** para confirmar la operación.</span><span class="sxs-lookup"><span data-stu-id="f2142-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="f2142-135">Para vincular el nuevo entorno, siga los pasos de la [guía de instalación](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="f2142-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>