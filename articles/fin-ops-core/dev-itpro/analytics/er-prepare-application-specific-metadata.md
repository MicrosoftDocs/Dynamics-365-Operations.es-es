---
title: Preparar metadatos específicos de la aplicación para RCS y ER
description: En este tema se explica cómo preparar metadatos específicos de la aplicación para Regulatory configuration service (RCS) e informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 74750397dc344d74c018c27114357d3d05b95b7e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550116"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a><span data-ttu-id="40a02-103">Preparar metadatos específicos de la aplicación para RCS y ER</span><span class="sxs-lookup"><span data-stu-id="40a02-103">Prepare application-specific metadata for RCS and ER</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="40a02-104">Este tema le guía por ejemplos de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="40a02-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="40a02-105">Preparar metadatos de la aplicación que pueden usarse en RCS</span><span class="sxs-lookup"><span data-stu-id="40a02-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="40a02-106">Acceder a metadatos de la aplicación mediante el uso de una configuración de ER</span><span class="sxs-lookup"><span data-stu-id="40a02-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="40a02-107">Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas</span><span class="sxs-lookup"><span data-stu-id="40a02-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="40a02-108">Preparar metadatos de la aplicación que pueden usarse en RCS</span><span class="sxs-lookup"><span data-stu-id="40a02-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="40a02-109">El siguiente procedimiento muestra cómo un usuario que tiene en el rol de **Administrador del sistema** o **Desarrollador de informes electrónicos** puede crear una configuración de informes electrónicos (ER) que contenga metadatos para la aplicación y que se utiliza para diseñar configuraciones de asignación del modelo de ER en Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="40a02-109">The following procedure shows how a user who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="40a02-110">La configuración de asignación del modelo de ER de ejemplo que se crea en este ejemplo se utilizará para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="40a02-111">Para este ejemplo, desea utilizar RCS para diseñar una solución de ER para la aplicación que se utilizará para generar documentos electrónicos que contienen información del dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-111">For this example, you want to use RCS to design an ER solution for the application that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="40a02-112">Para especificar la asignación entre el modelo de datos de ER y los orígenes de datos requeridos, debe tener acceso a los metadatos de la aplicación en RCS.</span><span class="sxs-lookup"><span data-stu-id="40a02-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata in RCS.</span></span> <span data-ttu-id="40a02-113">Por lo tanto, como parte del proceso de diseñar la solución de ER, debe configurar una nueva configuración de metadatos de ER que contenga todos los metadatos que se requieren actualmente para generar informes de ER para el dominio empresarial seleccionado.</span><span class="sxs-lookup"><span data-stu-id="40a02-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="40a02-114">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="40a02-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="40a02-115">Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="40a02-116">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="40a02-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="40a02-117">Si no ve a este proveedor de configuración, complete el procedimiento [Creación de un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="40a02-117">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="40a02-118">Seleccione **Configuraciones de metadatos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="40a02-119">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="40a02-120">En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca un nombre.</span><span class="sxs-lookup"><span data-stu-id="40a02-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="40a02-121">Para este ejemplo, introduzca **Metadatos de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="40a02-122">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="40a02-123">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-123">Select **Designer**.</span></span>
8. <span data-ttu-id="40a02-124">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-125">Puede seleccionar todos los metadatos para toda la aplicación o para modelos o módulos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="40a02-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="40a02-126">En ambos casos, tenga en cuenta que los siguientes metadatos se agregarán automáticamente: tablas de registros, enumeraciones y tipos de datos extendidos (EDT).</span><span class="sxs-lookup"><span data-stu-id="40a02-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="40a02-127">Cuando se requieren tipos adicionales de metadatos, deben agregarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="40a02-127">When additional types of metadata are required, they must be manually added.</span></span>

