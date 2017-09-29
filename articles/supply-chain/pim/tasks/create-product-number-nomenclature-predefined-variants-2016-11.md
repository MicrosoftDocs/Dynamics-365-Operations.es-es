--- 
title: "Crear un número de producto para las variantes de producto predefinidas"
description: "Esta guía muestra cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="6a809-103">Crear un número de producto para las variantes de producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="6a809-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a809-104">Esta guía muestra cómo configurar una nomenclatura del número de producto para las variantes de producto predefinidas y cómo se puede asignar a un grupo de dimensiones del producto apropiado.</span><span class="sxs-lookup"><span data-stu-id="6a809-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="6a809-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="6a809-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6a809-106">La nueva nomenclatura del número de producto se asigna al grupo de dimensiones de producto Color y Tamaño.</span><span class="sxs-lookup"><span data-stu-id="6a809-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="6a809-107">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="6a809-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="6a809-108">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="6a809-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="6a809-109">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="6a809-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="6a809-110">Haga clic en Nomenclatura de producto.</span><span class="sxs-lookup"><span data-stu-id="6a809-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="6a809-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6a809-111">Click New.</span></span>
4. <span data-ttu-id="6a809-112">En el campo Nombre, escriba el nombre de la nomenclatura que ayude a identificar el grupo de dimensiones de producto de destino, por ejemplo, ColorSize.</span><span class="sxs-lookup"><span data-stu-id="6a809-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="6a809-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6a809-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="6a809-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6a809-114">Click Add.</span></span>
7. <span data-ttu-id="6a809-115">Haga clic en Número de producto maestro.</span><span class="sxs-lookup"><span data-stu-id="6a809-115">Click Product master number.</span></span>
8. <span data-ttu-id="6a809-116">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6a809-116">Click Add.</span></span>
9. <span data-ttu-id="6a809-117">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="6a809-117">Click Text constant.</span></span>
10. <span data-ttu-id="6a809-118">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6a809-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="6a809-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6a809-119">Click Add.</span></span>
12. <span data-ttu-id="6a809-120">Haga clic en Color.</span><span class="sxs-lookup"><span data-stu-id="6a809-120">Click Color.</span></span>
13. <span data-ttu-id="6a809-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6a809-121">Click Add.</span></span>
14. <span data-ttu-id="6a809-122">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="6a809-122">Click Text constant.</span></span>
15. <span data-ttu-id="6a809-123">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6a809-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="6a809-124">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6a809-124">Click Add.</span></span>
17. <span data-ttu-id="6a809-125">Haga clic en Tamaño.</span><span class="sxs-lookup"><span data-stu-id="6a809-125">Click Size.</span></span>
18. <span data-ttu-id="6a809-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a809-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="6a809-127">Asignar la nomenclatura a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="6a809-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="6a809-128">Haga clic en Grupos de dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="6a809-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="6a809-129">Seleccione el grupo de dimensiones de productos SizeCol.</span><span class="sxs-lookup"><span data-stu-id="6a809-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="6a809-130">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="6a809-130">Click Edit.</span></span>
4. <span data-ttu-id="6a809-131">Seleccione Sí en el campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="6a809-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="6a809-132">En el campo Nomenclatura del número de variante del producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6a809-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="6a809-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a809-133">Close the page.</span></span>


