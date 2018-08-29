--- 
title: "Definir asignaciones de modelo de ER y seleccionar orígenes de datos para ellas"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema desarrollador de informes electrónicos puede seleccionar orígenes de datos para un modelo de datos de informes electrónicos."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 2beda3555274fee3f17ad13c54c6823307216385
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="419a6-103">Definir asignaciones de modelo de ER y seleccionar orígenes de datos para ellas</span><span class="sxs-lookup"><span data-stu-id="419a6-103">Define ER model mappings and select data sources for them</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="419a6-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema desarrollador de informes electrónicos puede seleccionar orígenes de datos para un modelo de datos de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="419a6-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="419a6-105">Los orígenes de datos estarán vinculados a componentes individuales del modelo de datos seleccionado en el momento del diseño y rellenarán los datos empresariales según ese modelo de datos en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="419a6-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="419a6-106">En este ejemplo, seleccionará orígenes de datos para un modelo de datos existente que se ha creado para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Creación de un nuevo modelo de datos".</span><span class="sxs-lookup"><span data-stu-id="419a6-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="419a6-107">Abra árbol de configuraciones de Electronic Reporting (informes electrónicos)</span><span class="sxs-lookup"><span data-stu-id="419a6-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="419a6-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="419a6-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="419a6-109">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="419a6-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="419a6-110">Inserción de una asignación de modelo nueva</span><span class="sxs-lookup"><span data-stu-id="419a6-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="419a6-111">En el árbol, seleccione Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="419a6-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="419a6-112">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="419a6-112">Click Designer.</span></span>
3. <span data-ttu-id="419a6-113">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="419a6-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="419a6-114">Click New.</span></span>
    * <span data-ttu-id="419a6-115">Esto creará un nuevo registro que asignará el modelo de datos a orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="419a6-116">En este ejemplo, asignará el modelo de datos a orígenes de datos para el tipo de pago deseado: transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="419a6-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="419a6-117">Es posible diseñar más de una asignación para un modelo de datos en particular.</span><span class="sxs-lookup"><span data-stu-id="419a6-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="419a6-118">Por ejemplo, podría crear una asignación para los distintos tipos de pagos, por ejemplo de domiciliaciones bancarias o transferencias de crédito.</span><span class="sxs-lookup"><span data-stu-id="419a6-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="419a6-119">En este ejemplo, creará una asignación para transferencias de crédito.</span><span class="sxs-lookup"><span data-stu-id="419a6-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="419a6-120">En el campo Nombre, escriba "Asignación CT".</span><span class="sxs-lookup"><span data-stu-id="419a6-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="419a6-121">Asignación CT</span><span class="sxs-lookup"><span data-stu-id="419a6-121">CT mapping</span></span>  
6. <span data-ttu-id="419a6-122">En el campo Descripción, escriba "Asignación CT para modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="419a6-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="419a6-123">Asignación del modelo de pago CT</span><span class="sxs-lookup"><span data-stu-id="419a6-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="419a6-124">En el campo Definición, escriba "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="419a6-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="419a6-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="419a6-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="419a6-126">ResolveChanges la Definición.</span><span class="sxs-lookup"><span data-stu-id="419a6-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="419a6-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="419a6-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="419a6-128">Definición de orígenes de datos necesarios para la asignación de modelo actual</span><span class="sxs-lookup"><span data-stu-id="419a6-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="419a6-129">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="419a6-129">Click Designer.</span></span>
2. <span data-ttu-id="419a6-130">En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".</span><span class="sxs-lookup"><span data-stu-id="419a6-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="419a6-131">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="419a6-131">Click Add root.</span></span>
    * <span data-ttu-id="419a6-132">Especifique este origen de datos para acceder a las transacciones de pago.</span><span class="sxs-lookup"><span data-stu-id="419a6-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="419a6-133">En el campo Nombre, escriba "Transacciones".</span><span class="sxs-lookup"><span data-stu-id="419a6-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="419a6-134">Transacciones</span><span class="sxs-lookup"><span data-stu-id="419a6-134">Transactions</span></span>  
5. <span data-ttu-id="419a6-135">Especifique "Transacciones" en el campo Etiqueta.</span><span class="sxs-lookup"><span data-stu-id="419a6-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="419a6-136">Transacciones</span><span class="sxs-lookup"><span data-stu-id="419a6-136">Transactions</span></span>  
6. <span data-ttu-id="419a6-137">En el campo Ayuda, especifique "Líneas de diario de contabilidad".</span><span class="sxs-lookup"><span data-stu-id="419a6-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="419a6-138">Líneas de diario de contabilidad</span><span class="sxs-lookup"><span data-stu-id="419a6-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="419a6-139">Seleccione Sí en el campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="419a6-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="419a6-140">Seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="419a6-140">Select Yes.</span></span>  
8. <span data-ttu-id="419a6-141">En el campo Tabla, escriba "LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="419a6-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="419a6-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="419a6-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="419a6-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-143">Click OK.</span></span>
    * <span data-ttu-id="419a6-144">Seleccione la tabla LedgerJournalTrans como origen de datos para el modelo de datos actual.</span><span class="sxs-lookup"><span data-stu-id="419a6-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="419a6-145">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="419a6-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="419a6-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="419a6-146">Click Add.</span></span>
    * <span data-ttu-id="419a6-147">Haga clic en Agregar para agregar un nuevo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="419a6-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="419a6-148">En el campo Nombre, escriba "$EndToEndID".</span><span class="sxs-lookup"><span data-stu-id="419a6-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="419a6-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="419a6-149">$EndToEndID</span></span>  
