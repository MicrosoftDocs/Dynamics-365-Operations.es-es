---
title: MX-00020 Configuración del plan de cuentas para una entidad jurídica en México
description: Configure parámetros específicos en el plan contable para habilitar la generación de informes de contabilidad electrónicos para una entidad jurídica mexicana.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccount, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f52b93f9f1217cd309d67e1a1448ca2d4401fca5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174608"
---
# <a name="mx-00020-set-up-the-chart-of-accounts-for-a-legal-entity-in-mexico"></a><span data-ttu-id="1482d-103">MX-00020 Configuración del plan de cuentas para una entidad jurídica en México</span><span class="sxs-lookup"><span data-stu-id="1482d-103">MX-00020 Set up the chart of accounts for a legal entity in Mexico</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1482d-104">Configure parámetros específicos en el plan contable para habilitar la generación de informes de contabilidad electrónicos para una entidad jurídica mexicana.</span><span class="sxs-lookup"><span data-stu-id="1482d-104">Set up specific parameters in the chart of accounts to allow the generation of electronic ledger accounting reports for a Mexican legal entity.</span></span> <span data-ttu-id="1482d-105">Esta tarea se creó con la empresa de datos de demostración MXMF.</span><span class="sxs-lookup"><span data-stu-id="1482d-105">This task was created using the MXMF demo data company.</span></span>


## <a name="set-up-parameters-for-electronic-ledger-accounting-report"></a><span data-ttu-id="1482d-106">Configuración de parámetros para el informe electrónico de contabilidad de libro mayor</span><span class="sxs-lookup"><span data-stu-id="1482d-106">Set up parameters for electronic ledger accounting report</span></span>
1. <span data-ttu-id="1482d-107">Vaya a Contabilidad general > Plan contable > Cuentas > Cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="1482d-107">Go to General ledger > Chart of accounts > Accounts > Main accounts.</span></span>
2. <span data-ttu-id="1482d-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1482d-108">Click New.</span></span>
3. <span data-ttu-id="1482d-109">En el campo Cuenta principal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-109">In the Main account field, type a value.</span></span>
4. <span data-ttu-id="1482d-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1482d-111">En el campo Valor predet. Debe/Haber, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1482d-111">In the DB/CR default field, select an option.</span></span>
    * <span data-ttu-id="1482d-112">Use este campo para especificar la transacción típica (débito o crédito).</span><span class="sxs-lookup"><span data-stu-id="1482d-112">Use this field to specify the typical transaction (debit/credit).</span></span> <span data-ttu-id="1482d-113">Este campo se usa en el archivo XML para notificar el tipo de cuenta principal de gobierno en el nodo <Natur>.</span><span class="sxs-lookup"><span data-stu-id="1482d-113">This field is used in the XML file to report the government type of main account in the node <Natur>.</span></span>  <span data-ttu-id="1482d-114">El tipo de cuenta principal se usará para determinar el tipo de cuenta de gobierno cuando este campo esté en blanco.</span><span class="sxs-lookup"><span data-stu-id="1482d-114">Main account type will be used to determine the government type of account when this field is blank.</span></span>  
6. <span data-ttu-id="1482d-115">En el campo Cuenta principal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1482d-115">In the Parent account field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1482d-116">Ejemplo: 110 Use este archivo para configurar la cuenta principal del nivel anterior.</span><span class="sxs-lookup"><span data-stu-id="1482d-116">Example: 110  Use this file to set up the parent main account of the previous level.</span></span>     <span data-ttu-id="1482d-117">Deje este campo en blanco cuando la cuenta principal represente el primer nivel de empresa en el plan contable.</span><span class="sxs-lookup"><span data-stu-id="1482d-117">Leave this field blank when the main account represents the first level of company in the chart of accounts.</span></span>    
7. <span data-ttu-id="1482d-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1482d-118">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="1482d-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1482d-119">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1482d-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1482d-120">Click Save.</span></span>

