---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)'
description: En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92efd6a0b36471286c292a80542b81cd14a8eff3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551354"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2-model-mapping"></a><span data-ttu-id="5e0a6-103">ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)</span><span class="sxs-lookup"><span data-stu-id="5e0a6-103">ER Use financial dimensions as a data source (Part 2: Model mapping)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e0a6-104">En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="5e0a6-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="5e0a6-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 1: Diseño del modelo de datos)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="5e0a6-107">Agregar los orígenes de datos necesarios a la asignación de modelos</span><span class="sxs-lookup"><span data-stu-id="5e0a6-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="5e0a6-108">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="5e0a6-109">En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="5e0a6-110">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-110">Click Designer.</span></span>
4. <span data-ttu-id="5e0a6-111">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="5e0a6-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-112">Click New.</span></span>
6. <span data-ttu-id="5e0a6-113">En el campo Definición, seleccione Entrada.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="5e0a6-114">En el campo Nombre, escriba "Asignación de datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="5e0a6-115">En el campo Descripción, escriba "Asignación de datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="5e0a6-116">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-116">Click Save.</span></span>
10. <span data-ttu-id="5e0a6-117">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-117">Click Designer.</span></span>
11. <span data-ttu-id="5e0a6-118">En el árbol, seleccione "Dynamics 365 for Operations\Tabla".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="5e0a6-119">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-119">Click Add root.</span></span>
13. <span data-ttu-id="5e0a6-120">Escriba "Empresa" en el campo Nombre.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="5e0a6-121">En el campo Tabla, escriba "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="5e0a6-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e0a6-122">Click OK.</span></span>
16. <span data-ttu-id="5e0a6-123">En el árbol, seleccione "Funciones\Detalles de las dimensiones financieras".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="5e0a6-124">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-124">Click Add root.</span></span>
    * <span data-ttu-id="5e0a6-125">Este origen de datos especifica cómo el ámbito de dimensiones financieras se definirá para los informes que usen este modelo como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="5e0a6-126">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="5e0a6-127">Seleccione Sí en el campo Pedir dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="5e0a6-128">Seleccione Sí para permitir al usuario seleccionar las dimensiones en el tiempo de ejecución en el formulario del cuadro de diálogo de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="5e0a6-129">Si selecciona No, se utilizarán todas las dimensiones financieras de la instancia actual de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="5e0a6-130">En el campo Selección de dimensiones financieras, elija "Entidad jurídica".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="5e0a6-131">Seleccione Todos para permitir al usuario seleccionar las dimensiones deseadas para la instancia actual en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="5e0a6-132">Seleccione Entidad legal para permitir al usuario seleccionar las dimensiones para la empresa en el campo Buscar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="5e0a6-133">Seleccione Dimensión para permitir al usuario seleccionar las dimensiones usando un conjunto de dimensiones único.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="5e0a6-134">Seleccione Sí en el campo Pedir cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="5e0a6-135">Establezca "Pedir cuenta principal" en Sí para permitir a los usuarios seleccionar la cuenta principal como parte de la lista de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="5e0a6-136">Si se establece en No, la cuenta principal no se incluirá en la lista de dimensiones y la opción "La cuenta principal es obligatoria" se habilita.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="5e0a6-137">Si "La cuenta principal es obligatoria" se establece en Sí, incluya la cuenta principal en la lista de dimensiones independientemente de la selección del usuario.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="5e0a6-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e0a6-138">Click OK.</span></span>
