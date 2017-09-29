--- 
title: Procesar cartas de cobro
description: "Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="process-collection-letters"></a><span data-ttu-id="cc221-103">Procesar cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="cc221-103">Process collection letters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc221-104">Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="cc221-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="cc221-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="cc221-106">Configurar una secuencia de cartas de cobro en el perfil de registro</span><span class="sxs-lookup"><span data-stu-id="cc221-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="cc221-107">Vaya a Crédito y cobros > Configuración > Perfiles de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="cc221-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="cc221-108">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cc221-108">Click Edit.</span></span>
    * <span data-ttu-id="cc221-109">Seleccione una secuencia de cartas de cobro en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="cc221-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="cc221-110">Si no desea generar cartas de cobro para las transacciones que usan este perfil de contabilización, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="cc221-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="cc221-111">La ficha Restricciones de tablas le permite cambiar la forma en la que se procesan las cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="cc221-112">Si este campo está establecido en Sí, se crearán las cartas de cobro para este perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="cc221-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="cc221-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cc221-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="cc221-114">Crear cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="cc221-114">Create collection letters</span></span>
1. <span data-ttu-id="cc221-115">Vaya a Crédito y cobros > Carta de cobro > Crear cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="cc221-116">Debe seleccionar los tipos de transacción para los que desee cobrar cartas.</span><span class="sxs-lookup"><span data-stu-id="cc221-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="cc221-117">Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="cc221-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="cc221-118">En el campo Carta de cobro, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cc221-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="cc221-119">Escriba la fecha de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="cc221-120">Hay dos opciones para el perfil de contabilización: Cuenta: se usa el perfil de contabilización asignado a la cuenta del cliente para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="cc221-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="cc221-121">Seleccionar: se usa el perfil de contabilización que seleccione en el campo Perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="cc221-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="cc221-122">Seleccione un perfil de contabilización si ha cambiado "Utilizar el perfil de contabilización desde" a "Seleccionar".</span><span class="sxs-lookup"><span data-stu-id="cc221-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="cc221-123">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="cc221-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="cc221-124">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="cc221-124">Click Filter.</span></span>
6. <span data-ttu-id="cc221-125">En el campo Criterios, escriba una id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc221-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="cc221-126">Por ejemplo, escriba "US-001".</span><span class="sxs-lookup"><span data-stu-id="cc221-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="cc221-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cc221-127">Click OK.</span></span>
8. <span data-ttu-id="cc221-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cc221-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="cc221-129">Imprimir cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="cc221-129">Print collection letters</span></span>
1. <span data-ttu-id="cc221-130">Vaya a Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="cc221-131">En el campo Estado, seleccione Creado.</span><span class="sxs-lookup"><span data-stu-id="cc221-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="cc221-132">En el campo Impreso, seleccione No se ha impreso.</span><span class="sxs-lookup"><span data-stu-id="cc221-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="cc221-133">Haga clic en Imprimir.</span><span class="sxs-lookup"><span data-stu-id="cc221-133">Click Print.</span></span>
5. <span data-ttu-id="cc221-134">Haga clic en Nota de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="cc221-135">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="cc221-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="cc221-136">Especificar la fecha límite para los registros</span><span class="sxs-lookup"><span data-stu-id="cc221-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="cc221-137">Haga clic en Aceptar para imprimir la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="cc221-138">Registrar la carta de cobro</span><span class="sxs-lookup"><span data-stu-id="cc221-138">Post the collection letter</span></span>
1. <span data-ttu-id="cc221-139">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="cc221-139">Click Post.</span></span>
2. <span data-ttu-id="cc221-140">Escriba la fecha de registro para la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="cc221-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="cc221-141">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="cc221-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="cc221-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cc221-142">Click OK.</span></span>
5. <span data-ttu-id="cc221-143">En el campo Estado, seleccione Registrada.</span><span class="sxs-lookup"><span data-stu-id="cc221-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="cc221-144">En el campo Impreso, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cc221-144">In the Printed field, select an option.</span></span>


