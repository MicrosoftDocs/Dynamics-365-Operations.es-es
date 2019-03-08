---
title: Gestionar la asignación de modelos de ER en distintas configuraciones de ER
description: En los pasos siguientes se explica cómo un usuario con el rol de Administrador del sistema o con el rol de Desarrollador de informes electrónicos puede administrar asignaciones de modelo de informe electrónico (ER) en configuraciones de ER independientes.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24ca4124d190df94e7ca9ac31c2ea757fe9ff242
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "349156"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="4ae3a-103">Gestionar la asignación de modelos de ER en distintas configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ae3a-104">En los pasos siguientes se explica cómo un usuario con el rol de Administrador del sistema o con el rol de Desarrollador de informes electrónicos puede administrar asignaciones de modelo de informe electrónico (ER) en configuraciones de ER independientes.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="4ae3a-105">En este manual de la tarea, creará las configuraciones necesarias de ER para la empresa del ejemplo, Litware, Inc. Para completar esta guía de la tarea, primero debe completar los pasos de la guía de la tarea,  "ER crea un proveedor de la configuración” y lo marca como activo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, “ER Create a configuration provider” and mark it as active.</span></span> 

<span data-ttu-id="4ae3a-106">Dado que las configuraciones de ER se comparten entre las empresas, puede completar esta guía de tareas mediante el conjunto de datos de la empresa de su elección.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="4ae3a-107">La funcionalidad de esta guía de tareas está disponible si ha instalado una de las siguientes revisiones: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 para la versión de Dynamics AX 7.0 o https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 para la versión de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="4ae3a-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="4ae3a-109">Compruebe que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="4ae3a-110">Si no ve a este proveedor de configuración, primero debe completar los pasos de la guía de tareas Creación de un proveedor de configuración y marcarlo como activo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-110">If you don’t see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="4ae3a-111">Añada una nueva configuración para el modelo ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="4ae3a-112">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="4ae3a-113">Agregue una nueva configuración para el modelo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-113">Add a new model configuration.</span></span> <span data-ttu-id="4ae3a-114">El nombre debe ser exclusivo en el árbol de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="4ae3a-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="4ae3a-116">En el campo Nombre, escriba "Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="4ae3a-117">Modelo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae3a-117">Sample data model</span></span>  
4. <span data-ttu-id="4ae3a-118">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-118">Click Create configuration.</span></span>
5. <span data-ttu-id="4ae3a-119">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-119">Click Designer.</span></span>
6. <span data-ttu-id="4ae3a-120">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="4ae3a-121">Escriba "Raíz" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="4ae3a-122">Raíz</span><span class="sxs-lookup"><span data-stu-id="4ae3a-122">Root</span></span>  
8. <span data-ttu-id="4ae3a-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-123">Click Add.</span></span>
9. <span data-ttu-id="4ae3a-124">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="4ae3a-125">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="4ae3a-126">Compañía</span><span class="sxs-lookup"><span data-stu-id="4ae3a-126">Company</span></span>  
11. <span data-ttu-id="4ae3a-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-127">Click Add.</span></span>
12. <span data-ttu-id="4ae3a-128">En el campo Descripción, escriba el texto, Descripción de la entidad jurídica o empresa en que un usuario se registra en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="4ae3a-129">Descripción de la entidad jurídica o de la empresa en la que un usuario se registró en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="4ae3a-130">Haga clic en Referencia raíz.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-130">Click Root reference.</span></span>
14. <span data-ttu-id="4ae3a-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-131">Click OK.</span></span>
15. <span data-ttu-id="4ae3a-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-132">Click Save.</span></span>
16. <span data-ttu-id="4ae3a-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-133">Close the page.</span></span>
17. <span data-ttu-id="4ae3a-134">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-134">Click Change status.</span></span>
18. <span data-ttu-id="4ae3a-135">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-135">Click Complete.</span></span>
19. <span data-ttu-id="4ae3a-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="4ae3a-137">Agregar una nueva configuración de asignación al modelo de ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-137">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="4ae3a-138">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="4ae3a-139">En el campo Nuevo, especifique "Asignación de modelo basado en el modelo Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="4ae3a-140">En el campo Nombre, escriba "Asignación de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="4ae3a-141">Asignación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae3a-141">Sample mapping</span></span>  
4. <span data-ttu-id="4ae3a-142">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-142">Click Create configuration.</span></span>
5. <span data-ttu-id="4ae3a-143">Expanda la sección Requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="4ae3a-144">Tenga en cuenta el grupo de los requisitos previos de implementaciones se ha agregado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-144">Note that the Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="4ae3a-145">El grupo contiene el componente de requisitos previos necesario que se refiere a la configuración principal del modelo de datos y se marca como Implementación.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="4ae3a-146">Esto significa que esta configuración de asignación del Modelo de asignación de ejemplo se considerada la implementación del modelo de datos, Modelo de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-146">This means that this Sample mapping model mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="4ae3a-147">Por lo tanto, este componente forzará al ER que descargue la configuración de asignación del modelo, Asignación de ejemplo de un repositorio de ER cuando se descarga la configuración del modelo, Modelo de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-147">Therefore, this component will force ER to download the model mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="4ae3a-148">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-148">Click Designer.</span></span>
    * <span data-ttu-id="4ae3a-149">Tenga en cuenta que la configuración creada de asignación de modelo contiene una nueva asignación en blanco con el mismo nombre que la configuración creada.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-149">Note that the created model mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="4ae3a-150">Tenga en cuenta que cuando una configuración de modelo de elemento principal seleccionada contiene asignaciones de modelo, se copiarán en una configuración de modelo nueva.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-150">Be aware that when a selected parent model configuration contains model mappings, they will be copied to a new model mapping configuration.</span></span>   
