--- 
title: "Preparar modelos de datos para usar archivos de gestión documental en salidas de formato"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f99259056fab2d56d1ccf7487681c183551c64f
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="prepare-data-model-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="079f7-103">Preparar modelos de datos para usar archivos de gestión documental en salidas de formato</span><span class="sxs-lookup"><span data-stu-id="079f7-103">Prepare data model to use Document Management files in format outputs</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="079f7-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="079f7-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="079f7-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="079f7-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="079f7-106">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="079f7-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="079f7-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="079f7-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="079f7-108">Obtenga acceso a la lista de configuraciones proporcionada por Microsoft</span><span class="sxs-lookup"><span data-stu-id="079f7-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="079f7-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="079f7-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="079f7-110">Asegúrese de que el proveedor “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="079f7-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="079f7-111">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="079f7-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="079f7-112">Seleccione el proveedor "Litware,</span><span class="sxs-lookup"><span data-stu-id="079f7-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="079f7-113">Inc.</span><span class="sxs-lookup"><span data-stu-id="079f7-113">provider.</span></span>
3. <span data-ttu-id="079f7-114">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="079f7-114">Click Repositories.</span></span>
    * <span data-ttu-id="079f7-115">Si ya existe un repositorio tipo “Recursos de operaciones", omita los pasos restantes de la subtarea actual.</span><span class="sxs-lookup"><span data-stu-id="079f7-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="079f7-116">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="079f7-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="079f7-117">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="079f7-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="079f7-118">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="079f7-118">Click Create repository.</span></span>
7. <span data-ttu-id="079f7-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="079f7-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="079f7-120">Obtenga las configuraciones del modelo de factura de Cliente proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="079f7-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="079f7-121">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="079f7-121">Click Show filters.</span></span>
2. <span data-ttu-id="079f7-122">Aplique los filtros siguientes: Introduzca un valor de filtro de “Recursos de operaciones” en el campo ”Nombre” mediante el operador de filtro “comienza con”; introduzca un valor de filtro de "" en el campo “Descripción”, mediante el operador de filtro “comienza con”</span><span class="sxs-lookup"><span data-stu-id="079f7-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="079f7-123">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="079f7-123">Click Show filters.</span></span>
4. <span data-ttu-id="079f7-124">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="079f7-124">Click Open.</span></span>
5. <span data-ttu-id="079f7-125">En el árbol, seleccione “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="079f7-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="079f7-126">Seleccione la configuración del modelo “Modelo de factura del cliente” para importarla.</span><span class="sxs-lookup"><span data-stu-id="079f7-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="079f7-127">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="079f7-127">Click Import.</span></span>
    * <span data-ttu-id="079f7-128">Haga clic en importar la versión 1 de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="079f7-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="079f7-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="079f7-129">Click Yes.</span></span>
8. <span data-ttu-id="079f7-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="079f7-130">Close the page.</span></span>
9. <span data-ttu-id="079f7-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="079f7-131">Close the page.</span></span>
10. <span data-ttu-id="079f7-132">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="079f7-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="079f7-133">En el árbol, seleccione “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="079f7-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="079f7-134">Cree el modelo derivado para admitir el acceso a los archivos de la gestión de documentos.</span><span class="sxs-lookup"><span data-stu-id="079f7-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="079f7-135">Usted creará su propia configuración del modelo de factura de Cliente derivándola de la configuración proporcionada por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="079f7-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="079f7-136">Use esta configuración para implementar el acceso a los archivos de gestión de documentos, y permita que estén disponibles para los documentos electrónicos que cree en base a este modelo.</span><span class="sxs-lookup"><span data-stu-id="079f7-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="079f7-137">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="079f7-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="079f7-138">En el campo Nuevo, introduzca “Derivar de nombre: Modelo de factura de cliente, Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="079f7-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="079f7-139">En el campo Nombre, introduzca "Modelo de factura de cliente (personalizado)".</span><span class="sxs-lookup"><span data-stu-id="079f7-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="079f7-140">Modelo de factura de cliente (personalizado)</span><span class="sxs-lookup"><span data-stu-id="079f7-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="079f7-141">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="079f7-141">Click Create configuration.</span></span>


