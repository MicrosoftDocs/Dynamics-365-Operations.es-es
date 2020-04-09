---
title: Calcular la amortización de activos fijos en las entidades jurídicas
description: La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 074a1b80584050302920a95c20fb547523a4866c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142924"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a><span data-ttu-id="3e17a-103">Calcular la amortización de activos fijos en las entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="3e17a-103">Calculate fixed asset depreciation across legal entities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e17a-104">La depreciación de activos fijos se puede ejecutar en entidades jurídicas en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="3e17a-104">Fixed asset depreciation can be run across legal entities in a single step.</span></span> <span data-ttu-id="3e17a-105">Este procedimiento muestra cómo establecer y ejecutar el proceso para varias entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="3e17a-105">This procedure shows you to how set up and run the process for multiple legal entities.</span></span> <span data-ttu-id="3e17a-106">Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="3e17a-106">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="set-up-cross-company-depreciation-run-journals"></a><span data-ttu-id="3e17a-107">Configure diarios de ejecución de depreciación entre empresas</span><span class="sxs-lookup"><span data-stu-id="3e17a-107">Set up cross company depreciation run journals</span></span>
1. <span data-ttu-id="3e17a-108">Vaya a Activos fijos > Configuración > Parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3e17a-108">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="3e17a-109">Expanda la sección de propuestas de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3e17a-109">Expand the Fixed asset proposals section.</span></span>
3. <span data-ttu-id="3e17a-110">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3e17a-110">Click Add.</span></span>
4. <span data-ttu-id="3e17a-111">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3e17a-111">In the Posting layer field, enter or select a value.</span></span>
5. <span data-ttu-id="3e17a-112">En el campo Nombre del diario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3e17a-112">In the Journal name field, enter or select a value.</span></span>
    * <span data-ttu-id="3e17a-113">Repita la configuración del diario en la página de parámetros de activos fijos en cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="3e17a-113">Repeat the journal setup on the Fixed asset parameters page in each legal entity.</span></span>  

## <a name="depreciation-run"></a><span data-ttu-id="3e17a-114">Ejecución de depreciación</span><span class="sxs-lookup"><span data-stu-id="3e17a-114">Depreciation run</span></span>
1. <span data-ttu-id="3e17a-115">Vaya a Activos fijos > Movimientos de diario > Crear propuesta de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3e17a-115">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="3e17a-116">En el campo Capa de registro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3e17a-116">In the Posting layer field, enter or select a value.</span></span>
    * <span data-ttu-id="3e17a-117">El nombre del diario se tomará de forma predeterminado de los parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3e17a-117">The journal name will default from the Fixed asset parameters.</span></span> <span data-ttu-id="3e17a-118">Puede cambiarlo aquí para la entidad jurídica actual.</span><span class="sxs-lookup"><span data-stu-id="3e17a-118">It can be changed here for the current legal entity.</span></span>  
3. <span data-ttu-id="3e17a-119">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="3e17a-119">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="3e17a-120">Seleccione las entidades jurídicas que se incluirán en la ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3e17a-120">Select the legal entities to be included in the depreciation run.</span></span>  
    * <span data-ttu-id="3e17a-121">Sólo se mostrarán en la lista las entidades jurídicas con diarios configurados para propuestas de activos fijos en la página de parámetros de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3e17a-121">Only legal entities with journals set up for Fixed asset proposals on the Fixed asset parameters page will be shown in the list.</span></span>  
4. <span data-ttu-id="3e17a-122">Seleccione Sí en el campo Registrar diarios.</span><span class="sxs-lookup"><span data-stu-id="3e17a-122">Select Yes in the Post journals field.</span></span>
    * <span data-ttu-id="3e17a-123">El filtrado de campos incluye todos los activos fijos, grupos, y libros para las entidades jurídicas seleccionadas para esta ejecución de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3e17a-123">Filtering fields include all fixed assets, groups, and books for the legal entities selected for this depreciation run.</span></span>  
    * <span data-ttu-id="3e17a-124">La opción de procesamiento por lotes se habilita de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3e17a-124">The Batch processing option is enabled by default.</span></span> <span data-ttu-id="3e17a-125">Cuando se habilita esta opción, la creación y el registro de diarios y depreciación se ejecutará en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3e17a-125">When this option is enabled, the depreciation journal creation and posting will run in the background.</span></span>  
5. <span data-ttu-id="3e17a-126">Haga clic en Crear diario.</span><span class="sxs-lookup"><span data-stu-id="3e17a-126">Click Create journal.</span></span>
6. <span data-ttu-id="3e17a-127">Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3e17a-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>

