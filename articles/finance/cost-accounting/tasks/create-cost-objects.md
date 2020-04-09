---
title: Crear objetos de coste
description: Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste en la contabilidad de Costes a través de un conector de los datos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed020348e50158362fda7b6b36dcdb17c48b4532
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142326"
---
# <a name="create-cost-objects"></a><span data-ttu-id="856bd-103">Crear objetos de coste</span><span class="sxs-lookup"><span data-stu-id="856bd-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="856bd-104">Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste en la contabilidad de Costes a través de un conector de los datos.</span><span class="sxs-lookup"><span data-stu-id="856bd-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="856bd-105">Se ha utilizado la empresa de demostración USMF para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="856bd-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="856bd-106">Crea nuevos objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="856bd-106">Create new cost objects</span></span>
1. <span data-ttu-id="856bd-107">Vaya a contabilidad de Costes > Dimensiones > dimensiones del objeto de Coste.</span><span class="sxs-lookup"><span data-stu-id="856bd-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="856bd-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="856bd-108">Click New.</span></span>
3. <span data-ttu-id="856bd-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="856bd-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="856bd-110">En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="856bd-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="856bd-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="856bd-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="856bd-112">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="856bd-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="856bd-113">Configura el conector de datos</span><span class="sxs-lookup"><span data-stu-id="856bd-113">Configure the data connector</span></span>
1. <span data-ttu-id="856bd-114">Haga clic en Configurar proveedor de miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="856bd-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="856bd-115">Seleccione CostCenter para importar la dimensión de CostCenter en la contabilidad de Costes.</span><span class="sxs-lookup"><span data-stu-id="856bd-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="856bd-116">En el campo Nombre de dimensión, seleccione el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="856bd-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="856bd-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="856bd-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="856bd-118">Importar centros de coste</span><span class="sxs-lookup"><span data-stu-id="856bd-118">Import cost centers</span></span>
1. <span data-ttu-id="856bd-119">Haga clic en Importar miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="856bd-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="856bd-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="856bd-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="856bd-121">Ver los centros de coste importados</span><span class="sxs-lookup"><span data-stu-id="856bd-121">View the imported cost centers</span></span>
1. <span data-ttu-id="856bd-122">Haga clic en miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="856bd-122">Click View dimension members.</span></span>

