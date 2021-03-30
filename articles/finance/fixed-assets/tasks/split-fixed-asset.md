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
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db601be192b57fbec220193d3c9fde1a4f50c085
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213517"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="ba0f4-103">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="ba0f4-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba0f4-104">En este tema se explica cómo dividir un porcentaje de un libro de activos a un nuevo libro de activos.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="ba0f4-105">Usa el rol de contable y los datos de prueba de USMF.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="ba0f4-106">Crear un activo fijo nuevo</span><span class="sxs-lookup"><span data-stu-id="ba0f4-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="ba0f4-107">En el panel de exploración, vaya a **Módulos \> Activos fijos \> Activos fijos \> Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="ba0f4-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-108">Select **New**.</span></span>
3. <span data-ttu-id="ba0f4-109">En el campo **Grupo de activos fijos**, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="ba0f4-110">Anote el número de activo fijo que se va a usar en el proceso de división más adelante.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="ba0f4-111">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="ba0f4-112">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="ba0f4-113">Dividir un activo fijo</span><span class="sxs-lookup"><span data-stu-id="ba0f4-113">Split a fixed asset</span></span>

<span data-ttu-id="ba0f4-114">Antes de dividir un activo totalmente depreciado, hay que cambiar manualmente el estado del libro de activos de **Cerrado** a **Abierto**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="ba0f4-115">Este paso es necesario porque el estado del libro debe ser **Abierto** si se van a contabilizar transacciones para el activo (por ejemplo, para una venta de cancelación).</span><span class="sxs-lookup"><span data-stu-id="ba0f4-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="ba0f4-116">También debe activr el parámetro **Permitir múltiples transacciones en un asiento** en la pestaña **General** de la página **Parámetros del libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-116">You must also turn on the **Allow multiple transactions within one voucher** parameter on the **General** tab of the **General ledger parameters** page.</span></span> <span data-ttu-id="ba0f4-117">Una vez que se cambia el estado del libro de activos y se han permitido múltiples transacciones dentro de un asiento, complete los siguientes pasos para dividir el activo.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-117">After the asset book status is changed and multiple transactions within one voucher have been allowed, complete the following steps to split the asset.</span></span>

1. <span data-ttu-id="ba0f4-118">En la lista, busque y seleccione el vínculo del activo fijo para dividir.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-118">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="ba0f4-119">Seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-119">Select **Books**.</span></span> <span data-ttu-id="ba0f4-120">Seleccione el libro para dividir el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-120">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="ba0f4-121">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-121">Select **Functions**.</span></span>
4. <span data-ttu-id="ba0f4-122">Seleccione **Dividir activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-122">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="ba0f4-123">En el campo **Hasta activo fijo**, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-123">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="ba0f4-124">En el campo **Al libro**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-124">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ba0f4-125">En el campo **Fecha de transacción**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-125">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="ba0f4-126">En el campo **Porcentaje**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-126">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="ba0f4-127">En el campo **Nombre del diario**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-127">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="ba0f4-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-128">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="ba0f4-129">Registrar la transacción de diario</span><span class="sxs-lookup"><span data-stu-id="ba0f4-129">Post the journal transaction</span></span>

1. <span data-ttu-id="ba0f4-130">En el panel de navegación, vaya a **Módulos \> Activos fijos \> Entradas del diario \> Diario de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-130">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="ba0f4-131">En la lista, seleccione el diario creado con el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-131">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="ba0f4-132">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-132">Select **Lines**.</span></span>

    - <span data-ttu-id="ba0f4-133">Compruebe las líneas de diario creadas.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-133">Verify the journal lines created.</span></span>
    - <span data-ttu-id="ba0f4-134">Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-134">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="ba0f4-135">Se crea una transacción de adquisición del nuevo activo para el mismo importe.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-135">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="ba0f4-136">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="ba0f4-136">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]