---
title: Dimensiones de objeto de coste
description: Al analizar costes, se usan las dimensiones del elemento de coste para determinar a dónde fluyen los costes. Las dimensiones del objeto de coste se usan para determinar dónde se deben asignar los costes. Este tema proporciona información sobre las dimensiones de objeto de coste.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 90d9176a2ca37b581ef82306cc1ceef515ceb624
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841570"
---
# <a name="cost-object-dimensions"></a><span data-ttu-id="1b045-105">Dimensiones de objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b045-105">Cost object dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b045-106">Al analizar costes, se usan las dimensiones del elemento de coste para determinar a dónde fluyen los costes.</span><span class="sxs-lookup"><span data-stu-id="1b045-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="1b045-107">Las dimensiones del objeto de coste se usan para determinar dónde se deben asignar los costes.</span><span class="sxs-lookup"><span data-stu-id="1b045-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="1b045-108">Este tema proporciona información sobre las dimensiones de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="1b045-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="1b045-109">Un objeto de coste puede ser cualquier tipo de objeto para el que desea realizar una estimación, asignar costes o medir directamente.</span><span class="sxs-lookup"><span data-stu-id="1b045-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="1b045-110">Los objetos típicos de coste incluyen productos, proyectos, recursos, departamentos, centros de coste, y regiones geográficas.</span><span class="sxs-lookup"><span data-stu-id="1b045-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="1b045-111">La administración utiliza objetos de coste para cuantificar costes y también para realizar un análisis de la rentabilidad.</span><span class="sxs-lookup"><span data-stu-id="1b045-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="1b045-112">Dimensiones del objeto de coste y miembros de la dimensión del objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b045-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="1b045-113">Los objetos de coste se conocen como *dimensiones de objeto de coste*.</span><span class="sxs-lookup"><span data-stu-id="1b045-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="1b045-114">Una vez haya decidido a qué entidad debe hacer referencia la dimensión de objeto de coste, debe especificar los valores de dimensión individuales o importarlos en la contabilidad de costes desde otros sistemas de origen.</span><span class="sxs-lookup"><span data-stu-id="1b045-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="1b045-115">Estos valores de dimensión individuales se conocen como *miembros de dimensión de objeto de coste*.</span><span class="sxs-lookup"><span data-stu-id="1b045-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="1b045-116">Por ejemplo, si desea usar la dimensión financiera que se denomina Centro de coste como dimensión de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="1b045-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="1b045-117">Para ver cómo fluyen los costes a los centros de coste individuales, debe importar a los miembros de dimensión de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="1b045-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="1b045-118">En este caso, los miembros de dimensión de objeto de coste son los centros de coste real, como Ventas, Producción, Administración y ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="1b045-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="1b045-119">El captura de pantalla siguiente muestra un ejemplo de Centros de coste como la dimensión de objeto de coste con sus centros de coste real como miembros de dimensión de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="1b045-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="1b045-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="1b045-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="1b045-121">Importar miembros de dimensión de objeto de coste mediante conectores de datos</span><span class="sxs-lookup"><span data-stu-id="1b045-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="1b045-122">Para realizar la importación de miembros de dimensión de objeto de coste, se usan los conectores de datos para recuperar los valores de las entidades que desea usar como dimensiones de objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="1b045-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="1b045-123">Puede utilizar los conectores de datos generados previamente o conectores de datos personalizados que genere usted.</span><span class="sxs-lookup"><span data-stu-id="1b045-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>



