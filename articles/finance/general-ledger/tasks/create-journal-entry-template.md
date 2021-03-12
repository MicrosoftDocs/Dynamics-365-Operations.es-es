---
title: Creación de un movimiento de diario mediante una plantilla
description: Los asientos del diario registrados se pueden guardar como plantillas de asientos y aplicarse en un nuevo asiento del diario.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 234cfb98cc07f6c8c81821584e4e1d509d033477
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988583"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="c79fe-103">Creación de un movimiento de diario mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="c79fe-103">Create a journal entry using template</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c79fe-104">Los asientos del diario registrados se pueden guardar como plantillas de asientos y aplicarse en un nuevo asiento del diario.</span><span class="sxs-lookup"><span data-stu-id="c79fe-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="c79fe-105">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c79fe-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="c79fe-106">Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-106">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
2. <span data-ttu-id="c79fe-107">En el **panel de acciones**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-107">On the **Action pane**, click **New**.</span></span> <span data-ttu-id="c79fe-108">Este procedimiento comienza por crear y registrar un asiento de diario, pero cualquier asiento del diario previamente registrado se puede guardar como plantilla.</span><span class="sxs-lookup"><span data-stu-id="c79fe-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
3. <span data-ttu-id="c79fe-109">En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c79fe-109">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="c79fe-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c79fe-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c79fe-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c79fe-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c79fe-112">Haga clic en **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-112">Click **Lines**.</span></span>
7. <span data-ttu-id="c79fe-113">En el campo **Tipo de cuenta**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-113">In the **Account type** field, type a value.</span></span>
8. <span data-ttu-id="c79fe-114">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-114">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="c79fe-115">En el campo **Débito**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-115">In the **Debit** field, type a value.</span></span>
10. <span data-ttu-id="c79fe-116">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-116">Click **New**.</span></span>
11. <span data-ttu-id="c79fe-117">En el campo **Tipo de cuenta**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-117">In the **Account type** field, type a value.</span></span>
12. <span data-ttu-id="c79fe-118">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-118">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="c79fe-119">En el campo **Débito**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-119">In the **Debit** field, type a value.</span></span>
14. <span data-ttu-id="c79fe-120">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-120">Click **New**.</span></span>
14. <span data-ttu-id="c79fe-121">En el campo **Cuenta**, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="c79fe-121">In the **Account** field, specify the desired values.</span></span>
15. <span data-ttu-id="c79fe-122">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c79fe-122">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="c79fe-123">En el campo **Crédito**, escriba un valor para saldar el asiento.</span><span class="sxs-lookup"><span data-stu-id="c79fe-123">In the **Credit** field, type a value to balance the voucher.</span></span>
17. <span data-ttu-id="c79fe-124">En el **panel de acciones**, haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-124">On the **Action pane**, click **Post**.</span></span>
18. <span data-ttu-id="c79fe-125">Haga clic en **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-125">Click **Functions**.</span></span>
19. <span data-ttu-id="c79fe-126">Haga clic en la plantilla **Guardar asiento**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-126">Click **Save voucher** template.</span></span>
20. <span data-ttu-id="c79fe-127">Este procedimiento supone un tipo de **Plantilla de porcentaje**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-127">This procedure assumes a **Percent Template** type.</span></span> <span data-ttu-id="c79fe-128">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="c79fe-128">Click OK.</span></span>
    - <span data-ttu-id="c79fe-129">Porcentaje: los importes del asiento se convierten en factores de porcentaje, lo que permite aplicar cualquier importe cuando se selecciona la plantilla de asientos.</span><span class="sxs-lookup"><span data-stu-id="c79fe-129">Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>
    - <span data-ttu-id="c79fe-130">Importe: los importes reales se almacenarán y se aplicarán.</span><span class="sxs-lookup"><span data-stu-id="c79fe-130">Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="c79fe-131">Haga clic en **Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-131">Click **General journals**.</span></span>
22. <span data-ttu-id="c79fe-132">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-132">Click **New**.</span></span>
23. <span data-ttu-id="c79fe-133">En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c79fe-133">In the **Name** field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="c79fe-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c79fe-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="c79fe-135">Haga clic en **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-135">Click **Lines**.</span></span>
26. <span data-ttu-id="c79fe-136">Haga clic en **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-136">Click **Functions**.</span></span>
27. <span data-ttu-id="c79fe-137">Haga clic en **Seleccionar plantilla de asientos**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-137">Click **Select voucher template**.</span></span>
28. <span data-ttu-id="c79fe-138">Busque la plantilla que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c79fe-138">Find the template that you created earlier.</span></span> <span data-ttu-id="c79fe-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-139">Click **OK**.</span></span> <span data-ttu-id="c79fe-140">Es posible que tenga que hacer clic en **Paso anterior** y seleccionar la plantilla correcta si existen otras plantillas.</span><span class="sxs-lookup"><span data-stu-id="c79fe-140">You may need to click **Previous step** and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="c79fe-141">En el campo **Importe**, especifique el importe que se aplicará al asiento.</span><span class="sxs-lookup"><span data-stu-id="c79fe-141">In the **Amount** field, enter the amount to be applied to the voucher.</span></span> <span data-ttu-id="c79fe-142">El campo **Importe** solo se muestra si la plantilla de asientos es del tipo Porcentaje.</span><span class="sxs-lookup"><span data-stu-id="c79fe-142">The **Amount** field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="c79fe-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c79fe-143">Click **OK**.</span></span>

