---
title: Crear un estado de ciclo de vida de producto predeterminado
description: Este procedimiento muestra cómo crear un estado de ciclo de vida de producto predeterminado además de cómo asociar el estado predeterminado con los productos emitidos.
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
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8766208f0dff0cf24db7335ef00c42749811f8fd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436843"
---
# <a name="create-a-default-product-lifecycle-state"></a><span data-ttu-id="34eed-103">Crear un estado de ciclo de vida de producto predeterminado</span><span class="sxs-lookup"><span data-stu-id="34eed-103">Create a default product lifecycle state</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34eed-104">Este procedimiento muestra cómo crear un estado de ciclo de vida de producto predeterminado además de cómo asociar el estado predeterminado con los productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="34eed-104">This procedure shows how to create a default product lifecycle state as well as how to associate the default state with released products.</span></span>


## <a name="create-a-default-lifecycle-state"></a><span data-ttu-id="34eed-105">Crear un estado de ciclo de vida predeterminado</span><span class="sxs-lookup"><span data-stu-id="34eed-105">Create a default lifecycle state</span></span>
1. <span data-ttu-id="34eed-106">Vaya a Gestión de información de productos > Configuración > Estado de ciclo de vida de producto.</span><span class="sxs-lookup"><span data-stu-id="34eed-106">Go to Product information management > Setup > Product lifecycle state.</span></span>
2. <span data-ttu-id="34eed-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="34eed-107">Click New.</span></span>
3. <span data-ttu-id="34eed-108">En el campo Estado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-108">In the State field, type a value.</span></span>
4. <span data-ttu-id="34eed-109">Seleccione Sí en el campo Predeterminado cuando se libera a entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="34eed-109">Select Yes in the Default when released to legal entity field.</span></span>
5. <span data-ttu-id="34eed-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-110">In the Description field, type a value.</span></span>
6. <span data-ttu-id="34eed-111">Seleccione No en el campo Es activo para planificación.</span><span class="sxs-lookup"><span data-stu-id="34eed-111">Select No in the Is active for planning field.</span></span>

> [!NOTE]
> <span data-ttu-id="34eed-112">Si no debe incluirse un nuevo producto liberado en la planificación maestra, seleccione No.</span><span class="sxs-lookup"><span data-stu-id="34eed-112">If a new released product should not be included in Master planning, select No.</span></span> <span data-ttu-id="34eed-113">Si debe incluirse en la planificación maestra, deje el control en el valor predeterminado Sí.</span><span class="sxs-lookup"><span data-stu-id="34eed-113">If it should be included in Master planning, leave the control at its default value Yes.</span></span>  

## <a name="create-a-new-released-product"></a><span data-ttu-id="34eed-114">Crear un nuevo producto liberado</span><span class="sxs-lookup"><span data-stu-id="34eed-114">Create a new released product</span></span>
1. <span data-ttu-id="34eed-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="34eed-115">Close the page.</span></span>
2. <span data-ttu-id="34eed-116">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="34eed-116">Go to Product information management > Products > Released products.</span></span>
3. <span data-ttu-id="34eed-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="34eed-117">Click New.</span></span>
4. <span data-ttu-id="34eed-118">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-118">In the Product number field, type a value.</span></span>
5. <span data-ttu-id="34eed-119">En el campo Nombre de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-119">In the Product name field, type a value.</span></span>
6. <span data-ttu-id="34eed-120">En el campo Nombre de búsqueda, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-120">In the Search name field, type a value.</span></span>
7. <span data-ttu-id="34eed-121">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-121">In the Item model group field, enter or select a value.</span></span>
8. <span data-ttu-id="34eed-122">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-122">In the Item group field, enter or select a value.</span></span>
9. <span data-ttu-id="34eed-123">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-123">In the Storage dimension group field, enter or select a value.</span></span>
10. <span data-ttu-id="34eed-124">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-124">In the Tracking dimension group field, enter or select a value.</span></span>
11. <span data-ttu-id="34eed-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="34eed-125">Click OK.</span></span>

> [!NOTE]
> <span data-ttu-id="34eed-126">El estado del ciclo de vida del producto predeterminado es una definición global.</span><span class="sxs-lookup"><span data-stu-id="34eed-126">The default product lifecycle state is a global definition.</span></span>  

## <a name="change-the-product-to-an-active-state"></a><span data-ttu-id="34eed-127">Cambiar el producto a un estado activo</span><span class="sxs-lookup"><span data-stu-id="34eed-127">Change the product to an active state</span></span>
1. <span data-ttu-id="34eed-128">En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="34eed-128">In the Product lifecycle state field, enter or select a value.</span></span>

> [!NOTE]
> <span data-ttu-id="34eed-129">Supongamos que ha configurado un estado activo, ahora puede seleccionar el estado activo para permitir que el producto se use en el cálculo de la planificación maestra y del nivel de L.MAT.</span><span class="sxs-lookup"><span data-stu-id="34eed-129">Assume that you have set up an active state, you can now select the active state to allow the product to be used in Master planning and BOM-level calculation.</span></span> <span data-ttu-id="34eed-130">Obviamente, esto solo tiene sentido si se especifican todos los detalles del producto que se necesitan para una planificación coherente.</span><span class="sxs-lookup"><span data-stu-id="34eed-130">Obviously, this only makes sense if all the product details that are required for consistent planning are specified.</span></span>  