<span data-ttu-id="40a02-128">Debe agregar algunos metadatos que están relacionados con transacciones de comercio exterior y seleccionar elementos de metadatos manualmente.</span><span class="sxs-lookup"><span data-stu-id="40a02-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="40a02-129">Seleccione **Agregar origen de datos \> Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="40a02-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="40a02-130">Filtre según un valor de **Intrastat** en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="40a02-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="40a02-131">Seleccione el registro de tabla de **Intrastat** .</span><span class="sxs-lookup"><span data-stu-id="40a02-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="40a02-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-132">Select **OK**.</span></span>

<span data-ttu-id="40a02-133">Debe agregar información de metadatos sobre la tabla de registros de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="40a02-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="40a02-134">En el árbol, seleccione **Registros de tabla de Intrastat \> \>Relations \> IntrastatCommodity (Registros de tabla EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="40a02-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="40a02-135">Seleccione **Agregar metadatos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-136">Los metadatos sobre las relaciones necesarias para la tabla de registros seleccionada se deben agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="40a02-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="40a02-137">Seleccione **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="40a02-138">Seleccione **Enumeración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="40a02-139">Filtre según un valor de **IntrastatDirection** en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="40a02-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="40a02-140">Seleccione el registro de enumeración de **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="40a02-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="40a02-141">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-141">Select **OK**.</span></span>
20. <span data-ttu-id="40a02-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-142">Select **Save**.</span></span>
21. <span data-ttu-id="40a02-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="40a02-143">Close the page.</span></span>
22. <span data-ttu-id="40a02-144">Completar la versión de borrador de la configuración de metadatos:</span><span class="sxs-lookup"><span data-stu-id="40a02-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="40a02-145">Seleccione **Cambiar estado\> Completada**.</span><span class="sxs-lookup"><span data-stu-id="40a02-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="40a02-146">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-146">Select **OK**.</span></span>
    3. <span data-ttu-id="40a02-147">Seleccione la versión completada 1.</span><span class="sxs-lookup"><span data-stu-id="40a02-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="40a02-148">Exporte la versión completada de la configuración de metadatos desde la aplicación como archivo XML:</span><span class="sxs-lookup"><span data-stu-id="40a02-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="40a02-149">Seleccione **Intercambiar \> Exportar como archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="40a02-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="40a02-150">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-150">Select **OK**.</span></span>