7. <span data-ttu-id="4ae3a-151">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-151">Click Designer.</span></span>
8. <span data-ttu-id="4ae3a-152">En el árbol, seleccione "Dynamics 365 for Operations\Tabla".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="4ae3a-153">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-153">Click Add root.</span></span>
10. <span data-ttu-id="4ae3a-154">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="4ae3a-155">Compañía</span><span class="sxs-lookup"><span data-stu-id="4ae3a-155">Company</span></span>  
11. <span data-ttu-id="4ae3a-156">En el campo Tabla, escriba "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="4ae3a-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="4ae3a-157">CompanyInfo</span></span>  
12. <span data-ttu-id="4ae3a-158">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-158">Click OK.</span></span>
13. <span data-ttu-id="4ae3a-159">En el árbol, expanda "Empresa".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="4ae3a-160">En el árbol, expanda "Empresa\buscar()".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="4ae3a-161">En el árbol, seleccione "Empresa\buscar()\Nombre".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="4ae3a-162">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-162">Click Bind.</span></span>
17. <span data-ttu-id="4ae3a-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-163">Click Save.</span></span>
18. <span data-ttu-id="4ae3a-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-164">Close the page.</span></span>
19. <span data-ttu-id="4ae3a-165">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-165">Close the page.</span></span>
20. <span data-ttu-id="4ae3a-166">En el panel de acciones, haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="4ae3a-167">Haga clic en Parámetros de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-167">Click User parameters.</span></span>
22. <span data-ttu-id="4ae3a-168">Seleccione Sí en el campo Parámetros de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="4ae3a-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-169">Click OK.</span></span>
24. <span data-ttu-id="4ae3a-170">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-170">Click Edit.</span></span>
25. <span data-ttu-id="4ae3a-171">Seleccione Sí en el campo Borrador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="4ae3a-172">Añada una nueva configuración para el formato de ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="4ae3a-173">En el árbol, seleccione "Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="4ae3a-174">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="4ae3a-175">En el campo Nuevo, especifique "Formato basado en el modelo Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="4ae3a-176">En el campo Nombre, escriba "Formato de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="4ae3a-177">Formato de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae3a-177">Sample format</span></span>  
5. <span data-ttu-id="4ae3a-178">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-178">Click Create configuration.</span></span>
6. <span data-ttu-id="4ae3a-179">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-179">Click Designer.</span></span>
7. <span data-ttu-id="4ae3a-180">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="4ae3a-181">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="4ae3a-182">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-182">Click OK.</span></span>
10. <span data-ttu-id="4ae3a-183">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="4ae3a-184">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="4ae3a-185">En el árbol, seleccione "modelo\Empresa".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="4ae3a-186">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-186">Click Bind.</span></span>
14. <span data-ttu-id="4ae3a-187">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-187">Click Save.</span></span>
15. <span data-ttu-id="4ae3a-188">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-188">Close the page.</span></span>
    * <span data-ttu-id="4ae3a-189">Ejecute la versión de borrador del formato creado para probar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="4ae3a-190">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-190">Click Run.</span></span>
    * <span data-ttu-id="4ae3a-191">En las versiones de ficha desplegable, haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="4ae3a-192">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-192">Click OK.</span></span>
    * <span data-ttu-id="4ae3a-193">Revise la salida que contiene el nombre de la empresa en la que el usuario que está ejecutando esta configuración del formato se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="4ae3a-194">Tenga en cuenta que la configuración creada de asignación del modelo se usa por esta configuración del formato ya que solo hay una configuración disponible que contiene asignaciones de modelo necesarias.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-194">Note that the created model mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="4ae3a-195">Agregar una configuración alternativa de asignación al modelo de ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-195">Add alternative ER model mapping configuration</span></span>
