---
title: Procesar interés
description: Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a495dc13cb1d20d21fc4e4a4803f8b3cf44ca3a7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816253"
---
# <a name="process-interest"></a><span data-ttu-id="27951-103">Procesar interés</span><span class="sxs-lookup"><span data-stu-id="27951-103">Process interest</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27951-104">Este procedimiento muestra cómo crear, imprimir y registrar notas de interés.</span><span class="sxs-lookup"><span data-stu-id="27951-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="27951-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="27951-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="27951-106">Configuración del interés en el perfil de contabilización</span><span class="sxs-lookup"><span data-stu-id="27951-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="27951-107">En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Configuración > Perfiles de contabilización del cliente**.</span><span class="sxs-lookup"><span data-stu-id="27951-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="27951-108">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="27951-108">Click **Edit**.</span></span>
3. <span data-ttu-id="27951-109">En la **Ficha desplegable Configuración**, en el campo **Código de interés**, seleccione un código de interés de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="27951-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="27951-110">Si no desea que se calcule el interés para las transacciones que usan este perfil de contabilización, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="27951-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="27951-111">La ficha desplegable **Restricciones de tablas** le permite cambiar la forma en la que se procesa el interés.</span><span class="sxs-lookup"><span data-stu-id="27951-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="27951-112">Si este campo está establecido en Sí, se calculará el interés para este perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="27951-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="27951-113">Calcular interés</span><span class="sxs-lookup"><span data-stu-id="27951-113">Calculate interest</span></span>
1. <span data-ttu-id="27951-114">En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Interés > Crear notas de interés**.</span><span class="sxs-lookup"><span data-stu-id="27951-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="27951-115">Debe seleccionar los tipos de transacción para los que desee calcular el interés.</span><span class="sxs-lookup"><span data-stu-id="27951-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="27951-116">Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="27951-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="27951-117">Si establece **Interés** en "Sí", calculará el interés sobre el interés.</span><span class="sxs-lookup"><span data-stu-id="27951-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="27951-118">Es posible que desee comprobar las normas que rigen el cálculo de interés sobre el interés antes de incluir estas transacciones.</span><span class="sxs-lookup"><span data-stu-id="27951-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="27951-119">En el campo **Fecha inicial**, especifique una fecha desde la que se calculará el interés.</span><span class="sxs-lookup"><span data-stu-id="27951-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="27951-120">Si no se especifica una **Fecha inicial**, todas las notas de interés no registradas se cancelarán, y el interés se volverá a calcular a partir de la fecha de transacción.</span><span class="sxs-lookup"><span data-stu-id="27951-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="27951-121">En el campo **Fecha final**, especifique una fecha hasta la que se calculará el interés.</span><span class="sxs-lookup"><span data-stu-id="27951-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="27951-122">En el campo **Utilizar el perfil de contabilización desde**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="27951-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="27951-123">Existen tres opciones de perfil de registro:</span><span class="sxs-lookup"><span data-stu-id="27951-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="27951-124">Cuenta: use el perfil de contabilización asignado a la cuenta de cliente para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="27951-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="27951-125">Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="27951-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="27951-126">Transacción: se usa el perfil de contabilización individual de las transacciones en las que se calcula el interés para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="27951-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="27951-127">Las transacciones que no tengan un perfil de contabilización asignado usarán el perfil de registro que se especifica en el área Impuestos y contabilidad del formulario Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="27951-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="27951-128">Expanda la ficha desplegable **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="27951-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="27951-129">Haga clic en **Filtro.**</span><span class="sxs-lookup"><span data-stu-id="27951-129">Click **Filter**.</span></span>
9. <span data-ttu-id="27951-130">En el campo **Criterios**, especifique un id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="27951-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="27951-131">Por ejemplo, escriba "US-001".</span><span class="sxs-lookup"><span data-stu-id="27951-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="27951-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27951-132">Click **OK**.</span></span>
7. <span data-ttu-id="27951-133">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27951-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="27951-134">Imprimir notas de interés</span><span class="sxs-lookup"><span data-stu-id="27951-134">Print interest notes</span></span>
1. <span data-ttu-id="27951-135">En el **Panel de navegación**, vaya a **Módulos > Crédito y cobros > Interés > Revisar y procesar notas de interés**.</span><span class="sxs-lookup"><span data-stu-id="27951-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="27951-136">En el campo **Estado**, seleccione "Creado".</span><span class="sxs-lookup"><span data-stu-id="27951-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="27951-137">En el campo **Impreso**, seleccione "No se ha impreso".</span><span class="sxs-lookup"><span data-stu-id="27951-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="27951-138">Haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="27951-138">Click **Print**.</span></span>
5. <span data-ttu-id="27951-139">Expanda la ficha desplegable **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="27951-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="27951-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27951-140">Click **OK**.</span></span>
7. <span data-ttu-id="27951-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="27951-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="27951-142">Registro de la nota de interés</span><span class="sxs-lookup"><span data-stu-id="27951-142">Post the interest note</span></span>
1. <span data-ttu-id="27951-143">Seleccione una nota de interés lista para registrar (estado Creado).</span><span class="sxs-lookup"><span data-stu-id="27951-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="27951-144">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="27951-144">Click **Post**.</span></span>
3. <span data-ttu-id="27951-145">Especifique la fecha de registro para la nota de interés.</span><span class="sxs-lookup"><span data-stu-id="27951-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="27951-146">Seleccione Sí para crear una transacción de contabilidad general para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="27951-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="27951-147">Si no selecciona Sí, el interés de todas las notas de interés para el cliente se acumula y se registra en la contabilidad general en una transacción.</span><span class="sxs-lookup"><span data-stu-id="27951-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="27951-148">Expanda la ficha desplegable **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="27951-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="27951-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27951-149">Click **OK**.</span></span>
6. <span data-ttu-id="27951-150">En el campo **Estado**, seleccione "Registrado".</span><span class="sxs-lookup"><span data-stu-id="27951-150">In the **Status** field, select 'Posted'.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]