<span data-ttu-id="40a02-151">La configuración de metadatos de ER que creó se guarda como el archivo **Metadatos de comercio exterior.xml** .</span><span class="sxs-lookup"><span data-stu-id="40a02-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="40a02-152">Ahora puede importarla en RCS para que pueda utilizarse como origen de metadatos para el dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain.</span></span> <span data-ttu-id="40a02-153">Según esta información, puede especificar la asignación entre los metadatos de la aplicación y el modelo de datos de ER.</span><span class="sxs-lookup"><span data-stu-id="40a02-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="40a02-154">Acceder a metadatos de la aplicación mediante el uso de una configuración de ER</span><span class="sxs-lookup"><span data-stu-id="40a02-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="40a02-155">El siguiente procedimiento muestra cómo un usuario de RCS que tiene el rol **Administrador del sistema** o de **Desarrollador de informes electrónicos** puede diseñar una nueva asignación del modelo de ER mediante el uso de metadatos desde la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the application.</span></span> <span data-ttu-id="40a02-156">Se accederá a los metadatos de la aplicación mediante el uso de una configuración de metadatos de ER que contenga un conjunto de metadatos de ejemplo para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="40a02-157">Para poder completar este procedimiento, primero debe completar los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="40a02-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="40a02-158">Creación y activación de un proveedor de configuraciones</span><span class="sxs-lookup"><span data-stu-id="40a02-158">Create a configuration provider and mark it as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="40a02-159">Preparar metadatos de la aplicación que pueden usarse en RCS</span><span class="sxs-lookup"><span data-stu-id="40a02-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="40a02-160">Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="40a02-161">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="40a02-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="40a02-162">Si no ve a este proveedor de configuración, complete el procedimiento [Creación de un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="40a02-162">If you don't see this configuration provider, complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="40a02-163">Importe la configuración de metadatos de ER que contenga metadatos para la aplicación y que esté configurada para generar documentos electrónicos para el dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-163">Import the ER metadata configuration that contains metadata for the application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="40a02-164">Creó esta configuración de metadatos de ER y la exportó como archivo XML en el procedimiento [Preparar metadatos de la aplicación que pueden usarse en RCS](#prepare-application-metadata-that-can-be-used-in-rcs) descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="40a02-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="40a02-165">Seleccione **Configuraciones de metadatos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="40a02-166">Seleccione **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="40a02-167">Seleccione **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="40a02-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="40a02-168">Examine para seleccionar el archivo **Metadatos de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="40a02-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="40a02-169">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-169">Select **OK**.</span></span>
    6. <span data-ttu-id="40a02-170">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="40a02-170">Close the page.</span></span>

4. <span data-ttu-id="40a02-171">Cree una configuración de modelo de datos:</span><span class="sxs-lookup"><span data-stu-id="40a02-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="40a02-172">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="40a02-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="40a02-173">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="40a02-174">En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Modelo de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="40a02-175">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="40a02-176">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="40a02-177">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="40a02-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="40a02-178">Escriba **Raíz** en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="40a02-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="40a02-179">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="40a02-180">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="40a02-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="40a02-181">En el campo **Nombre**, escriba **Transacción**.</span><span class="sxs-lookup"><span data-stu-id="40a02-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="40a02-182">En el campo **Tipo de artículo**, seleccione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="40a02-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="40a02-183">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="40a02-184">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="40a02-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="40a02-185">En el campo **Nombre**, escriba **Código de mercancía**.</span><span class="sxs-lookup"><span data-stu-id="40a02-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="40a02-186">En el campo **Tipo de artículo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="40a02-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="40a02-187">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-187">Select **Add**.</span></span>

    9. <span data-ttu-id="40a02-188">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="40a02-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="40a02-189">En el campo Nombre, introduzca **Importe facturado**.</span><span class="sxs-lookup"><span data-stu-id="40a02-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="40a02-190">En el campo **Tipo de artículo**, seleccione **Real**.</span><span class="sxs-lookup"><span data-stu-id="40a02-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="40a02-191">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-191">Select **Add**.</span></span>

    10. <span data-ttu-id="40a02-192">Seleccione **Nuevo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="40a02-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="40a02-193">En el campo **Nombre**, escriba **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="40a02-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="40a02-194">En el campo **Tipo de artículo**, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="40a02-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="40a02-195">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="40a02-196">Seleccione **Agregar \> Referencia raíz**.</span><span class="sxs-lookup"><span data-stu-id="40a02-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="40a02-197">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-197">Select **OK**.</span></span>
    13. <span data-ttu-id="40a02-198">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-198">Select **Save**.</span></span>
    14. <span data-ttu-id="40a02-199">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="40a02-199">Close the page.</span></span>
    15. <span data-ttu-id="40a02-200">Seleccione **Cambiar estado\> Completada**.</span><span class="sxs-lookup"><span data-stu-id="40a02-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="40a02-201">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-201">Select **OK**.</span></span>

5. <span data-ttu-id="40a02-202">Cree una configuración de asignación del modelo:</span><span class="sxs-lookup"><span data-stu-id="40a02-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="40a02-203">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="40a02-204">En el cuadro de diálogo desplegable, en el campo **Nuevo**, introduzca **Asignación de modelo basado en el modelo de datos Modelo de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="40a02-205">En el campo **Nombre**, introduzca **Asignación de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="40a02-206">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="40a02-207">En la ficha desplegable **Requisitos previos**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="40a02-208">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="40a02-208">Select **New**.</span></span>
    7. <span data-ttu-id="40a02-209">En el campo **Tipo de componente de requisito previo**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="40a02-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="40a02-210">Seleccione la configuración **Metadatos de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="40a02-211">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-211">Select **Save**.</span></span> <span data-ttu-id="40a02-212">Tenga en cuenta que la referencia se agrega a la versión 1 de la configuración **Metadatos de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="40a02-213">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña la asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="40a02-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="40a02-214">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="40a02-214">Close the page.</span></span>
    11. <span data-ttu-id="40a02-215">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="40a02-216">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="40a02-217">En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="40a02-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="40a02-218">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="40a02-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="40a02-219">En el campo **Nombre**, especifique **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="40a02-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="40a02-220">Seleccione el registro de tabla de **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="40a02-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="40a02-221">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="40a02-222">Solo se ofrecen dos tablas, ya que solo se agregaron dos tablas al conjunto de metadatos que se utiliza actualmente.</span><span class="sxs-lookup"><span data-stu-id="40a02-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="40a02-223">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="40a02-224">En el árbol, seleccione **Intrastat \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="40a02-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="40a02-225">En el árbol, seleccione **Transacción = Intrastat \> Importe facturado**.</span><span class="sxs-lookup"><span data-stu-id="40a02-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="40a02-226">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="40a02-227">En el árbol, seleccione **Intrastat \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="40a02-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="40a02-228">En el árbol, seleccione **Transacción = Intrastat \> Fecha**.</span><span class="sxs-lookup"><span data-stu-id="40a02-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="40a02-229">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="40a02-230">En el árbol, seleccione **Intrastat \> \>Relaciones \> IntrastatCommodity \> Código**.</span><span class="sxs-lookup"><span data-stu-id="40a02-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="40a02-231">En el árbol, seleccione **Transacción = Intrastat \> Código de mercancía**.</span><span class="sxs-lookup"><span data-stu-id="40a02-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="40a02-232">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="40a02-233">Seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="40a02-234">Una vez que se complete la validación, habrá enlazado correctamente los elementos del modelo de datos a los artículos de los orígenes de datos que se describen con detalles de metadatos de la aplicación desde la configuración de metadatos de ER a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="40a02-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="40a02-235">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-235">Select **Save**.</span></span>

<span data-ttu-id="40a02-236">Según necesite, puede ampliar el conjunto de metadatos existente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-236">As you require, you can extend the existing set of metadata in the application.</span></span> <span data-ttu-id="40a02-237">A continuación, puede exportar la nueva versión completada de la configuración de metadatos de ER, importarla en RCS y actualizar los requisitos previos de la configuración de asignación del modelo configurado para hacer referencia a una nueva versión de la configuración de los metadatos importados.</span><span class="sxs-lookup"><span data-stu-id="40a02-237">You can then export the new completed version of the ER metadata configuration, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="40a02-238">Este método para obtener información sobre metadatos de la aplicación es el único método disponible para las aplicaciones que se implementan localmente (es decir, cuando se utiliza un modelo de implementación de datos empresariales locales \[LBD\], o en las instalaciones, para la aplicación).</span><span class="sxs-lookup"><span data-stu-id="40a02-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for the application).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="40a02-239">Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas</span><span class="sxs-lookup"><span data-stu-id="40a02-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="40a02-240">El siguiente procedimiento muestra cómo un usuario de RCS que tiene el rol **Administrador del sistema** o de **Desarrollador de informes electrónicos** puede diseñar una nueva asignación del modelo de ER mediante el uso de metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the application.</span></span> <span data-ttu-id="40a02-241">Se accederá en línea a los metadatos de la aplicación mediante el uso de la aplicación conectada de RCS.</span><span class="sxs-lookup"><span data-stu-id="40a02-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="40a02-242">Una asignación del modelo de ER de ejemplo se configurará para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="40a02-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="40a02-243">Para completar este procedimiennto, primero debe completar el procedimiento [Creación de un proveedor de configuraciones y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md) en RCS.</span><span class="sxs-lookup"><span data-stu-id="40a02-243">To complete this procedure, you must first complete the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="40a02-244">Si todavía no ha completado el procedimiento [Acceder a metadatos de la aplicación mediante el uso de una configuración de ER](#access-application-metadata-by-using-an-er-configuration) descrito anteriormente en este tema, vaya a la página [Guías de tareas de informes electrónicos para Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) para descargar los siguientes archivos de configuración de ER por adelantado y guardarlos localmente: **Metadatos de comercial exterior.xml**, **Modelo de comercio exterior.xml** y **Asignación de comercio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="40a02-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="40a02-245">Obtener las configuraciones de ER necesarias</span><span class="sxs-lookup"><span data-stu-id="40a02-245">Get required ER configurations</span></span>

