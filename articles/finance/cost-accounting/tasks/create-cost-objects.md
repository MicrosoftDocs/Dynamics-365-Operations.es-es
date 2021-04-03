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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236803"
---
# <a name="create-cost-objects"></a><span data-ttu-id="4cfdc-103">Crear objetos de coste</span><span class="sxs-lookup"><span data-stu-id="4cfdc-103">Create cost objects</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4cfdc-104">Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste en la contabilidad de Costes a través de un conector de los datos.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-104">This procedure shows how to create cost objects by importing the cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="4cfdc-105">Se ha utilizado la empresa de demostración USMF para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-105">The USMF demo company was used to create this procedure.</span></span> 


## <a name="create-new-cost-objects"></a><span data-ttu-id="4cfdc-106">Crea nuevos objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-106">Create new cost objects</span></span>
1. <span data-ttu-id="4cfdc-107">Vaya a contabilidad de Costes > Dimensiones > dimensiones del objeto de Coste.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-107">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="4cfdc-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-108">Click New.</span></span>
3. <span data-ttu-id="4cfdc-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="4cfdc-110">En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-110">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="4cfdc-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="4cfdc-112">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-112">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="4cfdc-113">Configura el conector de datos</span><span class="sxs-lookup"><span data-stu-id="4cfdc-113">Configure the data connector</span></span>
1. <span data-ttu-id="4cfdc-114">Haga clic en Configurar proveedor de miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-114">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="4cfdc-115">Seleccione CostCenter para importar la dimensión de CostCenter en la contabilidad de Costes.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-115">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="4cfdc-116">En el campo Nombre de dimensión, seleccione el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-116">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="4cfdc-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4cfdc-117">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="4cfdc-118">Importar centros de coste</span><span class="sxs-lookup"><span data-stu-id="4cfdc-118">Import cost centers</span></span>
1. <span data-ttu-id="4cfdc-119">Haga clic en Importar miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-119">Click Import dimension members.</span></span>
2. <span data-ttu-id="4cfdc-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4cfdc-120">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="4cfdc-121">Ver los centros de coste importados</span><span class="sxs-lookup"><span data-stu-id="4cfdc-121">View the imported cost centers</span></span>
1. <span data-ttu-id="4cfdc-122">Haga clic en miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4cfdc-122">Click View dimension members.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]