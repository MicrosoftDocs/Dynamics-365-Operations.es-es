---
title: Procesar cartas de cobro
description: En este tema se muestra cómo crear, imprimir y registrar cartas de cobro.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179819"
---
# <a name="process-collection-letters"></a><span data-ttu-id="1be15-103">Procesar cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="1be15-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1be15-104">En este tema se muestra cómo crear, imprimir y registrar cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-104">This topic shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="1be15-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1be15-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="1be15-106">Configurar una secuencia de cartas de cobro en el perfil de registro</span><span class="sxs-lookup"><span data-stu-id="1be15-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="1be15-107">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Perfiles de contabilización del cliente**.</span><span class="sxs-lookup"><span data-stu-id="1be15-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="1be15-108">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-108">Click **Edit**.</span></span>
3. <span data-ttu-id="1be15-109">Seleccione una secuencia de cartas de cobro en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1be15-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="1be15-110">Si no desea generar cartas de cobro para las transacciones que usan este perfil de contabilización, deje el campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1be15-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="1be15-111">Expanda la pestaña **Restricciones de tablas** para cambiar la forma en la que se procesan las cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-111">Expand the **Table restrictions** tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="1be15-112">Si este campo está establecido en **Sí**, se crearán las cartas de cobro para este perfil de contabilización.</span><span class="sxs-lookup"><span data-stu-id="1be15-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="1be15-113">Crear cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="1be15-113">Create collection letters</span></span>
1. <span data-ttu-id="1be15-114">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Crear cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-114">Go to **Navigation pane > Modules > Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="1be15-115">Seleccione los tipos de transacción para los que desee cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="1be15-116">Todas las transacciones abiertas de estos tipos se incluirán en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="1be15-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="1be15-117">En el campo **Carta de cobro**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1be15-117">In the **Collection letter** field, select an option.</span></span>
4. <span data-ttu-id="1be15-118">En el campo **Fecha de la carta de cobro**, especifique la fecha de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-118">In the **Collection letter date** field, enter the date of the collection letter.</span></span>
5. <span data-ttu-id="1be15-119">Seleccione un perfil de contabilización si ha cambiado **"Utilizar el perfil de contabilización desde** a **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="1be15-120">Existen dos opciones de perfil de registro:</span><span class="sxs-lookup"><span data-stu-id="1be15-120">There are two posting profile options:</span></span>   

   - <span data-ttu-id="1be15-121">**Cuenta**: use el perfil de contabilización asignado a la cuenta de cliente para cada nota de interés.</span><span class="sxs-lookup"><span data-stu-id="1be15-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="1be15-122">**Seleccionar**: se usa el perfil de contabilización que seleccione en el campo **Perfil de contabilización**.</span><span class="sxs-lookup"><span data-stu-id="1be15-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  