13. <span data-ttu-id="419a6-150">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-150">Click Edit formula.</span></span>
14. <span data-ttu-id="419a6-151">En el árbol, seleccione String\CONCATENATE.</span><span class="sxs-lookup"><span data-stu-id="419a6-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="419a6-152">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="419a6-152">Click Add function.</span></span>
16. <span data-ttu-id="419a6-153">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="419a6-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="419a6-154">En el árbol, seleccione Transacciones\Asiento.</span><span class="sxs-lookup"><span data-stu-id="419a6-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="419a6-155">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-155">Click Add data source.</span></span>
19. <span data-ttu-id="419a6-156">En el campo Fórmula, escriba "CONCATENATE(Transactions.Voucher, "-", '.</span><span class="sxs-lookup"><span data-stu-id="419a6-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="419a6-157">Escriba [ , “-“, ] al final de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="419a6-158">En el árbol, seleccione String\TEXT.</span><span class="sxs-lookup"><span data-stu-id="419a6-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="419a6-159">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="419a6-159">Click Add function.</span></span>
22. <span data-ttu-id="419a6-160">En el árbol, seleccione Transacciones\Record-ID(RecId).</span><span class="sxs-lookup"><span data-stu-id="419a6-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="419a6-161">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-161">Click Add data source.</span></span>
24. <span data-ttu-id="419a6-162">En el campo Fórmula, escriba "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".</span><span class="sxs-lookup"><span data-stu-id="419a6-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="419a6-163">Escriba [))] al final de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="419a6-164">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="419a6-164">Click Save.</span></span>
    * <span data-ttu-id="419a6-165">Asegúrese de que no se hayan detectado errores en la fórmula creada.</span><span class="sxs-lookup"><span data-stu-id="419a6-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="419a6-166">Consulte la ficha ERRORES debajo del control de edición de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="419a6-167">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-167">Close the page.</span></span>
27. <span data-ttu-id="419a6-168">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-168">Click OK.</span></span>
    * <span data-ttu-id="419a6-169">Agregue el campo calculado a este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="419a6-170">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="419a6-170">Click Add.</span></span>
    * <span data-ttu-id="419a6-171">Haga clic en Agregar para agregar un nuevo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="419a6-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="419a6-172">Escriba "$Amount'" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="419a6-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="419a6-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="419a6-173">$Amount</span></span>  
30. <span data-ttu-id="419a6-174">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-174">Click Edit formula.</span></span>
31. <span data-ttu-id="419a6-175">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="419a6-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="419a6-176">En el árbol, seleccione Transacciones\Débito(AmountCurDebit).</span><span class="sxs-lookup"><span data-stu-id="419a6-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="419a6-177">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-177">Click Add data source.</span></span>
34. <span data-ttu-id="419a6-178">En el campo Fórmula, escriba 'Transactions.AmountCurDebit - '.</span><span class="sxs-lookup"><span data-stu-id="419a6-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="419a6-179">Escriba [ - ] al final de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="419a6-180">En el árbol, seleccione Transacciones\Crédito(AmountCurCredit).</span><span class="sxs-lookup"><span data-stu-id="419a6-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="419a6-181">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-181">Click Add data source.</span></span>
37. <span data-ttu-id="419a6-182">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="419a6-182">Click Save.</span></span>
38. <span data-ttu-id="419a6-183">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-183">Close the page.</span></span>
39. <span data-ttu-id="419a6-184">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-184">Click OK.</span></span>
    * <span data-ttu-id="419a6-185">Esto agregará el campo calculado $Amount al origen de datos seleccionado para el modelo de datos actual.</span><span class="sxs-lookup"><span data-stu-id="419a6-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="419a6-186">En el árbol, seleccione 'Transacciones\$Importe'.</span><span class="sxs-lookup"><span data-stu-id="419a6-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="419a6-187">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="419a6-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="419a6-188">En el árbol, expanda o contraiga 'Transacciones\$Importe'.</span><span class="sxs-lookup"><span data-stu-id="419a6-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="419a6-189">En el árbol, expanda o contraiga "Transacciones".</span><span class="sxs-lookup"><span data-stu-id="419a6-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="419a6-190">En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".</span><span class="sxs-lookup"><span data-stu-id="419a6-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="419a6-191">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="419a6-191">Click Add root.</span></span>
    * <span data-ttu-id="419a6-192">Especifique este origen de datos para acceder a los detalles de la cuenta bancaria de la empresa.</span><span class="sxs-lookup"><span data-stu-id="419a6-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="419a6-193">En el campo Nombre, escriba "BankAccount".</span><span class="sxs-lookup"><span data-stu-id="419a6-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="419a6-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="419a6-194">BankAccount</span></span>  