23. <span data-ttu-id="5e0a6-139">En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="5e0a6-140">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-140">Click Add root.</span></span>
25. <span data-ttu-id="5e0a6-141">En el campo Nombre, escriba "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="5e0a6-142">Seleccione Sí en el campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="5e0a6-143">En el campo Tabla, escriba "LedgerJournalTable".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="5e0a6-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e0a6-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="5e0a6-145">Asignar los elementos del modelo de datos a los orígenes de datos agregados</span><span class="sxs-lookup"><span data-stu-id="5e0a6-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="5e0a6-146">En el árbol, expanda "Diario".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="5e0a6-147">En el árbol, expanda "Diario\Transacción".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="5e0a6-148">En el árbol, expanda "Diario\Transacción\Datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="5e0a6-149">En el árbol, expanda "Configuración de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="5e0a6-150">En el árbol, expanda "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="5e0a6-151">En el árbol, expanda "LibroDiario\<Relaciones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="5e0a6-152">En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="5e0a6-153">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Comprobante".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="5e0a6-154">En el árbol, seleccione "Diario\Transacción\Asiento".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="5e0a6-155">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-155">Click Bind.</span></span>
11. <span data-ttu-id="5e0a6-156">En el árbol, seleccione "LibroDiario\<Relations\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="5e0a6-157">Tenga en cuenta que para las referencias a las dimensiones financieras en las que se fija, por ejemplo, LedgerDimension, está disponible un elemento de orígenes de datos correspondiente (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="5e0a6-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="5e0a6-158">Este elemento de origen de datos proporciona las dimensiones financieras de las dimensiones establecidas como la lista del registro.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="5e0a6-159">En el árbol, expanda "LibroDiariol\<Relaciones\LibroDiarioTrans\Contabilidad.Dimensión(DimensiónContable.Dimensión)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="5e0a6-160">En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensionContable.Dimensión)\Cuenta principal y dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="5e0a6-161">En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimension)\Cuenta principal y dimensiones\Valor".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="5e0a6-162">En el árbol, expanda "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Definición".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="5e0a6-163">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Definición\Nombre".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="5e0a6-164">En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Nombre".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="5e0a6-165">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-165">Click Bind.</span></span>
19. <span data-ttu-id="5e0a6-166">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Valor\Descripción".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="5e0a6-167">En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Descripción".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="5e0a6-168">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-168">Click Bind.</span></span>
22. <span data-ttu-id="5e0a6-169">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones\Valor\Código".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="5e0a6-170">En el árbol, seleccione "Diario\Transacción\Datos de dimensiones\Código".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="5e0a6-171">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-171">Click Bind.</span></span>
25. <span data-ttu-id="5e0a6-172">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Cuenta.Dimensión(DimensiónContable.Dimensión)\Cuenta principal y dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="5e0a6-173">En el árbol, seleccione "Diario\Transacción\Datos de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="5e0a6-174">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-174">Click Bind.</span></span>
28. <span data-ttu-id="5e0a6-175">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Débito(ImporteMonedaDébito)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="5e0a6-176">En el árbol, seleccione "Diario\Transacción\Débito".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="5e0a6-177">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-177">Click Bind.</span></span>
31. <span data-ttu-id="5e0a6-178">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Fecha(TransFecha)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="5e0a6-179">En el árbol, seleccione "Diario\Transacción\Fecha".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="5e0a6-180">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-180">Click Bind.</span></span>
34. <span data-ttu-id="5e0a6-181">En el árbol, seleccione "LibroDiario\<Relaciones\LibriDiarioTrans\Moneda(MonedaCódigo)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="5e0a6-182">En el árbol, seleccione "Diario\Transacción\Divisa".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="5e0a6-183">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-183">Click Bind.</span></span>
37. <span data-ttu-id="5e0a6-184">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans\Crédito(ImporteMonedaCrédito)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="5e0a6-185">En el árbol, seleccione "Diario\Transacción\Crédito".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="5e0a6-186">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-186">Click Bind.</span></span>
40. <span data-ttu-id="5e0a6-187">En el árbol, seleccione "LibroDiario\<Relaciones\LibroDiarioTrans".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="5e0a6-188">En el árbol, seleccione "Diario\Transacción".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="5e0a6-189">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-189">Click Bind.</span></span>
43. <span data-ttu-id="5e0a6-190">En el árbol, seleccione "LedgerJournal\Número de lote de diario(JournalNum)".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="5e0a6-191">En el árbol, seleccione "Diario\Lote".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="5e0a6-192">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-192">Click Bind.</span></span>
46. <span data-ttu-id="5e0a6-193">En el árbol, seleccione "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="5e0a6-194">En el árbol, seleccione "Diario".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="5e0a6-195">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-195">Click Bind.</span></span>
49. <span data-ttu-id="5e0a6-196">En el árbol, expanda "Dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="5e0a6-197">En el árbol, expanda "Dimensiones\Cuenta principal y dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="5e0a6-198">En el árbol, expanda "Dimensiones\Cuenta principal y dimensiones\Definición".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="5e0a6-199">En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones\Definición\Nombre".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="5e0a6-200">En el árbol, seleccione "Configuración de dimensiones\Código".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="5e0a6-201">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-201">Click Bind.</span></span>
55. <span data-ttu-id="5e0a6-202">En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones\Definición\Nombre de columna de informe".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="5e0a6-203">En el árbol, seleccione "Configuración de dimensiones\Nombre".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="5e0a6-204">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-204">Click Bind.</span></span>
58. <span data-ttu-id="5e0a6-205">En el árbol, seleccione "Dimensiones\Cuenta principal y dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="5e0a6-206">En el árbol, seleccione "Configuración de dimensiones".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="5e0a6-207">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-207">Click Bind.</span></span>
61. <span data-ttu-id="5e0a6-208">En el árbol, seleccione "Empresa".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="5e0a6-209">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-209">Click Edit.</span></span>
63. <span data-ttu-id="5e0a6-210">En el campo expressionAsStringText, especifique "Company.'find()'.'name()".</span><span class="sxs-lookup"><span data-stu-id="5e0a6-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="5e0a6-211">Company.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="5e0a6-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="5e0a6-212">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-212">Click Save.</span></span>
65. <span data-ttu-id="5e0a6-213">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-213">Close the page.</span></span>
66. <span data-ttu-id="5e0a6-214">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-214">Click Save.</span></span>
67. <span data-ttu-id="5e0a6-215">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="5e0a6-216">Completar la versión de este modelo de borrador</span><span class="sxs-lookup"><span data-stu-id="5e0a6-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="5e0a6-217">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-217">Close the page.</span></span>
2. <span data-ttu-id="5e0a6-218">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-218">Close the page.</span></span>
3. <span data-ttu-id="5e0a6-219">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-219">Click Change status.</span></span>
4. <span data-ttu-id="5e0a6-220">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="5e0a6-220">Click Complete.</span></span>
5. <span data-ttu-id="5e0a6-221">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e0a6-221">Click OK.</span></span>

