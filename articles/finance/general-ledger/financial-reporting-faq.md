---
title: Preguntas frecuentes sobre informes financieros
description: Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070226"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="26bc8-103">Preguntas frecuentes sobre informes financieros</span><span class="sxs-lookup"><span data-stu-id="26bc8-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="26bc8-104">Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="26bc8-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="26bc8-105">¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?</span><span class="sxs-lookup"><span data-stu-id="26bc8-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="26bc8-106">Escenario: la empresa de demostración USMF tiene un informe de balance de situación que no desea que todos los usuarios de informes financieros puedan ver en D365.</span><span class="sxs-lookup"><span data-stu-id="26bc8-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="26bc8-107">Solución: puede utilizar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo determinados usuarios puedan acceder al informe.</span><span class="sxs-lookup"><span data-stu-id="26bc8-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="26bc8-108">Inicie sesión en Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="26bc8-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="26bc8-109">Cree una nueva definición de árbol (Archivo | Nuevo | Definición de árbol) a.</span><span class="sxs-lookup"><span data-stu-id="26bc8-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="26bc8-110">Haga doble clic en la línea **Resumen** de la columna **Seguridad de la unidad**.</span><span class="sxs-lookup"><span data-stu-id="26bc8-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="26bc8-111">i.</span><span class="sxs-lookup"><span data-stu-id="26bc8-111">i.</span></span>    <span data-ttu-id="26bc8-112">Haga clic en Usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="26bc8-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="26bc8-113">1.    Seleccione los usuarios o el grupo a los que desearía conceder acceso a este informe.</span><span class="sxs-lookup"><span data-stu-id="26bc8-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="26bc8-114">[![pantalla de usuario](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="26bc8-115">[![pantalla de seguridad](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="26bc8-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="26bc8-116">b.</span><span class="sxs-lookup"><span data-stu-id="26bc8-116">b.</span></span>    <span data-ttu-id="26bc8-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="26bc8-117">Click **Save**.</span></span>
  
<span data-ttu-id="26bc8-118">[![botón de guardar](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="26bc8-119">En su definición del informe, agregue su nueva definición de árbol</span><span class="sxs-lookup"><span data-stu-id="26bc8-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="26bc8-120">[![formulario de definición de árbol](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="26bc8-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="26bc8-121">A.</span><span class="sxs-lookup"><span data-stu-id="26bc8-121">A.</span></span>  <span data-ttu-id="26bc8-122">Mientras se encuentra en la definición de árbol, haga clic en Configuración y, en "Selección de unidad de informes", marque “Incluir todas las unidades”</span><span class="sxs-lookup"><span data-stu-id="26bc8-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="26bc8-123">[![formulario de selección de unidad de informes](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="26bc8-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="26bc8-124">**Antes:** [![antes de la captura de pantalla](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="26bc8-125">**Después:** [![después de la captura de pantalla](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="26bc8-126">Nota: el motivo del mensaje anterior es que mi usuario no tiene acceso a ese informe después de aplicar Seguridad de la unidad</span><span class="sxs-lookup"><span data-stu-id="26bc8-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="26bc8-127">¿Cómo puedo determinar qué cuentas no coinciden con mis saldos en D365?</span><span class="sxs-lookup"><span data-stu-id="26bc8-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="26bc8-128">Cuando tenga un informe que no coincida con lo que podría esperar en D365, aquí hay algunos pasos que puede seguir para identificar esas cuentas y las desviaciones.</span><span class="sxs-lookup"><span data-stu-id="26bc8-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="26bc8-129">En Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="26bc8-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="26bc8-130">Cree una nueva definición de fila a.</span><span class="sxs-lookup"><span data-stu-id="26bc8-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="26bc8-131">Haga clic en Editar | Insertar filas desde Dimensiones i.</span><span class="sxs-lookup"><span data-stu-id="26bc8-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="26bc8-132">Seleccione MainAccount [![Seleccione Pantalla principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="26bc8-133">ii.</span><span class="sxs-lookup"><span data-stu-id="26bc8-133">ii.</span></span> <span data-ttu-id="26bc8-134">Haga clic en Aceptar b.</span><span class="sxs-lookup"><span data-stu-id="26bc8-134">Click Ok b.</span></span>    <span data-ttu-id="26bc8-135">Guardar la definición de fila</span><span class="sxs-lookup"><span data-stu-id="26bc8-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="26bc8-136">Crear una nueva definición de columna     [![Crear una nueva definición de columna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="26bc8-137">Cree una nueva definición del informe a.</span><span class="sxs-lookup"><span data-stu-id="26bc8-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="26bc8-138">Haga clic en Configuración y desmarque [![Formulario de configuración](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="26bc8-139">Genere el informe.</span><span class="sxs-lookup"><span data-stu-id="26bc8-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="26bc8-140">Exportar el informe a Excel.</span><span class="sxs-lookup"><span data-stu-id="26bc8-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="26bc8-141">En D365:</span><span class="sxs-lookup"><span data-stu-id="26bc8-141">In D365:</span></span> 
1.  <span data-ttu-id="26bc8-142">Haga clic en Contabilidad general | Consultas e informes | Saldo de comprobación a.</span><span class="sxs-lookup"><span data-stu-id="26bc8-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="26bc8-143">Parámetros i.</span><span class="sxs-lookup"><span data-stu-id="26bc8-143">Parameters i.</span></span>  <span data-ttu-id="26bc8-144">Desde la fecha: inicio del ejercicio ii.</span><span class="sxs-lookup"><span data-stu-id="26bc8-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="26bc8-145">Hasta la fecha: fecha en la que generó el informe para iii.</span><span class="sxs-lookup"><span data-stu-id="26bc8-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="26bc8-146">Conjunto de dimensiones financieras “Conjunto de cuenta principal” [![Formulario de cuenta principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="26bc8-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="26bc8-147">b.</span><span class="sxs-lookup"><span data-stu-id="26bc8-147">b.</span></span>    <span data-ttu-id="26bc8-148">Haga clic en Calcular</span><span class="sxs-lookup"><span data-stu-id="26bc8-148">Click Calculate</span></span>

2.  <span data-ttu-id="26bc8-149">Exportar el informe a Excel</span><span class="sxs-lookup"><span data-stu-id="26bc8-149">Export the report to Excel</span></span>

<span data-ttu-id="26bc8-150">Ahora debería poder copiar los datos desde el informe de Excel de FR al informe de saldo de comprobación de D365 y comparar las columnas "Saldo de cierre".</span><span class="sxs-lookup"><span data-stu-id="26bc8-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>
