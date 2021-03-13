---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 1: Creación de formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 1)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a3639b5ac28f8a571642e983906d658dabf05b1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093031"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a><span data-ttu-id="47dab-104">Informe electrónico Configurar el formato para contar y sumar (Parte 1: Creación de formato)</span><span class="sxs-lookup"><span data-stu-id="47dab-104">ER Configure format to do counting and summing (Part 1 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47dab-105">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="47dab-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="47dab-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="47dab-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="47dab-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="47dab-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="47dab-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="47dab-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="47dab-109">Obtenga acceso a la lista de configuraciones proporcionada por Microsoft</span><span class="sxs-lookup"><span data-stu-id="47dab-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="47dab-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="47dab-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="47dab-111">Asegúrese de que “Litware, Inc.”</span><span class="sxs-lookup"><span data-stu-id="47dab-111">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="47dab-112">está disponible y marcado como activo.</span><span class="sxs-lookup"><span data-stu-id="47dab-112">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="47dab-113">Seleccione "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="47dab-113">Select the "Litware, Inc."</span></span> <span data-ttu-id="47dab-114">Inc.</span><span class="sxs-lookup"><span data-stu-id="47dab-114">provider.</span></span>
3. <span data-ttu-id="47dab-115">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="47dab-115">Click Repositories.</span></span>
    * <span data-ttu-id="47dab-116">Si ya existe un repositorio del tipo "Recursos de Operations", omita los pasos restantes de la subtarea actual.</span><span class="sxs-lookup"><span data-stu-id="47dab-116">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="47dab-117">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="47dab-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="47dab-118">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="47dab-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="47dab-119">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="47dab-119">Click Create repository.</span></span>
7. <span data-ttu-id="47dab-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="47dab-120">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="47dab-121">Obtenga las configuraciones de Intrastat proporcionadas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="47dab-121">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="47dab-122">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="47dab-122">Click Open.</span></span>
2. <span data-ttu-id="47dab-123">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="47dab-123">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="47dab-124">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="47dab-124">Click Import.</span></span>
    * <span data-ttu-id="47dab-125">Haga clic en Importar para la versión 1.1 de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="47dab-125">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="47dab-126">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="47dab-126">Click Yes.</span></span>
5. <span data-ttu-id="47dab-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="47dab-127">Close the page.</span></span>
6. <span data-ttu-id="47dab-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="47dab-128">Close the page.</span></span>
7. <span data-ttu-id="47dab-129">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="47dab-129">Click Reporting configurations.</span></span>
8. <span data-ttu-id="47dab-130">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="47dab-130">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="47dab-131">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="47dab-131">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>

