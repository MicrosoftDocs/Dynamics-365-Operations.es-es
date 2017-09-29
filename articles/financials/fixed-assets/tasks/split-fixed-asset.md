--- 
title: Dividir un activo fijo
description: "Esta guía de la tarea va a dividir un porcentaje de un libro de activos a un nuevo libro de activos."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="765ae-103">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="765ae-103">Split a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="765ae-104">Esta guía de la tarea va a dividir un porcentaje de un libro de activos a un nuevo libro de activos.</span><span class="sxs-lookup"><span data-stu-id="765ae-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="765ae-105">Usa el rol de contable y los datos de prueba de USMF.</span><span class="sxs-lookup"><span data-stu-id="765ae-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="765ae-106">Crear un activo fijo nuevo</span><span class="sxs-lookup"><span data-stu-id="765ae-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="765ae-107">Vaya a Activos fijos > Activos fijos > Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="765ae-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="765ae-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="765ae-108">Click New.</span></span>
3. <span data-ttu-id="765ae-109">En el campo Grupo de activos fijos, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="765ae-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="765ae-110">Anote el número de activo fijo que se va a usar en el proceso de división más adelante.</span><span class="sxs-lookup"><span data-stu-id="765ae-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="765ae-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="765ae-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="765ae-112">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="765ae-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="765ae-113">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="765ae-113">Split a fixed asset</span></span>
1. <span data-ttu-id="765ae-114">En la lista, busque y seleccione el activo fijo para dividir.</span><span class="sxs-lookup"><span data-stu-id="765ae-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="765ae-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="765ae-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="765ae-116">Haga clic en Libros.</span><span class="sxs-lookup"><span data-stu-id="765ae-116">Click Books.</span></span>
    * <span data-ttu-id="765ae-117">Seleccione el libro para dividir el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="765ae-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="765ae-118">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="765ae-118">Click Functions.</span></span>
5. <span data-ttu-id="765ae-119">Haga clic en Dividir activo fijo.</span><span class="sxs-lookup"><span data-stu-id="765ae-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="765ae-120">En el campo Hasta activo fijo, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="765ae-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="765ae-121">En el campo Al libro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="765ae-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="765ae-122">En el campo Fecha de transacción, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="765ae-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="765ae-123">En el campo Porcentaje, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="765ae-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="765ae-124">En el campo Nombre del diario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="765ae-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="765ae-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="765ae-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="765ae-126">Registrar la transacción de diario</span><span class="sxs-lookup"><span data-stu-id="765ae-126">Post the journal transaction</span></span>
1. <span data-ttu-id="765ae-127">Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.</span><span class="sxs-lookup"><span data-stu-id="765ae-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="765ae-128">En la lista, seleccione el diario creado con el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="765ae-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="765ae-129">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="765ae-129">Click Lines.</span></span>
    * <span data-ttu-id="765ae-130">Compruebe las líneas de diario creadas.</span><span class="sxs-lookup"><span data-stu-id="765ae-130">Verify the journal lines created.</span></span>  <span data-ttu-id="765ae-131">Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="765ae-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="765ae-132">Se crea una transacción de adquisición del nuevo activo para el mismo importe.</span><span class="sxs-lookup"><span data-stu-id="765ae-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="765ae-133">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="765ae-133">Click Post.</span></span>


