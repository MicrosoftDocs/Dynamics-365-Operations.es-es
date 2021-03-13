---
title: Preparar metadatos de la aplicación para usarse en RCS
description: Este tema describe cómo crear una nueva configuración de informes que contenga metadatos de la aplicación.
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5f55d089a88642cb2bda70274472ad0f0e45cd7
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094249"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="1ecd4-103">Preparar metadatos de la aplicación para usarse en RCS</span><span class="sxs-lookup"><span data-stu-id="1ecd4-103">Prepare application metadata to be used in RCS</span></span>
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ecd4-104">Los siguiente pasos explican cómo un usuario en el rol de Administrador del sistema o Desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos (ER) que contiene metadatos de la aplicación para diseñar configuraciones de asignación del modelo de ER en Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1ecd4-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="1ecd4-105">Esta configuración se utilizará para diseñar una configuración de asignación del modelo de ER de ejemplo para acceder a transacciones de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="1ecd4-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="1ecd4-107">Para completar estos pasos, primero debe completar los pasos del tema [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1ecd4-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1ecd4-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1ecd4-108">Prerequisites</span></span>
1.    <span data-ttu-id="1ecd4-109">Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.    <span data-ttu-id="1ecd4-110">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1ecd4-111">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1ecd4-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.    <span data-ttu-id="1ecd4-112">Haga clic en **Configuraciones de metadatos**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-112">Click **Metadata configurations**.</span></span> 
4.    <span data-ttu-id="1ecd4-113">Supongamos que RCS se utilizará para diseñar una solución de ER para una aplicación de Finance and Operations que generará documentos electrónicos que contienen información de dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="1ecd4-114">Para especificar la asignación entre el modelo de datos de ER y los orígenes de datos requeridos, en RCS necesitamos tener acceso a los metadatos de la aplicación de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="1ecd4-115">Por lo tanto, como parte del diseño de la solución de ER, configuramos una nueva configuración de metadatos de ER que contiene todos los metadatos que se requieren actualmente para generar informes de ER para el dominio empresarial seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="1ecd4-116">Agregar configuración de metadatos</span><span class="sxs-lookup"><span data-stu-id="1ecd4-116">Add metadata configuration</span></span> 
1.    <span data-ttu-id="1ecd4-117">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.    <span data-ttu-id="1ecd4-118">En el campo **Nombre**, escriba 'Metadatos de comercio exterior'.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.    <span data-ttu-id="1ecd4-119">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-119">Click **Create configuration**.</span></span> 
4.    <span data-ttu-id="1ecd4-120">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-120">Click **Designer**.</span></span> 
5.    <span data-ttu-id="1ecd4-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ecd4-122">Puede seleccionar todos los metadatos para toda la aplicación o modelos o módulos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="1ecd4-123">Tenga en cuenta que, en este caso, los siguientes metadatos se agregarán automáticamente: tablas de registros, enumeraciones y tipos de datos extendidos.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="1ecd4-124">Cuando se necesitan tipos adicionales de metadatos, deben agregarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="1ecd4-125">Disponemos de algunos metadatos relacionados con transacciones de comercio exterior seleccionando elementos de metadatos manualmente.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.    <span data-ttu-id="1ecd4-126">Haga clic en **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-126">Click **Add data source**.</span></span> 
7.    <span data-ttu-id="1ecd4-127">Haga clic en **Registros de tabla**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-127">Click **Table records**.</span></span> 
8.    <span data-ttu-id="1ecd4-128">Use el filtro rápido para filtrar el campo **Nombre** con un valor de 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.    <span data-ttu-id="1ecd4-129">Seleccione el registro de tabla de **Intrastat** .</span><span class="sxs-lookup"><span data-stu-id="1ecd4-129">Select the **Intrastat** table record.</span></span> 
10.    <span data-ttu-id="1ecd4-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-130">Click **OK**.</span></span>
  
<span data-ttu-id="1ecd4-131">Agregamos información de metadatos sobre la tabla de registros de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11.    <span data-ttu-id="1ecd4-132">En el árbol, expanda **Registros de tabla de Intrastat**\>**Relaciones**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12.    <span data-ttu-id="1ecd4-133">En el árbol, seleccione **Registros de tabla de Intrastat**\>**Relations\IntrastatCommodity (Registros de tabla EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>     
13.    <span data-ttu-id="1ecd4-134">Haga clic en **Agregar metadatos**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1ecd4-135">Los metadatos sobre las relaciones necesarias para la tabla de registros seleccionada se deben agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16.    <span data-ttu-id="1ecd4-136">Haga clic en **Agregar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-136">Click **Add data source**.</span></span> 
17.    <span data-ttu-id="1ecd4-137">Haga clic en **Enumeración**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-137">Click **Enumeration**.</span></span> 
18.    <span data-ttu-id="1ecd4-138">Use el filtro rápido para filtrar el campo **Nombre** con un valor de 'IntrastatDirection'.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19.    <span data-ttu-id="1ecd4-139">Seleccione el registro **Enumeración de IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20.    <span data-ttu-id="1ecd4-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-140">Click **OK**.</span></span> 
21.    <span data-ttu-id="1ecd4-141">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-141">Click **Save**.</span></span>  
22.    <span data-ttu-id="1ecd4-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="1ecd4-143">Completar la versión de borrador de la configuración de metadatos</span><span class="sxs-lookup"><span data-stu-id="1ecd4-143">Complete the draft version of metadata configuration</span></span>
1.    <span data-ttu-id="1ecd4-144">Haga clic en **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-144">Click **Change status**.</span></span> 
2.    <span data-ttu-id="1ecd4-145">Haga clic en **Completar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-145">Click **Complete**.</span></span> 
3.    <span data-ttu-id="1ecd4-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-146">Click **OK**.</span></span> 
4.    <span data-ttu-id="1ecd4-147">Seleccione la versión completada **1**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="1ecd4-148">Exportar la versión completada de la configuración de metadatos desde la aplicación como archivo XML</span><span class="sxs-lookup"><span data-stu-id="1ecd4-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.    <span data-ttu-id="1ecd4-149">Haga clic en **Intercambiar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-149">Click **Exchange**.</span></span> 
2.    <span data-ttu-id="1ecd4-150">Haga clic en **Exportar como archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-150">Click **Export as XML file**.</span></span> 
3.    <span data-ttu-id="1ecd4-151">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-151">Click **OK**.</span></span> 
    
<span data-ttu-id="1ecd4-152">La configuración de metadatos de ER creada se ha guardado como archivo XML que se puede importar a RCS y utilizar como la fuente de información sobre metadatos para el dominio empresarial de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="1ecd4-153">Según esta información, podemos especificar la asignación entre los metadatos de la aplicación y el modelo de datos de ER.</span><span class="sxs-lookup"><span data-stu-id="1ecd4-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>
