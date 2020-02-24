---
title: 'Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 1: Preparación del modelo de datos)'
description: En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b82b1719990caeb1b383ab806a3e09a4c4a6e41a
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026143"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="dac0e-103">Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 1: Preparación del modelo de datos)</span><span class="sxs-lookup"><span data-stu-id="dac0e-103">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dac0e-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="dac0e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="dac0e-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="dac0e-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="dac0e-106">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="dac0e-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="dac0e-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="dac0e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="dac0e-108">Obtenga acceso a la lista de configuraciones proporcionada por Microsoft</span><span class="sxs-lookup"><span data-stu-id="dac0e-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="dac0e-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="dac0e-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="dac0e-110">Asegúrese de que el proveedor “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="dac0e-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="dac0e-111">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="dac0e-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="dac0e-112">Seleccione el proveedor "Litware,</span><span class="sxs-lookup"><span data-stu-id="dac0e-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="dac0e-113">Inc.</span><span class="sxs-lookup"><span data-stu-id="dac0e-113">provider.</span></span>
3. <span data-ttu-id="dac0e-114">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="dac0e-114">Click Repositories.</span></span>
    * <span data-ttu-id="dac0e-115">Si ya existe un repositorio tipo “Recursos de operaciones", omita los pasos restantes de la subtarea actual.</span><span class="sxs-lookup"><span data-stu-id="dac0e-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="dac0e-116">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="dac0e-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="dac0e-117">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="dac0e-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="dac0e-118">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="dac0e-118">Click Create repository.</span></span>
7. <span data-ttu-id="dac0e-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dac0e-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="dac0e-120">Obtenga las configuraciones del modelo de factura de Cliente proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="dac0e-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="dac0e-121">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="dac0e-121">Click Show filters.</span></span>
2. <span data-ttu-id="dac0e-122">Aplique los filtros siguientes: Introduzca un valor de filtro de “Recursos de operaciones” en el campo ”Nombre” mediante el operador de filtro “comienza con”; introduzca un valor de filtro de "" en el campo “Descripción”, mediante el operador de filtro “comienza con”</span><span class="sxs-lookup"><span data-stu-id="dac0e-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="dac0e-123">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="dac0e-123">Click Show filters.</span></span>
4. <span data-ttu-id="dac0e-124">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="dac0e-124">Click Open.</span></span>
5. <span data-ttu-id="dac0e-125">En el árbol, seleccione “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="dac0e-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="dac0e-126">Seleccione la configuración del modelo “Modelo de factura del cliente” para importarla.</span><span class="sxs-lookup"><span data-stu-id="dac0e-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="dac0e-127">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="dac0e-127">Click Import.</span></span>
    * <span data-ttu-id="dac0e-128">Haga clic en importar la versión 1 de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dac0e-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="dac0e-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="dac0e-129">Click Yes.</span></span>
8. <span data-ttu-id="dac0e-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dac0e-130">Close the page.</span></span>
9. <span data-ttu-id="dac0e-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="dac0e-131">Close the page.</span></span>
10. <span data-ttu-id="dac0e-132">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="dac0e-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="dac0e-133">En el árbol, seleccione “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="dac0e-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="dac0e-134">Cree el modelo derivado para admitir el acceso a los archivos de la gestión de documentos.</span><span class="sxs-lookup"><span data-stu-id="dac0e-134">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="dac0e-135">Usted creará su propia configuración del modelo de factura de Cliente derivándola de la configuración proporcionada por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dac0e-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="dac0e-136">Use esta configuración para implementar el acceso a los archivos de gestión de documentos, y permita que estén disponibles para los documentos electrónicos que cree en base a este modelo.</span><span class="sxs-lookup"><span data-stu-id="dac0e-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="dac0e-137">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="dac0e-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="dac0e-138">En el campo Nuevo, introduzca “Derivar de nombre: Modelo de factura de cliente, Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="dac0e-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="dac0e-139">En el campo Nombre, introduzca "Modelo de factura de cliente (personalizado)".</span><span class="sxs-lookup"><span data-stu-id="dac0e-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="dac0e-140">Modelo de factura de cliente (personalizado)</span><span class="sxs-lookup"><span data-stu-id="dac0e-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="dac0e-141">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="dac0e-141">Click Create configuration.</span></span>

