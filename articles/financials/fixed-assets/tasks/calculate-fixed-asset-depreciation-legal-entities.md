--- 
title: "Calcular la amortización de activos fijos en las entidades jurídicas"
description: "Este procedimiento muestra cómo establecer y ejecutar el proceso de depreciación para varias entidades jurídicas."
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4221acf200f41ca39803bcd56c1b05e0d87bd948
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="cf45e-103">Calcular la amortización de activos fijos en las entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="cf45e-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf45e-104">La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="cf45e-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="cf45e-105">Este procedimiento muestra cómo establecer y ejecutar el proceso para varias entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="cf45e-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="cf45e-106">Usa el rol de contable.</span><span class="sxs-lookup"><span data-stu-id="cf45e-106">It uses the accountant role.</span></span>  

<span data-ttu-id="cf45e-107">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="cf45e-107">This recording uses the USMF demo company.</span></span>


<span data-ttu-id="cf45e-108">Subtarea de (16) pasos: Configure diarios de ejecución de depreciación entre empresas.</span><span class="sxs-lookup"><span data-stu-id="cf45e-108">Steps (16) Sub-task: Set up cross company depreciation run journals.</span></span> 

1. <span data-ttu-id="cf45e-109">En primer lugar, debe configurar los diarios que usará en la depreciación entre empresas en cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="cf45e-109">First, you must set up the journals to be used in the cross company depreciation run in each legal entity.</span></span> <span data-ttu-id="cf45e-110">Vaya a Activos fijos > Configuración > Parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-110">Go to Fixed assets > Setup > Fixed assets parameters.</span></span> 
2. <span data-ttu-id="cf45e-111">Expanda la sección de propuestas de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-111">Expand the Fixed asset proposals section.</span></span> 
3. <span data-ttu-id="cf45e-112">Cree un registro con el nombre del diario que se usará para cada capa de registro en la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="cf45e-112">Create a record with the journal name to be used for each posting layer in the legal entity.</span></span> <span data-ttu-id="cf45e-113">Si los libros no se registran en la contabilidad general, la capa de registro Ninguna se debe seleccionar con el diario asociado.</span><span class="sxs-lookup"><span data-stu-id="cf45e-113">If books do not post to the general ledger, then the None posting layer should be selected with the associated journal.</span></span> <span data-ttu-id="cf45e-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="cf45e-114">Click Add.</span></span> 
4. <span data-ttu-id="cf45e-115">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf45e-115">In the Posting layer field, enter or select a value.</span></span> 
5. <span data-ttu-id="cf45e-116">En el campo Nombre del diario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf45e-116">In the Journal name field, enter or select a value.</span></span> 
6. <span data-ttu-id="cf45e-117">Repita la configuración del diario en la página de parámetros de activos fijos en cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="cf45e-117">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span> 

<span data-ttu-id="cf45e-118">Subtarea: calcular depreciación.</span><span class="sxs-lookup"><span data-stu-id="cf45e-118">Sub-task: Calculate depreciation</span></span>

1. <span data-ttu-id="cf45e-119">Use la página Crear propuesta de depreciación para iniciar la ejecución de depreciación en entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="cf45e-119">Use the Create depreciation proposal page to start your depreciation run across legal entities.</span></span> <span data-ttu-id="cf45e-120">Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cf45e-120">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span> 
2. <span data-ttu-id="cf45e-121">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf45e-121">In the Posting layer field, enter or select a value.</span></span> 
3. <span data-ttu-id="cf45e-122">El nombre del diario se tomará de forma predeterminado de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-122">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="cf45e-123">Puede cambiarlo aquí para la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="cf45e-123">It can be changed here for the current legal entity.</span></span> 
4. <span data-ttu-id="cf45e-124">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="cf45e-124">In the To date field, enter a date.</span></span> 
5. <span data-ttu-id="cf45e-125">Seleccione las entidades jurídicas que se incluirán en la ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cf45e-125">Select the legal entities to be included in the depreciation run.</span></span> <span data-ttu-id="cf45e-126">Sólo se mostrarán en la lista las entidades jurídicas con diarios configurados para propuestas de activos fijos en la página de parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-126">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span> 
6. <span data-ttu-id="cf45e-127">Cuando está habilitada, la opción Registrar diarios enviará automáticamente los diarios de depreciación cuando se crean.</span><span class="sxs-lookup"><span data-stu-id="cf45e-127">When enabled, the Post journals option will automatically post the depreciation journals when they are created.</span></span> <span data-ttu-id="cf45e-128">Si no están seleccionados, los diarios se crearán, pero no se registrarán, para que pueda revisar los detalles antes de registrarlos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-128">When not selected, the journals will be created, but not posted, so you can review the details before posting.</span></span> <span data-ttu-id="cf45e-129">Seleccione Sí en el campo Registrar diarios.</span><span class="sxs-lookup"><span data-stu-id="cf45e-129">Select Yes in the Post journals field.</span></span> 
7. <span data-ttu-id="cf45e-130">El filtrado de campos incluye todos los activos fijos, grupos, y libros para las entidades jurídicas seleccionadas para esta ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cf45e-130">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span> 
8. <span data-ttu-id="cf45e-131">La opción de procesamiento por lotes se habilita de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cf45e-131">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="cf45e-132">Cuando se habilita esta opción, la creación y el registro de diarios y depreciación se ejecutará en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="cf45e-132">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span> 
9. <span data-ttu-id="cf45e-133">Haga clic en Crear diario.</span><span class="sxs-lookup"><span data-stu-id="cf45e-133">Click Create journal.</span></span> 
10. <span data-ttu-id="cf45e-134">Debe ver los diarios de depreciación creados en las entidades jurídicas respectivas.</span><span class="sxs-lookup"><span data-stu-id="cf45e-134">You must view the depreciation journals created in the respective legal entities.</span></span> <span data-ttu-id="cf45e-135">Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="cf45e-135">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

