---
title: Crear una aplicación de exportación de datos recurrente
description: Este artículo muestra cómo crear una aplicación lógica de Microsoft Azure que exporta datos de Microsoft Dynamics 365 Human Resources según una programación periódica.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 97972d2179c42e9d2d672cbebb75643ef0a02a62
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114124"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="bb8e0-103">Crear una aplicación de exportación de datos recurrente</span><span class="sxs-lookup"><span data-stu-id="bb8e0-103">Create a recurring data export app</span></span>

<span data-ttu-id="bb8e0-104">Este artículo muestra cómo crear una aplicación lógica de Microsoft Azure que exporta datos de Microsoft Dynamics 365 Human Resources según una programación periódica.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="bb8e0-105">El tutorial aprovecha la interfaz de programación de aplicaciones (API) REST del paquete DMF de Human Resources para exportar los datos.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="bb8e0-106">Después de exportar los datos, la aplicación lógica guarda el paquete de datos exportados en la carpeta de Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="bb8e0-107">Escenario empresarial</span><span class="sxs-lookup"><span data-stu-id="bb8e0-107">Business scenario</span></span>

<span data-ttu-id="bb8e0-108">En un escenario empresarial típico para integraciones de Microsoft Dynamics 365, los datos deben exportarse a un sistema descendente según una programación periódica.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="bb8e0-109">Este tutorial muestra cómo exportar todos los registros de trabajo de Microsoft Dynamics 365 Human Resources y guardar la lista de trabajadores en una carpeta de OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="bb8e0-110">Los datos específicos que se exportan en este tutorial y el destino de los datos exportados son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="bb8e0-111">Puede cambiarlos fácilmente para satisfacer sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="bb8e0-112">Tecnologías utilizadas</span><span class="sxs-lookup"><span data-stu-id="bb8e0-112">Technologies used</span></span>

