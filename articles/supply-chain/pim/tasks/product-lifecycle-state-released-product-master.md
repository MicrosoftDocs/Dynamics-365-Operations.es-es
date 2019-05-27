---
title: Asignar un estado del ciclo de vida del producto a un producto maestro
description: Este procedimiento muestra cómo asignar un estado de ciclo de vida de producto a un producto maestro liberado y sus variantes.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555917"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a><span data-ttu-id="eac3c-103">Asignar un estado del ciclo de vida del producto a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="eac3c-103">Assign a product lifecycle state to a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eac3c-104">Este procedimiento muestra cómo asignar un estado de ciclo de vida de producto a un producto maestro liberado y sus variantes.</span><span class="sxs-lookup"><span data-stu-id="eac3c-104">This procedure shows how to assign a product lifecycle state to a released product master and its variants.</span></span> <span data-ttu-id="eac3c-105">Requisito previo: Necesita reproducir primero la guía de tareas “Crear un nuevo estado de ciclo de vida de producto” para asegurarse de que al menos tiene un estado de ciclo de vida del producto antes de reproducir esta guía de tareas.</span><span class="sxs-lookup"><span data-stu-id="eac3c-105">Prerequisite: You need to play the task guide "Create a new product lifecycle state" first to make sure that you have at least one product lifecycle state created before you can play this task guide.</span></span>


## <a name="find-a-released-product-master"></a><span data-ttu-id="eac3c-106">Buscar un producto maestro liberado</span><span class="sxs-lookup"><span data-stu-id="eac3c-106">Find a released product master</span></span>
1. <span data-ttu-id="eac3c-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="eac3c-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="eac3c-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="eac3c-108">In the list, find and select the desired record.</span></span>

> [!NOTE]
> <span data-ttu-id="eac3c-109">Un producto maestro tiene el producto maestro del subtipo producto.</span><span class="sxs-lookup"><span data-stu-id="eac3c-109">A product master has the Product subtype Product master.</span></span>  

## <a name="update-the-lifecycle-state"></a><span data-ttu-id="eac3c-110">Actualice el estado del ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="eac3c-110">Update the lifecycle state</span></span>
1. <span data-ttu-id="eac3c-111">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="eac3c-111">Click Edit.</span></span>
2. <span data-ttu-id="eac3c-112">En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="eac3c-112">In the Product lifecycle state field, enter or select a value.</span></span>
3. <span data-ttu-id="eac3c-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="eac3c-113">Click Save.</span></span>
4. <span data-ttu-id="eac3c-114">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="eac3c-114">Click Yes.</span></span>

> [!NOTE]
> <span data-ttu-id="eac3c-115">Si se selecciona Sí, todas las variantes del producto liberado relacionado con el mismo estado original que el producto maestro liberado también se actualizan al nuevo estado de ciclo de vida de producto.</span><span class="sxs-lookup"><span data-stu-id="eac3c-115">If Yes is selected, all the related released product variants that have the same original status as the released product master are also updated to the new product lifecycle state.</span></span> <span data-ttu-id="eac3c-116">Si se selecciona No, todas las variantes conservan su estado real.</span><span class="sxs-lookup"><span data-stu-id="eac3c-116">If No is selected, all variants keep their actual state.</span></span> <span data-ttu-id="eac3c-117">Las variantes cuyo estado del ciclo de vida de producto es diferente al del producto maestro liberado no se actualizan.</span><span class="sxs-lookup"><span data-stu-id="eac3c-117">Variants that have a different product lifecycle state from the released product master are not updated.</span></span>  

## <a name="verify-the-lifecycle-state-of-the-variants"></a><span data-ttu-id="eac3c-118">Compruebe el estado del ciclo de vida de las variantes</span><span class="sxs-lookup"><span data-stu-id="eac3c-118">Verify the lifecycle state of the variants</span></span>
1. <span data-ttu-id="eac3c-119">Haga clic en Variantes del producto emitidas.</span><span class="sxs-lookup"><span data-stu-id="eac3c-119">Click Released product variants.</span></span>

> [!NOTE]
> <span data-ttu-id="eac3c-120">Tenga en cuenta que todas las variantes han heredado el estado de ciclo de vida seleccionado del producto maestro.</span><span class="sxs-lookup"><span data-stu-id="eac3c-120">Note that all variants have inherited the selected lifecycle state from the released product master.</span></span>  

2. <span data-ttu-id="eac3c-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="eac3c-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="eac3c-122">En el campo Estado de ciclo de vida de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="eac3c-122">In the Product lifecycle state field, enter or select a value.</span></span>

