---
title: Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas
description: Los pasos de este tema explican cómo un usuario de Regulatory Configuration Service (RCS) puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d3581f6ae2d91b9648da3ba69e6b1d36cd08196
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727061"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="e34d4-103">Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas</span><span class="sxs-lookup"><span data-stu-id="e34d4-103">Access application metadata by using connected applications</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e34d4-104">En los pasos siguientes se explica cómo un usuario de Regulatory Configuration Service (RCS) con el rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e34d4-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="e34d4-105">Se accederá en línea a los metadatos de la aplicación mediante el uso de la aplicación conectada de RCS.</span><span class="sxs-lookup"><span data-stu-id="e34d4-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="e34d4-106">La asignación del modelo de ER de ejemplo se configurará para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="e34d4-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="e34d4-107">Para completar estos pasos, en RCS primero debe completar los pasos del tema [Creación de un proveedor de configuraciones y marcarlo como activo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e34d4-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="e34d4-108">Si no ha completado los pasos del tema [Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), vaya a la [Página de ejemplos de informes electrónicos](https://go.microsoft.com/fwlink/?linkid=862266) para descargar y guardar las siguientes configuraciones de ER: Metadatos de comercio exterior.xml; Modelo de comercio exterior.xml; Asignación de comercio exterior.xml y, a continuación, complete los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e34d4-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e34d4-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e34d4-109">Prerequisites</span></span>
1. <span data-ttu-id="e34d4-110">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="e34d4-111">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e34d4-112">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Creación de un proveedor de configuración y marcarlo como activo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e34d4-112">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="e34d4-113">Obtener las configuraciones de ER necesarias</span><span class="sxs-lookup"><span data-stu-id="e34d4-113">Get required ER configurations</span></span>
1. <span data-ttu-id="e34d4-114">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="e34d4-115">Si ya ha completado los pasos del procedimiento [(RCS) Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), ya tiene todas las configuraciones de ER necesarias (configuraciones de metadatos, modelo y asignación de comercio exterior) en la instancia de RCS actual.</span><span class="sxs-lookup"><span data-stu-id="e34d4-115">If you already completed the steps in the [(RCS) Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="e34d4-116">Puede omitir todos los pasos restantes de esta subtarea.</span><span class="sxs-lookup"><span data-stu-id="e34d4-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="e34d4-117">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="e34d4-118">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="e34d4-119">Haga clic en **Examinar** y seleccione el archivo **Metadatos de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="e34d4-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-120">Click **OK**.</span></span> 
7. <span data-ttu-id="e34d4-121">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="e34d4-122">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="e34d4-123">Haga clic en **Examinar** y seleccione el archivo **Modelo de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="e34d4-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-124">Click **OK**.</span></span> 
11. <span data-ttu-id="e34d4-125">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="e34d4-126">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="e34d4-127">Haga clic en **Examinar** y seleccione el archivo **Asignación de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="e34d4-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-128">Click **OK**.</span></span> 

## <a name="register-connected-dynamics-365-for-finance-and-operations-application"></a><span data-ttu-id="e34d4-129">Registrar aplicación conectada de Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e34d4-129">Register connected Dynamics 365 for Finance and Operations application</span></span>
1. <span data-ttu-id="e34d4-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-130">Close the page.</span></span> 
2. <span data-ttu-id="e34d4-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-131">Close the page.</span></span> 
3. <span data-ttu-id="e34d4-132">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="e34d4-133">Haga clic en **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="e34d4-134">Asegúrese de que la aplicación configurada se basa en Azure y el usuario actual de RCS puede acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="e34d4-134">Make sure that the configured application is Azura based and accessible for the current RCS user.</span></span> <span data-ttu-id="e34d4-135">También se requiere que el usuario actual de RCS tenga acceso a la aplicación seleccionada y se haya registrado como usuario de esta aplicación con un rol que le dé privilegios para acceder a los metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e34d4-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving him privileges to access application’s metadata.</span></span> 
6. <span data-ttu-id="e34d4-136">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-136">Click **New**.</span></span> 
7. <span data-ttu-id="e34d4-137">En el campo **Nombre**, escriba 'MyConnectedApp'.</span><span class="sxs-lookup"><span data-stu-id="e34d4-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="e34d4-138">En el campo **Aplicación**, escriba 'https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="e34d4-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="e34d4-139">En el campo **Inquilino**, escriba ‘mycompany.onmicrosoft.com’.</span><span class="sxs-lookup"><span data-stu-id="e34d4-139">In the **Tenant** field, type ‘mycompany.onmicrosoft.com’.</span></span> 
10. <span data-ttu-id="e34d4-140">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-140">Click **Save**.</span></span> 
11. <span data-ttu-id="e34d4-141">Cuando compruebe la conexión a la aplicación configurada, en la página **Conectar con aplicación remota**, haga clic en el vínculo **Haga clic aquí para conectarse a la aplicación remota seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="e34d4-142">Haga clic en **Comprobar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="e34d4-143">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-143">Click **Close**.</span></span> 
14. <span data-ttu-id="e34d4-144">Cuando la validación de la conexión fue correcta, se actualizarán los detalles de la versión y del inquilino para la aplicación configurada en la cuadrícula actual.</span><span class="sxs-lookup"><span data-stu-id="e34d4-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="e34d4-145">Revisar configuración de asignación existente del modelo</span><span class="sxs-lookup"><span data-stu-id="e34d4-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="e34d4-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-146">Close the page.</span></span> 
2. <span data-ttu-id="e34d4-147">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="e34d4-148">En el árbol, expanda **Modelo de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="e34d4-149">En el árbol, seleccione **Modelo de comercio exterior\Asignación de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="e34d4-150">Expanda la sección **Requisitos previos**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-150">Expand the **Prerequisites** section.</span></span> 

> [!NOTE]
> <span data-ttu-id="e34d4-151">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e34d4-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e34d4-152">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="e34d4-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="e34d4-153">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="e34d4-154">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="e34d4-155">En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="e34d4-156">Haga clic en **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="e34d4-157">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e34d4-157">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="e34d4-158">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e34d4-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e34d4-159">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="e34d4-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="e34d4-160">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="e34d4-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-161">Close the page.</span></span> 
13. <span data-ttu-id="e34d4-162">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="e34d4-163">Asignar aplicación conectada a asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="e34d4-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="e34d4-164">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="e34d4-165">Seleccione la aplicacón **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-165">Select **MyConnectedApp** application.</span></span> 

> [!NOTE]
> <span data-ttu-id="e34d4-166">Actualmente, esta asignación hace referencia a los metadatos de la aplicación conectada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e34d4-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="e34d4-167">Cuando la misma asignación hace referencia a la configuración de metadatos y a la aplicación conectada al mismo tiempo, se utilizarán los metadatos de la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="e34d4-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="e34d4-168">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="e34d4-169">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="e34d4-170">En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="e34d4-171">Haga clic en **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="e34d4-172">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e34d4-172">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="e34d4-173">Se ofrecieron más de dos tablas de la aplicación ya que esta asignación utiliza todos los metadatos de la aplicación conectada que se le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="e34d4-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="e34d4-174">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="e34d4-175">Hacer clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="e34d4-175">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="e34d4-176">Enlazamos correctamente elementos del modelo de datos con artículos de orígenes de datos que se describen con detalles de metadatos de la aplicación conectada que se ha asignado para esta asignación.</span><span class="sxs-lookup"><span data-stu-id="e34d4-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="e34d4-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-177">Close the page.</span></span> 
11. <span data-ttu-id="e34d4-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e34d4-178">Close the page.</span></span> 

<span data-ttu-id="e34d4-179">Cuando tenga que evaluar esta asignación de modelo mediante el uso de metadatos de una aplicación de versión diferente, registre otra aplicación conectada, asígnela a esta asignación de modelo y valídela con nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="e34d4-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>
