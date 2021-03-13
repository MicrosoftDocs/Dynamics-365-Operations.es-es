---
title: Crear dimensiones e importar miembros de dimensión
description: La contabilidad de costes es un módulo independiente que requiere datos maestros de otros módulos.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 610a9302610af7a074a91dfc2a8c87725b0a1a82
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009502"
---
# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="d9fc7-103">Crear dimensiones e importar miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="d9fc7-103">Create dimensions and import dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9fc7-104">La contabilidad de costes es un módulo independiente que requiere datos de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="d9fc7-105">Estos datos se categorizan en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9fc7-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="d9fc7-106">Elementos de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-106">Cost elements</span></span>
-  <span data-ttu-id="d9fc7-107">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-107">Cost objects</span></span>
-  <span data-ttu-id="d9fc7-108">Dimensiones estadísticas</span><span class="sxs-lookup"><span data-stu-id="d9fc7-108">Statistical dimensions</span></span>

<span data-ttu-id="d9fc7-109">Un **elemento de coste** corresponde a un artículo de coste relevante del plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="d9fc7-110">Un **objeto de coste** corresponde a cualquier tipo de dimensión financiera, como productos, centros de coste y proyectos de los que quiera realizar una estimación, asignar costes o medir directamente.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="d9fc7-111">Una **dimensión estadística** y sus miembros se usan para registrar entradas no monetarias.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="d9fc7-112">Los miembros de dimensión estadística se pueden usar como base de asignación en la distribución y asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="d9fc7-113">En el diagrama siguiente se muestran las dimensiones que se usan en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="d9fc7-114">[![Dimensiones en contabilidad de costes](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="d9fc7-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="d9fc7-115">Una vez se importan los datos en la contabilidad de costes, puede usarlos para crear las diferentes perspectivas que proporcionarán información detallada a los gerentes de todos los niveles de la organización.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="d9fc7-116">En los temas siguientes se ofrece información acerca de la creación de dimensiones y la importación de los miembros de esas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="d9fc7-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="d9fc7-117">Dimensiones de elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="d9fc7-118">Crear elementos de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-118">Create cost elements</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="d9fc7-119">Dimensiones de objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="d9fc7-120">Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="d9fc7-120">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="d9fc7-121">Asignar una dimensión de elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d9fc7-121">Map a cost element dimension</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="d9fc7-122">Miembros de dimensiones estadísticas y plantillas de proveedor de medidas estadísticas</span><span class="sxs-lookup"><span data-stu-id="d9fc7-122">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)