47. <span data-ttu-id="419a6-195">Especifique "Cuenta bancaria" en el campo Etiqueta.</span><span class="sxs-lookup"><span data-stu-id="419a6-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="419a6-196">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="419a6-196">Bank Account</span></span>  
48. <span data-ttu-id="419a6-197">Especifique "Cuenta bancaria" en el campo Ayuda.</span><span class="sxs-lookup"><span data-stu-id="419a6-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="419a6-198">Cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="419a6-198">Bank Account</span></span>  
49. <span data-ttu-id="419a6-199">Seleccione Sí en el campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="419a6-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="419a6-200">Seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="419a6-200">Select Yes.</span></span>  
50. <span data-ttu-id="419a6-201">En el campo Tabla, escriba "BankAccountTable".</span><span class="sxs-lookup"><span data-stu-id="419a6-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="419a6-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="419a6-202">BankAccountTable</span></span>  
51. <span data-ttu-id="419a6-203">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-203">Click OK.</span></span>
    * <span data-ttu-id="419a6-204">Seleccione la tabla BankAccountTable como origen de datos para el modelo de datos actual.</span><span class="sxs-lookup"><span data-stu-id="419a6-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="419a6-205">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="419a6-205">Click Add root.</span></span>
    * <span data-ttu-id="419a6-206">Especifique este origen de datos para acceder a los requisitos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="419a6-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="419a6-207">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="419a6-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="419a6-208">Compañía</span><span class="sxs-lookup"><span data-stu-id="419a6-208">Company</span></span>  
54. <span data-ttu-id="419a6-209">En el campo Etiqueta, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="419a6-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="419a6-210">Información de la empresa</span><span class="sxs-lookup"><span data-stu-id="419a6-210">Company information</span></span>  
55. <span data-ttu-id="419a6-211">En el campo Ayuda, escriba "Información de la empresa".</span><span class="sxs-lookup"><span data-stu-id="419a6-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="419a6-212">Información de la empresa</span><span class="sxs-lookup"><span data-stu-id="419a6-212">Company information</span></span>  
56. <span data-ttu-id="419a6-213">Seleccione Sí en el campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="419a6-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="419a6-214">Seleccione Sí.</span><span class="sxs-lookup"><span data-stu-id="419a6-214">Select Yes.</span></span>  
57. <span data-ttu-id="419a6-215">En el campo Tabla, escriba "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="419a6-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="419a6-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="419a6-216">CompanyInfo</span></span>  
58. <span data-ttu-id="419a6-217">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-217">Click OK.</span></span>
    * <span data-ttu-id="419a6-218">Seleccione la tabla CompanyInfo como origen de datos para el modelo de datos actual.</span><span class="sxs-lookup"><span data-stu-id="419a6-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="419a6-219">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="419a6-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="419a6-220">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="419a6-220">Click Add root.</span></span>
    * <span data-ttu-id="419a6-221">Inserte un campo calculado como un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="419a6-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="419a6-222">En el campo Nombre, escriba "ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="419a6-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="419a6-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="419a6-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="419a6-224">En el campo Etiqueta, escriba "Fecha y hora de procesamiento".</span><span class="sxs-lookup"><span data-stu-id="419a6-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="419a6-225">Fecha y hora de procesamiento</span><span class="sxs-lookup"><span data-stu-id="419a6-225">Processing date & time</span></span>  
63. <span data-ttu-id="419a6-226">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="419a6-226">Click Edit formula.</span></span>
64. <span data-ttu-id="419a6-227">En el árbol, seleccione "Fecha/hora\SESSIONNOW"</span><span class="sxs-lookup"><span data-stu-id="419a6-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="419a6-228">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="419a6-228">Click Add function.</span></span>
66. <span data-ttu-id="419a6-229">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="419a6-229">Click Save.</span></span>
67. <span data-ttu-id="419a6-230">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-230">Close the page.</span></span>
68. <span data-ttu-id="419a6-231">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="419a6-231">Click OK.</span></span>
    * <span data-ttu-id="419a6-232">Agregue el campo calculado ProcessingDateTime como origen de datos para el modelo de datos actual.</span><span class="sxs-lookup"><span data-stu-id="419a6-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="419a6-233">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="419a6-233">Click Save.</span></span>
70. <span data-ttu-id="419a6-234">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-234">Close the page.</span></span>
71. <span data-ttu-id="419a6-235">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-235">Close the page.</span></span>
72. <span data-ttu-id="419a6-236">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="419a6-236">Close the page.</span></span>


