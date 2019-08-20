---
title: Configurar e instalar tutorial Regression Suite Automation Tool
description: Este tema es un tutorial que muestra cómo configurar e instalar Regression Suite Automation Tool (RSAT).
author: kfend
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2287cb0281e920de219cb88d41cd69264911f93
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850879"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="6a957-103">Configurar e instalar tutorial Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="6a957-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="6a957-104">Este tema es un tutorial que le ayuda a configurar e iniciar la RSAT y las herramientas asociadas al uso de la RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="6a957-105">Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato PDF.</span><span class="sxs-lookup"><span data-stu-id="6a957-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="6a957-106">Conceptos clave</span><span class="sxs-lookup"><span data-stu-id="6a957-106">Key concepts</span></span>

- <span data-ttu-id="6a957-107">Comprender la instalación y la configuración de requisitos previos necesarios para las distintas aplicaciones que admite la Regression Suite Automation Tool (RSAT).</span><span class="sxs-lookup"><span data-stu-id="6a957-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="6a957-108">Comprender cómo la característica del Grabador de tareas en Microsoft Dynamics 365 for Finance and Operations, junto con Microsoft Dynamics Lifecycle Services (LCS) y Microsoft Azure DevOps, le permite crear, configurar, ejecutar, investigar e informar sobre casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-108">Understand how the Task recorder feature in Microsoft Dynamics 365 for Finance and Operations, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="6a957-109">Permitir a usuarios funcionales grabar tareas empresariales mediante el uso del Grabador de tareas en Finance and Operations, y convertir las grabaciones de tareas en un conjunto de pruebas automatizadas, sin tener que escribir código fuente.</span><span class="sxs-lookup"><span data-stu-id="6a957-109">Empower functional users to record business tasks by using Task recorder in Finance and Operations, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6a957-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="6a957-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6a957-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6a957-111">Prerequisites</span></span>

- <span data-ttu-id="6a957-112">Para este tutorial se requiere un entorno de Finance and Operations que ejecuta la versión 10.0 de Microsoft Dynamics 365 for Finance and Operations (abril de 2019) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6a957-112">A Finance and Operations environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="6a957-113">Para los clientes que utilizan Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, también se admite la Platform update 20 (PU20) o superior.</span><span class="sxs-lookup"><span data-stu-id="6a957-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="6a957-114">El usuario debe tener derechos de administración para el entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-114">The user must have admin rights to the Finance and Operations environment.</span></span>
- <span data-ttu-id="6a957-115">Debe tener acceso al LCS de suscriptor de cliente y a Azure DevOps (anteriormente conocido como Microsoft Visual Studio Team Services \[VSTS\]).</span><span class="sxs-lookup"><span data-stu-id="6a957-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="6a957-116">El usuario que crea y administra conjuntos de pruebas debe tener una licencia de Azure DevOps Test Plans o Test Manager.</span><span class="sxs-lookup"><span data-stu-id="6a957-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="6a957-117">Las licencias siguientes también le brindarán acceso a Test Plans:</span><span class="sxs-lookup"><span data-stu-id="6a957-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="6a957-118">Licencia de Visual Studio Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a957-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="6a957-119">Licencia de Visual Studio Test Professional</span><span class="sxs-lookup"><span data-stu-id="6a957-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="6a957-120">Licencia de suscriptor de plataformas de MSDN</span><span class="sxs-lookup"><span data-stu-id="6a957-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="6a957-121">RSAT debe tener acceso al entorno de prueba a través de un explorador web.</span><span class="sxs-lookup"><span data-stu-id="6a957-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="6a957-122">Para generar y editar parámetros de prueba, debe tener instalado Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="6a957-123">Configurar Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="6a957-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="6a957-124">Idoneidad del usuario</span><span class="sxs-lookup"><span data-stu-id="6a957-124">User eligibility</span></span>