6. <span data-ttu-id="1be15-123">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="1be15-123">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="1be15-124">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-124">Select **Filter**.</span></span>
8. <span data-ttu-id="1be15-125">En el campo **Criterios**, especifique un id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="1be15-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="1be15-126">Por ejemplo, escriba "US-001".</span><span class="sxs-lookup"><span data-stu-id="1be15-126">For example, enter 'US-001'.</span></span>
9. <span data-ttu-id="1be15-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-127">Select **OK**.</span></span>
10. <span data-ttu-id="1be15-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-128">Select **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="1be15-129">Imprimir cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="1be15-129">Print collection letters</span></span>
1. <span data-ttu-id="1be15-130">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-130">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="1be15-131">En el campo **Estado**, seleccione **Creado**.</span><span class="sxs-lookup"><span data-stu-id="1be15-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="1be15-132">En el campo **Impreso**, seleccione **No se ha impreso**.</span><span class="sxs-lookup"><span data-stu-id="1be15-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="1be15-133">Seleccione **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="1be15-133">Select **Print**.</span></span>
5. <span data-ttu-id="1be15-134">Seleccione **Nota de la carta de cobro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-134">Select **Collection letter note**.</span></span>
6. <span data-ttu-id="1be15-135">En la sección **Parámetros**, especifique la fecha límite para los registros.</span><span class="sxs-lookup"><span data-stu-id="1be15-135">In the **Parameters** section, enter the cutoff date for postings.</span></span>
7. <span data-ttu-id="1be15-136">Expanda la sección **Registros que incluir** y especifique los detalles de la nota de la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-136">Expand the **Records to include** section and enter the details of the Collection letter note.</span></span>
8. <span data-ttu-id="1be15-137">Seleccione **Aceptar** para imprimir la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-137">Select **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="1be15-138">Registre la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-138">Post the collection letter.</span></span>

    1. <span data-ttu-id="1be15-139">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-139">Select **Post**.</span></span>
    1. <span data-ttu-id="1be15-140">Escriba la fecha de registro para la carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-140">Enter the posting date for the collection letter.</span></span>
    1. <span data-ttu-id="1be15-141">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="1be15-141">Expand the **Records to include** section.</span></span>
    1. <span data-ttu-id="1be15-142">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1be15-142">Select **OK**.</span></span>
    1. <span data-ttu-id="1be15-143">En el campo **Estado**, seleccione **Registrado**.</span><span class="sxs-lookup"><span data-stu-id="1be15-143">In the **Status** field, select **Posted**.</span></span>
    1. <span data-ttu-id="1be15-144">En el campo **Impreso**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1be15-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="1be15-145">Supervisar las cartas de cobro a nivel de cliente</span><span class="sxs-lookup"><span data-stu-id="1be15-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="1be15-146">También puede configurar las cartas de cobro a nivel de cliente para seguir el código de carta de cobro para cada transacción, pero el procesamiento de la carta de cobro se basará en un único nivel de la carta de cobro que se almacena para el cliente.</span><span class="sxs-lookup"><span data-stu-id="1be15-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="1be15-147">La única carta de cobro contendrá todas las transacciones que están vencidas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="1be15-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="1be15-148">Dado que los días de gracia ahora se siguen a nivel de cliente, la siguiente carta de cobro no se registrará hasta que el número de días de gracia haya pasado para la carta de cobro siguiente de la secuencia, aunque las transacciones vencen después de que la última carta de cobro se haya enviado.</span><span class="sxs-lookup"><span data-stu-id="1be15-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="1be15-149">Esta opción reduce el número de cartas de cobro que enviará por cliente.</span><span class="sxs-lookup"><span data-stu-id="1be15-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="1be15-150">Configurar el cliente para que controle las cartas de cobro a nivel de cliente</span><span class="sxs-lookup"><span data-stu-id="1be15-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="1be15-151">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Parámetros de clientes** y seleccione la pestaña **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="1be15-151">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and select the **Collections** tab.</span></span> 
2.  <span data-ttu-id="1be15-152">Cambie el valor de **Cree la carta de cobro por** a **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="1be15-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="1be15-153">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Carta de cobro > Revisar y procesar cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-153">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="1be15-154">Solo una carta de cobro se generará para un cliente con todas las transacciones vencidas.</span><span class="sxs-lookup"><span data-stu-id="1be15-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="1be15-155">Omitir pagos y notas de crédito al calcular el código de carta de cobro</span><span class="sxs-lookup"><span data-stu-id="1be15-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="1be15-156">Si incluye pagos y notas de crédito en las transacciones que se incluirán en las cartas de cobro, puede hacer que haya pagos o notas de crédito que desencadenen una carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="1be15-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="1be15-157">Puede controlar la manera en que los pagos y los notas de crédito controlan el código de la carta de cobro modificando el valor del parámetro **Omitir pagos y notas de crédito al calcular el código de carta de cobro**.</span><span class="sxs-lookup"><span data-stu-id="1be15-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="1be15-158">Para omitir pagos y notas de crédito al calcular el código de carta de cobro, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1be15-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>

1. <span data-ttu-id="1be15-159">Vaya a **Panel de navegación > Módulos > Crédito y cobros > Configuración > Parámetros de clientes** y haga clic en la pestaña **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="1be15-159">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="1be15-160">Cambie el valor de **Omitir pagos y notas de crédito al calcular el código de carta de cobro** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="1be15-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>