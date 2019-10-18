---
title: Importar datos de las plantillas de la entidad de los datos de Excel que tengan varias hojas de cálculo
description: Este tema describe cómo importar datos mediante las plantillas de la entidad de los datos de Excel en Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: e27b657d3d38ace158bcf4481d1445195147816b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181965"
---
# <a name="import-data-from-excel-data-entity-templates-that-have-multiple-worksheets"></a><span data-ttu-id="26ae3-103">Importar datos de las plantillas de la entidad de los datos de Excel que tengan varias hojas de cálculo</span><span class="sxs-lookup"><span data-stu-id="26ae3-103">Import data from Excel data entity templates that have multiple worksheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26ae3-104">La administración de datos en la aplicación admite plantillas basadas en Microsoft Excel para entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="26ae3-104">Data management in the application supports Microsoft Excel-based templates for data entities.</span></span> <span data-ttu-id="26ae3-105">Estas plantillas pueden contener una o varias hojas de cálculo.</span><span class="sxs-lookup"><span data-stu-id="26ae3-105">These templates can contain one or more worksheets.</span></span> <span data-ttu-id="26ae3-106">Las plantillas con varias hojas de cálculo se utilizan a menudo cuando es conveniente administrar datos en un solo archivo e importarlos a múltiples entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="26ae3-106">Templates with multiple worksheets are often used when it is convenient to manage data in a single file and import it to multiple data entities.</span></span> <span data-ttu-id="26ae3-107">Un ejemplo serían sitios y almacenes.</span><span class="sxs-lookup"><span data-stu-id="26ae3-107">An example would be sites and warehouses.</span></span>

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a><span data-ttu-id="26ae3-108">Cargar un archivo una vez y asígnarlo a todas las entidades</span><span class="sxs-lookup"><span data-stu-id="26ae3-108">Upload a file once and map it to all entities</span></span>
<span data-ttu-id="26ae3-109">Tomemos un ejemplo en el que exista un archivo de Excel con las hojas de cálculo denominadas **Sitios** y **Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="26ae3-109">Let's take an example where there is one Excel file with worksheets called **Sites** and **Warehouses**.</span></span> <span data-ttu-id="26ae3-110">Para configurar el proyecto de la importación de datos, agregaría la primera entidad de datos, **Sitios** y después cargaría el archivo.</span><span class="sxs-lookup"><span data-stu-id="26ae3-110">To set up the data import project, you would add the first data entity, **Sites** and then upload the file.</span></span> <span data-ttu-id="26ae3-111">Podrá seleccionar **Sitios** como la hoja de cálculo que se utilizará para esta entidad.</span><span class="sxs-lookup"><span data-stu-id="26ae3-111">You will be able to select **Sites** as the worksheet to be used for this entity.</span></span>

<span data-ttu-id="26ae3-112">Si agrega la segunda entidad **Almacenes** sin salir del formulario **Agregar archivo** , la búsqueda de la hoja de cálculo le permitirá seleccionar la hoja de cálculo **Almacenes** sin tener que cargar el archivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="26ae3-112">If you add the second entity **Warehouses** without leaving the **Add file** form, the worksheet lookup will let you select the **Warehouses** worksheet without having to upload the file again.</span></span> <span data-ttu-id="26ae3-113">El único motivo para cargar un nuevo archivo sería si los datos **Almacenes** figuraban en un archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="26ae3-113">The only reason to upload a new file would be if the **Warehouses** data was in a different file.</span></span>

