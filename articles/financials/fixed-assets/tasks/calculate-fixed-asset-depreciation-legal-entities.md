--- 
title: "Calcular la amortización de activos fijos en las entidades jurídicas"
description: "La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b2575354af322827972ffa650e9c732170c5a6eb
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="e481b-103">Calcular la amortización de activos fijos en las entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="e481b-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e481b-104">La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="e481b-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="e481b-105">Este procedimiento muestra cómo establecer y ejecutar el proceso para varias entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="e481b-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="e481b-106">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="e481b-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="e481b-107">Configure diarios de ejecución de depreciación entre empresas</span><span class="sxs-lookup"><span data-stu-id="e481b-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="e481b-108">Vaya a Activos fijos > Configuración > Parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e481b-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="e481b-109">Expanda la sección de propuestas de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e481b-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="e481b-110">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e481b-110">Click Add.</span></span>
4. <span data-ttu-id="e481b-111">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e481b-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="e481b-112">En el campo Nombre del diario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e481b-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="e481b-113">Repita la configuración del diario en la página de parámetros de activos fijos en cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="e481b-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="e481b-114">Ejecución de depreciación</span><span class="sxs-lookup"><span data-stu-id="e481b-114">Depreciation run</span></span>
1. <span data-ttu-id="e481b-115">Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.</span><span class="sxs-lookup"><span data-stu-id="e481b-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="e481b-116">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e481b-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="e481b-117">El nombre del diario se tomará de forma predeterminado de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e481b-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="e481b-118">Puede cambiarlo aquí para la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="e481b-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="e481b-119">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="e481b-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="e481b-120">Seleccione las entidades jurídicas que se incluirán en la ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="e481b-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="e481b-121">Sólo se mostrarán en la lista las entidades jurídicas con diarios configurados para propuestas de activos fijos en la página de parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e481b-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="e481b-122">Seleccione Sí en el campo Registrar diarios.</span><span class="sxs-lookup"><span data-stu-id="e481b-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="e481b-123">El filtrado de campos incluye todos los activos fijos, grupos, y libros para las entidades jurídicas seleccionadas para esta ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="e481b-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="e481b-124">La opción de procesamiento por lotes se habilita de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e481b-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="e481b-125">Cuando se habilita esta opción, la creación y el registro de diarios y depreciación se ejecutará en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e481b-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="e481b-126">Haga clic en Crear diario.</span><span class="sxs-lookup"><span data-stu-id="e481b-126">Click Create journal.</span></span>
6. <span data-ttu-id="e481b-127">Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="e481b-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>