<span data-ttu-id="6a957-125">Asegúrese de que el usuario se crea en Azure DevOps y tiene un nivel de suscripción que brinda acceso a Azure Test Plans.</span><span class="sxs-lookup"><span data-stu-id="6a957-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="6a957-126">Se requiere una licencia de Azure DevOps Test Plans solo si el usuario creará y administrará casos de prueba (es decir, no todos los usuarios de RSAT requieren esta licencia).</span><span class="sxs-lookup"><span data-stu-id="6a957-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="6a957-127">Para obtener información sobre los requisitos de la licencia, consulte [Requisitos de la licencia](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="6a957-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="6a957-128">Crear un proyecto nuevo de Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="6a957-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="6a957-129">RSAT utiliza Azure Devops para la administración de casos de prueba y de conjuntos de pruebas, la generación de informes y la investigación de los resultados de ejecución de las prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="6a957-130">Puede utilizar un proyecto existente de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="6a957-131">Sin embargo, si su proyecto existente de Azure DevOps se configura de modo que tenga una plantilla personalizada, recibirá un error "Error de sincronización de VSTS" cuando sincroniza casos de prueba del Modelador de procesos empresariales (BPM) a Azure DevOps (consulte la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="6a957-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="6a957-132">Si las siguientes prácticas recomendadas se han seguido para la plantilla personalizada, podrá sincronizar los casos de prueba con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="6a957-133">(Estas prácticas recomendadas aparecen en el mensaje de error.)</span><span class="sxs-lookup"><span data-stu-id="6a957-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="6a957-134">No eliminar tipos de elementos de trabajo o campos listos para usar.</span><span class="sxs-lookup"><span data-stu-id="6a957-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="6a957-135">No eliminar estados de un tipo de elemento de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6a957-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="6a957-136">No agregar campos obligatorios a un tipo de elemento de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6a957-136">Do not add any required fields to a work item type.</span></span>

![Mensaje de error con una lista de prácticas recomendadas](./media/setup_rsa_tool_02.png)

<span data-ttu-id="6a957-138">De lo contrario, para este tutorial, le recomendamos que cree un nuevo proyecto de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="6a957-139">Para obtener más información, consulte [Problemas al sincronizar a BPM usando una plantilla de proceso de Azure DevOps (VSTS)](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="6a957-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="6a957-140">Abra la URL de Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="6a957-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="6a957-141">Seleccione **Crear proyecto** en la esquina superior derecha de la página Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Botón Crear proyecto](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="6a957-143">Rellene los siguientes campos y, a continuación, seleccione **Crear**:</span><span class="sxs-lookup"><span data-stu-id="6a957-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="6a957-144">**Nombre del proyecto**</span><span class="sxs-lookup"><span data-stu-id="6a957-144">**Project name**</span></span>
    - <span data-ttu-id="6a957-145">**Control de la versión**: Seleccione **Control de versiones de Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="6a957-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="6a957-146">Tenga en cuenta que la opción predeterminada, **Git**, no es compatible.</span><span class="sxs-lookup"><span data-stu-id="6a957-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="6a957-147">**Trabajo de elemento de proceso**</span><span class="sxs-lookup"><span data-stu-id="6a957-147">**Work item process**</span></span>

    ![Cuadro de diálogo Crear nuevo proyecto](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="6a957-149">Crear un token de acceso personal</span><span class="sxs-lookup"><span data-stu-id="6a957-149">Create a personal access token</span></span>

<span data-ttu-id="6a957-150">En este tutorial, utilizará al Modelador de procesos empresariales (BPM) de LCS para crear una biblioteca del caso de prueba y sincronizar sus casos de prueba con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="6a957-151">Necesitará un token de acceso personal para sincronizar BPM con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="6a957-152">Seleccione el icono del perfil en la esquina superior derecha de la página para el proyecto de Azure DevOps y luego seleccione **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6a957-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Comando Seguridad](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="6a957-154">En el panel izquierdo, en **Seguridad**, seleccione **Tokens de acceso personal**.</span><span class="sxs-lookup"><span data-stu-id="6a957-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="6a957-155">A continuación, seleccione **Nuevo token**.</span><span class="sxs-lookup"><span data-stu-id="6a957-155">Then select **New Token**.</span></span>

    ![Botón Nuevo token en la pestaña Tokens de acceso personal en Configuración de usuario](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="6a957-157">Rellene los siguientes campos y, a continuación, seleccione **Crear**:</span><span class="sxs-lookup"><span data-stu-id="6a957-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="6a957-158">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6a957-158">**Name**</span></span>
    - <span data-ttu-id="6a957-159">**Vencimiento (UTC)**: seleccione **Personalizar definido** y use el selector de fecha para seleccionar la última fecha disponible.</span><span class="sxs-lookup"><span data-stu-id="6a957-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="6a957-160">**Ámbitos**: seleccione la opción **Acceso completo**.</span><span class="sxs-lookup"><span data-stu-id="6a957-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Cuadro de diálogo Crear un nuevo token de acceso personal](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-162">Anote el token de acceso personal que se crea.</span><span class="sxs-lookup"><span data-stu-id="6a957-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="6a957-163">Lo necesitará más adelante cuando realice la configuración de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Token de acceso personal](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="6a957-165">Configurar el proyecto LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-165">Configure the LCS project</span></span>

<span data-ttu-id="6a957-166">Necesita un proyecto de Lifecycle Services (LCS) para su biblioteca de pruebas maestra.</span><span class="sxs-lookup"><span data-stu-id="6a957-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="6a957-167">El Modelador de procesos empresariales (BPM) de LCS se utiliza como la biblioteca maestra para sus casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="6a957-168">BPM se emplea para adminsitrar y distribuir bibliotecas de prueba en proyectos de LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="6a957-169">Por ejemplo, un partner de Microsoft o un proveedor de software independiente (ISV) que crea bibliotecas de prueba publicarán casos de prueba en forma de biblioteca de BPM.</span><span class="sxs-lookup"><span data-stu-id="6a957-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="6a957-170">En BPM, los casos de prueba se organizan por proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="6a957-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="6a957-171">BPM no define el orden o la frecuencia de ejecución de la aprobación de su prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="6a957-172">Estos detalles se administran en Azure DevOps, como se describe más tarde en este tema.</span><span class="sxs-lookup"><span data-stu-id="6a957-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="6a957-173">Para su proyecto de LCS, puede usar una implementación de cliente existente o un proyecto de partner.</span><span class="sxs-lookup"><span data-stu-id="6a957-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="6a957-174">Actualizar el lenguaje LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-175">Para que la interfaz de usuario (IU) muestre correctamente los procesos empresariales, el idioma preferido de LCS debe establecerse en **Inglés (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="6a957-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="6a957-176">Vaya al proyecto de implementación de LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="6a957-177">Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha de la página y, a continuación, seleccione **Preferencia de idioma**.</span><span class="sxs-lookup"><span data-stu-id="6a957-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Comandos en el menú Configuración](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="6a957-179">En el campo **Idioma preferido**, seleccione **Inglés (Estados Unidos)** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Pestaña Preferencia de idioma en Configuración de usuario](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="6a957-181">Configurar LCS para conectarse al proyecto de Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="6a957-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="6a957-182">Si creó un nuevo proyecto de Azure DevOps anteriormente, configure el proyecto de LCS para conectarse a este.</span><span class="sxs-lookup"><span data-stu-id="6a957-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="6a957-183">De lo contrario, si su proyecto de LCS ya está conectado a su proyecto de Azure DevOps , puede continuar con la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="6a957-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="6a957-184">Vaya al proyecto de implementación de LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="6a957-185">Seleccione el botón **Menú** y, a continuación, seleccione **Configuración del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a957-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Comando Configuración del proyecto](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="6a957-187">En el panel izquierdo, seleccione **Visual Studio Team Services** y, seguidamente, seleccione **Configurar Visual Studio Team Services**.</span><span class="sxs-lookup"><span data-stu-id="6a957-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Pestaña de Visual Studio Team Services en Configuración del proyecto](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="6a957-189">En el campo **URL del sitio Azure DevOps**, introduzca la URL del sitio de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="6a957-190">En el campo **Token de acceso personal**, introduzca el token de acceso personal que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a957-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-191">Aunque VSTS ahora se conoce como Azure DevOps, para conectar LCS a su proyecto de Azure DevOps, utilice la dirección URL antigua.</span><span class="sxs-lookup"><span data-stu-id="6a957-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="6a957-192">Por ejemplo, la dirección URL de Azure DevOps que se usa en este tutorial es `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="6a957-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="6a957-193">Sin embargo, en la siguiente ilustración, se especifica como `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="6a957-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Paso 1 en la configuración de Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="6a957-195">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-195">Select **Continue**.</span></span>
6. <span data-ttu-id="6a957-196">En el campo **Poryecto de Visual Studio Team Services**, seleccione el proyecto VSTS en el sitio seleccionado para vincularlo con el proyecto de LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="6a957-197">El campo **Plantilla de proceso** se establece de forma predeterminada en **Ágil**.</span><span class="sxs-lookup"><span data-stu-id="6a957-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="6a957-198">Para una plantilla personalizada, revise la guía práctica recomendada en la sección [Crear un nuevo proyecto de Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="6a957-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="6a957-199">A continuación, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-199">Then select **Continue**.</span></span>

    ![Paso 2 en la configuración de Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="6a957-201">Revise su configuración y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-201">Review your settings, and then select **Save**.</span></span>

    ![Paso 3 en la configuración de Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="6a957-203">Seleccione **Autorizar** para autorizar LCS y acceder al sitio de Azure DevOps configurado en su nombre y para activar las características que se integran con VSTS.</span><span class="sxs-lookup"><span data-stu-id="6a957-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Botón Autorizar](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="6a957-205">Aparece un cuadro de mensaje que indica: "Se le redirigirá a un sitio externo para autorizar a LCS a conectar con Visual Studio Team Services en su nombre.</span><span class="sxs-lookup"><span data-stu-id="6a957-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="6a957-206">¿Desea continuar?"</span><span class="sxs-lookup"><span data-stu-id="6a957-206">Proceed?"</span></span> <span data-ttu-id="6a957-207">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6a957-207">Select **Yes**.</span></span>

    ![Cuadro de mensaje](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="6a957-209">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-209">Select **Accept**.</span></span>

    ![Autorizar acceso](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="6a957-211">Si es un usuario autorizado, la IU debe devolverse a la página de configuración del proyecto de LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Usuario autorizado](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="6a957-213">Crear una nueva biblioteca de BPM</span><span class="sxs-lookup"><span data-stu-id="6a957-213">Create a new BPM library</span></span>

1. <span data-ttu-id="6a957-214">Vaya al proyecto de implementación de LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="6a957-215">Seleccione el botón **Menú** y, a continuación, seleccione **Modelador de procesos empresariales**.</span><span class="sxs-lookup"><span data-stu-id="6a957-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Comando Modelador de procesos empresariales](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="6a957-217">Seleccione **Nueva biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6a957-217">Select **New library**.</span></span>

    ![Botón Nueva biblioteca](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="6a957-219">En el campo **Nombre de biblioteca**, introduzca un nombre y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6a957-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="6a957-220">Para este tutorial, asigne un nombre a la biblioteca de BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Cuadro de diálogo Crear nueva biblioteca](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="6a957-222">Abra la nueva biblioteca de BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="6a957-223">Seleccione el proceso **Proceso empresarial principal de ejemplo** y, a continuación, a la derecha, seleccione **Modo de edición**.</span><span class="sxs-lookup"><span data-stu-id="6a957-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Botón Modo de edición](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="6a957-225">Cambie el valor del campo **Nombre** y del campo **Descripción** para **Crear un producto**.</span><span class="sxs-lookup"><span data-stu-id="6a957-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="6a957-226">A continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-226">Then select **Save**.</span></span>

    ![Campos Nombre y Descripción](./media/setup_rsa_tool_24.png)

## <a name="finance-and-operations-environment"></a><span data-ttu-id="6a957-228">Entorno de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6a957-228">Finance and Operations environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="6a957-229">Requisito de versión</span><span class="sxs-lookup"><span data-stu-id="6a957-229">Version requirement</span></span>

<span data-ttu-id="6a957-230">Se requiere un entorno de prueba o de espacio aislado de Finance and Operations que ejecute la versión 10.</span><span class="sxs-lookup"><span data-stu-id="6a957-230">A Finance and Operations test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="6a957-231">Para los clientes que utilizan la versión 7.3, también se admite la Platform update 20 o superior.</span><span class="sxs-lookup"><span data-stu-id="6a957-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-232">RSAT debe tener acceso a su entorno de prueba de Finance and Operations a través de un explorador web.</span><span class="sxs-lookup"><span data-stu-id="6a957-232">RSAT must have access to your Finance and Operations test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="6a957-233">Criterios del usuario</span><span class="sxs-lookup"><span data-stu-id="6a957-233">User criteria</span></span>

<span data-ttu-id="6a957-234">El usuario debe tener derechos de administración para este entorno.</span><span class="sxs-lookup"><span data-stu-id="6a957-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="6a957-235">Configuración de ayuda para conectar con LCS</span><span class="sxs-lookup"><span data-stu-id="6a957-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="6a957-236">Este paso es necesario para conectar con LCS y poder guardar grabaciones de tareas en la biblioteca de BPM adecuada en LCS a través del cliente de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the Finance and Operations client.</span></span>

1. <span data-ttu-id="6a957-237">Abra el cliente de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-237">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="6a957-238">Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="6a957-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="6a957-239">En la pestaña **Ayuda**, en el campo **Configuración de ayuda de Lifecycle Services**, seleccione el proyecto de LCS pertinente (**RSAT** para este tutorial).</span><span class="sxs-lookup"><span data-stu-id="6a957-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Campo Configuración de ayuda de Lifecycle Services en la pestaña Ayuda](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="6a957-241">Las bibliotecas de BPM se rellenan en el proyecto de LCS apropiado.</span><span class="sxs-lookup"><span data-stu-id="6a957-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="6a957-242">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-242">Select **Save**.</span></span>
5. <span data-ttu-id="6a957-243">Es posible que tenga que actualizar el explorador para ver el contenido de la ayuda actualizado.</span><span class="sxs-lookup"><span data-stu-id="6a957-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Notificación sobre la actualización del explorador](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="6a957-245">Grabaciones de tareas</span><span class="sxs-lookup"><span data-stu-id="6a957-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-246">Asegúrese de que todas sus grabaciones de tareas comienzan en el panel principal de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-246">Make sure that all your task recordings start on the main dashboard of Finance and Operations.</span></span> <span data-ttu-id="6a957-247">Las grabaciones individuales deben ser breves y centrarse en una tarea empresarial, como la creación de un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a957-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="6a957-248">Crear una grabación de tareas y guardarla en la biblioteca de BPM</span><span class="sxs-lookup"><span data-stu-id="6a957-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="6a957-249">Cree una grabación de tareas correspondiente que pueda adjuntar al proceso empresarial simple que se creó en la nueva biblioteca de BPM.</span><span class="sxs-lookup"><span data-stu-id="6a957-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="6a957-250">Abra el cliente de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-250">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="6a957-251">En el panel principal, seleccione el botón **Configuración** (el símbolo de engranaje) y, a continuación, seleccione **Grabador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="6a957-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Comandos en el menú Configuración](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="6a957-253">Seleccione **Crear grabación**.</span><span class="sxs-lookup"><span data-stu-id="6a957-253">Select **Create recording**.</span></span>

    ![Botón Crear grabación](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="6a957-255">Rellene los campos **Nombre de la grabación** y **Descripción de la grabación** y, a continuación, seleccione **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="6a957-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Campos Nombre de la grabación y Descripción de la grabación](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="6a957-257">Grabe los pasos para crear un producto.</span><span class="sxs-lookup"><span data-stu-id="6a957-257">Record the steps for creating a product.</span></span> <span data-ttu-id="6a957-258">Cuando haya terminado, seleccione **Detener** para detener la grabación.</span><span class="sxs-lookup"><span data-stu-id="6a957-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Pasos para crear un producto](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="6a957-260">Seleccione **Guardar en Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="6a957-260">Select **Save to Lifecycle Services**.</span></span>

    ![Opciones para guardar](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="6a957-262">La información de la biblioteca se carga desde LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-262">Library information is loaded from LCS.</span></span>

    ![Indicador de progreso](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="6a957-264">Seleccione la biblioteca de BPM a la que asociar la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6a957-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="6a957-265">Para este tutorial, seleccione la biblioteca de BPM **RSAT** que se creó anteriormente y el proceso empresarial **Crear un producto** en esta.</span><span class="sxs-lookup"><span data-stu-id="6a957-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="6a957-266">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-266">Then select **OK**.</span></span>

    ![Asociar la grabación de tareas con una biblioteca de BPM y un proceso empresarial](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="6a957-268">Aparece un mesaje "El almacenamiento en Lifecycle Services se realizó correctamente".</span><span class="sxs-lookup"><span data-stu-id="6a957-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Mensaje que indica que se guardó correctamente en LCS](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="6a957-270">Si desea guardar la grabación de tareas localmente y, seguidamente, cargarla en BPM a través de LCS, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6a957-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="6a957-271">Una vez que se complete la grabación, seleccione **Guardar en este equipo**.</span><span class="sxs-lookup"><span data-stu-id="6a957-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Opciones para guardar](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="6a957-273">En la barra de notificación del explorador, seleccione **Guardar** o **Guardar como** para guardar el archivo en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="6a957-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Barra de notificación](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="6a957-275">Vaya a la biblioteca de BPM **RSAT** y seleccione el proceso empresarial para guardar la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6a957-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="6a957-276">En la pestaña **Información general**, seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Botón Cargar](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="6a957-278">Seleccione **Examinar**, y seleccione el archivo .axtr que guardó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a957-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="6a957-279">A continuación, seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-279">Then select **Upload**.</span></span>

        ![Selección del archivo .axtr que se va a cargar](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="6a957-281">Probar la sincronización de BPM a Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="6a957-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="6a957-282">Ahora que una grabación de tareas está vinculada al proceso empresarial, debe validar que el proceso empresarial y la grabación de tareas asociada se pueden sincronizar con Azure DevOps como una característica y un caso de prueba (respectivamente) mediante la característica de sincronización de VSTS en LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-283">El tipo de elemento de trabajo correspondiente que se crea en Azure DevOps variará, según la plantilla de proceso que seleccionó cuando configuró el proyecto de LCS con Azure DevOps, tal como se describe en la sección [Crear un nuevo proyecto de Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="6a957-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="6a957-284">Vaya a la biblioteca de BPM y abra la biblioteca **RSAT** que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a957-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="6a957-285">Seleccione el botón de los puntos suspensivos (**...**) y seleccione **Sincronización de VSTS**.</span><span class="sxs-lookup"><span data-stu-id="6a957-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Comando Sincronización de VSTS en el menú de puntos suspensivos](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="6a957-287">Una vez que se complete la sincronización de VSTS, aparece una pestaña **Requisitos** en el lado izquierdo e incluye el elemento de trabajo de Azure DevOps correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6a957-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-288">El elemento de trabajo que se crea en Azure DevOps tendrá el nombre de la biblioteca de BPM como prefijo del título.</span><span class="sxs-lookup"><span data-stu-id="6a957-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Pestaña Requisitos](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="6a957-290">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="6a957-290">Refresh the page.</span></span>
4. <span data-ttu-id="6a957-291">Seleccione el botón de los puntos suspensivos (**...**). Verá una opción adicional **Sincronizar casos de prueba**.</span><span class="sxs-lookup"><span data-stu-id="6a957-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="6a957-292">Seleccione esta opción.</span><span class="sxs-lookup"><span data-stu-id="6a957-292">Select this option.</span></span>

    ![Comando Sincronizar casos de prueba en el menú de puntos suspensivos](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-294">Si la opción **Sincronizar casos de prueba** no está disponible después de actualizar la página, vaya a la página principal para BPM y seleccione **Sincronizar casos de prueba** para toda la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6a957-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="6a957-295">De esta manera, fuerza de forma eficaz una sincronización para toda la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6a957-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![Selección de Sincronizar casos de prueba para toda la biblioteca](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="6a957-297">Una vez que se completen los casos de prueba, se crea un nuevo caso de prueba en la pestaña **Requisitos**.</span><span class="sxs-lookup"><span data-stu-id="6a957-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Nuevo caso de prueba en la pestaña Requisitos](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="6a957-299">Vaya a su proyecto de Azure DevOps y seleccione **Tableros \> Artículos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6a957-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Comando Artículos de trabajo en Tableros](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="6a957-301">Valide que existen el artículo de trabajo y el caso de prueba que creó a través de la sincronización de BPM.</span><span class="sxs-lookup"><span data-stu-id="6a957-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Artículo de trabajo y caso de prueba](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="6a957-303">Instalar y configurar RSAT</span><span class="sxs-lookup"><span data-stu-id="6a957-303">Install and Configure RSAT</span></span>

<span data-ttu-id="6a957-304">RSAT se puede instalar en cualquier equipo que ejecute Windows 10 y que pueda conectarse al entorno de Finance and Operations a través de un explorador Web (Internet Explorer o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="6a957-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the Finance and Operations environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-305">Antes de instalar una nueva versión de la herramienta, le recomendamos que desinstale la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="6a957-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="6a957-306">Instalar un certificado de autenticación</span><span class="sxs-lookup"><span data-stu-id="6a957-306">Install an authentication certificate</span></span>

<span data-ttu-id="6a957-307">Para habilitar una autenticación, debe generar e instalar un certificado en el mismo equipo en el que se está ejecutando RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="6a957-308">Generar un certificado</span><span class="sxs-lookup"><span data-stu-id="6a957-308">Generate a certificate</span></span>

1. <span data-ttu-id="6a957-309">Para generar un archivo de certificado, abra una ventana de Microsoft Windows PowerShell como administrador, y ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="6a957-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="6a957-310">Abra el gestor de certificados introduciendo **certlm.msc** en el cuadro de diálogo **Ejecutar** y confirme que el certificado **Certificado de prueba automatizada D365** se crea en **Personal \> Certificados**.</span><span class="sxs-lookup"><span data-stu-id="6a957-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-311">Asegúrese de introducir **certlm.msc**, no **certmgr.msc**, ya que los certificados se almacenan en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="6a957-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![Certificado de prueba automatizada D365](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="6a957-313">Haga clic con el botón secundario en el certificado y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="6a957-314">Vaya a **Entidades de certificación raíz de confianza \> Certificados**.</span><span class="sxs-lookup"><span data-stu-id="6a957-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Carpeta Certificados en el carpeta Entidades de certificación raíz de confianza](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="6a957-316">En el menú **Acción**, seleccione **Pegar** para copiar el certificado en la ubicación **Entidades de certificación raíz de confianza** .</span><span class="sxs-lookup"><span data-stu-id="6a957-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Comando Pegar en el menú Acción](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="6a957-318">Para obtener la huella digital del certificado instalado, pero sin espacios ni caracteres especiales, abra una ventana de Windows PowerShell como administrador y ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="6a957-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="6a957-319">Guarde la huella digital, ya que la necesitará más adelante cuando actualice los archivos .wif para Application Object Server (AOS) y ajuste la configuración de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="6a957-320">Configurar el equipo de AOS para que confíe en la conexión</span><span class="sxs-lookup"><span data-stu-id="6a957-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="6a957-321">Si el entorno de Finance and Operations es un entorno de nivel 2+, la huella digital del certificado debe actualizarse en el archivo wif.config para **todos** los equipos de AOS del entorno.</span><span class="sxs-lookup"><span data-stu-id="6a957-321">If the Finance and Operations environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="6a957-322">Establezca una conexión de Remote Desktop Protocol (RDP) par el equipo de AOS.</span><span class="sxs-lookup"><span data-stu-id="6a957-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="6a957-323">Los datos de inicio de sesión están disponibles en la página de detalles del entorno en LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="6a957-324">Abra Microsoft Internet Information Services (IIS) y encuentre **AOSService** en la lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="6a957-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService en la lista de sitios](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="6a957-326">Haga clic con el botón secundario en **Explorar** para abrir la carpeta **\<Drive\>: \\AosService\\WebRoot**.</span><span class="sxs-lookup"><span data-stu-id="6a957-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="6a957-327">Encuentre el archivo **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="6a957-327">Find the **wif.config** file.</span></span>

    ![Archivo wif.config en la carpeta WebRoot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="6a957-329">Actualice el archivo **wif.config** agregando una nueva entrada de la autoridad para el nombre del certificado y de la autoridad, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6a957-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="6a957-330">Si varios usuarios utilizan la misma aplicación de Finance and Operations, cada usuario debe generar huellas digitales independientes, y cada una de estas huellas digitales debe agregarse en la sección **\<claves\>** .</span><span class="sxs-lookup"><span data-stu-id="6a957-330">If multiple users are using the same Finance and Operations application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="6a957-331">Si hay más de un equipo de AOS, repita los pasos 3 a 4 para cada equipo adicional.</span><span class="sxs-lookup"><span data-stu-id="6a957-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-332">A diferencia de los entornos de nivel 2 anteriores, los nuevos entornos de nivel 2 se implementan con dos instancias de AOS.</span><span class="sxs-lookup"><span data-stu-id="6a957-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="6a957-333">Ejecute **iisreset** en todos los equipos de AOS.</span><span class="sxs-lookup"><span data-stu-id="6a957-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-334">Si no tiene derechos de administración para ejecutar **iisreset** en un equipo de nivel 1, en la página Detalles del entorno en LCS, seleccione Mantener > Reiniciar servicios.</span><span class="sxs-lookup"><span data-stu-id="6a957-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="6a957-335">Entorno de nivel 2+</span><span class="sxs-lookup"><span data-stu-id="6a957-335">Tier 2+ environment</span></span>

<span data-ttu-id="6a957-336">Si se utiliza un entorno de Finance and Operations de nivel 2+ (espacio aislado Prueba de aceptación estándar o superior), verifique o establezca la siguiente configuración de registro en el equipo en el que está instalado la RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) Finance and Operations environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="6a957-337">Este paso es necesario porque le ayuda a evitar la autenticación o errores de conexión de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="6a957-338">Instalar RSAT</span><span class="sxs-lookup"><span data-stu-id="6a957-338">Install RSAT</span></span>

1. <span data-ttu-id="6a957-339">Vaya a <https://www.microsoft.com/download/details.aspx?id=57357> y seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="6a957-340">Seleccione todos los archivos y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6a957-340">Select all the files, and then select **Next**.</span></span>

    ![Selección de todos los archivos](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="6a957-342">Haga doble clic en el paquete .msi para ejecutar el instalador.</span><span class="sxs-lookup"><span data-stu-id="6a957-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="6a957-343">Posteriormente, cuando se complete la instalación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![Archivo Instalador de RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="6a957-345">Instalar Selenium y controladores del explorador</span><span class="sxs-lookup"><span data-stu-id="6a957-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="6a957-346">En versiones anteriores de RSAT, tuvo que instalar Selenium y los controladores del explorador.</span><span class="sxs-lookup"><span data-stu-id="6a957-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="6a957-347">Ya no tendrá que instalar estos controladores porque se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6a957-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="6a957-348">La primera vez que abra la RSAT, se le pedirá que descargue e instale automáticamente Selenium.</span><span class="sxs-lookup"><span data-stu-id="6a957-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="6a957-349">Para obtener más información, consulte la sección [Configurar RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="6a957-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="6a957-350">Antes de poder ejecutar un caso de prueba, se le pedirá que descargue e instale automáticamente el controlador del explorador que corresponda al explorador predeterminado que está seleccionado en la configuración de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="6a957-351">Para obtener más información, consulte la sección [Cargar y ejecutar casos de prueba](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="6a957-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="6a957-352">Introducción a RSAT</span><span class="sxs-lookup"><span data-stu-id="6a957-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="6a957-353">Crear un plan de prueba y conjuntos de pruebas</span><span class="sxs-lookup"><span data-stu-id="6a957-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="6a957-354">Vaya al proyecto de Azure DevOps y seleccione **Planes de prueba**.</span><span class="sxs-lookup"><span data-stu-id="6a957-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Comando Planes de prueba](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="6a957-356">Seleccione **Nuevo plan de prueba**.</span><span class="sxs-lookup"><span data-stu-id="6a957-356">Select **New Test Plan**.</span></span>

    ![Botón Nuevo plan de prueba](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="6a957-358">Rellene el campo **Nombre** y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6a957-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="6a957-359">Para este tutorial, asigne un nombre al plan de prueba **Plan de prueba de RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Cuadro de diálogo Nuevo plan de prueba](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="6a957-361">Seleccione el signo más (**+**) y, a continuación, seleccione **Conjunto estático** para crear un conjunto estático en el nuevo plan de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="6a957-362">Asigne un nombre al nuevo conjunto de pruebas **T01 – Fabricar para existencias**.</span><span class="sxs-lookup"><span data-stu-id="6a957-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-363">También puede crear un conjunto basado en consultas, si desea que los nuevos casos de prueba de BPM se incluyan automáticamente en el conjunto de pruebas de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Creación de un conjunto estático](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="6a957-365">Adjuntar casos de prueba a conjuntos de pruebas</span><span class="sxs-lookup"><span data-stu-id="6a957-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="6a957-366">Seleccione **Agregar existente** en el lado derecho para agregar casos de prueba existentes al conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6a957-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Botón Agregar existente](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="6a957-368">En la página **Agregar casos de prueba a conjunto**, seleccione **Ejecutar consulta** y, seguidamente, seleccione el caso de prueba para agregar al conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6a957-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="6a957-369">Para este tutorial, seleccione el caso de prueba **Crear un nuevo producto** .</span><span class="sxs-lookup"><span data-stu-id="6a957-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="6a957-370">A continuación, seleccione **Agregar casos de prueba** en la esquina inferior derecha de la página (este botón no se muestra en la siguiente ilustración).</span><span class="sxs-lookup"><span data-stu-id="6a957-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Botón Ejecutar consulta](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="6a957-372">El caso de prueba se agrega al conjunto de pruebas **T01-Fabricar para existencias**.</span><span class="sxs-lookup"><span data-stu-id="6a957-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Caso de prueba agregado al conjunto de pruebas](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="6a957-374">Configurar RSAT</span><span class="sxs-lookup"><span data-stu-id="6a957-374">Configure RSAT</span></span>

1. <span data-ttu-id="6a957-375">Abra RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-375">Open RSAT.</span></span>

    ![Icono de RSAT](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="6a957-377">Recibe un mensaje de advertencia que dice: "La Regression Suite Automation Tool requiere Selenium, ¿desea descargarlo e instalarlo automáticamente ahora?"</span><span class="sxs-lookup"><span data-stu-id="6a957-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="6a957-378">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6a957-378">Select **Yes**.</span></span>

    ![Mensaje de advertencia](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="6a957-380">Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha y, a continuación, en el cuadro de diálogo que aparece, rellene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="6a957-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="6a957-381">**URL de Azure DevOps**: introduzca la dirección URL de su proyecto de Azure DevOps, como `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="6a957-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="6a957-382">**Token de acceso**: introduzca el token de acceso que permite a la herramienta conectarse a Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="6a957-383">Utilice el token de acceso personal que creó anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6a957-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="6a957-384">Para obtener más información, consulte [Autenticar acceso con tokens de acceso personales](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="6a957-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="6a957-385">**Nombre del proyecto**: seleccione el nombre de su proyecto de Azure DevOps .</span><span class="sxs-lookup"><span data-stu-id="6a957-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="6a957-386">**Plan de prueba**: seleccione el plan de prueba de Azure DevOps que contiene sus casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="6a957-387">Para obtener más información, consulte [Crear planes de prueba y conjuntos de pruebas](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="6a957-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="6a957-388">Tras seleccionar un plan de prueba, seleccione **Conexión de prueba** para probar su conexión a Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="6a957-389">**Nombre de host**: introduzca el nombre de host del entorno de prueba de Finance and Operations, como **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="6a957-389">**Hostname** – Enter the host name of the Finance and Operations test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="6a957-390">No incluya el prefijo **https://** o **http://**.</span><span class="sxs-lookup"><span data-stu-id="6a957-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="6a957-391">**Nombre de host de SOAP**: introduzca el nombre de host de SOAP del entorno de prueba de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-391">**SOAP Hostname** – Enter the SOAP host name of the Finance and Operations test environment.</span></span> <span data-ttu-id="6a957-392">Normalmente, el nombre de host de SOAP es el mismo que el nombre de host, pero tiene un sufijo **soap**.</span><span class="sxs-lookup"><span data-stu-id="6a957-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="6a957-393">A continuación se muestra un ejemplo: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="6a957-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="6a957-394">No incluya el prefijo **https://** o **http://**.</span><span class="sxs-lookup"><span data-stu-id="6a957-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6a957-395">Para encontrar el nombre de host y el nombre de host de SOAP, abra el Administrador de IIS, haga clic con el botón derecho en **Sitios \> AOSService** y, a continuación, seleccione **Editar enlaces**.</span><span class="sxs-lookup"><span data-stu-id="6a957-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="6a957-396">Los valores de la columna **Nombre de host** le brindan el nombre de host y el nombre de host de SOAP (el nombre de host de SOAP tiene el sufijo **soap** en la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="6a957-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Nombre de host y nombre de host de SOAP en la columna Nombre de host](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="6a957-398">**Nombre de usuario administrador**: introduzca la dirección de correo electrónico de un usuario administrador en el entorno de prueba de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-398">**Admin user name** – Enter the email address of an admin user in the Finance and Operations test environment.</span></span>
    - <span data-ttu-id="6a957-399">**Huella digital**: introduzca la huella digital del certificado de autenticación, tal como se describe anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6a957-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="6a957-400">**Directorio de trabajo**: especifique la ubicación de la carpeta para almacenar los archivos de automatización de pruebas, como archivos de datos de pruebas de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="6a957-401">Por ejemplo, introduzca o seleccione **C:\\Temp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="6a957-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6a957-402">Si el nombre de la carpeta tiene espacios, la ejecución no se realizará correctamente porque la carpeta no se puede encontrar.</span><span class="sxs-lookup"><span data-stu-id="6a957-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="6a957-403">Este problema es un problema conocido y se debe corregir en la última versión de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6a957-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="6a957-404">**Explorador predeterminado**: seleccione **Internet Explorer** o **Google Chomre**.</span><span class="sxs-lookup"><span data-stu-id="6a957-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="6a957-405">Asegúrese de que se han instalado los controladores del explorador adecuados.</span><span class="sxs-lookup"><span data-stu-id="6a957-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="6a957-406">**Tiempo de espera de ejecución de la prueba**: especifique el período de tiempo de espera, en minutos, para ejecuciones de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="6a957-407">Cuando transcurra el período de tiempo de espera, todas las ventanas activas se cierran y fallan los casos de prueba pendientes.</span><span class="sxs-lookup"><span data-stu-id="6a957-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="6a957-408">**Tiempo de espera de la acción de prueba**: este campo controla el período de tiempo de espera, en minutos, para solicitudes de servidor del entorno de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="6a957-409">Normalmente, el valor predeterminado (2 minutos) debe ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="6a957-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="6a957-410">Sin embargo, para entornos más lentos, es posible que desee aumentar el valor si se producen errores relacionados con los tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="6a957-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="6a957-411">**Nombre de la empresa**: introduzca el nombre de la empresa que se utilizará como la empresa predeterminada de Finance and Operations cuando se crea un archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-411">**Company name** – Enter the company name to use as your default Finance and Operations company when Excel parameter files are created.</span></span> <span data-ttu-id="6a957-412">Puede cambiar la empresa más adelante editando el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Cuadro de diálogo Configuración](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="6a957-414">Seleccione **Aplicar** para aplicar y guardar su configuración.</span><span class="sxs-lookup"><span data-stu-id="6a957-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="6a957-415">Para guardar su configuración actual en un archivo de configuración en su equipo, seleccione **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="6a957-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="6a957-416">Para restaurar su configuración desde un archivo de configuración en su equipo, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6a957-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="6a957-417">Haga clic en **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6a957-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="6a957-418">Cargar y ejecutar casos de prueba</span><span class="sxs-lookup"><span data-stu-id="6a957-418">Load and run test cases</span></span>

1. <span data-ttu-id="6a957-419">Seleccione **Cargar** para cargar el plan de prueba **Plan de prueba de RSAT** desde el proyecto de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Botón Cargar](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="6a957-421">Seleccione el caso de prueba **Crear un nuevo producto** desde el conjunto de pruebas y, a continuación, seleccione **Nuevo \> Generar archivos Ejecución de prueba y Parámetro**.</span><span class="sxs-lookup"><span data-stu-id="6a957-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Comando Generar archivos Ejecución de prueba y Parámetro en el menú Nuevo](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="6a957-423">El archivo de parámetros de Excel se crea en la carpeta local que especificó en la configuración de RSAT (por ejemplo, **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="6a957-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![Archivo de parámetros de Excel creado](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="6a957-425">Si desea guardar los archivos de parámetros, seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="6a957-426">Los archivos de automatización de pruebas de todos los casos de prueba seleccionados se cargan en Azure DevOps para un uso posterior.</span><span class="sxs-lookup"><span data-stu-id="6a957-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="6a957-427">(Estos archivos incluyen archivos de parámetros de prueba de Excel.)</span><span class="sxs-lookup"><span data-stu-id="6a957-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="6a957-428">De esta manera, puede seleccionar **Cargar** para cargar archivos de parámetros (y archivos de automatización) del caso de prueba directamente desde Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="6a957-429">No es necesario volver a generar los archivos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="6a957-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="6a957-430">Este enfoque será importante más adelante, cuando quiera mantener las modificaciones en el archivo de parámetros y no quiera que se sobrescriban.</span><span class="sxs-lookup"><span data-stu-id="6a957-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="6a957-431">Para verificar que los archivos de automatización y los archivos de parámetros se guardan en Azure DevOps, vaya al proyecto de Azure DevOps, seleccione **Tableros \> Artículos de trabajo** y seleccione el caso de prueba **Crear un nuevo producto**.</span><span class="sxs-lookup"><span data-stu-id="6a957-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="6a957-432">En la pestaña **Archivos adjuntos**, debe ver cuatro archivos:</span><span class="sxs-lookup"><span data-stu-id="6a957-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="6a957-433">**.cs** – Archivo de automatización C\#</span><span class="sxs-lookup"><span data-stu-id="6a957-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="6a957-434">**.dll** – Archivo de automatización compilado como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="6a957-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="6a957-435">**.xlsx** – Archivo de parámetros de Excel</span><span class="sxs-lookup"><span data-stu-id="6a957-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="6a957-436">**.xml** – Archivo de las grabaciones</span><span class="sxs-lookup"><span data-stu-id="6a957-436">**.xml** – Recording file</span></span>

    ![Archivos en la pestaña Archivos adjuntos](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="6a957-438">Seleccione el caso de prueba que desea ejecutar y, a continuación, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-439">Antes de ejecutar los casos de prueba, si utiliza Internet Explorer como el explorador, asegúrese de que la resolución de su escritorio está establecida en **100%** en **Configuración de la pantalla de Windows \> Escala y diseño**.</span><span class="sxs-lookup"><span data-stu-id="6a957-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="6a957-440">Si no puede cambiar esta configuración en una máquina virtual (VM), cámbiela en el cliente (portátil) desde el que está intentando acceder a la VM.</span><span class="sxs-lookup"><span data-stu-id="6a957-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="6a957-441">La configuración de la resolución será heredada por la configuración de la pantalla de la VM.</span><span class="sxs-lookup"><span data-stu-id="6a957-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Resolución del escritorio establecida en 100%](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="6a957-443">Si los controladores del explorador no están instalados en el sistema, recibirá un mensaje de advertencia que dice: "Esta operación requiere el controlador del \<nombre del explorador\>.</span><span class="sxs-lookup"><span data-stu-id="6a957-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="6a957-444">¿Desea descargarlo e instalarlo automáticamente ahora?"</span><span class="sxs-lookup"><span data-stu-id="6a957-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="6a957-445">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6a957-445">Select **Yes**.</span></span>

    ![Mensaje de advertencia para Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Mensaje de advertencia para Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-448">Si utiliza Chrome como el explorador y recibe un mensaje de error que indica que la sesión no se creó porque la versión de Chrome no es correcta, descargue el último controlador de Chrome desde <http://chromedriver.chromium.org/downloads> a la carpeta **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool\\Común\\Externo\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="6a957-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Mensaje de error para Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="6a957-450">Se ejecuta el caso de prueba y se actualiza el campo **Resultado**.</span><span class="sxs-lookup"><span data-stu-id="6a957-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Indicador de progreso](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="6a957-452">Si ha seguido este tutorial tal y como está escrito, el caso de prueba **Crear un nuevo producto** no se realizará correctamente porque la grabación de tareas para la creación de un producto guardó el nombre del producto como un valor codificado.</span><span class="sxs-lookup"><span data-stu-id="6a957-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="6a957-453">Si vuelve a ejecutar el mismo caso de prueba, debe recibir un mensaje de error, ya que el producto ya existe.</span><span class="sxs-lookup"><span data-stu-id="6a957-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Campo Resultado establecido en Fallido](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="6a957-455">Ver los resultados de la prueba</span><span class="sxs-lookup"><span data-stu-id="6a957-455">View the test results</span></span>

1. <span data-ttu-id="6a957-456">Haga doble clic en el caso de prueba fallido.</span><span class="sxs-lookup"><span data-stu-id="6a957-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="6a957-457">Recibe un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6a957-457">You receive an error message.</span></span>

    ![Mensaje de error](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="6a957-459">Seleccione **Detalles** para ver el mensaje de error completo.</span><span class="sxs-lookup"><span data-stu-id="6a957-459">Select **Details** to view the whole error message.</span></span>

    ![Mensaje de error completo](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="6a957-461">Para ver una versión detallada del mensaje de error en Azure DevOps, seleccione **Abrir en Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="6a957-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="6a957-462">En Azure DevOps, puede ver el estado del caso de prueba y el mensaje de error detallado.</span><span class="sxs-lookup"><span data-stu-id="6a957-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Mensaje de error detallado en Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="6a957-464">Para ver los resultados de la prueba directamente en el proyecto de Azure DevOps , vaya a **Planes de prueba \> Planes de prueba \> Ejecuciones**.</span><span class="sxs-lookup"><span data-stu-id="6a957-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="6a957-465">Haga doble clic en la ejecución de la prueba sobre la que desea ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="6a957-465">Double-click the test run that you want to see more details for.</span></span>

    ![Lista de ejecuciones de pruebas en Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="6a957-467">La pestaña **Resumen de la ejecución** indica que el caso de prueba ha fallado, aunque no proporciona el mensaje de error real.</span><span class="sxs-lookup"><span data-stu-id="6a957-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="6a957-468">Para ver el mensaje de error detallado, seleccione la pestaña **Resultados de la prueba**.</span><span class="sxs-lookup"><span data-stu-id="6a957-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Pestaña Resumen de la ejecución](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="6a957-470">La pestaña **Resultados de la prueba** proporciona información sobre el caso de la prueba, junto con el resultado y el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6a957-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Pestaña Resultados de prueba](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="6a957-472">Haga doble clic en el registro relevante para ver el mensaje de error detallado.</span><span class="sxs-lookup"><span data-stu-id="6a957-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Mensaje de error detallado](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-474">Todos los mensajes de error están disponibles localmente en **C:\\Usuarios\\\$YourUserName\\AppData\\Roaming\\RegressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="6a957-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="6a957-475">También puede exportar los resultados de la prueba del nivel del plan de prueba seleccionando **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Exportación de un plan de prueba](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="6a957-477">Modificar el archivo de parámetros de Excel</span><span class="sxs-lookup"><span data-stu-id="6a957-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="6a957-478">Abra RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-478">Open RSAT.</span></span>
2. <span data-ttu-id="6a957-479">Seleccione el caso de prueba y, a continuación. seleccione **Editar** para abrir el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="6a957-480">En la hoja **EcoResProductCreate**, compruebe que el valor del campo **Código de producto** está codificado.</span><span class="sxs-lookup"><span data-stu-id="6a957-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="6a957-481">Debe actualizar este campo a un nuevo código de producto antes de volver a ejecutar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="6a957-482">Para generar un código de producto único para cada ejecución sin tener que volver a abrir el archivo de parámetros de Excel y actualizar manualmente el código de producto cada vez, utilice la siguiente fórmula de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="6a957-483">Además de la pestaña **General**, el archivo de parámetros de Excel contiene una pestaña de datos para cada página del formulario de Finance and Operations que visita el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every Finance and Operations form page the test case visits.</span></span>

    ![Campo Código de producto](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="6a957-485">Seleccione **Guardar** y, a continuación, cierre el libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="6a957-486">Seleccione **Cargar** para guardar el archivo de parámetros de Excel en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Mensaje de carga correcta](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-488">Para ejecutar casos de prueba en un determinado contexto del usuario, introduzca el id. de correo electrónico del usuario en el campo **Usuario de la prueba** en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="6a957-489">En la última versión de RSAT, se ha actualizado el diseño de los campos en el archivo de parámetros de Excel, pero el concepto permanece igual.</span><span class="sxs-lookup"><span data-stu-id="6a957-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Campo Usuario de la prueba](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="6a957-491">Validar los resultados</span><span class="sxs-lookup"><span data-stu-id="6a957-491">Validate the results</span></span>

- <span data-ttu-id="6a957-492">Seleccione **Ejecutar** para volver a ejecutar el caso de prueba y verifique que se ha aprobado el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="6a957-493">Puede ver los resultados de la prueba tal y como se descibe en la sección [Ver los resultados de la prueba](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="6a957-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Campo Resultado establecido en Aprobado](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="6a957-495">Encadenamiento de casos de prueba</span><span class="sxs-lookup"><span data-stu-id="6a957-495">Chaining of test cases</span></span>

<span data-ttu-id="6a957-496">Una característica clave de RSAT es el encadenamiento de casos de prueba (es decir, la capacidad de una prueba para transferir valores a otras pruebas).</span><span class="sxs-lookup"><span data-stu-id="6a957-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="6a957-497">Los casos de prueba se ejecutan según el pedido definido en el plan de prueba de Azure DevOps .</span><span class="sxs-lookup"><span data-stu-id="6a957-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="6a957-498">(Este pedido también se puede actualizar en la propia herramienta de prueba.) Por lo tanto, si desea transferir variables desde un caso de prueba a otro, es muy importante que las pruebas estén en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="6a957-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="6a957-499">En esta sección, creará una variable guardada en el primer caso de prueba, creará un segundo caso de prueba y transferirá la variable guardada del primer caso de prueba al segundo caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="6a957-500">A continuación, ejecutará los casos de prueba como un caso de prueba encadenado en RSAT.</span><span class="sxs-lookup"><span data-stu-id="6a957-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="6a957-501">Modificar una grabación de tareas existente para crear una variable guardada</span><span class="sxs-lookup"><span data-stu-id="6a957-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="6a957-502">Abra el cliente de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a957-502">Open the Finance and Operations client.</span></span>
2. <span data-ttu-id="6a957-503">Seleccione el botón **Configuración** (el símbolo de engranaje) y, a continuación, seleccione **Grabador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="6a957-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="6a957-504">Seleccione **Editar grabación**.</span><span class="sxs-lookup"><span data-stu-id="6a957-504">Select **Edit Recording**.</span></span>

    ![Botón Editar grabación](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="6a957-506">Seleccione **Abrir desde Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="6a957-506">Select **Open from Lifecycle Services**.</span></span>

    ![Botón Abrir desde Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="6a957-508">Seleccione **Seleccionar la biblioteca de Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="6a957-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Botón Seleccionar la biblioteca de Lifecycle Services](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="6a957-510">Las bibliotecas de BPM se cargan desde LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-510">BPM libraries are loaded from LCS.</span></span>

    ![Indicador de progreso](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="6a957-512">Una vez que las bibliotecas de BPM se carguen desde LCS, seleccione la biblioteca de BPM **RSAT** y el proceso empresarial **Crear un nuevo producto** con el que se asoció la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6a957-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="6a957-513">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-513">Then select **OK**.</span></span>

    ![Selección de una biblioteca de BPM y un proceso de negocio](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="6a957-515">El nombre de la grabación de tareas adecuada se introduce en el campo **Nombre de la grabación**.</span><span class="sxs-lookup"><span data-stu-id="6a957-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="6a957-516">Seleccione **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="6a957-516">Select **Start**.</span></span>

    ![Nombre de la grabación de tareas en el campo Nombre de la grabación](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="6a957-518">Vaya a **Gestión de información de productos \> Productos** y seleccione **Nuevo** para abrir la página en la que se grabó la grabación de tareas original **Crear un producto**.</span><span class="sxs-lookup"><span data-stu-id="6a957-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="6a957-519">Seleccione **Insertar paso**.</span><span class="sxs-lookup"><span data-stu-id="6a957-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-520">El nuevo paso se inserta **después** del paso que seleccionó en el panel.</span><span class="sxs-lookup"><span data-stu-id="6a957-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Botón Insertar paso](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="6a957-522">Haga clic con el botón secundario en el campo **Código de producto** y, a continuación, seleccione **Grabador de tareas \> Copiar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Comando Copiar](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="6a957-524">Se agrega un nuevo paso al panel.</span><span class="sxs-lookup"><span data-stu-id="6a957-524">A new step is added in the pane.</span></span> <span data-ttu-id="6a957-525">Anote el valor en el campo **Código de producto**, puesto que lo necesitará más adelante.</span><span class="sxs-lookup"><span data-stu-id="6a957-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Nuevo paso agregado](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="6a957-527">Seleccione **Edición finalizada**.</span><span class="sxs-lookup"><span data-stu-id="6a957-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="6a957-528">Seleccione **Guardar en Lifecycle Services** y asocie la nueva grabación de tareas con la misma biblioteca de BPM y el proceso empresarial con el que se asoció la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6a957-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="6a957-529">Para obtener más información, consulte la sección [Crear una grabación de tareas y guardarla en la biblioteca de BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="6a957-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="6a957-530">Vaya a la biblioteca de BPM y seleccione **Sincronizar casos de prueba** para sobrescribir la grabación de tareas vinculada al caso de prueba en Azure DevOps, tal y como se describe en la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="6a957-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="6a957-531">Abra RSAT y seleccione **Cargar** para recargar todos los casos de prueba del conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6a957-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="6a957-532">Debe volver a generar los archivos de automatización y de parámetros para el caso de prueba adecuado seleccionando el caso de prueba y luego seleccionandolo **Nuevo \> Generar archivos Ejecución de prueba y Parámetro**, tal y como se describe en la sección [Cargar y ejecutar casos de prueba](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="6a957-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-533">Si el archivo de parámetros de Excel se deja abierto, la regeneración fallará.</span><span class="sxs-lookup"><span data-stu-id="6a957-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="6a957-534">Por lo tanto, asegúrese de que el archivo de de parámetros de Excel para el caso de prueba está cerrado antes de generar el nuevo archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="6a957-535">Seleccione **Editar** para abrir el nuevo archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="6a957-536">Verá una nueva entrada **Variable guardada** en la línea 9.</span><span class="sxs-lookup"><span data-stu-id="6a957-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="6a957-537">Esta variable, **{{EcoResProductCreate\_Identificación\_ProductNumber\_Copia}}** se guarda en el archivo XML de la grabación de tareas y se puede utilizar en pruebas posteriores.</span><span class="sxs-lookup"><span data-stu-id="6a957-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Entrada de variable guardada](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="6a957-539">Crear un nuevo caso de prueba</span><span class="sxs-lookup"><span data-stu-id="6a957-539">Create a new test case</span></span>

1. <span data-ttu-id="6a957-540">Vaya a la biblioteca de BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="6a957-541">Seleccione el proceso **Proceso empresarial de soporte de ejemplo** y, a continuación, a la derecha, seleccione **Modo de edición**.</span><span class="sxs-lookup"><span data-stu-id="6a957-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="6a957-542">Cambie el valor del campo **Nombre** y del campo **Descripción** para **Lanzar un producto**.</span><span class="sxs-lookup"><span data-stu-id="6a957-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="6a957-543">A continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-543">Then select **Save**.</span></span>

    ![Nombre y descripción cambiados para Lanzar un producto](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="6a957-545">Crear una nueva grabación de tareas que tenga una función Validar</span><span class="sxs-lookup"><span data-stu-id="6a957-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="6a957-546">Cree una grabación de tareas para lanzar el producto que se creó anteriormente en la entidad jurídica de USRT.</span><span class="sxs-lookup"><span data-stu-id="6a957-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="6a957-547">Para obtener más información, consulte la sección [Crear una grabación de tareas y guardarla en la biblioteca de BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="6a957-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a957-548">Para los casos de prueba encadenados, le recomendamos que busque o filtre la grabación que necesita *escribiendo manualmente el valor del campo*.</span><span class="sxs-lookup"><span data-stu-id="6a957-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="6a957-549">De esa manera, la herramienta puede determinar el registro que debe realizar la acción en el caso de prueba posterior.</span><span class="sxs-lookup"><span data-stu-id="6a957-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Nueva grabación de tareas que tenga una función Validar](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="6a957-551">Como se muestra en la ilustración anterior, después de encontrar el producto usando el filtro rápido, pero antes de seleccionar **Lanzar productos**, valide el valor del campo **Código de producto** para asegurarse de que el id. del producto es el id. del producto que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6a957-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="6a957-552">Para validar el valor, haga clic con el botón secundario en el campo **Código de producto** y, a continuación, seleccione **Grabador de tareas \> Validar \> Valor actual**.</span><span class="sxs-lookup"><span data-stu-id="6a957-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Validación del valor actual](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="6a957-554">Guardar la grabación de tareas en BPM</span><span class="sxs-lookup"><span data-stu-id="6a957-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="6a957-555">Una vez que se complete la grabación de tareas, seleccione **Guardar en Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="6a957-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Opciones para guardar](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="6a957-557">La información de la biblioteca se carga desde LCS.</span><span class="sxs-lookup"><span data-stu-id="6a957-557">Library information is loaded from LCS.</span></span>

    ![Indicador de progreso](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="6a957-559">Seleccione la biblioteca de BPM a la que asociar la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6a957-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="6a957-560">Para este tutorial, seleccione la biblioteca de BPM **RSAT** que se creó anteriormente y el proceso empresarial **Lanzar un producto** en esta.</span><span class="sxs-lookup"><span data-stu-id="6a957-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="6a957-561">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="6a957-562">Sincronizar BPM con Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="6a957-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="6a957-563">Vaya a la biblioteca de BPM y abra la biblioteca **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="6a957-564">Seleccione **Sincronización de VSTS** y luego **Sincronizar casos de prueba**.</span><span class="sxs-lookup"><span data-stu-id="6a957-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="6a957-565">Para obtener más información, consulte la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="6a957-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="6a957-566">Una vez que se complete la sincronización, el nuevo artículo de trabajo y el caso de prueba correspondiente para el proceso empresarial **Lanzar un producto** aparecerán en Azure DevOps en **Tableros \> Artículos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6a957-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="6a957-567">Agregar nuevo caso de prueba al conjunto de prueba existente</span><span class="sxs-lookup"><span data-stu-id="6a957-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="6a957-568">Vaya a **Planes de prueba \> Planes de prueba** y seleccione el plan **Plan de prueba de RSAT**.</span><span class="sxs-lookup"><span data-stu-id="6a957-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="6a957-569">Seleccionar **Agregar existente**.</span><span class="sxs-lookup"><span data-stu-id="6a957-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="6a957-570">En la página **Agregar casos de prueba al conjunto**, seleccione **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="6a957-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="6a957-571">Seleccione el nuevo caso de prueba que se creó para **Lanzar un producto** y, a continuación, seleccione **Agregar casos de prueba** en la esquina inferior derecha de la página (este botón no se muestra en la siguiente ilustración).</span><span class="sxs-lookup"><span data-stu-id="6a957-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Página Agregar casos de prueba a conjunto](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="6a957-573">El conjunto d epruebas ahora tiene dos casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-573">The test suite now has two test cases.</span></span>

    ![Dos casos de prueba en el conjunto de pruebas](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="6a957-575">Cargar casos de prueba en RSAT</span><span class="sxs-lookup"><span data-stu-id="6a957-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="6a957-576">Abra RSAT y seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="6a957-577">Se cargan los casos de prueba y recibe una advertencia que dice: "Esta acción sobrescribirá los archivos de datos de pruebas de Excel, se perderán los cambios locales.</span><span class="sxs-lookup"><span data-stu-id="6a957-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="6a957-578">¿Desea continuar?"</span><span class="sxs-lookup"><span data-stu-id="6a957-578">Do you want to proceed?"</span></span> <span data-ttu-id="6a957-579">Seleccione **Sí** para actualizar los archivos de parámetros de Excel en el sistema local, pero no los archivos de parámetros de Excel que se cargaron en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Mensaje de advertencia](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="6a957-581">Se cargan los dos casos de prueba, junto con el archivo de parámetros de Excel para el primer caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="6a957-582">Puesto que seleccionó **Cargar** en la última ejecución, los archivos de parámetros se extraen de Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6a957-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Casos de prueba caragdos](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="6a957-584">Seleccione solo el segundo caso de prueba y, a continuación, seleccione **Nuevo \> Generar archivos de ejecución de prueba y parámetro**.</span><span class="sxs-lookup"><span data-stu-id="6a957-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="6a957-585">Editar el archivo de parámetros de Excel</span><span class="sxs-lookup"><span data-stu-id="6a957-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="6a957-586">Seleccione solo el segundo caso de prueba y, a continuación. seleccione **Editar** para abrir el archivo de parámetros de Excel correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6a957-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="6a957-587">Copie la variable guardada **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (consulte la sección [Modificar una grabación de tareas existente para crear una variable guardada](#modify-an-existing-task-recording-to-create-a-saved-variable)) deel primer caso de prueba en todos los campos en los que se utiliza el código de producto.</span><span class="sxs-lookup"><span data-stu-id="6a957-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="6a957-588">En este caso, copie la variable en los campos **Código de producto** y **Validar código de producto** en la hoja **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="6a957-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Campos Código de producto y Validar código de producto](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="6a957-590">Las variables se pueden transferir entre las pruebas solo durante la misma prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="6a957-591">Los nombres de las variables deben coincidir exactamente.</span><span class="sxs-lookup"><span data-stu-id="6a957-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="6a957-592">Seleccione **Guardar** y, a continuación, cierre el libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="6a957-593">Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6a957-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="6a957-594">Ejecutar los casos de prueba encadenados</span><span class="sxs-lookup"><span data-stu-id="6a957-594">Run the chained test cases</span></span>

1. <span data-ttu-id="6a957-595">Seleccione ambos casos de prueba y, a continuación, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6a957-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="6a957-596">Verifique que se hayan aprobado ambos casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6a957-596">Verify that both test cases have passed.</span></span>

    ![Campo Resultado establecido en aprobado para ambos casos de prueba](./media/setup_rsa_tool_105.png)
