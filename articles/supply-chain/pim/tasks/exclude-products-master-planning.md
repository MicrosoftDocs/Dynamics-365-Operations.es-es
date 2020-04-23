---
title: Crear un estado de ciclo de vida del producto para excluir productos de planificación maestra
description: Este procedimiento muestra cómo crear un estado de ciclo de vida de producto nuevo que excluya los productos de cálculo de la planificación maestra y de nivel L. MAT.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 999702b9a14965271b1ed350cda752e715a22a25
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203604"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a><span data-ttu-id="35034-103">Crear un estado de ciclo de vida del producto para excluir productos de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="35034-103">Create a product lifecycle state to exclude products from Master planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="35034-104">Este procedimiento muestra cómo crear un estado de ciclo de vida de producto nuevo que excluya los productos de cálculo de la planificación maestra y de nivel L. MAT.</span><span class="sxs-lookup"><span data-stu-id="35034-104">This procedure shows how to create a new product lifecycle state that excludes the products from Master planning and BOM-level calculation.</span></span>


## <a name="create-an-obsolete-state"></a><span data-ttu-id="35034-105">Crear un estado obsoleto</span><span class="sxs-lookup"><span data-stu-id="35034-105">Create an obsolete state</span></span>
1. <span data-ttu-id="35034-106">Vaya a Gestión de información de productos > Configuración > Estado de ciclo de vida de producto.</span><span class="sxs-lookup"><span data-stu-id="35034-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="35034-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="35034-107">Click New.</span></span>
3. <span data-ttu-id="35034-108">En el campo Estado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="35034-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="35034-109">Seleccione No en el campo Es activo para planificación.</span><span class="sxs-lookup"><span data-stu-id="35034-109">Select No in the Is active for planning field.</span></span>
5. <span data-ttu-id="35034-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="35034-110">In the Description field, type a value.</span></span>

## <a name="associate-the-obsolete-state-to-a-released-product"></a><span data-ttu-id="35034-111">Asociar el estado obsoleto a un producto emitido</span><span class="sxs-lookup"><span data-stu-id="35034-111">Associate the obsolete state to a released product</span></span>
1. <span data-ttu-id="35034-112">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="35034-112">Close the page.</span></span>
2. <span data-ttu-id="35034-113">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="35034-113">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="35034-114">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="35034-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="35034-115">Por ejemplo, filtre el campo Nombre de búsqueda con el valor "M00".</span><span class="sxs-lookup"><span data-stu-id="35034-115">For example, filter on the Search name field with a value of 'M00'.</span></span>
4. <span data-ttu-id="35034-116">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="35034-116">Click Edit.</span></span>
5. <span data-ttu-id="35034-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35034-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="35034-118">En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="35034-118">In the Product lifecycle state field, enter or select a value.</span></span>