1. <span data-ttu-id="4ae3a-196">En el árbol, seleccione "Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="4ae3a-197">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="4ae3a-198">En el campo Nuevo, especifique "Asignación de modelo basado en el modelo Modelo de datos de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="4ae3a-199">En el campo Nombre, escriba "Asignación ejemplo (alternativa)".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="4ae3a-200">Asignación de ejemplo (alternativa)</span><span class="sxs-lookup"><span data-stu-id="4ae3a-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="4ae3a-201">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-201">Click Create configuration.</span></span>
6. <span data-ttu-id="4ae3a-202">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-202">Click Designer.</span></span>
7. <span data-ttu-id="4ae3a-203">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-203">Click Designer.</span></span>
8. <span data-ttu-id="4ae3a-204">En el árbol, seleccione "Dynamics 365 for Operations\Tabla".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="4ae3a-205">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-205">Click Add root.</span></span>
10. <span data-ttu-id="4ae3a-206">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="4ae3a-207">Compañía</span><span class="sxs-lookup"><span data-stu-id="4ae3a-207">Company</span></span>  
11. <span data-ttu-id="4ae3a-208">En el campo Tabla, escriba "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="4ae3a-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="4ae3a-209">CompanyInfo</span></span>  
12. <span data-ttu-id="4ae3a-210">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-210">Click OK.</span></span>
13. <span data-ttu-id="4ae3a-211">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-211">Click Edit.</span></span>
14. <span data-ttu-id="4ae3a-212">En el árbol, seleccione String\CONCATENATE.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="4ae3a-213">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-213">Click Add function.</span></span>
16. <span data-ttu-id="4ae3a-214">En el árbol, expanda "Empresa".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="4ae3a-215">En el árbol, expanda "Empresa\buscar()".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="4ae3a-216">En el árbol, seleccione "Empresa\buscar()\Nombre".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="4ae3a-217">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-217">Click Add data source.</span></span>
20. <span data-ttu-id="4ae3a-218">En el campo Fórmula, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="4ae3a-219">CONCATENAR(Empresa.'buscar()'.Nombre, ";",</span><span class="sxs-lookup"><span data-stu-id="4ae3a-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="4ae3a-220">En el árbol, seleccione "Empresa\buscar()\Empresa(ÁreaDatos)".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="4ae3a-221">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-221">Click Add data source.</span></span>
23. <span data-ttu-id="4ae3a-222">En el campo Fórmula, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="4ae3a-223">CONCATENAR(Empresa.'buscar()'.Nombre, “; ”, Empresa.'buscar().ÁreaDatos)</span><span class="sxs-lookup"><span data-stu-id="4ae3a-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="4ae3a-224">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-224">Click Save.</span></span>
25. <span data-ttu-id="4ae3a-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-225">Close the page.</span></span>
26. <span data-ttu-id="4ae3a-226">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-226">Click Save.</span></span>
27. <span data-ttu-id="4ae3a-227">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-227">Close the page.</span></span>
28. <span data-ttu-id="4ae3a-228">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-228">Close the page.</span></span>
29. <span data-ttu-id="4ae3a-229">Seleccione Sí en el campo Borrador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="4ae3a-230">Use una configuración de asignación existente del modelo de ER</span><span class="sxs-lookup"><span data-stu-id="4ae3a-230">Use an existing ER model mapping configuration</span></span>
1. <span data-ttu-id="4ae3a-231">En el árbol, seleccione "Muestra modelo de datos\Muestra formato".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="4ae3a-232">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-232">Click Run.</span></span>
    * <span data-ttu-id="4ae3a-233">Tenga en cuenta que la versión de borrador de la configuración del formato de ER no se puede ejecutar porque hay más de una configuración de asignación de modelo disponible para el modelo de datos sin definir que se ha seleccionado como el origen de datos de formato de ER en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-233">Note that the selected draft version of the ER format configuration can’t be executed because there is more than one model mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="4ae3a-234">A continuación, se definirá la configuración de la asignación de modelo alternativa como aquella desde la que las asignaciones de modelo se usarán como orígenes de datos para ejecutar el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-234">Next, you will define the alternative model mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="4ae3a-235">En el árbol, seleccione "Muestra modelo de datos\Asignación de Muestra (alternativa)".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="4ae3a-236">Seleccione Sí en el campo Valor predeterminado de la asignación de modelo.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-236">Select Yes in the Default for model mapping field.</span></span>
5. <span data-ttu-id="4ae3a-237">En el árbol, seleccione "Muestra modelo de datos\Muestra formato".</span><span class="sxs-lookup"><span data-stu-id="4ae3a-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="4ae3a-238">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4ae3a-238">Click Run.</span></span>
7. <span data-ttu-id="4ae3a-239">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4ae3a-239">Click OK.</span></span>
    * <span data-ttu-id="4ae3a-240">Tenga en cuenta que la configuración de la asignación de modelo predeterminada se usa por esta configuración de formato para generar el documento electrónico (la salida creada contiene el código de empresa).</span><span class="sxs-lookup"><span data-stu-id="4ae3a-240">Note that the default model mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

