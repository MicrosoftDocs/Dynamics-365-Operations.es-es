---
title: Saldos de apertura que faltan en el cierre de fin de año
description: Este tema explica por qué pueden faltar los saldos de apertura al cerrar un año y cómo reconstruir esos saldos si faltan.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028585"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="c3de5-103">Saldos de apertura que faltan en el cierre de fin de año</span><span class="sxs-lookup"><span data-stu-id="c3de5-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3de5-104">Este tema explica por qué pueden faltar los saldos de apertura al cerrar un año y cómo reconstruir esos saldos si faltan.</span><span class="sxs-lookup"><span data-stu-id="c3de5-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="c3de5-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="c3de5-105">Symptom</span></span>

<span data-ttu-id="c3de5-106">¿Por qué no hay saldos iniciales después de ejecutar el cierre de fin de año del libro mayor?</span><span class="sxs-lookup"><span data-stu-id="c3de5-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="c3de5-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="c3de5-107">Resolution</span></span>

<span data-ttu-id="c3de5-108">Estas son cosas a comprobar si ha cerrado un año en el libro mayor y luego ha generado un saldo de comprobación que no muestra los saldos de apertura para el próximo ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="c3de5-109">Si el campo **Deshacer cierre anterior** está establecido en **Sí**, se estará deshaciendo el cierre de año anterior para el mismo ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="c3de5-110">Al ejecutar un proceso de deshacer el cierre de fin de ejercicio, se eliminarán todas las entradas de los saldos de cierre y apertura, como si nunca se hubiera ejecutado el cierre de fin de ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="c3de5-111">Los asientos también se eliminan.</span><span class="sxs-lookup"><span data-stu-id="c3de5-111">The vouchers are also deleted.</span></span> <span data-ttu-id="c3de5-112">El proceso de cierre de fin de ejercicio no se volverá a ejecutar de forma automática.</span><span class="sxs-lookup"><span data-stu-id="c3de5-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="c3de5-113">Debe iniciar el proceso de nuevo, pero esta vez actualice la opción **Deshacer cierre anterior** a **No**.</span><span class="sxs-lookup"><span data-stu-id="c3de5-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="c3de5-114">Este escenario se trata en el tema de preguntas frecuentes sobre el cierre de fin de ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="c3de5-115">Para más información, consulte [Preguntas frecuentes sobre actividades de fin de ejercicio](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="c3de5-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="c3de5-116">Síntoma</span><span class="sxs-lookup"><span data-stu-id="c3de5-116">Symptom</span></span>

<span data-ttu-id="c3de5-117">He ejecutado el cierre del ejercicio con la opción **Deshacer cierre anterior** establecida en **No**, y todavía no tengo saldos de apertura para mi ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="c3de5-118">Resolución</span><span class="sxs-lookup"><span data-stu-id="c3de5-118">Resolution</span></span>

<span data-ttu-id="c3de5-119">En primer lugar, compruebe el estado del trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="c3de5-119">First check the status of the batch job.</span></span> <span data-ttu-id="c3de5-120">El cierre de un ejercicio incluye una serie de tareas diferentes, pero el paso más crítico es la tarea por lotes con la descripción de tarea **Paso 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="c3de5-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="c3de5-121">El registro de las transacciones de apertura y, opcionalmente, las transacciones de cierre, en el libro mayor tiene lugar durante este paso.</span><span class="sxs-lookup"><span data-stu-id="c3de5-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="c3de5-122">[![Lista de historiales de lotes](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="c3de5-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="c3de5-123">Si este paso finalizó correctamente, pero no aparecen los saldos de apertura en la página **Consulta de saldo de comprobación** (**Libro mayor > Consultas e informes > Saldo de comprobación**), revise los resultados del trabajo por lotes de cierre del ejercicio para ver si el paso Reconstruir saldos se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3de5-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="c3de5-124">[![Resultados del trabajo por lotes de cierre del ejercicio](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="c3de5-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="c3de5-125">Si han aparecido errores en este paso por cualquier motivo, puede ocurrir que las transacciones de apertura (y, opcionalmente, de cierre) se hayan registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3de5-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="c3de5-126">Puede verificar que las transacciones del libro mayor se registraron correctamente utilizando la página **Consulta de transacciones de asientos**, especificando el número de asiento y la fecha proporcionada en el cuadro de diálogo de cierre de ejercicio para el año que cerró (**Libro mayor > Consultas e informes> Transacciones de asientos**).</span><span class="sxs-lookup"><span data-stu-id="c3de5-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="c3de5-127">[![Consulta de transacciones de asientos](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="c3de5-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="c3de5-128">Si los comprobantes de apertura (y, opcionalmente, de cierre) están presentes, no es necesario volver a ejecutar el cierre de fin de ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="c3de5-129">En su lugar, consulte la siguiente sección para obtener información sobre cómo avanzar.</span><span class="sxs-lookup"><span data-stu-id="c3de5-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="c3de5-130">Síntoma</span><span class="sxs-lookup"><span data-stu-id="c3de5-130">Symptom</span></span>

<span data-ttu-id="c3de5-131">El paso "Reconstruir saldos" del cierre de fin de ejercicio produjo errores, entonces ¿debo volver a ejecutar todo el proceso de cierre de ejercicio?</span><span class="sxs-lookup"><span data-stu-id="c3de5-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="c3de5-132">Resolución</span><span class="sxs-lookup"><span data-stu-id="c3de5-132">Resolution</span></span>

<span data-ttu-id="c3de5-133">El paso Reconstruir saldos actualiza los saldos del libro mayor que se utilizan cuando se genera la Consulta de saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c3de5-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="c3de5-134">Es el paso final del proceso de cierre de ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="c3de5-135">Si este paso es el único con errores, las transacciones del libro mayor se han registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3de5-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="c3de5-136">No es necesario que vuelva a ejecutar el cierre del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="c3de5-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="c3de5-137">Puede ejecutar el proceso para reconstruir los saldos manualmente utilizando la página **Conjuntos de dimensiones financieras** (**Libro mayor > Plan de cuentas > Dimensiones> Conjuntos de dimensiones financieras**).</span><span class="sxs-lookup"><span data-stu-id="c3de5-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="c3de5-138">[![Botón Reconstruir saldos en la página Conjuntos de dimensiones financieras](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="c3de5-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="c3de5-139">Si este paso tarda mucho en procesarse, recomendamos revisar las mejores prácticas para los conjuntos de dimensiones financieras, como se describe en [Prácticas recomendadas para actualizar conjuntos de dimensiones financieras](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="c3de5-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

