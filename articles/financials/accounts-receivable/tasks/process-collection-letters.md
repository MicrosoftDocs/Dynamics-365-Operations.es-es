---
title: Procesar cartas de cobro
description: Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8a3f74d2891c050294e089eae14ba2386449d7c9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549638"
---
# <a name="process-collection-letters"></a><span data-ttu-id="bcb35-103">Procesar cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="bcb35-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bcb35-104">Este procedimiento muestra cómo crear, imprimir y registrar cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="bcb35-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="bcb35-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="bcb35-106">Configurar una secuencia de cartas de cobro en el perfil de registro</span><span class="sxs-lookup"><span data-stu-id="bcb35-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="bcb35-107">Vaya a **Crédito y cobros > Configuración > Perfiles de contabilización del cliente.**</span><span class="sxs-lookup"><span data-stu-id="bcb35-107">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="bcb35-108">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-108">Click **Edit**.</span></span>
3. <span data-ttu-id="bcb35-109">Seleccione una secuencia de cartas de cobro en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bcb35-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="bcb35-110">Si no desea generar cartas de cobro para las transacciones que usan este perfil de contabilización, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="bcb35-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="bcb35-111">Expanda la ficha Restricciones de tablas para cambiar la forma en la que se procesan las cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-111">Expand the table restriction tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="bcb35-112">Si este campo está establecido en **Sí**, se crearán las cartas de cobro para este perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="bcb35-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="bcb35-113">Crear cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="bcb35-113">Create collection letters</span></span>
1. <span data-ttu-id="bcb35-114">Vaya a **Crédito y cobros > Carta de cobro > Crear cartas de cobro.**</span><span class="sxs-lookup"><span data-stu-id="bcb35-114">Go to **Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="bcb35-115">Seleccione los tipos de transacción para los que desee cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="bcb35-116">Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="bcb35-116">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="bcb35-117">En el campo **Carta de cobro**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="bcb35-117">In the **Collection letter** field, select an option.</span></span>
3. <span data-ttu-id="bcb35-118">Escriba la fecha de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-118">Enter the date of the collection letter.</span></span>
4. <span data-ttu-id="bcb35-119">Seleccione un perfil de contabilización si ha cambiado **"Utilizar el perfil de contabilización desde** a **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="bcb35-120">Existen dos opciones de perfil de registro:</span><span class="sxs-lookup"><span data-stu-id="bcb35-120">There are two posting profile options:</span></span>   
   - <span data-ttu-id="bcb35-121">**Cuenta**: use el perfil de contabilización asignado a la cuenta de cliente para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="bcb35-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="bcb35-122">**Seleccionar**: se usa el perfil de contabilización que seleccione en el campo **Perfil de contabilización**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  
