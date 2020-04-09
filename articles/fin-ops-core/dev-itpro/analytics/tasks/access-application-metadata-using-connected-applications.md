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
ms.openlocfilehash: 28b8346b916729669af42ca47fe9a882e7a77bd0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142210"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="6edb9-103">Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas</span><span class="sxs-lookup"><span data-stu-id="6edb9-103">Access application metadata by using connected applications</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6edb9-104">En los pasos siguientes se explica cómo un usuario de Regulatory Configuration Service (RCS) con el rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6edb9-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="6edb9-105">Se accederá en línea a los metadatos de la aplicación mediante el uso de la aplicación conectada de RCS.</span><span class="sxs-lookup"><span data-stu-id="6edb9-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="6edb9-106">La asignación del modelo de ER de ejemplo se configurará para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="6edb9-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="6edb9-107">Para completar estos pasos, en RCS primero debe completar los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="6edb9-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="6edb9-108">Si no ha completado los pasos del tema [Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), vaya a la [Página de ejemplos de informes electrónicos](https://go.microsoft.com/fwlink/?linkid=862266) para descargar y guardar las siguientes configuraciones de ER: Metadatos de comercio exterior.xml; Modelo de comercio exterior.xml; Asignación de comercio exterior.xml y, a continuación, complete los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6edb9-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6edb9-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6edb9-109">Prerequisites</span></span>
1. <span data-ttu-id="6edb9-110">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="6edb9-111">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="6edb9-112">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="6edb9-112">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="6edb9-113">Obtener las configuraciones de ER necesarias</span><span class="sxs-lookup"><span data-stu-id="6edb9-113">Get required ER configurations</span></span>
1. <span data-ttu-id="6edb9-114">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="6edb9-115">Si ya ha completado los pasos del procedimiento [Acceder a metadatos de la aplicación mediante el uso de la configuración de ER](access-application-metadata-er-configuration.md), ya tiene todas las configuraciones de ER necesarias (configuraciones de metadatos, modelo y asignación de comercio exterior) en la instancia de RCS actual.</span><span class="sxs-lookup"><span data-stu-id="6edb9-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="6edb9-116">Puede omitir todos los pasos restantes de esta subtarea.</span><span class="sxs-lookup"><span data-stu-id="6edb9-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="6edb9-117">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="6edb9-118">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="6edb9-119">Haga clic en **Examinar** y seleccione el archivo **Metadatos de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="6edb9-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-120">Click **OK**.</span></span> 
7. <span data-ttu-id="6edb9-121">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="6edb9-122">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="6edb9-123">Haga clic en **Examinar** y seleccione el archivo **Modelo de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="6edb9-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-124">Click **OK**.</span></span> 
11. <span data-ttu-id="6edb9-125">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="6edb9-126">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="6edb9-127">Haga clic en **Examinar** y seleccione el archivo **Asignación de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="6edb9-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="6edb9-129">Registrar una aplicación conectada</span><span class="sxs-lookup"><span data-stu-id="6edb9-129">Register a connected application</span></span>
1. <span data-ttu-id="6edb9-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-130">Close the page.</span></span> 
2. <span data-ttu-id="6edb9-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-131">Close the page.</span></span> 
3. <span data-ttu-id="6edb9-132">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="6edb9-133">Haga clic en **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="6edb9-134">Asegúrese de que la aplicación configurada se basa en Azure y el usuario actual de RCS puede acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="6edb9-134">Make sure that the configured application is Azure based and accessible for the current RCS user.</span></span> <span data-ttu-id="6edb9-135">También se requiere que el usuario actual de RCS tenga acceso a la aplicación seleccionada y se haya registrado como usuario de esta aplicación con un rol que le dé privilegios para acceder a los metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6edb9-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving him privileges to access application's metadata.</span></span> 
6. <span data-ttu-id="6edb9-136">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-136">Click **New**.</span></span> 
7. <span data-ttu-id="6edb9-137">En el campo **Nombre**, escriba 'MyConnectedApp'.</span><span class="sxs-lookup"><span data-stu-id="6edb9-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="6edb9-138">En el campo **Aplicación**, escriba 'https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="6edb9-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="6edb9-139">En el campo **Inquilino**, escriba "mycompany.onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="6edb9-139">In the **Tenant** field, type 'mycompany.onmicrosoft.com'.</span></span> 
10. <span data-ttu-id="6edb9-140">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-140">Click **Save**.</span></span> 
11. <span data-ttu-id="6edb9-141">Cuando compruebe la conexión a la aplicación configurada, en la página **Conectar con aplicación remota**, haga clic en el vínculo **Haga clic aquí para conectarse a la aplicación remota seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="6edb9-142">Haga clic en **Comprobar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="6edb9-143">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-143">Click **Close**.</span></span> 
14. <span data-ttu-id="6edb9-144">Cuando la validación de la conexión fue correcta, se actualizarán los detalles de la versión y del inquilino para la aplicación configurada en la cuadrícula actual.</span><span class="sxs-lookup"><span data-stu-id="6edb9-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="6edb9-145">Revisar configuración de asignación existente del modelo</span><span class="sxs-lookup"><span data-stu-id="6edb9-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="6edb9-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-146">Close the page.</span></span> 
2. <span data-ttu-id="6edb9-147">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="6edb9-148">En el árbol, expanda **Modelo de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="6edb9-149">En el árbol, seleccione **Modelo de comercio exterior\Asignación de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="6edb9-150">Expanda la sección **Requisitos previos**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6edb9-151">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="6edb9-152">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="6edb9-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="6edb9-153">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="6edb9-154">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="6edb9-155">En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="6edb9-156">Haga clic en **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="6edb9-157">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6edb9-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6edb9-158">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="6edb9-159">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="6edb9-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="6edb9-160">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="6edb9-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-161">Close the page.</span></span> 
13. <span data-ttu-id="6edb9-162">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="6edb9-163">Asignar aplicación conectada a asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="6edb9-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="6edb9-164">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="6edb9-165">Seleccione la aplicacón **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6edb9-166">Actualmente, esta asignación hace referencia a los metadatos de la aplicación conectada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6edb9-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="6edb9-167">Cuando la misma asignación hace referencia a la configuración de metadatos y a la aplicación conectada al mismo tiempo, se utilizarán los metadatos de la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="6edb9-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="6edb9-168">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="6edb9-169">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="6edb9-170">En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="6edb9-171">Haga clic en **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="6edb9-172">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6edb9-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6edb9-173">Se ofrecieron más de dos tablas de la aplicación ya que esta asignación utiliza todos los metadatos de la aplicación conectada que se le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="6edb9-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="6edb9-174">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="6edb9-175">Hacer clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6edb9-176">Enlazamos correctamente elementos del modelo de datos con artículos de orígenes de datos que se describen con detalles de metadatos de la aplicación conectada que se ha asignado para esta asignación.</span><span class="sxs-lookup"><span data-stu-id="6edb9-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="6edb9-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-177">Close the page.</span></span> 
11. <span data-ttu-id="6edb9-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6edb9-178">Close the page.</span></span> 

<span data-ttu-id="6edb9-179">Cuando tenga que evaluar esta asignación de modelo mediante el uso de metadatos de una aplicación de versión diferente, registre otra aplicación conectada, asígnela a esta asignación de modelo y valídela con nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>
