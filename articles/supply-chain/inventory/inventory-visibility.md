---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017015"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="449b5-103">Complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="449b5-104">El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="449b5-105">Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="449b5-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="449b5-106">Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.</span><span class="sxs-lookup"><span data-stu-id="449b5-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="449b5-107">Inventory Visibility es un microservicio construido en Microsoft Dataverse, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="449b5-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="449b5-108">También es posible actualizar el índice para realizar consultas de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="449b5-109">Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros.</span><span class="sxs-lookup"><span data-stu-id="449b5-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="449b5-110">Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.</span><span class="sxs-lookup"><span data-stu-id="449b5-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="449b5-111">Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).</span><span class="sxs-lookup"><span data-stu-id="449b5-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="449b5-112">Instalar el complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="449b5-113">Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="449b5-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="449b5-114">LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="449b5-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="449b5-115">Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="449b5-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="449b5-116">Requisitos previos del complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="449b5-117">Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="449b5-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="449b5-118">Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="449b5-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="449b5-119">Asegúrese de que los requisitos previos para configurar complementos proporcionados en [Descripción general de los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ha sido completado.</span><span class="sxs-lookup"><span data-stu-id="449b5-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="449b5-120">La visibilidad de inventario no requiere vinculación de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="449b5-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="449b5-121">Póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los siguientes tres archivos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="449b5-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="449b5-122">`Inventory Visibility Integration.zip` (si la versión de Supply Chain Management que está ejecutando es anterior a la versión 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="449b5-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="449b5-123">De forma alternativa, póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los paquetes de Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="449b5-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="449b5-124">Estos paquetes pueden ser utilizados en una herramienta oficial de Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="449b5-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="449b5-125">`InventoryServiceApplication.PackageDeployer.zip` (este paquete contiene todos los cambios en el paquete `InventoryServiceBase`, además de componentes adicionales de la aplicación de interfaz de usuario)</span><span class="sxs-lookup"><span data-stu-id="449b5-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="449b5-126">Siga las instrucciones dadas en [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar una aplicación y agregar un secreto de cliente a AAD bajo su suscripción azure.</span><span class="sxs-lookup"><span data-stu-id="449b5-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="449b5-127">Registrar una aplicación</span><span class="sxs-lookup"><span data-stu-id="449b5-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="449b5-128">Agregar un secreto de lciente</span><span class="sxs-lookup"><span data-stu-id="449b5-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="449b5-129">El **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino** se utilizarán en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="449b5-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="449b5-130">Los países y regiones admitidos actualmente incluyen Canadá, Estados Unidos y la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="449b5-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="449b5-131">Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="449b5-132">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="449b5-132">Set up Dataverse</span></span>

<span data-ttu-id="449b5-133">Para configurar Dataverse para usarlo con visibilidad de inventario, primero debe preparar los requisitos previos y luego decidir si desea configurar Dataverse utilizando la herramienta Package Deployer o importando manualmente las soluciones (no tiene que hacer ambas cosas).</span><span class="sxs-lookup"><span data-stu-id="449b5-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="449b5-134">Después, instale el complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="449b5-135">En las siguientes subsecciones, se describe cómo completar cada tarea.</span><span class="sxs-lookup"><span data-stu-id="449b5-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="449b5-136">Preparar los requisitos previos de Dataverse</span><span class="sxs-lookup"><span data-stu-id="449b5-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="449b5-137">Antes de comenzar a configurar Dataverse, agregue un principio de servicio a su inquilino haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="449b5-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="449b5-138">Instale Azure AD PowerShell Module v2 como se describe en [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="449b5-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="449b5-139">Ejecute el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="449b5-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="449b5-140">Configurar Dataverse usando la herramienta Package Deployer</span><span class="sxs-lookup"><span data-stu-id="449b5-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="449b5-141">Una vez que haya cumplido los requisitos previos, utilice el siguiente procedimiento si prefiere configurar Dataverse utilizando la herramienta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="449b5-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="449b5-142">Consulte la siguiente sección para obtener detalles sobre cómo importar las soluciones manualmente (no haga ambas cosas).</span><span class="sxs-lookup"><span data-stu-id="449b5-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="449b5-143">Instale las herramientas de desarrollo como se describe en [Descargar herramientas de NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="449b5-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="449b5-144">Según los requisitos de su negocio, elija el paquete `InventoryServiceBase` o `InventoryServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="449b5-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="449b5-145">Importe las soluciones:</span><span class="sxs-lookup"><span data-stu-id="449b5-145">Import the solutions:</span></span>
    1. <span data-ttu-id="449b5-146">Para el paquete `InventoryServiceBase`:</span><span class="sxs-lookup"><span data-stu-id="449b5-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="449b5-147">Descomprima `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="449b5-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="449b5-148">Busque la carpeta `InventoryServiceBase`, el archivo `[Content_Types].xml`, el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` y el archivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="449b5-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="449b5-149">Copie cada una de estas carpetas y archivos en el directorio `.\Tools\PackageDeployment`, que se creó cuando instaló las herramientas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="449b5-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="449b5-150">Para el paquete `InventoryServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="449b5-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="449b5-151">Descomprima `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="449b5-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="449b5-152">Busque la carpeta `InventoryServiceApplication`, el archivo `[Content_Types].xml`, el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` y el archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="449b5-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="449b5-153">Copie cada una de estas carpetas y archivos en el directorio `.\Tools\PackageDeployment`, que se creó cuando instaló las herramientas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="449b5-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="449b5-154">Ejecute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="449b5-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="449b5-155">Siga las instrucciones en su pantalla para importar las soluciones.</span><span class="sxs-lookup"><span data-stu-id="449b5-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="449b5-156">Asigne roles de seguridad al usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="449b5-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="449b5-157">Abra la URL de su entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="449b5-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="449b5-158">Vaya a **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y busque el usuario llamado **#InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="449b5-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="449b5-159">Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**.</span><span class="sxs-lookup"><span data-stu-id="449b5-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="449b5-160">Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.</span><span class="sxs-lookup"><span data-stu-id="449b5-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="449b5-161">Configurar Dataverse manualmente importando soluciones</span><span class="sxs-lookup"><span data-stu-id="449b5-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="449b5-162">Una vez que haya cumplido los requisitos previos, utilice el siguiente procedimiento si prefiere configurar Dataverse importanto soluciones manualmente.</span><span class="sxs-lookup"><span data-stu-id="449b5-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="449b5-163">Consulte la sección anterior para obtener detalles sobre cómo usar la herramienta Package Deployer en su lugar (no haga ambas cosas).</span><span class="sxs-lookup"><span data-stu-id="449b5-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="449b5-164">Cree un usuario de la aplicación para la visibilidad del inventario en Dataverse:</span><span class="sxs-lookup"><span data-stu-id="449b5-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="449b5-165">Abra la URL de su entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="449b5-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="449b5-166">Ir **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y cree un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="449b5-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="449b5-167">Use el menú de vista para cambiar la vista de página a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="449b5-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="449b5-168">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="449b5-168">Select **New**.</span></span> <span data-ttu-id="449b5-169">Establezca el Id. de aplicación en *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="449b5-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="449b5-170">(El ID del objeto se cargará automáticamente cuando guarde los cambios). Puede personalizar el nombre.</span><span class="sxs-lookup"><span data-stu-id="449b5-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="449b5-171">Por ejemplo, puede cambiarlo a *Visibilidad de inventario*.</span><span class="sxs-lookup"><span data-stu-id="449b5-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="449b5-172">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="449b5-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="449b5-173">Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**.</span><span class="sxs-lookup"><span data-stu-id="449b5-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="449b5-174">Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.</span><span class="sxs-lookup"><span data-stu-id="449b5-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="449b5-175">Para obtener más información, consulte [Crear un usuario de aplicación](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="449b5-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="449b5-176">Si el idioma predeterminado de Dataverse no es **inglés**:</span><span class="sxs-lookup"><span data-stu-id="449b5-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="449b5-177">Ir **Configuración avanzada \> Administración \> Idiomas**,</span><span class="sxs-lookup"><span data-stu-id="449b5-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="449b5-178">Seleccione **Inglés (LanguageCode = 1033)** y seleccione **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="449b5-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="449b5-179">Importe el archivo `Inventory Visibility Dataverse Solution.zip`, que incluye las entidades relacionadas con la configuración de Dataverse y Power Apps:</span><span class="sxs-lookup"><span data-stu-id="449b5-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="449b5-180">Vaya a la página **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="449b5-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="449b5-181">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="449b5-181">Select **Import**.</span></span>

1. <span data-ttu-id="449b5-182">Importe el flujo de activación de la actualización de la configuración:</span><span class="sxs-lookup"><span data-stu-id="449b5-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="449b5-183">Vaya a la página de Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="449b5-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="449b5-184">Asegúrese de que la conexión que se denomina *Dataverse (heredado)* existe.</span><span class="sxs-lookup"><span data-stu-id="449b5-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="449b5-185">(Si no existe, créela).</span><span class="sxs-lookup"><span data-stu-id="449b5-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="449b5-186">Importe el archivo `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="449b5-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="449b5-187">Una vez importado, el disparador aparecerá debajo de **Mis flujos**.</span><span class="sxs-lookup"><span data-stu-id="449b5-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="449b5-188">Inicialice las siguientes cuatro variables, según la información del entorno:</span><span class="sxs-lookup"><span data-stu-id="449b5-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="449b5-189">Id. de inquilino de Azure</span><span class="sxs-lookup"><span data-stu-id="449b5-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="449b5-190">Id. de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="449b5-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="449b5-191">Secreto de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="449b5-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="449b5-192">Punto de conexión de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="449b5-193">Para obtener más información sobre esta variable, consulte la sección [Configurar la integración de visibilidad de inventario](#setup-inventory-visibility-integration) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="449b5-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="449b5-194">![Desencadenador de configuración](media/configuration-trigger.png "Desencadenador de configuración")</span><span class="sxs-lookup"><span data-stu-id="449b5-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="449b5-195">Seleccione **Encender**.</span><span class="sxs-lookup"><span data-stu-id="449b5-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="449b5-196">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="449b5-196">Install the add-in</span></span>

<span data-ttu-id="449b5-197">Para instalar el complemento de visibilidad de inventario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="449b5-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="449b5-198">Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="449b5-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="449b5-199">En la página de inicio, seleccione el proyecto donde se implementa su entorno.</span><span class="sxs-lookup"><span data-stu-id="449b5-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="449b5-200">En la página del proyecto, seleccione el entorno donde desea instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="449b5-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="449b5-201">En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno** en la sección **Integración de Power Platform**, donde puede encontrar el nombre del entorno Dataverse.</span><span class="sxs-lookup"><span data-stu-id="449b5-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="449b5-202">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="449b5-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="449b5-203">![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")</span><span class="sxs-lookup"><span data-stu-id="449b5-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="449b5-204">Seleccione el vínculo **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="449b5-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="449b5-205">Se abre una lista de complementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="449b5-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="449b5-206">En la lista, seleccione **Visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="449b5-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="449b5-207">Ingrese valores para los siguientes campos para su entorno:</span><span class="sxs-lookup"><span data-stu-id="449b5-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="449b5-208">**ID de aplicación de AAD (cliente)**</span><span class="sxs-lookup"><span data-stu-id="449b5-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="449b5-209">**Id. de suscriptor de AAD**</span><span class="sxs-lookup"><span data-stu-id="449b5-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="449b5-210">![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")</span><span class="sxs-lookup"><span data-stu-id="449b5-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="449b5-211">Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="449b5-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="449b5-212">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="449b5-212">Select **Install**.</span></span> <span data-ttu-id="449b5-213">El estado del complemento se mostrará como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="449b5-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="449b5-214">Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="449b5-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="449b5-215">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="449b5-215">Uninstall the add-in</span></span>

<span data-ttu-id="449b5-216">Para desinstalar el complemento, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="449b5-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="449b5-217">Cuando actualice LCS, el complemento de visibilidad de inventario se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="449b5-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="449b5-218">El proceso de desinstalación elimina el registro del complemento y también inicia un trabajo para limpiar todos los datos comerciales almacenados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="449b5-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="449b5-219">Consumir datos de inventario disponibles de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="449b5-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="449b5-220">Implementar el paquete de integración de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="449b5-221">Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete.</span><span class="sxs-lookup"><span data-stu-id="449b5-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="449b5-222">Luego implemente el paquete en LCS.</span><span class="sxs-lookup"><span data-stu-id="449b5-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="449b5-223">Si se produce un error de discrepancia de versión durante la implementación, debe importar manualmente el proyecto X ++ a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="449b5-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="449b5-224">Luego, cree el paquete implementable en su entorno de desarrollo e impleméntelo en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="449b5-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="449b5-225">El código se incluye con Supply Chain Management versión 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="449b5-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="449b5-226">Si está ejecutando esa versión o una posterior, la implementación no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="449b5-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="449b5-227">Asegúrese de que las siguientes funciones estén activadas en su entorno de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="449b5-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="449b5-228">(De forma predeterminada, están activadas).</span><span class="sxs-lookup"><span data-stu-id="449b5-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="449b5-229">Descripción de la característica</span><span class="sxs-lookup"><span data-stu-id="449b5-229">Feature description</span></span> | <span data-ttu-id="449b5-230">Versión de código</span><span class="sxs-lookup"><span data-stu-id="449b5-230">Code version</span></span> | <span data-ttu-id="449b5-231">Alternar clase</span><span class="sxs-lookup"><span data-stu-id="449b5-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="449b5-232">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSum</span><span class="sxs-lookup"><span data-stu-id="449b5-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="449b5-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="449b5-233">10.0.11</span></span> | <span data-ttu-id="449b5-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="449b5-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="449b5-235">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="449b5-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="449b5-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="449b5-236">10.0.12</span></span> | <span data-ttu-id="449b5-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="449b5-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="449b5-238">Configurar integración de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="449b5-239">En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active la caracterísica **Integración de visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="449b5-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="449b5-240">Ir **Gestión del inventario \> Configurar \> Parámetros de integración de visibilidad de inventario** e ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="449b5-241">Busque la región de Azure de su entorno LCS y luego ingrese la URL.</span><span class="sxs-lookup"><span data-stu-id="449b5-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="449b5-242">La URL tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="449b5-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="449b5-243">Por ejemplo, si se encuentra en Europa, su entorno tendrá una de las siguientes URL:</span><span class="sxs-lookup"><span data-stu-id="449b5-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="449b5-244">Tiene a su disposición las siguientes regiones:</span><span class="sxs-lookup"><span data-stu-id="449b5-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="449b5-245">Región de Azure</span><span class="sxs-lookup"><span data-stu-id="449b5-245">Azure region</span></span> | <span data-ttu-id="449b5-246">Nombre corto de la región</span><span class="sxs-lookup"><span data-stu-id="449b5-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="449b5-247">Este de Australia</span><span class="sxs-lookup"><span data-stu-id="449b5-247">Australia east</span></span> | <span data-ttu-id="449b5-248">eau</span><span class="sxs-lookup"><span data-stu-id="449b5-248">eau</span></span> |
    | <span data-ttu-id="449b5-249">Sudeste de Australia</span><span class="sxs-lookup"><span data-stu-id="449b5-249">Australia southeast</span></span> | <span data-ttu-id="449b5-250">seau</span><span class="sxs-lookup"><span data-stu-id="449b5-250">seau</span></span> |
    | <span data-ttu-id="449b5-251">Canadá central</span><span class="sxs-lookup"><span data-stu-id="449b5-251">Canada central</span></span> | <span data-ttu-id="449b5-252">cca</span><span class="sxs-lookup"><span data-stu-id="449b5-252">cca</span></span> |
    | <span data-ttu-id="449b5-253">Este de Canadá</span><span class="sxs-lookup"><span data-stu-id="449b5-253">Canada east</span></span> | <span data-ttu-id="449b5-254">eca</span><span class="sxs-lookup"><span data-stu-id="449b5-254">eca</span></span> |
    | <span data-ttu-id="449b5-255">Norte de Europa</span><span class="sxs-lookup"><span data-stu-id="449b5-255">North Europe</span></span> | <span data-ttu-id="449b5-256">neu</span><span class="sxs-lookup"><span data-stu-id="449b5-256">neu</span></span> |
    | <span data-ttu-id="449b5-257">Europa Occidental</span><span class="sxs-lookup"><span data-stu-id="449b5-257">West Europe</span></span> | <span data-ttu-id="449b5-258">weu</span><span class="sxs-lookup"><span data-stu-id="449b5-258">weu</span></span> |
    | <span data-ttu-id="449b5-259">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="449b5-259">East US</span></span> | <span data-ttu-id="449b5-260">eus</span><span class="sxs-lookup"><span data-stu-id="449b5-260">eus</span></span> |
    | <span data-ttu-id="449b5-261">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="449b5-261">West US</span></span> | <span data-ttu-id="449b5-262">wus</span><span class="sxs-lookup"><span data-stu-id="449b5-262">wus</span></span> |

1. <span data-ttu-id="449b5-263">Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo.</span><span class="sxs-lookup"><span data-stu-id="449b5-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="449b5-264">Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="449b5-265">API pública de complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="449b5-266">La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos para integración.</span><span class="sxs-lookup"><span data-stu-id="449b5-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="449b5-267">Admite tres tipos principales de interacción:</span><span class="sxs-lookup"><span data-stu-id="449b5-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="449b5-268">Publicar cambios de inventario disponible en el complemento desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="449b5-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="449b5-269">Consultar cantidades actuales disponibles desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="449b5-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="449b5-270">Sincronización automática con el inventario disponible de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="449b5-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="449b5-271">La sincronización automática no forma parte de la API pública.</span><span class="sxs-lookup"><span data-stu-id="449b5-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="449b5-272">En su lugar, se maneja en segundo plano para entornos en los que el complemento de visibilidad de inventario está habilitado.</span><span class="sxs-lookup"><span data-stu-id="449b5-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="449b5-273">Autentificación</span><span class="sxs-lookup"><span data-stu-id="449b5-273">Authentication</span></span>

<span data-ttu-id="449b5-274">El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="449b5-275">Por lo tanto, debe generar un *token de Azure Active Directory (Azure AD)* usando su aploicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="449b5-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="449b5-276">A continuación, debe utilizar el token de Azure AD para obtener el *token de acceso* del servicio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="449b5-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="449b5-277">Obtenga un token de servicio de seguridad de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="449b5-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="449b5-278">Inicie sesión en Azure Portal y utilícelo para encontrar el `clientId` y el `clientSecret` para su aplicación Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="449b5-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="449b5-279">Busque un token Azure Active Directory (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="449b5-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="449b5-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="449b5-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="449b5-281">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="449b5-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="449b5-282">**Contenido del cuerpo (datos del formulario)**:</span><span class="sxs-lookup"><span data-stu-id="449b5-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="449b5-283">key</span><span class="sxs-lookup"><span data-stu-id="449b5-283">key</span></span> | <span data-ttu-id="449b5-284">valor</span><span class="sxs-lookup"><span data-stu-id="449b5-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="449b5-285">client_id</span><span class="sxs-lookup"><span data-stu-id="449b5-285">client_id</span></span> | <span data-ttu-id="449b5-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="449b5-286">${aadAppId}</span></span> |
        | <span data-ttu-id="449b5-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="449b5-287">client_secret</span></span> | <span data-ttu-id="449b5-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="449b5-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="449b5-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="449b5-289">grant_type</span></span> | <span data-ttu-id="449b5-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="449b5-290">client_credentials</span></span> |
        | <span data-ttu-id="449b5-291">resource</span><span class="sxs-lookup"><span data-stu-id="449b5-291">resource</span></span> | <span data-ttu-id="449b5-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="449b5-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="449b5-293">Debería recibir un `aadToken` en respuesta, que se parece al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="449b5-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="449b5-294">Formule una solicitud JSON similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="449b5-294">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="449b5-295">Donde:</span><span class="sxs-lookup"><span data-stu-id="449b5-295">Where:</span></span>
    - <span data-ttu-id="449b5-296">El valor `client_assertion` debe ser el `aadToken` que recibió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="449b5-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="449b5-297">El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.</span><span class="sxs-lookup"><span data-stu-id="449b5-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="449b5-298">Configure todos los demás valores como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="449b5-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="449b5-299">Envíe una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="449b5-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="449b5-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="449b5-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="449b5-301">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="449b5-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="449b5-302">**Encabezado HTTP** - Incluya la versión de API (la clave es `Api-Version` y el valor es `1.0`)</span><span class="sxs-lookup"><span data-stu-id="449b5-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="449b5-303">**Contenido del cuerpo** - Incluya la solicitud JSON que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="449b5-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="449b5-304">Obtendrá `access_token` como respuesta.</span><span class="sxs-lookup"><span data-stu-id="449b5-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="449b5-305">Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="449b5-306">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="449b5-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="449b5-307">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="449b5-307">Sample Request</span></span>

<span data-ttu-id="449b5-308">Para su referencia, aquí hay una solicitud http de muestra, puede usar cualquier herramienta o lenguaje de codificación para enviar esta solicitud, como ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="449b5-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="449b5-309">Configurar la API de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="449b5-310">Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="449b5-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="449b5-311">La configuración puede variar según los detalles de su entorno.</span><span class="sxs-lookup"><span data-stu-id="449b5-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="449b5-312">Incluye principalmente cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="449b5-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="449b5-313">Partición</span><span class="sxs-lookup"><span data-stu-id="449b5-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="449b5-314">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="449b5-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="449b5-315">Indexación</span><span class="sxs-lookup"><span data-stu-id="449b5-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="449b5-316">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="449b5-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="449b5-317">Partición</span><span class="sxs-lookup"><span data-stu-id="449b5-317">Partitioning</span></span>

<span data-ttu-id="449b5-318">El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="449b5-319">Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.</span><span class="sxs-lookup"><span data-stu-id="449b5-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="449b5-320">`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="449b5-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="449b5-321">Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.</span><span class="sxs-lookup"><span data-stu-id="449b5-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="449b5-322">*Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="449b5-323">En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="449b5-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="449b5-324">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="449b5-324">Dimension configurations</span></span>

<span data-ttu-id="449b5-325">Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.</span><span class="sxs-lookup"><span data-stu-id="449b5-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="449b5-326">La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="449b5-327">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="449b5-327">Dimension type</span></span> | <span data-ttu-id="449b5-328">Nombre de dimensión</span><span class="sxs-lookup"><span data-stu-id="449b5-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="449b5-329">Producto</span><span class="sxs-lookup"><span data-stu-id="449b5-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="449b5-330">Producto</span><span class="sxs-lookup"><span data-stu-id="449b5-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="449b5-331">Producto</span><span class="sxs-lookup"><span data-stu-id="449b5-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="449b5-332">Producto</span><span class="sxs-lookup"><span data-stu-id="449b5-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="449b5-333">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="449b5-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="449b5-334">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="449b5-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="449b5-335">Ubicación</span><span class="sxs-lookup"><span data-stu-id="449b5-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="449b5-336">Ubicación</span><span class="sxs-lookup"><span data-stu-id="449b5-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="449b5-337">Estado de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="449b5-338">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="449b5-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="449b5-339">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="449b5-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="449b5-340">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="449b5-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="449b5-341">El tipo de dimensión enumerado en la tabla anterior es solo para referencia.</span><span class="sxs-lookup"><span data-stu-id="449b5-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="449b5-342">No es necesario definir el tipo de dimensión en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="449b5-343">Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="449b5-344">Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados.</span><span class="sxs-lookup"><span data-stu-id="449b5-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="449b5-345">Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="449b5-346">Las dimensiones de destino deben ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="449b5-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="449b5-347">Dimensiones predeterminadas en visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="449b5-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="449b5-348">Dimensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="449b5-348">Custom dimensions</span></span>

<span data-ttu-id="449b5-349">El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="449b5-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="449b5-350">Indexación</span><span class="sxs-lookup"><span data-stu-id="449b5-350">Indexing</span></span>

<span data-ttu-id="449b5-351">La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="449b5-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="449b5-352">La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="449b5-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="449b5-353">Actualmente, solo puede configurar índices hasta un máximo de cinco.</span><span class="sxs-lookup"><span data-stu-id="449b5-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="449b5-354">Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="449b5-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="449b5-355">Por ejemplo, si desea consultar productos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="449b5-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="449b5-356">Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.</span><span class="sxs-lookup"><span data-stu-id="449b5-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="449b5-357">En algunos casos, solo desea consultar el producto en total.</span><span class="sxs-lookup"><span data-stu-id="449b5-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="449b5-358">Tendría dos índices definidos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="449b5-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="449b5-359">El corchete vacío se agregará según el ID del producto dentro de la partición.</span><span class="sxs-lookup"><span data-stu-id="449b5-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="449b5-360">La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="449b5-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="449b5-361">En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`.</span><span class="sxs-lookup"><span data-stu-id="449b5-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="449b5-362">De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.</span><span class="sxs-lookup"><span data-stu-id="449b5-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="449b5-363">Puede poner sus criterios de consulta en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="449b5-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="449b5-364">Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="449b5-364">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

<span data-ttu-id="449b5-365">Para el campo `filters`, actualmente solo `ProductId` admite varios valores.</span><span class="sxs-lookup"><span data-stu-id="449b5-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="449b5-366">Si `ProductId` es una matriz vacía, se consultarán todos los productos.</span><span class="sxs-lookup"><span data-stu-id="449b5-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="449b5-367">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="449b5-367">Custom measurement</span></span>

<span data-ttu-id="449b5-368">Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="449b5-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="449b5-369">Sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las medidas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="449b5-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="449b5-370">Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.</span><span class="sxs-lookup"><span data-stu-id="449b5-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="449b5-371">La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="449b5-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="449b5-372">Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="449b5-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="449b5-373">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="449b5-373">Consumption system</span></span> | <span data-ttu-id="449b5-374">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="449b5-374">Calculated measurers</span></span> | <span data-ttu-id="449b5-375">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="449b5-375">Data source</span></span> | <span data-ttu-id="449b5-376">Modificador</span><span class="sxs-lookup"><span data-stu-id="449b5-376">Modifier</span></span> | <span data-ttu-id="449b5-377">Tipo de cálculo del modificador</span><span class="sxs-lookup"><span data-stu-id="449b5-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="449b5-378">Adición</span><span class="sxs-lookup"><span data-stu-id="449b5-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="449b5-379">Adición</span><span class="sxs-lookup"><span data-stu-id="449b5-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="449b5-380">Resta</span><span class="sxs-lookup"><span data-stu-id="449b5-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="449b5-381">Adición</span><span class="sxs-lookup"><span data-stu-id="449b5-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="449b5-382">Resta</span><span class="sxs-lookup"><span data-stu-id="449b5-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="449b5-383">Adición</span><span class="sxs-lookup"><span data-stu-id="449b5-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="449b5-384">Adición</span><span class="sxs-lookup"><span data-stu-id="449b5-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="449b5-385">Resta</span><span class="sxs-lookup"><span data-stu-id="449b5-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="449b5-386">Resta</span><span class="sxs-lookup"><span data-stu-id="449b5-386">Subtraction</span></span> |

<span data-ttu-id="449b5-387">Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="449b5-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="449b5-388">La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="449b5-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="449b5-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="449b5-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="449b5-390">Publicar cambios disponibles</span><span class="sxs-lookup"><span data-stu-id="449b5-390">Posting on-hand changes</span></span>

<span data-ttu-id="449b5-391">La URL exacta en la que se publicará el evento dependerá de su región geográfica.</span><span class="sxs-lookup"><span data-stu-id="449b5-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="449b5-392">Tomará la forma:</span><span class="sxs-lookup"><span data-stu-id="449b5-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="449b5-393">Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.</span><span class="sxs-lookup"><span data-stu-id="449b5-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="449b5-394">Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos.</span><span class="sxs-lookup"><span data-stu-id="449b5-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="449b5-395">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="449b5-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="449b5-396">Publicación de cambios disponibles ejemplo de consulta 1</span><span class="sxs-lookup"><span data-stu-id="449b5-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="449b5-397">Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="449b5-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="449b5-398">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="449b5-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="449b5-399">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="449b5-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="449b5-400">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="449b5-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="449b5-401">Publicación de cambios disponibles ejemplo de consulta 2</span><span class="sxs-lookup"><span data-stu-id="449b5-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="449b5-402">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="449b5-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="449b5-403">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="449b5-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="449b5-404">Propiedades de campo de documento JSON</span><span class="sxs-lookup"><span data-stu-id="449b5-404">JSON document field properties</span></span>

<span data-ttu-id="449b5-405">Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="449b5-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="449b5-406">Id. del campo</span><span class="sxs-lookup"><span data-stu-id="449b5-406">Field ID</span></span> | <span data-ttu-id="449b5-407">Descripción</span><span class="sxs-lookup"><span data-stu-id="449b5-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="449b5-408">Un ID único para el evento de cambio específico.</span><span class="sxs-lookup"><span data-stu-id="449b5-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="449b5-409">Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema.</span><span class="sxs-lookup"><span data-stu-id="449b5-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="449b5-410">El identificador de la organización vinculada al evento.</span><span class="sxs-lookup"><span data-stu-id="449b5-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="449b5-411">Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos.</span><span class="sxs-lookup"><span data-stu-id="449b5-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="449b5-412">El identificador del producto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="449b5-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="449b5-413">La cantidad por la que se debe cambiar el producto disponible.</span><span class="sxs-lookup"><span data-stu-id="449b5-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="449b5-414">Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10.</span><span class="sxs-lookup"><span data-stu-id="449b5-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="449b5-415">Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3.</span><span class="sxs-lookup"><span data-stu-id="449b5-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="449b5-416">La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación.</span><span class="sxs-lookup"><span data-stu-id="449b5-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="449b5-417">Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="449b5-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="449b5-418">Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales.</span><span class="sxs-lookup"><span data-stu-id="449b5-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="449b5-419">Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="449b5-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="449b5-420">Una bolsa dinámica de pares clave / valor.</span><span class="sxs-lookup"><span data-stu-id="449b5-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="449b5-421">Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="449b5-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="449b5-422">Consultando la corriente disponible</span><span class="sxs-lookup"><span data-stu-id="449b5-422">Querying current on-hand</span></span>

<span data-ttu-id="449b5-423">El punto final para consultar el actual disponible tendrá una URL similar:</span><span class="sxs-lookup"><span data-stu-id="449b5-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="449b5-424">Se consultará con el método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="449b5-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="449b5-425">Ejemplo 1 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="449b5-425">Current on-hand query example 1</span></span>

<span data-ttu-id="449b5-426">Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="449b5-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="449b5-427">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="449b5-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="449b5-428">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="449b5-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="449b5-429">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="449b5-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="449b5-430">Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="449b5-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="449b5-431">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="449b5-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="449b5-432">Ejemplo 2 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="449b5-432">Current on-hand query example 2</span></span>

<span data-ttu-id="449b5-433">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="449b5-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="449b5-434">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="449b5-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="449b5-435">Resultado devuelto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="449b5-435">Example return result</span></span>

<span data-ttu-id="449b5-436">Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.</span><span class="sxs-lookup"><span data-stu-id="449b5-436">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="449b5-437">Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.</span><span class="sxs-lookup"><span data-stu-id="449b5-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