![Varias hojas de cálculo](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a><span data-ttu-id="26ae3-115">Corregir hoja de cálculo para la asignación de la entidad</span><span class="sxs-lookup"><span data-stu-id="26ae3-115">Fix worksheet to entity mapping</span></span>

<span data-ttu-id="26ae3-116">La asignación de la hoja de cálculo a una entidad de datos en el trabajo de importación se puede corregir desde la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="26ae3-116">The mapping of the worksheet to a data entity in the import job can be fixed from the grid.</span></span> <span data-ttu-id="26ae3-117">La columna **Hoja de cálculo** en la cuadrícula muestra las hojas de cálculo del archivo que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="26ae3-117">The **Worksheet** column in the grid shows the worksheets from the file that was mapped.</span></span> <span data-ttu-id="26ae3-118">Puede elegir otra hoja de cálculo del menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="26ae3-118">You can choose a different worksheet from the drop-down menu.</span></span> <span data-ttu-id="26ae3-119">Si la hoja de cálculo seleccionada ya está asignada a una entidad en el proyecto de los datos, el sistema le pedirá que confirme el cambio.</span><span class="sxs-lookup"><span data-stu-id="26ae3-119">If the chosen worksheet is already mapped to an entity in the data project, the system asks you to confirm the change.</span></span> <span data-ttu-id="26ae3-120">Recomendamos que corrija todas las asignaciones en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="26ae3-120">We recommend that you fix all mappings in the grid.</span></span>

![Actualizar la asignación de hoja de cálculo](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a><span data-ttu-id="26ae3-122">Volver a asignar a un nuevo archivo</span><span class="sxs-lookup"><span data-stu-id="26ae3-122">Re-map to a new file</span></span>

<span data-ttu-id="26ae3-123">En casos en los que una versión nueva del mismo archivo o un archivo completamente nuevo se deba cargar para las entidades existentes en un proyecto de datos, debe usar la experiencia **Agregar archivo** y agregar las entidades de nuevo como si las agregara por primera vez.</span><span class="sxs-lookup"><span data-stu-id="26ae3-123">In cases where a new version of the same file or a completely new file must be uploaded for existing entities in a data project, you must use the **Add file** experience, and add the entities again as if they were being added for the first time.</span></span> <span data-ttu-id="26ae3-124">El sistema confirmará que desea sobrescribir las entidades existentes del proyecto de datos antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="26ae3-124">The system will confirm that you want to overwrite the existing entities in the data project before proceeding.</span></span> <span data-ttu-id="26ae3-125">Las entidades que no están agregadas de nuevo (o sobrescritas) continuarán llevando a cabo las asignaciones anteriores del archivo anterior.</span><span class="sxs-lookup"><span data-stu-id="26ae3-125">Entities that are not added again (or overwritten) will continue to hold the previous mappings from the previous file.</span></span>

## <a name="upload-a-file-using-run-project"></a><span data-ttu-id="26ae3-126">Cargar archivo mediante Ejecutar proyecto</span><span class="sxs-lookup"><span data-stu-id="26ae3-126">Upload a file using Run project</span></span>

<span data-ttu-id="26ae3-127">Puede cargar un archivo de Excel mediante la opción **Ejecutar proyecto** para ejecutar un proyecto de importación.</span><span class="sxs-lookup"><span data-stu-id="26ae3-127">You can upload an Excel file while using the **Run project** option to execute an import project.</span></span> <span data-ttu-id="26ae3-128">Debe tener cuidado de cargar solo los archivos con las mismas hojas de cálculo que las asignaciones existentes en entidades de datos en los proyectos de datos.</span><span class="sxs-lookup"><span data-stu-id="26ae3-128">You must be careful to upload only files that have the same worksheets as the existing mappings on the data entities in the data project.</span></span> <span data-ttu-id="26ae3-129">Si una hoja de cálculo no se encuentra en el archivo recién cargado, el sistema muestra un error y detendrá la importación.</span><span class="sxs-lookup"><span data-stu-id="26ae3-129">If a worksheet is not found in the newly uploaded file, the system displays an error and will stop the import.</span></span> <span data-ttu-id="26ae3-130">Si la asignación a la hoja de cálculo debe cambiarse para una entidad, las asignaciones del proyecto de datos se deben actualizar primero desde el proyecto de datos antes de utilizar el archivo en la experiencia **Ejecutar proyecto**.</span><span class="sxs-lookup"><span data-stu-id="26ae3-130">If the mapping to the worksheet must be changed for an entity, then the mappings in the data project must be first updated from within the data project before using the file in the **Run project** experience.</span></span>
