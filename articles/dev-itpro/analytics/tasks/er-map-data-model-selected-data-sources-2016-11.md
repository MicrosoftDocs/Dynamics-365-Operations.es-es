--- 
title: "Asignar un modelo de datos para seleccionar orígenes de datos para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de Administrador del Sistema o Desarrollador de Informes Electrónicos puede asignar un modelo de datos de Informes Electrónicos (ER) a los orígenes de datos seleccionados de Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96974d7c1597db4ac31168be40cecbc7e12d6edd
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="f18f2-103">Asignar un modelo de datos para seleccionar orígenes de datos para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="f18f2-103">Map a data model to selected data sources for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f18f2-104">En los pasos siguientes se explica cómo un usuario con rol de Administrador del Sistema o Desarrollador de Informes Electrónicos puede asignar un modelo de datos de Informes Electrónicos (ER) a los orígenes de datos seleccionados de Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="f18f2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected Dynamics 365 for Finance and Operations, Enterprise edition data sources.</span></span> <span data-ttu-id="f18f2-105">Esta asignación de modelo se usará posteriormente como origen de datos en una configuración de formato que se usará para gestionar documentos de pago electrónico.</span><span class="sxs-lookup"><span data-stu-id="f18f2-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="f18f2-106">En este ejemplo, asignará un modelo de datos de la empresa de demostración Litware, Inc. a los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="f18f2-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="f18f2-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "Selección de orígenes de datos para asignar modelos".</span><span class="sxs-lookup"><span data-stu-id="f18f2-107">To complete these steps, you must first complete the steps in the “Select data sources for model mapping” procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="f18f2-108">Apertura del árbol de configuraciones de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="f18f2-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="f18f2-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="f18f2-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f18f2-110">Haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="f18f2-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="f18f2-111">Selección de la asignación de modelo creada</span><span class="sxs-lookup"><span data-stu-id="f18f2-111">Select created model mapping</span></span>
1. <span data-ttu-id="f18f2-112">En el árbol, seleccione Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="f18f2-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="f18f2-113">Asegúrese de que la configuración del modelo "Pagos (modelo simplificado)" se haya creado antes.</span><span class="sxs-lookup"><span data-stu-id="f18f2-113">Make sure that the model configuration “Payments (simplified model)” has been created in advance.</span></span> <span data-ttu-id="f18f2-114">Si no, detenga ahora y vuelva tras completar la guía de tareas “Crear una nueva configuración con el modelo de datos del dominio seleccionado”.</span><span class="sxs-lookup"><span data-stu-id="f18f2-114">Otherwise, stop now and return after completion of the task guide ‘Create a new configuration with data model of the selected domain’.</span></span>  
2. <span data-ttu-id="f18f2-115">Haga clic en Diseñador de modelo.</span><span class="sxs-lookup"><span data-stu-id="f18f2-115">Click Model designer.</span></span>
3. <span data-ttu-id="f18f2-116">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f18f2-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="f18f2-117">Seleccione el registro Asignación CT.</span><span class="sxs-lookup"><span data-stu-id="f18f2-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="f18f2-118">Asignación CT</span><span class="sxs-lookup"><span data-stu-id="f18f2-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="f18f2-119">Enlace de los orígenes de datos creados con elementos del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="f18f2-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="f18f2-120">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="f18f2-120">Click Designer.</span></span>
2. <span data-ttu-id="f18f2-121">En el árbol, seleccione "Fecha y hora de procesamiento(ProcessingDateTime)".</span><span class="sxs-lookup"><span data-stu-id="f18f2-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="f18f2-122">En el árbol, seleccione Fecha de procesamiento(ProcessingDateTime).</span><span class="sxs-lookup"><span data-stu-id="f18f2-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="f18f2-123">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-123">Click Bind.</span></span>
5. <span data-ttu-id="f18f2-124">En el árbol, seleccione Identificación del mensaje de pago(MessageIdentification).</span><span class="sxs-lookup"><span data-stu-id="f18f2-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="f18f2-125">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="f18f2-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="f18f2-126">En el árbol, seleccione Transacciones\Número de lote de diario(JournalNum).</span><span class="sxs-lookup"><span data-stu-id="f18f2-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="f18f2-127">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-127">Click Bind.</span></span>
9. <span data-ttu-id="f18f2-128">En el árbol, seleccione Pagos.</span><span class="sxs-lookup"><span data-stu-id="f18f2-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="f18f2-129">En el árbol, seleccione Transacciones.</span><span class="sxs-lookup"><span data-stu-id="f18f2-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="f18f2-130">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-130">Click Bind.</span></span>
12. <span data-ttu-id="f18f2-131">En el árbol, expanda Pagos = Transacciones.</span><span class="sxs-lookup"><span data-stu-id="f18f2-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="f18f2-132">En el árbol, expanda Pagos = Transacciones\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="f18f2-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="f18f2-133">En el árbol, expanda Pagos = Transacciones\Acreedor\Cuenta.</span><span class="sxs-lookup"><span data-stu-id="f18f2-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="f18f2-134">En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Código de divisa(Currency).</span><span class="sxs-lookup"><span data-stu-id="f18f2-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="f18f2-135">En el árbol, expanda Transacciones\vendBankAccountInTransactionCompany().</span><span class="sxs-lookup"><span data-stu-id="f18f2-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="f18f2-136">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Divisa(CurrencyCode).</span><span class="sxs-lookup"><span data-stu-id="f18f2-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="f18f2-137">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-137">Click Bind.</span></span>
19. <span data-ttu-id="f18f2-138">En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Código IBAN(IBAN).</span><span class="sxs-lookup"><span data-stu-id="f18f2-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="f18f2-139">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\IBAN(BankIBAN).</span><span class="sxs-lookup"><span data-stu-id="f18f2-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="f18f2-140">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-140">Click Bind.</span></span>
22. <span data-ttu-id="f18f2-141">En el árbol, seleccione Pagos = Transacciones\Acreedor\Cuenta\Número.</span><span class="sxs-lookup"><span data-stu-id="f18f2-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="f18f2-142">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Número de cuenta bancaria(AccountNum)'.</span><span class="sxs-lookup"><span data-stu-id="f18f2-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="f18f2-143">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-143">Click Bind.</span></span>
25. <span data-ttu-id="f18f2-144">En el árbol, expanda Pagos = Transacciones\Acreedor\Agente.</span><span class="sxs-lookup"><span data-stu-id="f18f2-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="f18f2-145">En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="f18f2-146">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()Name.</span><span class="sxs-lookup"><span data-stu-id="f18f2-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="f18f2-147">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-147">Click Bind.</span></span>
29. <span data-ttu-id="f18f2-148">En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Número de ruta(RoutingNumber).</span><span class="sxs-lookup"><span data-stu-id="f18f2-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="f18f2-149">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Número de ruta(RegistrationNum).</span><span class="sxs-lookup"><span data-stu-id="f18f2-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="f18f2-150">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-150">Click Bind.</span></span>
32. <span data-ttu-id="f18f2-151">En el árbol, seleccione Pagos = Transacciones\Acreedor\Agente\Código SWIFT(SWIFT).</span><span class="sxs-lookup"><span data-stu-id="f18f2-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="f18f2-152">En el árbol, seleccione Transacciones\vendBankAccountInTransactionCompany()\Código SWIFT(SWIFTNo).</span><span class="sxs-lookup"><span data-stu-id="f18f2-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="f18f2-153">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-153">Click Bind.</span></span>
35. <span data-ttu-id="f18f2-154">En el árbol, seleccione Pagos = Transacciones\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="f18f2-155">En el árbol, expanda Transacciones\findVendTable().</span><span class="sxs-lookup"><span data-stu-id="f18f2-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="f18f2-156">En el árbol, seleccione "Transacciones\findVendTable()\name()".</span><span class="sxs-lookup"><span data-stu-id="f18f2-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="f18f2-157">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-157">Click Bind.</span></span>
39. <span data-ttu-id="f18f2-158">En el árbol, seleccione Pagos = Transacciones\Código de divisa(Currency).</span><span class="sxs-lookup"><span data-stu-id="f18f2-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="f18f2-159">En el árbol, expanda "Transacciones\>Relaciones".</span><span class="sxs-lookup"><span data-stu-id="f18f2-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="f18f2-160">En el árbol, expanda "Transacciones\>Relaciones\Tabla de divisas(Divisa)".</span><span class="sxs-lookup"><span data-stu-id="f18f2-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="f18f2-161">En el árbol, seleccione "Transacciones\>Relaciones\Tabla de divisas(Divisa)\Código de divisa(CurrencyCodeISO).</span><span class="sxs-lookup"><span data-stu-id="f18f2-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="f18f2-162">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-162">Click Bind.</span></span>
44. <span data-ttu-id="f18f2-163">En el árbol, expanda Pagos = Transacciones\Deudor.</span><span class="sxs-lookup"><span data-stu-id="f18f2-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="f18f2-164">En el árbol, expanda Pagos = Transacciones\Deudor\Cuenta.</span><span class="sxs-lookup"><span data-stu-id="f18f2-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="f18f2-165">En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Código de divisa(Currency).</span><span class="sxs-lookup"><span data-stu-id="f18f2-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="f18f2-166">En el árbol, seleccione Cuenta bancaria(BankAccount).</span><span class="sxs-lookup"><span data-stu-id="f18f2-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="f18f2-167">En el árbol, expanda Cuenta bancaria(BankAccount).</span><span class="sxs-lookup"><span data-stu-id="f18f2-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="f18f2-168">En el árbol, seleccione Cuenta bancaria(BankAccount)\Divisa(CurrencyCode).</span><span class="sxs-lookup"><span data-stu-id="f18f2-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="f18f2-169">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-169">Click Bind.</span></span>
51. <span data-ttu-id="f18f2-170">En el árbol, seleccione Cuenta bancaria(BankAccount)\IBAN.</span><span class="sxs-lookup"><span data-stu-id="f18f2-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="f18f2-171">En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Código IBAN(IBAN).</span><span class="sxs-lookup"><span data-stu-id="f18f2-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="f18f2-172">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-172">Click Bind.</span></span>
54. <span data-ttu-id="f18f2-173">En el árbol, seleccione Pagos = Transacciones\Deudor\Cuenta\Número.</span><span class="sxs-lookup"><span data-stu-id="f18f2-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="f18f2-174">En árbol, seleccione Cuenta bancaria(BankAccount)\Número de cuenta bancaria(AccountNum).</span><span class="sxs-lookup"><span data-stu-id="f18f2-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="f18f2-175">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-175">Click Bind.</span></span>
57. <span data-ttu-id="f18f2-176">En el árbol, expanda Pagos = Transacciones\Deudor\Agente.</span><span class="sxs-lookup"><span data-stu-id="f18f2-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="f18f2-177">En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="f18f2-178">En el árbol, seleccione Cuenta bancaria(BankAccount)\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="f18f2-179">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-179">Click Bind.</span></span>
61. <span data-ttu-id="f18f2-180">En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Número de ruta(RoutingNumber).</span><span class="sxs-lookup"><span data-stu-id="f18f2-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="f18f2-181">En árbol, seleccione Cuenta bancaria(BankAccount)\Número de ruta(RegistrationNum).</span><span class="sxs-lookup"><span data-stu-id="f18f2-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="f18f2-182">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-182">Click Bind.</span></span>
64. <span data-ttu-id="f18f2-183">En el árbol, seleccione Pagos = Transacciones\Deudor\Agente\Código SWIFT(SWIFT).</span><span class="sxs-lookup"><span data-stu-id="f18f2-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="f18f2-184">En el árbol, seleccione Cuenta bancaria(BankAccount)\Código SWIFT(SWIFTNo).</span><span class="sxs-lookup"><span data-stu-id="f18f2-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="f18f2-185">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-185">Click Bind.</span></span>
67. <span data-ttu-id="f18f2-186">En el árbol, seleccione Pagos = Transacciones\Deudor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="f18f2-187">En el árbol, seleccione Información de la empresa(Company).</span><span class="sxs-lookup"><span data-stu-id="f18f2-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="f18f2-188">En el árbol, expanda Información de la empresa(Company).</span><span class="sxs-lookup"><span data-stu-id="f18f2-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="f18f2-189">En el árbol, seleccione Información de la empresa(Company)\Nombre.</span><span class="sxs-lookup"><span data-stu-id="f18f2-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="f18f2-190">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-190">Click Bind.</span></span>
72. <span data-ttu-id="f18f2-191">En el árbol, seleccione Pagos = Transacciones\Descripción.</span><span class="sxs-lookup"><span data-stu-id="f18f2-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="f18f2-192">En el árbol, seleccione Transacciones\Descripción(Txt).</span><span class="sxs-lookup"><span data-stu-id="f18f2-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="f18f2-193">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-193">Click Bind.</span></span>
75. <span data-ttu-id="f18f2-194">En el árbol, seleccione Pagos = Transacciones\Código de identificación de extremo a extremo(End2EndID).</span><span class="sxs-lookup"><span data-stu-id="f18f2-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="f18f2-195">En el árbol, seleccione Transacciones\$EndToEndID.</span><span class="sxs-lookup"><span data-stu-id="f18f2-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="f18f2-196">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-196">Click Bind.</span></span>
78. <span data-ttu-id="f18f2-197">En el árbol, seleccione Pagos = Transacciones\Importe ordenado(InstructedAmount).</span><span class="sxs-lookup"><span data-stu-id="f18f2-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="f18f2-198">En el árbol, seleccione 'Transacciones\$Importe'.</span><span class="sxs-lookup"><span data-stu-id="f18f2-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="f18f2-199">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-199">Click Bind.</span></span>
81. <span data-ttu-id="f18f2-200">En el árbol, seleccione Pagos = Transacciones\Fecha de la transacción(TransactionDate).</span><span class="sxs-lookup"><span data-stu-id="f18f2-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="f18f2-201">En el árbol, seleccione Transacciones\Fecha(TransDate).</span><span class="sxs-lookup"><span data-stu-id="f18f2-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="f18f2-202">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="f18f2-203">Validación de la asignación creada</span><span class="sxs-lookup"><span data-stu-id="f18f2-203">Validate created mapping</span></span>
1. <span data-ttu-id="f18f2-204">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-204">Click Validate.</span></span>
    * <span data-ttu-id="f18f2-205">Valide la nueva asignación para garantizar que todos los enlaces son aceptables.</span><span class="sxs-lookup"><span data-stu-id="f18f2-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="f18f2-206">Haga clic en la flecha para expandir o contraer la sección Lista de errores.</span><span class="sxs-lookup"><span data-stu-id="f18f2-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="f18f2-207">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-207">Click Save.</span></span>
