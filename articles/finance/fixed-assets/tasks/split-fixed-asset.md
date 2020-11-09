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
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000302"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="37cdb-103">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="37cdb-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37cdb-104">En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos.</span><span class="sxs-lookup"><span data-stu-id="37cdb-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="37cdb-105">Usa el rol de contable y los datos de prueba de USMF.</span><span class="sxs-lookup"><span data-stu-id="37cdb-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="37cdb-106">Crear un activo fijo nuevo</span><span class="sxs-lookup"><span data-stu-id="37cdb-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="37cdb-107">En el panel de exploración, vaya a **Módulos \> Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="37cdb-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-108">Select **New**.</span></span>
3. <span data-ttu-id="37cdb-109">En el campo **Grupo de activos fijos** , escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="37cdb-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="37cdb-110">Anote el número de activo fijo que se va a usar en el proceso de división más adelante.</span><span class="sxs-lookup"><span data-stu-id="37cdb-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="37cdb-111">En el campo **Nombre** , escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="37cdb-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="37cdb-112">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="37cdb-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="37cdb-113">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="37cdb-113">Split a fixed asset</span></span>

<span data-ttu-id="37cdb-114">Antes de dividir un activo totalmente depreciado, hay que cambiar manualmente el estado del libro de activos de **Cerrado** a **Abierto**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="37cdb-115">Este paso es necesario porque el estado del libro debe ser **Abierto** si se van a contabilizar transacciones para el activo (por ejemplo, para una venta de cancelación).</span><span class="sxs-lookup"><span data-stu-id="37cdb-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="37cdb-116">Después de cambiar el estado del libro de activos, siga estos pasos para dividir el activo.</span><span class="sxs-lookup"><span data-stu-id="37cdb-116">After the asset book status is changed, follow these steps to split the asset.</span></span>

1. <span data-ttu-id="37cdb-117">En la lista, busque y seleccione el vínculo del activo fijo para dividir.</span><span class="sxs-lookup"><span data-stu-id="37cdb-117">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="37cdb-118">Seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-118">Select **Books**.</span></span> <span data-ttu-id="37cdb-119">Seleccione el libro para dividir el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="37cdb-119">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="37cdb-120">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-120">Select **Functions**.</span></span>
4. <span data-ttu-id="37cdb-121">Seleccione **Dividir activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-121">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="37cdb-122">En el campo **Hasta activo fijo** , escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="37cdb-122">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="37cdb-123">En el campo **Al libro** , seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="37cdb-123">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="37cdb-124">En el campo **Fecha de transacción** , especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="37cdb-124">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="37cdb-125">En el campo **Porcentaje** , especifique un número.</span><span class="sxs-lookup"><span data-stu-id="37cdb-125">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="37cdb-126">En el campo **Nombre del diario** , especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="37cdb-126">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="37cdb-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-127">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="37cdb-128">Registrar la transacción de diario</span><span class="sxs-lookup"><span data-stu-id="37cdb-128">Post the journal transaction</span></span>

1. <span data-ttu-id="37cdb-129">En el panel de navegación, vaya a **Módulos \> Activos fijos \> Entradas del diario \> Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-129">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="37cdb-130">En la lista, seleccione el diario creado con el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="37cdb-130">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="37cdb-131">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-131">Select **Lines**.</span></span>

    - <span data-ttu-id="37cdb-132">Compruebe las líneas de diario creadas.</span><span class="sxs-lookup"><span data-stu-id="37cdb-132">Verify the journal lines created.</span></span>
    - <span data-ttu-id="37cdb-133">Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="37cdb-133">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="37cdb-134">Se crea una transacción de adquisición del nuevo activo para el mismo importe.</span><span class="sxs-lookup"><span data-stu-id="37cdb-134">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="37cdb-135">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="37cdb-135">Select **Post**.</span></span>
