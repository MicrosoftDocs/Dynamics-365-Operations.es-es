---
title: Asignar una dimensión de elemento de coste
description: Un controlador de costes puede utilizar este procedimiento para asignar una dimensión de elemento de coste a una dimensión de elemento de coste en la entidad jurídica de MXMF.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 845ab27a09905f42c905f9018f9f176a64f8785a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841054"
---
# <a name="map-a-cost-element-dimension"></a><span data-ttu-id="53f9d-103">Asignar una dimensión de elemento de coste</span><span class="sxs-lookup"><span data-stu-id="53f9d-103">Map a cost element dimension</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53f9d-104">Un controlador de costes puede utilizar este procedimiento para asignar una dimensión de elemento de coste a una dimensión de elemento de coste en la entidad jurídica de MXMF.</span><span class="sxs-lookup"><span data-stu-id="53f9d-104">A cost controller can use this procedure to map a cost element dimension to a cost element dimension in the MXMF legal entity.</span></span> <span data-ttu-id="53f9d-105">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="53f9d-105">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="53f9d-106">Vaya a contabilidad de costes > Dimensiones > dimensiones del elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="53f9d-106">Go to Cost accounting > Dimensions > Cost element dimensions.</span></span>
2. <span data-ttu-id="53f9d-107">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="53f9d-107">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="53f9d-108">Para este ejemplo, seleccione Elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="53f9d-108">For this example, select Cost elements.</span></span>  
3. <span data-ttu-id="53f9d-109">Haga clic en Asignaciones de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="53f9d-109">Click Dimension mappings.</span></span>
4. <span data-ttu-id="53f9d-110">Haga clic en Configurar las asignaciones desde esta dimensión.</span><span class="sxs-lookup"><span data-stu-id="53f9d-110">Click Configure mappings from this dimension.</span></span>
5. <span data-ttu-id="53f9d-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="53f9d-111">Click New.</span></span>
6. <span data-ttu-id="53f9d-112">En el campo A dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="53f9d-112">In the To dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="53f9d-113">Para este ejemplo, seleccione Elementos de coste MXMF.</span><span class="sxs-lookup"><span data-stu-id="53f9d-113">For this example, select MXMF Cost elements.</span></span>  
7. <span data-ttu-id="53f9d-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="53f9d-114">Click New.</span></span>
8. <span data-ttu-id="53f9d-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="53f9d-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="53f9d-116">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="53f9d-116">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="53f9d-117">Para este ejemplo, seleccione Gasto de teléfono & fax del miembro de la dimensión 606400.</span><span class="sxs-lookup"><span data-stu-id="53f9d-117">For this example, select dimension member 606400 Telephone & Fax Expense.</span></span>  
10. <span data-ttu-id="53f9d-118">En el campo Hasta miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="53f9d-118">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="53f9d-119">Para este ejemplo, seleccione el Teléfono 6001004 del miembro de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="53f9d-119">For this example, select dimension member 6001004 Telefono.</span></span>  
11. <span data-ttu-id="53f9d-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="53f9d-120">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]