## <a name="set-up-government-group-mapping"></a><span data-ttu-id="1482d-121">Configuración de asignación de grupos del gobierno</span><span class="sxs-lookup"><span data-stu-id="1482d-121">Set up government group mapping</span></span>
1. <span data-ttu-id="1482d-122">Vaya a Contabilidad general > Plan contable > Cuentas > Grupos de cuentas de consolidación.</span><span class="sxs-lookup"><span data-stu-id="1482d-122">Go to General ledger > Chart of accounts > Accounts > Consolidation account groups.</span></span>
2. <span data-ttu-id="1482d-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1482d-123">Click New.</span></span>
3. <span data-ttu-id="1482d-124">En el campo Grupo de cuenta de consolidación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-124">In the Consolidation account group field, type a value.</span></span>
4. <span data-ttu-id="1482d-125">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-125">In the Name field, type a value.</span></span>
5. <span data-ttu-id="1482d-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1482d-126">Click Save.</span></span>
6. <span data-ttu-id="1482d-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1482d-127">Close the page.</span></span>
7. <span data-ttu-id="1482d-128">Vaya a Contabilidad general > Plan contable > Cuentas > Cuentas de consolidación adicionales.</span><span class="sxs-lookup"><span data-stu-id="1482d-128">Go to General ledger > Chart of accounts > Accounts > Additional consolidation accounts.</span></span>
8. <span data-ttu-id="1482d-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1482d-129">Click New.</span></span>
9. <span data-ttu-id="1482d-130">En el campo Cuenta principal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1482d-130">In the Main account field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="1482d-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1482d-131">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="1482d-132">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1482d-132">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="1482d-133">En el campo Grupo de cuenta de consolidación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1482d-133">In the Consolidation account group field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="1482d-134">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1482d-134">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="1482d-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1482d-135">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="1482d-136">En el campo Cuenta de consolidación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-136">In the Consolidation account field, type a value.</span></span>
    * <span data-ttu-id="1482d-137">Introduzca el grupo de la cuenta SAT.</span><span class="sxs-lookup"><span data-stu-id="1482d-137">Enter the SAT account group.</span></span> <span data-ttu-id="1482d-138">La lista de grupos de cuentas del gobierno está disponible en el sitio web de la administración pública.</span><span class="sxs-lookup"><span data-stu-id="1482d-138">The list of government account groups is available on the government website.</span></span>    
16. <span data-ttu-id="1482d-139">En el campo Nombre de cuenta de consolidación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1482d-139">In the Consolidation account name field, type a value.</span></span>
    * <span data-ttu-id="1482d-140">Puede insertar el nombre del grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="1482d-140">You can enter the name of the SAT account group.</span></span>    
17. <span data-ttu-id="1482d-141">En el campo Nivel de SAT, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="1482d-141">In the SAT level field, enter a number.</span></span>
    * <span data-ttu-id="1482d-142">Este es el nivel de grupo de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="1482d-142">This is the level of SAT account group.</span></span> <span data-ttu-id="1482d-143">La información se encuentra disponible en la lista de grupos de cuentas SAT.</span><span class="sxs-lookup"><span data-stu-id="1482d-143">The information is available in the list of SAT account groups.</span></span>  
18. <span data-ttu-id="1482d-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1482d-144">Click Save.</span></span>
    * <span data-ttu-id="1482d-145">Necesita repetir esta acción para cada cuenta principal creada en su empresa.</span><span class="sxs-lookup"><span data-stu-id="1482d-145">You need to repeat this action for each main account created in your company.</span></span> <span data-ttu-id="1482d-146">Si tiene muchas cuentas principales que crear, puede usar la herramienta de gestión de datos para importar las cuentas principales desde un archivo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1482d-146">If you have a lot of main accounts to create, you can use the Data management tool to import the main accounts from a Microsoft Excel file.</span></span>  
19. <span data-ttu-id="1482d-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1482d-147">Close the page.</span></span>

