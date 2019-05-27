---
title: Procesar interés
description: Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5652a38684061914f895d7f8b82999c9840fd63
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549615"
---
# <a name="process-interest"></a><span data-ttu-id="aaa01-103">Procesar interés</span><span class="sxs-lookup"><span data-stu-id="aaa01-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aaa01-104">Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="aaa01-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="aaa01-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="aaa01-106">Configuración del interés en el perfil de contabilización</span><span class="sxs-lookup"><span data-stu-id="aaa01-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="aaa01-107">Vaya a Crédito y cobros > Configuración > Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="aaa01-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="aaa01-108">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="aaa01-108">Click Edit.</span></span>
    * <span data-ttu-id="aaa01-109">Seleccione un código de interés en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="aaa01-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="aaa01-110">Si no desea que se calcule el interés para las transacciones que usan este perfil de contabilización, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="aaa01-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="aaa01-111">La ficha Restricciones de tablas le permite cambiar la forma en la que se procesa el interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="aaa01-112">Si este campo está establecido en Sí, se calculará el interés para este perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="aaa01-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="aaa01-113">Calcular interés</span><span class="sxs-lookup"><span data-stu-id="aaa01-113">Calculate interest</span></span>
1. <span data-ttu-id="aaa01-114">Vaya a Crédito y cobros > Interés > Crear notas de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="aaa01-115">Debe seleccionar los tipos de transacción para los que desee calcular el interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="aaa01-116">Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="aaa01-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="aaa01-117">Si selecciona Interés, calculará el interés sobre el interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="aaa01-118">Es posible que desee comprobar las normas que rigen el cálculo de interés sobre el interés antes de incluir estas transacciones.</span><span class="sxs-lookup"><span data-stu-id="aaa01-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="aaa01-119">El interés se calculará a partir de esta fecha hasta "Fecha final".</span><span class="sxs-lookup"><span data-stu-id="aaa01-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="aaa01-120">Si no se especifica una "Fecha final", todas las notas de interés no registradas se cancelarán, y el interés se volverá a calcular a partir de la fecha de transacción.</span><span class="sxs-lookup"><span data-stu-id="aaa01-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="aaa01-121">Especifique la fecha de la nota de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="aaa01-122">Hay tres opciones para el perfil de contabilización: Cuenta: se usa el perfil de contabilización asignado a la cuenta del cliente para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="aaa01-123">Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="aaa01-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="aaa01-124">Transacción: se usa el perfil de contabilización individual de las transacciones en las que se calcula el interés para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="aaa01-125">Las transacciones que no tengan un perfil de contabilización asignado usarán el perfil de registro que se especifica en el área Impuestos y contabilidad del formulario Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="aaa01-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="aaa01-126">Seleccione un perfil de contabilización aquí si ha cambiado "Utilizar el perfil de contabilización desde" a "Seleccionar".</span><span class="sxs-lookup"><span data-stu-id="aaa01-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="aaa01-127">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="aaa01-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="aaa01-128">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="aaa01-128">Click Filter.</span></span>
5. <span data-ttu-id="aaa01-129">En el campo Criterios, especifique un Id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="aaa01-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="aaa01-130">Por ejemplo, escriba "US-001".</span><span class="sxs-lookup"><span data-stu-id="aaa01-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="aaa01-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="aaa01-131">Click OK.</span></span>
7. <span data-ttu-id="aaa01-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="aaa01-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="aaa01-133">Imprimir notas de interés</span><span class="sxs-lookup"><span data-stu-id="aaa01-133">Print interest notes</span></span>
1. <span data-ttu-id="aaa01-134">Vaya a Crédito y cobros > Interés > Revisar y procesar notas de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="aaa01-135">En el campo Estado, seleccione Creado.</span><span class="sxs-lookup"><span data-stu-id="aaa01-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="aaa01-136">En el campo Impreso, seleccione No se ha impreso.</span><span class="sxs-lookup"><span data-stu-id="aaa01-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="aaa01-137">Haga clic en Imprimir.</span><span class="sxs-lookup"><span data-stu-id="aaa01-137">Click Print.</span></span>
5. <span data-ttu-id="aaa01-138">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="aaa01-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="aaa01-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="aaa01-139">Click OK.</span></span>
7. <span data-ttu-id="aaa01-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="aaa01-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="aaa01-141">Registro de la nota de interés</span><span class="sxs-lookup"><span data-stu-id="aaa01-141">Post the interest note</span></span>
1. <span data-ttu-id="aaa01-142">Seleccione una nota de interés lista para registrar (estado Creado).</span><span class="sxs-lookup"><span data-stu-id="aaa01-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="aaa01-143">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="aaa01-143">Click Post.</span></span>
3. <span data-ttu-id="aaa01-144">Especifique la fecha de registro para la nota de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="aaa01-145">Seleccione Sí para crear una transacción de contabilidad general para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="aaa01-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="aaa01-146">Si no selecciona Sí, el interés de todas las notas de interés para el cliente se acumula y se registra en la contabilidad general en una transacción.</span><span class="sxs-lookup"><span data-stu-id="aaa01-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="aaa01-147">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="aaa01-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="aaa01-148">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="aaa01-148">Click OK.</span></span>
6. <span data-ttu-id="aaa01-149">En el campo Estado, seleccione Registrada.</span><span class="sxs-lookup"><span data-stu-id="aaa01-149">In the Status field, select 'Posted'.</span></span>

