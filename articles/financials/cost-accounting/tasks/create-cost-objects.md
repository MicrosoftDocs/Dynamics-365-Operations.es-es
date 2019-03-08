---
title: Crear objetos de coste
description: Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, Enterprise Edition, en la contabilidad de Costes a través de un conector de los datos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e12de1d51658092fb19f652cef7c1cc78b255b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "322683"
---
# <a name="create-cost-objects"></a><span data-ttu-id="12b6b-103">Crear objetos de coste</span><span class="sxs-lookup"><span data-stu-id="12b6b-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12b6b-104">Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, Enterprise Edition, en la contabilidad de Costes a través de un conector de los datos.</span><span class="sxs-lookup"><span data-stu-id="12b6b-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations, Enterprise edition cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="12b6b-105">Se ha utilizado la empresa de demostración USMF para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="12b6b-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="12b6b-106">Este procedimiento se utiliza para la función contabilidad de cuentas, que se ha añadido a Dynamics 365 for Operations, versión 1611.</span><span class="sxs-lookup"><span data-stu-id="12b6b-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="12b6b-107">Crea nuevos objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="12b6b-107">Create new cost objects</span></span>
1. <span data-ttu-id="12b6b-108">Vaya a contabilidad de Costes > Dimensiones > dimensiones del objeto de Coste.</span><span class="sxs-lookup"><span data-stu-id="12b6b-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="12b6b-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="12b6b-109">Click New.</span></span>
3. <span data-ttu-id="12b6b-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="12b6b-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="12b6b-111">En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="12b6b-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="12b6b-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="12b6b-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="12b6b-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="12b6b-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="12b6b-114">Configura el conector de datos</span><span class="sxs-lookup"><span data-stu-id="12b6b-114">Configure the data connector</span></span>
1. <span data-ttu-id="12b6b-115">Haga clic en Configurar proveedor de miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="12b6b-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="12b6b-116">Seleccione CostCenter para importar la dimensión de CostCenter en la contabilidad de Costes.</span><span class="sxs-lookup"><span data-stu-id="12b6b-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="12b6b-117">En el campo Nombre de dimensión, seleccione el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="12b6b-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="12b6b-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="12b6b-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="12b6b-119">Importar centros de coste</span><span class="sxs-lookup"><span data-stu-id="12b6b-119">Import cost centers</span></span>
1. <span data-ttu-id="12b6b-120">Haga clic en Importar miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="12b6b-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="12b6b-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="12b6b-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="12b6b-122">Ver los centros de coste importados</span><span class="sxs-lookup"><span data-stu-id="12b6b-122">View the imported cost centers</span></span>
1. <span data-ttu-id="12b6b-123">Haga clic en miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="12b6b-123">Click View dimension members.</span></span>

