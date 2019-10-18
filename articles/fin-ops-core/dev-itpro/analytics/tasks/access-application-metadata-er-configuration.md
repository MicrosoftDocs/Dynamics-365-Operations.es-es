---
title: Acceder a metadatos de la aplicación mediante el uso de una configuración de ER
description: Los pasos de este tema explican cómo un usuario de Regulatory Configuration Service (RCS) puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos en Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
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
ms.openlocfilehash: 2bfe007995c894d6cc86d07ef2b52da65e32e950
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182747"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="38bf4-103">Acceder a metadatos de la aplicación mediante el uso de una configuración de ER</span><span class="sxs-lookup"><span data-stu-id="38bf4-103">Access application metadata by using ER configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38bf4-104">En los pasos siguientes se explica cómo un usuario de Regulatory Configuration Service (RCS) con el rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una nueva asignación de modelo de informes electrónicos (ER) mediante el uso de metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38bf4-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="38bf4-105">Se accederá a los metadatos de la aplicación mediante el uso de una configuración de metadatos de ER que contenga un conjunto de metadatos de ejemplo para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="38bf4-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="38bf4-106">Para completar estos pasos, en RCS primero debe completar los pasos del tema, el procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="38bf4-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="38bf4-107">A continuación, complete los pasos del tema, [(ER) Preparar metadatos de la aplicación para usarse en RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="38bf4-107">Then complete the steps in the topic, [(ER) Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38bf4-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="38bf4-108">Prerequisites</span></span>
1. <span data-ttu-id="38bf4-109">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="38bf4-110">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="38bf4-111">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="38bf4-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="38bf4-112">Importar configuración de metadatos</span><span class="sxs-lookup"><span data-stu-id="38bf4-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="38bf4-113">Haga clic en **Configuraciones de metadatos**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="38bf4-114">Importe la configuración de metadatos de ER que contenga metadatos que se han configurado para generar documentos electrónicos para el dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="38bf4-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="38bf4-115">Esta configuración de metadatos de ER se ha exportado como archivo XML mientras se hayan completado los pasos del procedimiento [(ER) Preparar metadatos de la aplicación para usarse en RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="38bf4-115">This ER metadata configuration has been exported as XML file while the steps in the [(ER) Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="38bf4-116">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="38bf4-117">Haga clic en **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="38bf4-118">Haga clic en **Examinar** y seleccione el archivo ‘Metadatos de comercio exterior.xml‘.</span><span class="sxs-lookup"><span data-stu-id="38bf4-118">Click **Browse** and select the ‘Foreign trade metadata.xml’ file.</span></span> 
6. <span data-ttu-id="38bf4-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-119">Click **OK**.</span></span> 
7. <span data-ttu-id="38bf4-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38bf4-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="38bf4-121">Crear configuración de modelo de datos</span><span class="sxs-lookup"><span data-stu-id="38bf4-121">Create data model configuration</span></span>
1. <span data-ttu-id="38bf4-122">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="38bf4-123">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="38bf4-124">En el campo **Nombre**, escriba 'Modelo de comercio exterior'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="38bf4-125">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="38bf4-126">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="38bf4-127">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="38bf4-128">Escriba 'Raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="38bf4-129">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-129">Click **Add**.</span></span> 
9. <span data-ttu-id="38bf4-130">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-130">Click **New** to open the drop dialog.</span></span> 
10. <span data-ttu-id="38bf4-131">En el campo **Nombre**, escriba 'Transacción'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-131">In the **Name** field, type 'Transaction'.</span></span> 
11. <span data-ttu-id="38bf4-132">En el campo **Tipo de artículo**, seleccione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-132">In the **Item type** field, select **Record list**.</span></span> 
12. <span data-ttu-id="38bf4-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-133">Click **Add**.</span></span> 
13. <span data-ttu-id="38bf4-134">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-134">Click **New** to open the drop dialog.</span></span> 
14. <span data-ttu-id="38bf4-135">En el campo **Nombre**, escriba 'Código de mercancía'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-135">In the **Name** field, type 'Commodity code'.</span></span> 
15. <span data-ttu-id="38bf4-136">En el campo **Tipo de artículo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-136">In the **Item type** field, select **String**.</span></span> 
16. <span data-ttu-id="38bf4-137">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-137">Click **Add**.</span></span> 
17. <span data-ttu-id="38bf4-138">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-138">Click **New** to open the drop dialog.</span></span> 
18. <span data-ttu-id="38bf4-139">En el campo **Nombre**, introduzca 'Importe facturado'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19. <span data-ttu-id="38bf4-140">En el campo **Tipo de artículo**, seleccione **Real**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-140">In the **Item type** field, select **Real**.</span></span> 
20. <span data-ttu-id="38bf4-141">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-141">Click **Add**.</span></span> 
21. <span data-ttu-id="38bf4-142">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-142">Click **New** to open the drop dialog.</span></span> 
22. <span data-ttu-id="38bf4-143">En el campo **Nombre**, escriba 'Fecha'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-143">In the **Name** field, type 'Date'.</span></span> 
23. <span data-ttu-id="38bf4-144">En el campo **Tipo de artículo**, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-144">In the **Item type** field, select **Date**.</span></span> 
24. <span data-ttu-id="38bf4-145">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-145">Click **Add**.</span></span> 
25. <span data-ttu-id="38bf4-146">Haga clic en **Referencia raíz**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-146">Click **Root reference**.</span></span> 
26. <span data-ttu-id="38bf4-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-147">Click **OK**.</span></span> 
27. <span data-ttu-id="38bf4-148">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-148">Click **Save**.</span></span> 
28. <span data-ttu-id="38bf4-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38bf4-149">Close the page.</span></span> 
29. <span data-ttu-id="38bf4-150">Haga clic en **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-150">Click **Change status**.</span></span> 
30. <span data-ttu-id="38bf4-151">Haga clic en **Completar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-151">Click **Complete**.</span></span> 
31. <span data-ttu-id="38bf4-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="38bf4-153">Crear configuración de asignación del modelo</span><span class="sxs-lookup"><span data-stu-id="38bf4-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="38bf4-154">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="38bf4-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="38bf4-155">En el campo **Nuevo**, especifique 'Asignación de modelo basado en el modelo de datos del Modelo de comecio exterior'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="38bf4-156">En el campo **Nombre**, escriba 'Asignación de comercio exterior'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="38bf4-157">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="38bf4-158">Expanda la sección **Requisitos previos**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="38bf4-159">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="38bf4-160">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-160">Click **New**.</span></span> 
8. <span data-ttu-id="38bf4-161">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="38bf4-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="38bf4-162">En el campo **Tipo de componente de requisito previo**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10. <span data-ttu-id="38bf4-163">Seleccione la configuración **Metadatos de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-163">Select **Foreign trade metadata** configuration.</span></span> 
11. <span data-ttu-id="38bf4-164">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-164">Click **Save**.</span></span> 
12. <span data-ttu-id="38bf4-165">Agregamos la referencia a la versión 1 de la configuración 'Metadatos de comercio exterior'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-165">We added the reference to the version 1 of the ‘Foreign trade metadata’ configuration.</span></span> <span data-ttu-id="38bf4-166">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="38bf4-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13. <span data-ttu-id="38bf4-167">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38bf4-167">Close the page.</span></span> 
14. <span data-ttu-id="38bf4-168">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-168">Click **Designer**.</span></span> 
15. <span data-ttu-id="38bf4-169">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-169">Click **Designer**.</span></span> 
16. <span data-ttu-id="38bf4-170">En el árbol, seleccione **Dynamics 365 for Operations\Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17. <span data-ttu-id="38bf4-171">Haga clic en **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-171">Click **Add root**.</span></span> 
18. <span data-ttu-id="38bf4-172">En el campo **Nombre**, escriba 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="38bf4-172">In the **Name** field, type 'Intrastat'.</span></span> 
19. <span data-ttu-id="38bf4-173">Seleccione el registro de tabla de **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-173">Select **Intrastat** table records.</span></span> 
20. <span data-ttu-id="38bf4-174">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="38bf4-175">Solo se ofrecieron 2 tablas, ya que solo se agregaron 2 tablas al conjunto de metadatos que se utiliza actualmente.</span><span class="sxs-lookup"><span data-stu-id="38bf4-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21. <span data-ttu-id="38bf4-176">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-176">Click **Bind**.</span></span> 
22. <span data-ttu-id="38bf4-177">En el árbol, expanda **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-177">In the tree, expand **Intrastat**.</span></span> 
23. <span data-ttu-id="38bf4-178">En el árbol, seleccione **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24. <span data-ttu-id="38bf4-179">En el árbol, expanda **Transacción = Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25. <span data-ttu-id="38bf4-180">En el árbol, seleccione **Transacción = Intrastat\Importe facturado**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26. <span data-ttu-id="38bf4-181">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-181">Click **Bind**.</span></span> 
27. <span data-ttu-id="38bf4-182">En el árbol, seleccione **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28. <span data-ttu-id="38bf4-183">En el árbol, seleccione **Transacción = Intrastat\Fecha**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29. <span data-ttu-id="38bf4-184">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-184">Click **Bind**.</span></span> 
30. <span data-ttu-id="38bf4-185">En el árbol, expanda **Intrastat\>Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31. <span data-ttu-id="38bf4-186">En el árbol, expanda **Intrastat\>Relaciones\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32. <span data-ttu-id="38bf4-187">En el árbol, seleccione **Intrastat\>Relaciones\IntrastatCommodity\Código**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33. <span data-ttu-id="38bf4-188">En el árbol, seleccione **Transacción = Intrastat\Código de mercancía**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34. <span data-ttu-id="38bf4-189">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-189">Click **Bind**.</span></span> 
35. <span data-ttu-id="38bf4-190">Hacer clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="38bf4-191">Hemos enlazada correctamente los elementos del modelo de datos con artículos de orígenes de datos que se describen con detalles de metadatos de la aplicación desde la configuración de metadatos de ER a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="38bf4-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36. <span data-ttu-id="38bf4-192">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="38bf4-192">Click **Save**.</span></span> 
37. <span data-ttu-id="38bf4-193">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38bf4-193">Close the page.</span></span> 
38. <span data-ttu-id="38bf4-194">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38bf4-194">Close the page.</span></span> 
39. <span data-ttu-id="38bf4-195">Cuando se necesiten, puede ampliar el conjunto existente de metadatos y después exportar la nueva versión completada de la configuración de los metadatos de ER.</span><span class="sxs-lookup"><span data-stu-id="38bf4-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="38bf4-196">A continuación puede importarla al RCS, y actualizar los requisitos previos de configuración de asignación de modelos configurados a una nueva versión de la configuración de metadatos importada.</span><span class="sxs-lookup"><span data-stu-id="38bf4-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="38bf4-197">Esta forma de obtener información sobre metadatos de la aplicación es la única disponible para aplicaciones implementadas localmente (cuando se utiliza un modelo de implementación de datos empresariales locales (LBD), o en las instalaciones).</span><span class="sxs-lookup"><span data-stu-id="38bf4-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        
