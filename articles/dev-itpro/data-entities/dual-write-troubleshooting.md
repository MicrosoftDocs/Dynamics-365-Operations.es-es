---
title: Guía de solución de problemas para integración de datos
description: Este tema proporciona información para solución de problemas de integración de datos entre Microsoft Dynamics 365 for Finance and Operations y Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797284"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="e95f6-103">Guía de solución de problemas para integración de datos</span><span class="sxs-lookup"><span data-stu-id="e95f6-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="e95f6-104">Habilitar el seguimiento de complementos en Common Data Service y comprobar los detalles del error en el complemento de escritura dual</span><span class="sxs-lookup"><span data-stu-id="e95f6-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="e95f6-105">Si tiene un problema o se produce un error en relación con la sincronización de la escritura dual, puede inspeccionar los errores en el registro de seguimiento:</span><span class="sxs-lookup"><span data-stu-id="e95f6-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="e95f6-106">Antes de que pueda inspeccionar los errores, debe habilitar el seguimiento de complementos según las instrucciones en [Complemento de registro](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) para habilitar el seguimiento de complementos.</span><span class="sxs-lookup"><span data-stu-id="e95f6-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="e95f6-107">Ahora ya puede inspeccionar errores.</span><span class="sxs-lookup"><span data-stu-id="e95f6-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="e95f6-108">Inicie sesión en Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="e95f6-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="e95f6-109">Haga clic en el icono de configuración (un engranaje) y seleccione **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="e95f6-110">En el menú **Configuración** , seleccione **Personalización > REgistro de seguimiento de complementos**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="e95f6-111">Haga clic en el nombre del tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** para mostrar los detalles de error.</span><span class="sxs-lookup"><span data-stu-id="e95f6-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="e95f6-112">Comprobar los errores de sincronización de escritura dual en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e95f6-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="e95f6-113">Puede comprobar los errores durante las pruebas siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e95f6-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="e95f6-114">Inicie sesión en LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e95f6-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="e95f6-115">Abra el proyecto LCS que seleccionó para realizar la prueba de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="e95f6-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="e95f6-116">Vaya a Entornos hospedados en la nube.</span><span class="sxs-lookup"><span data-stu-id="e95f6-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="e95f6-117">Escritorio remoto a VM Finance and Operations mediante la cuenta local que se muestra en LCS.</span><span class="sxs-lookup"><span data-stu-id="e95f6-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="e95f6-118">Abra el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="e95f6-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="e95f6-119">Vaya **Registros de aplicaciones y servicios > Microsoft > Dynamics > AX-DualWriteSync > Operacional**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="e95f6-120">Se muestran los errores y los detalles.</span><span class="sxs-lookup"><span data-stu-id="e95f6-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="e95f6-121">Cómo desvincular y vincular otro entorno Common Data Service de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e95f6-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="e95f6-122">Puede actualizar los vínculos siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e95f6-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="e95f6-123">Navegue al entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e95f6-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="e95f6-124">Abra Administración de datos.</span><span class="sxs-lookup"><span data-stu-id="e95f6-124">Open Data Management.</span></span>
+ <span data-ttu-id="e95f6-125">Hag clic en **Vínculo a CDS para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="e95f6-126">Seleccione todas las asignaciones en funcionamiento haga click en **Detener**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="e95f6-127">Seleccione todas las asignaciones y haga click en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e95f6-128">La opción **Eliminar** no aparecerá si se selecciona la plantilla **CustomerV3-Account** .</span><span class="sxs-lookup"><span data-stu-id="e95f6-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="e95f6-129">Anule su selección si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e95f6-129">Unselect it if needed.</span></span> <span data-ttu-id="e95f6-130">**CustomerV3-Account** es una antigua plantilla y funciona con la solución Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="e95f6-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="e95f6-131">Dado que el lanzamiento es global, aparecerá bajo todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="e95f6-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="e95f6-132">Haga click en **Desvincular entorno**.</span><span class="sxs-lookup"><span data-stu-id="e95f6-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="e95f6-133">Haga click en **Sí** como confirmación.</span><span class="sxs-lookup"><span data-stu-id="e95f6-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="e95f6-134">Para vincular el nuevo entorno, siga los pasos de la [guía de instalación](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="e95f6-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

