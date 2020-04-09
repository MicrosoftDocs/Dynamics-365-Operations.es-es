---
title: Solución de problemas generales
description: Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
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
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: f7ee0b5aa4e72614205e129acd986376b33efc70
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172700"
---
# <a name="general-troubleshooting"></a><span data-ttu-id="4f402-103">Solución de problemas generales</span><span class="sxs-lookup"><span data-stu-id="4f402-103">General troubleshooting</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4f402-104">Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4f402-104">This topic provides general troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f402-105">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4f402-105">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="4f402-106">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="4f402-106">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a><span data-ttu-id="4f402-107">Cuando intenta instalar el paquete de escritura doble utilizando la herramienta Package Deployer, no se muestran soluciones disponibles</span><span class="sxs-lookup"><span data-stu-id="4f402-107">When you try to install the dual-write package by using the package deployer tool, no available solutions are shown</span></span>

<span data-ttu-id="4f402-108">Algunas versiones de la herramienta Package Deployer son incompatibles con el paquete de solución de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="4f402-108">Some versions of the package deployer tool are incompatible with the dual-write solution package.</span></span> <span data-ttu-id="4f402-109">Para instalar con éxito el paquete, asegúrese de usar la [versión 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) o posterior de la herramienta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="4f402-109">To successfully install the package, be sure to use [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) or later of the package deployer tool.</span></span>

<span data-ttu-id="4f402-110">Después de instalar la herramienta Package Deployer, instale el paquete de la solución siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4f402-110">After you install the package deployer tool, install the solution package by following these steps.</span></span>

1. <span data-ttu-id="4f402-111">Descargue el archivo del paquete de solución más reciente de Yammer.com.</span><span class="sxs-lookup"><span data-stu-id="4f402-111">Download the latest solution package file from Yammer.com.</span></span> <span data-ttu-id="4f402-112">Después de descargar el archivo zip del paquete, haga clic con el botón derecho y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4f402-112">After the package zip file is downloaded, right-click it, and select **Properties**.</span></span> <span data-ttu-id="4f402-113">Selecciona la casilla **Desbloquear** y luego elija **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="4f402-113">Select the **Unblock** check box, and then select **Apply**.</span></span> <span data-ttu-id="4f402-114">Si no ve la casilla de verificación **Desbloquear**, el archivo zip ya está desbloqueado y puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="4f402-114">If you don't see the **Unblock** check box, the zip file is already unblocked, and you can skip this step.</span></span>

    ![Cuadro de diálogo Propiedades](media/unblock_option.png)

