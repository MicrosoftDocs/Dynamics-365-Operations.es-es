--- 
title: Crear objetos de coste
description: "Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, a la contabilidad de Costes a través de un conector de los datos."
author: ShylaThompson
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 571406164236c7c079e059367e5d757cc4cefb1f
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="create-cost-objects"></a><span data-ttu-id="06940-103">Crear objetos de coste</span><span class="sxs-lookup"><span data-stu-id="06940-103">Create cost objects</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06940-104">Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, a la contabilidad de Costes a través de un conector de los datos.</span><span class="sxs-lookup"><span data-stu-id="06940-104">This procedure shows how to create cost objects by importing the Dynamics 365 for Finance and Operations cost center financial dimension into Cost accounting via a data connector.</span></span> <span data-ttu-id="06940-105">Se ha utilizado la empresa de demostración USMF para crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="06940-105">The USMF demo company was used to create this procedure.</span></span> <span data-ttu-id="06940-106">Este procedimiento es para una función de la contabilidad de costes que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="06940-106">This procedure is for a Cost accounting feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-new-cost-objects"></a><span data-ttu-id="06940-107">Crea nuevos objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="06940-107">Create new cost objects</span></span>
1. <span data-ttu-id="06940-108">Vaya a contabilidad de Costes > Dimensiones > dimensiones del objeto de Coste.</span><span class="sxs-lookup"><span data-stu-id="06940-108">Go to Cost accounting > Dimensions > Cost object dimensions.</span></span>
2. <span data-ttu-id="06940-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="06940-109">Click New.</span></span>
3. <span data-ttu-id="06940-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="06940-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="06940-111">En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="06940-111">In the Data connector for dimension members field, enter or select a value.</span></span>
5. <span data-ttu-id="06940-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="06940-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="06940-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="06940-113">Click Save.</span></span>

## <a name="configure-the-data-connector"></a><span data-ttu-id="06940-114">Configura el conector de datos</span><span class="sxs-lookup"><span data-stu-id="06940-114">Configure the data connector</span></span>
1. <span data-ttu-id="06940-115">Haga clic en Configurar proveedor de miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="06940-115">Click Configure dimension member provider.</span></span>
    * <span data-ttu-id="06940-116">Seleccione CostCenter para importar la dimensión de CostCenter en la contabilidad de Costes.</span><span class="sxs-lookup"><span data-stu-id="06940-116">Select CostCenter to import the CostCenter dimension into Cost accounting.</span></span>  
2. <span data-ttu-id="06940-117">En el campo Nombre de dimensión, seleccione el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="06940-117">In the Dimension name field, select Cost center.</span></span>
3. <span data-ttu-id="06940-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="06940-118">Click OK.</span></span>

## <a name="import-cost-centers"></a><span data-ttu-id="06940-119">Importar centros de coste</span><span class="sxs-lookup"><span data-stu-id="06940-119">Import cost centers</span></span>
1. <span data-ttu-id="06940-120">Haga clic en Importar miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="06940-120">Click Import dimension members.</span></span>
2. <span data-ttu-id="06940-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="06940-121">Click OK.</span></span>

## <a name="view-the-imported-cost-centers"></a><span data-ttu-id="06940-122">Ver los centros de coste importados</span><span class="sxs-lookup"><span data-stu-id="06940-122">View the imported cost centers</span></span>
1. <span data-ttu-id="06940-123">Haga clic en miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="06940-123">Click View dimension members.</span></span>