<span data-ttu-id="bb8e0-113">Este tutorial utiliza las siguientes tecnologías:</span><span class="sxs-lookup"><span data-stu-id="bb8e0-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="bb8e0-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- El origen de datos maestros para los trabajadores que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="bb8e0-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** - La tecnología que proporciona la orquestación y la programación de la exportación periódica.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="bb8e0-116">**[Conectores](https://docs.microsoft.com/azure/connectors/apis-list)** - La tecnología que se utiliza para conectar la aplicación lógica con los puntos de conexión requeridos.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-116">**[Connectors](https://docs.microsoft.com/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="bb8e0-117">Conector [HTTP con Azure AD](https://docs.microsoft.com/connectors/webcontents/)</span><span class="sxs-lookup"><span data-stu-id="bb8e0-117">[HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="bb8e0-118">Conector [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)</span><span class="sxs-lookup"><span data-stu-id="bb8e0-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="bb8e0-119">**[API REST de paquetes DMF](../dev-itpro/data-entities/data-management-api.md)** - La tecnología que se utiliza para activar la exportación y controlar su progreso.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-119">**[DMF package REST API](../dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="bb8e0-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** - El destino de los trabajadores exportados.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb8e0-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bb8e0-121">Prerequisites</span></span>

<span data-ttu-id="bb8e0-122">Antes de comenzar el ejercicio en este tutorial, debe tener los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="bb8e0-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="bb8e0-123">Un entorno de Human Resources que tiene permisos de nivel de administrador en el entorno.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="bb8e0-124">Una [suscripción a Azure](https://azure.microsoft.com/free/) para hospedar la aplicación lógica</span><span class="sxs-lookup"><span data-stu-id="bb8e0-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="bb8e0-125">El ejercicio</span><span class="sxs-lookup"><span data-stu-id="bb8e0-125">The exercise</span></span>

<span data-ttu-id="bb8e0-126">Al final de este ejercicio, tendrá una aplicación lógica conectada a su entorno de Human Resources y su cuenta de OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="bb8e0-127">La aplicación lógica exportará un paquete de datos de Human Resources, esperará a que se complete la exportación, descargará el paquete de datos exportado y guardará el paquete de datos en la carpeta de OneDrive for Business que especificó.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="bb8e0-128">La aplicación lógica completada se parecerá a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-128">The completed logic app will resemble the following illustration.</span></span>

![Visión general de las aplicaciones lógicas](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="bb8e0-130">Paso 1: crear un proyecto de exportación de datos en Human Resources</span><span class="sxs-lookup"><span data-stu-id="bb8e0-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="bb8e0-131">En Human Resources, cree un proyecto de exportación de datos que exporte trabajadores.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="bb8e0-132">Asigne al proyecto el nombre **Exportar trabajadores** y asegúrese de que la opción **Generar paquete de datos** está establecida en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="bb8e0-133">Agregue una sola entidad (**Trabajador**) al proyecto y seleccione el formato para exportar.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="bb8e0-134">(En este tutorial se usa el formato de Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Exportar el proyecto de datos de trabajadores](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="bb8e0-136">Recuerde el nombre del proyecto de exportación de datos.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-136">Remember the name of the data export project.</span></span> <span data-ttu-id="bb8e0-137">Lo necesitará cuando cree la aplicación lógica en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="bb8e0-138">Paso 2: crear la aplicación lógica</span><span class="sxs-lookup"><span data-stu-id="bb8e0-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="bb8e0-139">La mayor parte del ejercicio implica la creación de la aplicación lógica.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="bb8e0-140">En Azure Portal, cree una aplicación lógica.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-140">In the Azure portal, create a logic app.</span></span>

    ![Página de creación de aplicaciones lógicas](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="bb8e0-142">En Logic Apps Designer, comience con una aplicación lógica en blanco.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="bb8e0-143">Agregue un [desencadenador de programación periódica](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) para ejecutar la aplicación lógica cada 24 horas (o de acuerdo con un horario de su elección).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-143">Add a [Recurrence Schedule trigger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Cuadro de diálogo Periodicidad](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="bb8e0-145">Llame a la API REST DMF [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) para programar la exportación del paquete de datos.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-145">Call the [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="bb8e0-146">Utilice la acción **Invocar una solicitud HTTP** desde el conector HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="bb8e0-147">**URL de recurso base:** la URL del entorno de Human Resources (no incluya información de ruta/espacio de nombres).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="bb8e0-148">URI de recurso de **Azure AD**: `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="bb8e0-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="bb8e0-149">El servicio Human Resources aún no proporciona un conector que exponga todas las API que componen la API REST de paquetes DMF, como **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="bb8e0-150">En su lugar, debe llamar a las API utilizando solicitudes HTTPS sin procesar a través del conector HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="bb8e0-151">Este conector usa Azure Active Directory (Azure AD) para la autenticación y autorización en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![Conector HTTP con Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="bb8e0-153">Inicie sesión en el entorno de Human Resources a través del conector HTTP con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="bb8e0-154">Configure una solicitud HTTP **POST** para llamar a la API REST DMF **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="bb8e0-155">**Método:** POST</span><span class="sxs-lookup"><span data-stu-id="bb8e0-155">**Method:** POST</span></span>
        - <span data-ttu-id="bb8e0-156">**URL de la solicitud:** https://\<hostname\>/espacios de nombres/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="bb8e0-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="bb8e0-157">**Cuerpo de la solicitud:**</span><span class="sxs-lookup"><span data-stu-id="bb8e0-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Invocar una acción de solicitud HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="bb8e0-159">Es posible que desee cambiar el nombre de cada paso para que sea más significativo que el nombre predeterminado, **Invocar una solicitud HTTP**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="bb8e0-160">Por ejemplo, puede cambiar el nombre de este paso **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="bb8e0-161">[Inicializar una variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) para almacenar el estado de ejecución de la solicitud **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-161">[Initialize a variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Acción Inicializar variable](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="bb8e0-163">Espere hasta que el estado de ejecución de la exportación de datos sea **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="bb8e0-164">Agregar un [bucle Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) que se repite hasta que el valor de la variable **ExecutionStatus** sea **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-164">Add an [Until loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="bb8e0-165">Agregue una acción **Retrasar** que espere cinco segundos antes de sondear el estado de ejecución actual de la exportación.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Contenedor de bucle Until](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="bb8e0-167">Establezca el recuento límite en **15** para esperar un máximo de 75 segundos (15 iteraciones × 5 segundos) a que se complete la exportación.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="bb8e0-168">Si su exportación lleva más tiempo, ajuste el recuento de límites según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="bb8e0-169">Agregue una acción **Invocar solicitud HTTP** para llamar a la API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) y establezca la variable **ExecutionStatus** en el resultado de la respuesta **GetExecutionSummaryStatus**.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="bb8e0-170">Este ejemplo no realiza la comprobación de errores.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="bb8e0-171">La API **GetExecutionSummaryStatus** puede devolver estados terminales no exitosos (es decir, estados distintos de **Correcto**).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="bb8e0-172">Para obtener más información, consulte la [documentación de la API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-172">For more information, see the [API documentation](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="bb8e0-173">**Método:** POST</span><span class="sxs-lookup"><span data-stu-id="bb8e0-173">**Method:** POST</span></span>
        - <span data-ttu-id="bb8e0-174">**Url de la solicitud:** https://\<hostname\>/espacios de nombres/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="bb8e0-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="bb8e0-175">**Cuerpo de la solicitud:** body('Invocar\_una\_solicitud\_HTTP')?['valor']</span><span class="sxs-lookup"><span data-stu-id="bb8e0-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="bb8e0-176">Puede que tenga que introducir el valor de **Cuerpo de la solicitud** en la vista de código o en el editor de funciones del diseñador.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Acción Invocar una solicitud HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Acción Establecer variable](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="bb8e0-179">El valor para la acción **Establecer variable** (**body('Invocar\_una\_solicitud\_HTTP\_2')?['valor']**) diferirá del valor del cuerpo de **Invocar una solicitud HTTP 2**, aunque el diseñador mostrará los valores de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="bb8e0-180">Obtenga la URL de descarga del paquete exportado.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="bb8e0-181">Agregue una acción **Invocar solicitud HTTP** para llamar a la API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="bb8e0-182">**Método:** POST</span><span class="sxs-lookup"><span data-stu-id="bb8e0-182">**Method:** POST</span></span>
        - <span data-ttu-id="bb8e0-183">**URL de la solicitud:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="bb8e0-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="bb8e0-184">**Cuerpo de la solicitud:** {"executionId": body('GetExportedPackageURL')?['valor']}</span><span class="sxs-lookup"><span data-stu-id="bb8e0-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Acción GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="bb8e0-186">Descargue el paquete exportado.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-186">Download the exported package.</span></span>

    - <span data-ttu-id="bb8e0-187">Agregue una solicitud HTTP **GET** (una [acción del conector HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-http) incorporada) para descargar el paquete desde la URL que se devolvió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-187">Add an HTTP **GET** request (a built-in [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="bb8e0-188">**Método:** GET</span><span class="sxs-lookup"><span data-stu-id="bb8e0-188">**Method:** GET</span></span>
        - <span data-ttu-id="bb8e0-189">**URI:** body('Invocar\_una\_solicitud\_HTTP\_3').valor</span><span class="sxs-lookup"><span data-stu-id="bb8e0-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="bb8e0-190">Puede que tenga que introducir el valor de **URI** en la vista de código o en el editor de funciones del diseñador.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Acción HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="bb8e0-192">Esta solicitud no requiere ninguna autenticación adicional, porque la URL que devuelve la API **GetExportedPackageUrl** incluye un token de firmas de acceso compartido que otorga acceso para descargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="bb8e0-193">Guarde el paquete descargado utilizando el conector de [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).</span><span class="sxs-lookup"><span data-stu-id="bb8e0-193">Save the downloaded package by using the [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="bb8e0-194">Agregue una acción [Crear archivo](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) en OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-194">Add a OneDrive for Business [Create File](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="bb8e0-195">Conéctese a su cuenta de OneDrive for Business según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="bb8e0-196">**Ruta de la carpeta:** una carpeta de su elección</span><span class="sxs-lookup"><span data-stu-id="bb8e0-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="bb8e0-197">**Nombre del archivo:** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="bb8e0-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="bb8e0-198">**Contenido del archivo**: el cuerpo del paso anterior (contenido dinámico)</span><span class="sxs-lookup"><span data-stu-id="bb8e0-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Acción Crear archivo](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="bb8e0-200">Paso 3: probar la aplicación lógica</span><span class="sxs-lookup"><span data-stu-id="bb8e0-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="bb8e0-201">Para probar la aplicación lógica, seleccione el botón **Ejecutar** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="bb8e0-202">Verá que los pasos de la aplicación lógica comienzan a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="bb8e0-203">Después de 30 a 40 segundos, la aplicación lógica debería terminar de ejecutarse y la carpeta de OneDrive for Business debe incluir un nuevo archivo de paquete que contenga los trabajadores exportados.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="bb8e0-204">Si se informa una falla para cualquier paso, seleccione el paso fallido en el diseñador y examine los campos **Entradas** y **Salidas** para ello.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="bb8e0-205">Depure y ajuste el paso según sea necesario para corregir los errores.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="bb8e0-206">La siguiente ilustración muestra cómo se ve el Logic Apps Designer cuando todos los pasos de la aplicación lógica se ejecutan correctamente.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Ejecución exitosa de la aplicación lógica](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="bb8e0-208">Resumen</span><span class="sxs-lookup"><span data-stu-id="bb8e0-208">Summary</span></span>

<span data-ttu-id="bb8e0-209">En este tutorial, aprendió a usar una aplicación lógica para exportar datos de Human Resources y guardar los datos exportados en una carpeta de OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="bb8e0-210">Puede modificar los pasos de este tutorial según sea necesario para satisfacer las necesidades de su negocio.</span><span class="sxs-lookup"><span data-stu-id="bb8e0-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>