2. <span data-ttu-id="4f402-116">Extraiga el archivo zip del paquete y copie todos los archivos en la carpeta **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.</span><span class="sxs-lookup"><span data-stu-id="4f402-116">Extract the package zip file, and copy all the files in the **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** folder.</span></span>

    ![Contenido de la carpeta Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. <span data-ttu-id="4f402-118">Pegue todos los archivos copiados en la carpeta **Herramientas** de la herramienta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="4f402-118">Paste all the copied files into the **Tools** folder of the package deployer tool.</span></span> 
4. <span data-ttu-id="4f402-119">Ejecute **PackageDeployer.exe** para seleccionar el entorno Common Data Service e instalar las soluciones.</span><span class="sxs-lookup"><span data-stu-id="4f402-119">Run **PackageDeployer.exe** to select the Common Data Service environment and install the solutions.</span></span>

    ![Contenido de la carpeta Herramientas](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a><span data-ttu-id="4f402-121">Habilite y vea el inicio de sesión de seguimiento del complemento Common Data Service para ver detalles del error</span><span class="sxs-lookup"><span data-stu-id="4f402-121">Enable and view the plug-in trace log in Common Data Service to view error details</span></span>

<span data-ttu-id="4f402-122">**Rol requerido para activar el registro de seguimiento y ver los errores:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="4f402-122">**Required role to turn on the trace log and view errors:** System admin</span></span>

<span data-ttu-id="4f402-123">Para activar el registro de seguimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4f402-123">To turn on the trace log, follow these steps.</span></span>

1. <span data-ttu-id="4f402-124">Inicie sesión en la aplicación Finance and Operations, abra la página **Configuración**, y luego, en **Sistema**, seleccione **Administración**.</span><span class="sxs-lookup"><span data-stu-id="4f402-124">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **System**, select **Administration**.</span></span>
2. <span data-ttu-id="4f402-125">En la página **Administración** , seleccione **Configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="4f402-125">On the **Administration** page, select **System Settings**.</span></span>
3. <span data-ttu-id="4f402-126">En la pestaña **Personalización**, en el campo **Complemento y seguimiento de actividad de flujo de trabajo personalizado**, seleccione **Todo** para habilitar el registro de seguimiento del complemento.</span><span class="sxs-lookup"><span data-stu-id="4f402-126">On the **Customization** tab, in the **Plug-in and custom workflow activity tracing** field, select **All** to enable the plug-in trace log.</span></span> <span data-ttu-id="4f402-127">Si desea registrar registros de rastreo solo cuando se producen excepciones, puede seleccionar **Excepción** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4f402-127">If you want to log trace logs only when exceptions occur, you can select **Exception** instead.</span></span>


<span data-ttu-id="4f402-128">Para ver el registro de seguimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4f402-128">To view the trace log, follow these steps.</span></span>

1. <span data-ttu-id="4f402-129">Inicie sesión en la aplicación Finance and Operations, abra la página **Configuración**, y luego, en **Personalización**, seleccione **Registro de seguimiento de complemento**.</span><span class="sxs-lookup"><span data-stu-id="4f402-129">Sign in to the Finance and Operations app, open the **Settings** page, and then, under **Customization**, select **Plug-in Trace Log**.</span></span>
2. <span data-ttu-id="4f402-130">Encuentre los registros de seguimiento donde el campo **Escribir nombre** se establece en **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span><span class="sxs-lookup"><span data-stu-id="4f402-130">Find the trace logs where the **Type Name** field is set to **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span></span>
3. <span data-ttu-id="4f402-131">Haga doble clic en un elemento para ver el registro completo y luego, en la ficha desplegable **Ejecución**, revise el texto **Bloque de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="4f402-131">Double-click an item to view the full log, and then, on the **Execution** FastTab, review the **Message Block** text.</span></span>

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a><span data-ttu-id="4f402-132">Habilite el modo de depuración para solucionar problemas de sincronización en vivo en aplicaciones Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f402-132">Enable debug mode to troubleshoot live synchronization issues in Finance and Operations apps</span></span>

<span data-ttu-id="4f402-133">**Rol requerido para ver los errores:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="4f402-133">**Required role to view the errors:** System admin</span></span>

<span data-ttu-id="4f402-134">Los errores de doble escritura que se originan en Common Data Service puede aparecer en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f402-134">Dual-write errors that originate in Common Data Service can appear in the Finance and Operations app.</span></span> <span data-ttu-id="4f402-135">En algunos casos, el texto completo del mensaje de error no está disponible porque el mensaje es demasiado largo o contiene información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="4f402-135">In some cases, the full text of the error message isn't available because the message is too long or contains personally identifying information (PII).</span></span> <span data-ttu-id="4f402-136">Puede activar el registro detallado de errores siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4f402-136">You can turn on verbose logging for errors by following these steps.</span></span>

1. <span data-ttu-id="4f402-137">Todas las configuraciones del proyecto en las aplicaciones Finance and Operations tienen una propiedad **IsDebugMode** en la entidad **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="4f402-137">All project configurations in Finance and Operations apps have an **IsDebugMode** property in the **DualWriteProjectConfiguration** entity.</span></span> <span data-ttu-id="4f402-138">Abra la entidad **DualWriteProjectConfiguration** usando el complemento de Excel.</span><span class="sxs-lookup"><span data-stu-id="4f402-138">Open the **DualWriteProjectConfiguration** entity by using the Excel add-in.</span></span>

    > [!TIP]
    > <span data-ttu-id="4f402-139">Una manera fácil de abrir la entidad es activar el modo **Diseño** en el complemento de Excel y luego agregar **DualWriteProjectConfigurationEntity** a la hoja de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f402-139">An easy way to open the entity is to turn on **Design** mode in the Excel add-in and then add **DualWriteProjectConfigurationEntity** to the worksheet.</span></span> <span data-ttu-id="4f402-140">Para más información consulte [Abrir los datos de entidad en Excel y actualizarlos mediante el complemento de Excel](../../office-integration/use-excel-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="4f402-140">For more information, see [Open entity data in Excel and update it by using the Excel add-in](../../office-integration/use-excel-add-in.md).</span></span>

2. <span data-ttu-id="4f402-141">Estableza la propiedad **IsDebugMode** a **Sí** para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f402-141">Set the **IsDebugMode** property to **Yes** for the project.</span></span>
3. <span data-ttu-id="4f402-142">Ejecute el escenario que genera errores.</span><span class="sxs-lookup"><span data-stu-id="4f402-142">Run the scenario that is generating errors.</span></span>
4. <span data-ttu-id="4f402-143">Los registros detallados están disponibles en la tabla DualWriteErrorLog.</span><span class="sxs-lookup"><span data-stu-id="4f402-143">The verbose logs are available in the DualWriteErrorLog table.</span></span> <span data-ttu-id="4f402-144">Para buscar datos en el navegador de tablas, use la siguiente URL (reemplace **XXX** según sea apropiado):</span><span class="sxs-lookup"><span data-stu-id="4f402-144">To look up data in the table browser, use the following URL (replace **XXX** as appropriate):</span></span>

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a><span data-ttu-id="4f402-145">Verifique los errores de sincronización en la máquina virtual para la aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f402-145">Check synchronization errors on the virtual machine for the Finance and Operations app</span></span>

<span data-ttu-id="4f402-146">**Rol requerido para ver los errores:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="4f402-146">**Required role to view the errors:** System admin</span></span>

1. <span data-ttu-id="4f402-147">Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4f402-147">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="4f402-148">Abra el proyecto LCS que seleccionó para realizar la prueba de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="4f402-148">Open the LCS project that you chose to do the dual-write testing for.</span></span>
3. <span data-ttu-id="4f402-149">Seleccione el mosaico **Entornos hospedados en la nube**.</span><span class="sxs-lookup"><span data-stu-id="4f402-149">Select the **Cloud-hosted environments** tile.</span></span>
4. <span data-ttu-id="4f402-150">Use Escritorio remoto para iniciar sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f402-150">Use Remote Desktop to sign in to the virtual machine (VM) for the Finance and Operations app.</span></span> <span data-ttu-id="4f402-151">Use la cuenta local que se muestra en LCS.</span><span class="sxs-lookup"><span data-stu-id="4f402-151">Use the local account that is shown in LCS.</span></span>
5. <span data-ttu-id="4f402-152">Abra el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4f402-152">Open Event viewer.</span></span>
6. <span data-ttu-id="4f402-153">Seleccione **Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.</span><span class="sxs-lookup"><span data-stu-id="4f402-153">Select **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span>
7. <span data-ttu-id="4f402-154">Revise la lista de errores recientes.</span><span class="sxs-lookup"><span data-stu-id="4f402-154">Review the list of recent errors.</span></span>

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a><span data-ttu-id="4f402-155">Desvincular y vincular a otro entorno de Common Data Service de una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f402-155">Unlink and link another Common Data Service environment from a Finance and Operations app</span></span>

<span data-ttu-id="4f402-156">**Credenciales requeridas para desvincular el entorno:** Administrador de inquilinos Azure AD</span><span class="sxs-lookup"><span data-stu-id="4f402-156">**Required credentials to unlink the environment:** Azure AD tenant admin</span></span>

1. <span data-ttu-id="4f402-157">Iniciar sesión en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f402-157">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="4f402-158">Vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="4f402-158">Go to **Workspaces \> Data management**, and select the **Dual Write** tile.</span></span>
3. <span data-ttu-id="4f402-159">Seleccione todas las asignaciones en funcionamiento y seleccione **Detener**.</span><span class="sxs-lookup"><span data-stu-id="4f402-159">Select all running mappings, and then select **Stop**.</span></span>
4. <span data-ttu-id="4f402-160">Seleccione **Desvincular entorno**.</span><span class="sxs-lookup"><span data-stu-id="4f402-160">Select **Unlink environment**.</span></span>
5. <span data-ttu-id="4f402-161">Seleccione **Sí** para confirmar la operación.</span><span class="sxs-lookup"><span data-stu-id="4f402-161">Select **Yes** to confirm the operation.</span></span>

<span data-ttu-id="4f402-162">Ahora puede vincular un nuevo entorno.</span><span class="sxs-lookup"><span data-stu-id="4f402-162">You can now link a new environment.</span></span>
