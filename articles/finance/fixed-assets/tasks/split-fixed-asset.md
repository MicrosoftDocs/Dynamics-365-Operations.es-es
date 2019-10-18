---
title: Dividir un activo fijo
description: En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179749"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="6704f-103">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="6704f-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6704f-104">En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos.</span><span class="sxs-lookup"><span data-stu-id="6704f-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="6704f-105">Usa el rol de contable y los datos de prueba de USMF.</span><span class="sxs-lookup"><span data-stu-id="6704f-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="6704f-106">Crear un activo fijo nuevo</span><span class="sxs-lookup"><span data-stu-id="6704f-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="6704f-107">En el panel de exploración, vaya a **Módulos > activos fijos > activos fijos > activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="6704f-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="6704f-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6704f-108">Select **New**.</span></span>
3. <span data-ttu-id="6704f-109">En el campo **Grupo de activos fijos**, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6704f-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="6704f-110">Anote el número de activo fijo que se va a usar en el proceso de división más adelante.</span><span class="sxs-lookup"><span data-stu-id="6704f-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="6704f-111">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6704f-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="6704f-112">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="6704f-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="6704f-113">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="6704f-113">Split a fixed asset</span></span>
1. <span data-ttu-id="6704f-114">En la lista, busque y seleccione el vínculo del activo fijo para dividir.</span><span class="sxs-lookup"><span data-stu-id="6704f-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="6704f-115">Seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="6704f-115">Select **Books**.</span></span> <span data-ttu-id="6704f-116">Seleccione el libro para dividir el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="6704f-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="6704f-117">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="6704f-117">Select **Functions**.</span></span>
4. <span data-ttu-id="6704f-118">Seleccione **Dividir activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="6704f-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="6704f-119">En el campo **Hasta activo fijo**, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6704f-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="6704f-120">En el campo **Al libro**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6704f-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6704f-121">En el campo **Fecha de transacción**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="6704f-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="6704f-122">En el campo **Porcentaje**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6704f-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="6704f-123">En el campo **Nombre del diario**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6704f-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="6704f-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6704f-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="6704f-125">Registrar la transacción de diario</span><span class="sxs-lookup"><span data-stu-id="6704f-125">Post the journal transaction</span></span>
1. <span data-ttu-id="6704f-126">En el panel de navegación, vaya a **Módulos > Activos fijos > Movimientos del diario > Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="6704f-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="6704f-127">En la lista, seleccione el diario creado con el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="6704f-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="6704f-128">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="6704f-128">Select **Lines**.</span></span>

    - <span data-ttu-id="6704f-129">Compruebe las líneas de diario creadas.</span><span class="sxs-lookup"><span data-stu-id="6704f-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="6704f-130">Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="6704f-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="6704f-131">Se crea una transacción de adquisición del nuevo activo para el mismo importe.</span><span class="sxs-lookup"><span data-stu-id="6704f-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="6704f-132">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="6704f-132">Select **Post**.</span></span>