4. <span data-ttu-id="f18f2-208">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f18f2-208">Close the page.</span></span>
5. <span data-ttu-id="f18f2-209">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f18f2-209">Close the page.</span></span>
6. <span data-ttu-id="f18f2-210">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f18f2-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="f18f2-211">Cambio del estado de la versión actual de la configuración del modelo</span><span class="sxs-lookup"><span data-stu-id="f18f2-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="f18f2-212">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="f18f2-212">Click Change status.</span></span>
    * <span data-ttu-id="f18f2-213">Cambie el estado de la configuración del modelo diseñado: de Borrador a Completado para que esté disponible para el diseño del formato de pago.</span><span class="sxs-lookup"><span data-stu-id="f18f2-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="f18f2-214">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-214">Click Complete.</span></span>
    * <span data-ttu-id="f18f2-215">Seleccione Completar.</span><span class="sxs-lookup"><span data-stu-id="f18f2-215">Select Complete.</span></span>  
3. <span data-ttu-id="f18f2-216">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f18f2-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="f18f2-217">Para ver un ejemplo, "versión 1".</span><span class="sxs-lookup"><span data-stu-id="f18f2-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="f18f2-218">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f18f2-218">Click OK.</span></span>
5. <span data-ttu-id="f18f2-219">Seleccione la versión finalizada de la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="f18f2-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="f18f2-220">Observe cómo la configuración creada se guarda como versión completada 1.</span><span class="sxs-lookup"><span data-stu-id="f18f2-220">Note that the created configuration is saved as completed version 1.</span></span>  