5. <span data-ttu-id="bcb35-123">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-123">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="bcb35-124">Haga clic en **Filtro.**</span><span class="sxs-lookup"><span data-stu-id="bcb35-124">Click **Filter**.</span></span>
7. <span data-ttu-id="bcb35-125">En el campo **Criterios**, especifique un id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="bcb35-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="bcb35-126">Por ejemplo, escriba "US-001".</span><span class="sxs-lookup"><span data-stu-id="bcb35-126">For example, enter 'US-001'.</span></span>
8. <span data-ttu-id="bcb35-127">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-127">Click **OK**.</span></span>
9. <span data-ttu-id="bcb35-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-128">Click **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="bcb35-129">Imprimir cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="bcb35-129">Print collection letters</span></span>
1. <span data-ttu-id="bcb35-130">Vaya a **Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-130">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="bcb35-131">En el campo **Estado**, seleccione **Creado**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="bcb35-132">En el campo **Impreso**, seleccione **No se ha impreso**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="bcb35-133">Haga clic en **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-133">Click **Print**.</span></span>
5. <span data-ttu-id="bcb35-134">Haga clic en **Nota de la carta de cobro**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-134">Click **Collection letter note**.</span></span>
6. <span data-ttu-id="bcb35-135">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-135">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="bcb35-136">Especifique la fecha límite para los registros.</span><span class="sxs-lookup"><span data-stu-id="bcb35-136">Enter the cutoff date for postings.</span></span>
8. <span data-ttu-id="bcb35-137">Haga clic en **Aceptar** para imprimir la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-137">Click **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="bcb35-138">Registre la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-138">Post the collection letter.</span></span>
   1. <span data-ttu-id="bcb35-139">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-139">Click **Post**.</span></span>
   2. <span data-ttu-id="bcb35-140">Escriba la fecha de registro para la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-140">Enter the posting date for the collection letter.</span></span>
   3. <span data-ttu-id="bcb35-141">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-141">Expand the **Records to include** section.</span></span>
   4. <span data-ttu-id="bcb35-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-142">Click **OK**.</span></span>
   5. <span data-ttu-id="bcb35-143">En el campo **Estado**, seleccione **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-143">In the **Status** field, select **Posted**.</span></span>
   6. <span data-ttu-id="bcb35-144">En el campo **Impreso**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="bcb35-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="bcb35-145">Supervisar las cartas de cobro a nivel de cliente</span><span class="sxs-lookup"><span data-stu-id="bcb35-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="bcb35-146">También puede configurar las cartas de cobro a nivel de cliente para seguir el código de carta de cobro para cada transacción, pero el procesamiento de la carta de cobro se basará en un único nivel de la carta de cobro que se almacena para el cliente.</span><span class="sxs-lookup"><span data-stu-id="bcb35-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="bcb35-147">La única carta de cobro contendrá todas las transacciones que están vencidas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="bcb35-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="bcb35-148">Dado que los días de gracia ahora se siguen a nivel de cliente, la siguiente carta de cobro no se registrará hasta que el número de días de gracia haya pasado para la carta de cobro siguiente de la secuencia, aunque las transacciones vencen después de que la última carta de cobro se haya enviado.</span><span class="sxs-lookup"><span data-stu-id="bcb35-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="bcb35-149">Esta opción reduce el número de cartas de cobro que enviará por cliente.</span><span class="sxs-lookup"><span data-stu-id="bcb35-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="bcb35-150">Configurar el cliente para que controle las cartas de cobro a nivel de cliente</span><span class="sxs-lookup"><span data-stu-id="bcb35-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="bcb35-151">Vaya a **Crédito y cobros > configuración > parámetros de clientes** y haga clic en la pestaña **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-151">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2.  <span data-ttu-id="bcb35-152">Cambie el valor de **Cree la carta de cobro por** a **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="bcb35-153">Vaya a **Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-153">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="bcb35-154">Solo una carta de cobro se generará para un cliente con todas las transacciones vencidas.</span><span class="sxs-lookup"><span data-stu-id="bcb35-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="bcb35-155">Omitir pagos y notas de crédito al calcular el código de carta de cobro</span><span class="sxs-lookup"><span data-stu-id="bcb35-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="bcb35-156">Si incluye pagos y notas de crédito en las transacciones que se incluirán en las cartas de cobro, puede hacer que haya pagos o notas de crédito que desencadenen una carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="bcb35-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="bcb35-157">Puede controlar la manera en que los pagos y los notas de crédito controlan el código de la carta de cobro modificando el valor del parámetro **Omitir pagos y notas de crédito al calcular el código de carta de cobro**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="bcb35-158">Para omitir pagos y notas de crédito al calcular el código de carta de cobro, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bcb35-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>
1. <span data-ttu-id="bcb35-159">Vaya a **Crédito y cobros > configuración > parámetros de clientes** y haga clic en la pestaña **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-159">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="bcb35-160">Cambie el valor de **Omitir pagos y notas de crédito al calcular el código de carta de cobro** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bcb35-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
