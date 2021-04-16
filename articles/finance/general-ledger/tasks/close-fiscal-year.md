---
title: Cerrar el ejercicio
description: Este procedimiento describe el proceso de cierre de fin de año que transfiere los saldos a un nuevo ejercicio.
author: aprilolson
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f17b7fefb9251a28bfba9d0e93b9ad171ef7b9c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815197"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="0cfca-103">Cerrar el ejercicio</span><span class="sxs-lookup"><span data-stu-id="0cfca-103">Close the fiscal year</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0cfca-104">Este procedimiento describe el proceso de cierre de fin de año que transfiere los saldos a un nuevo ejercicio.</span><span class="sxs-lookup"><span data-stu-id="0cfca-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="0cfca-105">Valide los parámetros de cierre de fin de año</span><span class="sxs-lookup"><span data-stu-id="0cfca-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="0cfca-106">Vaya a **Panel de exploración > Módulos > Contabilidad general > Configuración de contabilidad > Parámetros de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="0cfca-107">Expanda la sección **Cierre del ejercicio**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="0cfca-108">Seleccione "Sí" o "No" para la opción **Eliminar el asiento de cierre y apertura y generar uno nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="0cfca-109">Si ya ha cerrado el año fiscal y el cierre de fin de año se ejecuta de nuevo, este valor es importante.</span><span class="sxs-lookup"><span data-stu-id="0cfca-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="0cfca-110">Si se establece en Sí, el asiento del cierre de fin de año anterior se borrará y se creará un nuevo asiento para todas las cuentas con saldos iniciales.</span><span class="sxs-lookup"><span data-stu-id="0cfca-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="0cfca-111">Si se establece en No, se conservará el asiento anterior y solo se creará un nuevo asiento para ajustar las entradas que se han registrado después del último cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="0cfca-112">Seleccione "Sí" o "No" para la opción **Crear el asiento de cierre al lanzar el proceso de transacciones de cierre / apertura**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="0cfca-113">Si se establece en Sí, se crean dos transacciones.</span><span class="sxs-lookup"><span data-stu-id="0cfca-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="0cfca-114">Un asiento se crea en el ejercicio que se cierra para llevar los saldos de las cuentas contables de Pérdidas y Ganancias a cero y un segundo asiento se crea en el ejercicio siguiente para los saldos iniciales.</span><span class="sxs-lookup"><span data-stu-id="0cfca-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="0cfca-115">Si se establece en No, se crea un asiento único en el ejercicio siguiente para saldos iniciales.</span><span class="sxs-lookup"><span data-stu-id="0cfca-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="0cfca-116">Seleccione "Sí" o "No" para la opción **Establecer el estado del ejercicio en Cerrado de forma permanente**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="0cfca-117">Si se establece en Sí, el estado del ejercicio se fijará en Cerrado de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="0cfca-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="0cfca-118">Debido a que un año cerrado de forma permanente no se puede volver a abrir, ser recomienda establecer esta opción en No.</span><span class="sxs-lookup"><span data-stu-id="0cfca-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="0cfca-119">Seleccione "Sí" o "No" para la opción **Decidir si completar un número de asiento durante el cierre de fin de año**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="0cfca-120">Si se establece en Sí, deberá especificarse un número de asiento manualmente durante el proceso de cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="0cfca-121">No se usa ninguna secuencia numérica para generar dicho número de asiento.</span><span class="sxs-lookup"><span data-stu-id="0cfca-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="0cfca-122">Se recomienda elegir Sí.</span><span class="sxs-lookup"><span data-stu-id="0cfca-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="0cfca-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0cfca-123">Close the page.</span></span>
8. <span data-ttu-id="0cfca-124">Vaya a **Contabilidad general > Cierre de período > Cierre de fin de año**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="0cfca-125">Haga clic en **Nuevo** para crear una plantilla de cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="0cfca-126">Se puede crear una plantilla para un grupo de entidades jurídicas para ejecutar el cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="0cfca-127">Esta plantilla se puede volver a usar un año tras otro.</span><span class="sxs-lookup"><span data-stu-id="0cfca-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="0cfca-128">En el campo **Nombre del grupo**, especifique un nombre de plantilla de cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="0cfca-129">En el campo **Calendario fiscal**, seleccione el ejercicio para el que se va a crear la plantilla.</span><span class="sxs-lookup"><span data-stu-id="0cfca-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="0cfca-130">Solo las entidades jurídicas que utilizan el mismo ejercicio se pueden agrupar en la plantilla de cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="0cfca-131">Esto se debe a que el cierre de fin de año se hace seleccionando un ejercicio, no una fecha.</span><span class="sxs-lookup"><span data-stu-id="0cfca-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="0cfca-132">En el **panel de acciones**, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="0cfca-133">En la sección **Entidades jurídicas**, haga clic en **Agregar** para seleccionar las entidades jurídicas para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="0cfca-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="0cfca-134">Las entidades jurídicas se pueden agregar al seleccionar las entidades jurídicas o seleccionando una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="0cfca-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="0cfca-135">Sólo se agregan las entidades jurídicas con la jerarquía organizativa con el mismo calendario fiscal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0cfca-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="0cfca-136">Seleccione las entidades jurídicas o la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="0cfca-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="0cfca-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-137">Click **OK**.</span></span>
16. <span data-ttu-id="0cfca-138">Seleccione "Sí" o "No" en **Transferir dimensiones de balance de situación**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="0cfca-139">Es una práctica recomendada establecer esta opción en Sí para las cuentas de balance de situación.</span><span class="sxs-lookup"><span data-stu-id="0cfca-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="0cfca-140">Esto mantendrá las dimensiones financieras de las transacciones registradas al crear los saldos iniciales para las cuentas de balance de situación.</span><span class="sxs-lookup"><span data-stu-id="0cfca-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="0cfca-141">Para las cuentas de pérdidas y ganancias, puede seleccionar mantener las dimensiones financieras (Cerrar todo) cuando los saldos se mueven a las ganancias retenidas o puede seleccionar que las dimensiones financieras se reemplacen con un valor de la dimensión diferente (Cerrar uno).</span><span class="sxs-lookup"><span data-stu-id="0cfca-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="0cfca-142">Si elige Cerrar uno, puede definir un valor de dimensión concreto para cada dimensión o incluso optar por dejarlo en blanco.</span><span class="sxs-lookup"><span data-stu-id="0cfca-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="0cfca-143">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-143">Click **Save**.</span></span>
18. <span data-ttu-id="0cfca-144">Inicie el cierre de fin de año eligiendo **Ejecutar cierre fiscal** en el **panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="0cfca-145">El cierre de fin de año se ejecutará para la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0cfca-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="0cfca-146">Seleccione todas o un subconjunto de entidades jurídicas de la plantilla para el que ejecutar el cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="0cfca-147">En la primera ejecución del cierre de fin de año, para obtener los saldos iniciales la mayoría de las organizaciones pueden elegir ejecutar el cierre de fin de año para todas las entidades jurídicas dentro de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="0cfca-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="0cfca-148">Si después ajusta entradas, puede elegir ejecutar el cierre de fin de año para solo las entidades jurídicas que requieren ajustes.</span><span class="sxs-lookup"><span data-stu-id="0cfca-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="0cfca-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-149">Click **OK**.</span></span>
21. <span data-ttu-id="0cfca-150">Seleccione el ejercicio para el que ejecutar el cierre de fin de año.</span><span class="sxs-lookup"><span data-stu-id="0cfca-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="0cfca-151">En el campo **Asiento**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0cfca-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="0cfca-152">Es una práctica recomendada incluir el ejercicio en el número de asiento para facilitar la búsqueda del asiento de cierre de fin de año que se crea.</span><span class="sxs-lookup"><span data-stu-id="0cfca-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="0cfca-153">El cierre de fin de año se ejecuta en lote de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0cfca-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="0cfca-154">Es una práctica recomendada para los procesos de larga ejecución que se ejecuten en modo de lotes.</span><span class="sxs-lookup"><span data-stu-id="0cfca-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="0cfca-155">Suele ser uno de estos procesos y ese es el motivo por el que el valor predeterminado es utilizar el modo de lotes.</span><span class="sxs-lookup"><span data-stu-id="0cfca-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="0cfca-156">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfca-156">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]