<span data-ttu-id="40a02-246">Si ya ha completado el procedimiento [Acceder a metadatos de la aplicación mediante el uso de una configuración de ER](#access-application-metadata-by-using-an-er-configuration) descrito anteriormente en este tema, ya tiene todas las configuraciones de ER necesarias (las configuraciones de metadatos, modelo y asignación de comercio exterior) en la instancia de RCS actual.</span><span class="sxs-lookup"><span data-stu-id="40a02-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="40a02-247">En ese caso, puede omitir este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40a02-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="40a02-248">Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="40a02-249">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="40a02-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="40a02-250">Cargue los archivos de configuración **Metadatos de comercio exterior.xml**, **Modelo de comercio exterior.xml** y **Asignación de comercio exterior.xml** repitiendo la siguiente cadena de pasos para cada uno de ellos:</span><span class="sxs-lookup"><span data-stu-id="40a02-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="40a02-251">Seleccione **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="40a02-252">Seleccione **Cargar desde un archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="40a02-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="40a02-253">Seleccione **Examinar** y seleccionar un archivo.</span><span class="sxs-lookup"><span data-stu-id="40a02-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="40a02-254">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-the-application"></a><span data-ttu-id="40a02-255">Registre la conexión con la aplicación</span><span class="sxs-lookup"><span data-stu-id="40a02-255">Register the connection with the application</span></span>

1. <span data-ttu-id="40a02-256">Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="40a02-257">Seleccione **Aplicaciones conectadas**.</span><span class="sxs-lookup"><span data-stu-id="40a02-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="40a02-258">Asegúrese de que la aplicación configurada se basa en Microsoft Azure y de que los usuarios de RCS pueden acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="40a02-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="40a02-259">El usuario de RCS actual debe tener acceso a la aplicación configurada registrándose como usuario de esta aplicación en un rol que dé privilegios para acceder a los metadatos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives him or her privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="40a02-260">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="40a02-260">Select **New**.</span></span>
5. <span data-ttu-id="40a02-261">En el campo **Nombre**, introduzca **MyConnectedApp** como el nombre de la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="40a02-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="40a02-262">En el campo **Aplicación**, especifique la dirección URL de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="40a02-263">En el campo **Inquilino**, especifique el proveedor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a02-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="40a02-264">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-264">Select **Save**.</span></span> 
9. <span data-ttu-id="40a02-265">Cuando compruebe la conexión a la aplicación configurada, en la página **Conectar con aplicación remota**, seleccione el vínculo **Seleccione aquí para conectarse a la aplicación remota seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="40a02-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="40a02-266">Seleccione **Comprobar conexión** para validar el acceso a la aplicación configurada.</span><span class="sxs-lookup"><span data-stu-id="40a02-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="40a02-267">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-267">Select **Close**.</span></span>

<span data-ttu-id="40a02-268">Tras completar este procedimiento y la validación de la conexión correctamente, se actualizarán los detalles de la versión y del inquilino para la aplicación configurada en la cuadrícula actual.</span><span class="sxs-lookup"><span data-stu-id="40a02-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="40a02-269">Revisar la configuración de asignación existente del modelo</span><span class="sxs-lookup"><span data-stu-id="40a02-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="40a02-270">Vaya a **Todos los espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="40a02-271">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="40a02-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="40a02-272">En el árbol, seleccione **Modelo de comercio exterior \> Asignación de comercio exterior**.</span><span class="sxs-lookup"><span data-stu-id="40a02-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="40a02-273">Seleccione la ficha desplegable **Requisitos previos**.</span><span class="sxs-lookup"><span data-stu-id="40a02-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-274">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="40a02-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="40a02-275">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="40a02-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="40a02-276">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-276">Select **Designer**.</span></span>
5. <span data-ttu-id="40a02-277">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-277">Select **Designer**.</span></span>
6. <span data-ttu-id="40a02-278">En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="40a02-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="40a02-279">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="40a02-279">Select **Add root**.</span></span>
8. <span data-ttu-id="40a02-280">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="40a02-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-281">Actualmente, esta asignación hace referencia a la configuración de metadatos.</span><span class="sxs-lookup"><span data-stu-id="40a02-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="40a02-282">Los metadatos de la aplicación de esta configuración se ofrecerán mientras se diseña esta asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="40a02-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="40a02-283">Seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="40a02-284">Asignar la aplicación conectada a una asignación de modelo</span><span class="sxs-lookup"><span data-stu-id="40a02-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="40a02-285">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-285">Select **Edit**.</span></span>
2. <span data-ttu-id="40a02-286">En el **campo Aplicación conectada**, seleccione la aplicación **MyConnectedApp** .</span><span class="sxs-lookup"><span data-stu-id="40a02-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-287">Esta asignación hace referencia a los metadatos de la aplicación conectada seleccionada.</span><span class="sxs-lookup"><span data-stu-id="40a02-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="40a02-288">Si una asignación hace referencia a la configuración de metadatos y a la aplicación conectada al mismo tiempo, se utilizarán los metadatos de la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="40a02-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="40a02-289">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-289">Select **Designer**.</span></span>
4. <span data-ttu-id="40a02-290">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="40a02-290">Select **Designer**.</span></span>
5. <span data-ttu-id="40a02-291">En el árbol, seleccione **Dynamics 365 for Operations \> Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="40a02-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="40a02-292">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="40a02-292">Select **Add root**.</span></span>
7. <span data-ttu-id="40a02-293">En el campo **Tabla**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="40a02-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40a02-294">En este punto, se ofrecen más de dos tablas de la aplicación ya que esta asignación utiliza todos los metadatos de la aplicación conectada que se le ha asignado.</span><span class="sxs-lookup"><span data-stu-id="40a02-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="40a02-295">Seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="40a02-296">Seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="40a02-296">Select **Validate**.</span></span>

<span data-ttu-id="40a02-297">Ya ha enlazado elementos del modelo de datos con artículos de los orígenes de datos que se describen con detalles de los metadatos de la aplicación conectada que se ha asignado para esta asignación.</span><span class="sxs-lookup"><span data-stu-id="40a02-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="40a02-298">Cuando deba evaluar esta asignación de modelo mediante el uso de metadatos de una versión diferente de la aplicación, registre otra aplicación conectada, asígnela a esta asignación de modelo y valídela con los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="40a02-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40a02-299">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="40a02-299">Additional resources</span></span>

<span data-ttu-id="40a02-300">Como alternativa, puede reproducir la guía de tareas **Preparar metadatos de la aplicación que pueden usarse en RCS** en la aplicación, así como las guías de tareas **Acceder a metadatos de la aplicación mediante el uso de una configuración de ER** y **Acceder a metadatos de la aplicación mediante el uso de aplicaciones conectadas** en RCS.</span><span class="sxs-lookup"><span data-stu-id="40a02-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in the application as as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="40a02-301">Estas guías de tareas se pueden descargar en la página [Guías de tareas de informes electrónicos para Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="40a02-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>