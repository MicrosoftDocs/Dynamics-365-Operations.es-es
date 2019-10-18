---
title: Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía
description: Esta tarea crea instalaciones bancarias y un perfil de contabilización necesario para procesar una carta de garantía.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 427159048ffbb17749e813d67a900622900a7f21
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179796"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="39e90-103">Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía</span><span class="sxs-lookup"><span data-stu-id="39e90-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39e90-104">Esta tarea crea instalaciones bancarias y un perfil de contabilización necesario para procesar una carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="39e90-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="39e90-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="39e90-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="39e90-106">Parámetro de contabilidad general</span><span class="sxs-lookup"><span data-stu-id="39e90-106">General ledger parameter</span></span>
1. <span data-ttu-id="39e90-107">Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.</span><span class="sxs-lookup"><span data-stu-id="39e90-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="39e90-108">Expanda la sección Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="39e90-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="39e90-109">Seleccione la opción Habilitar carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="39e90-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="39e90-110">En el campo Diario de transacción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39e90-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="39e90-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39e90-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="39e90-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39e90-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="39e90-113">Haga clic en la ficha Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="39e90-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="39e90-114">Definición del código de secuencia numérica para el número de la carta de garantía y las referencias de transacción de la carta de garantía</span><span class="sxs-lookup"><span data-stu-id="39e90-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="39e90-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="39e90-115">Click Save.</span></span>
9. <span data-ttu-id="39e90-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39e90-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="39e90-117">Creación de instalaciones bancarias</span><span class="sxs-lookup"><span data-stu-id="39e90-117">Create Bank facility</span></span>
1. <span data-ttu-id="39e90-118">Vaya a Gestión de efectivo y bancos > Configuración > Instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="39e90-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="39e90-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="39e90-119">Click New.</span></span>
3. <span data-ttu-id="39e90-120">En el campo Grupo de instalaciones, especifique el nombre del grupo de instalaciones bancarias para la transacción de la carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="39e90-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="39e90-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39e90-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="39e90-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="39e90-122">Click Save.</span></span>
6. <span data-ttu-id="39e90-123">Haga clic en la ficha Tipos de instalación.</span><span class="sxs-lookup"><span data-stu-id="39e90-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="39e90-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="39e90-124">Click New.</span></span>
8. <span data-ttu-id="39e90-125">En el campo Tipo de instalación, escriba el nombre del tipo de instalación bancaria relacionado con el contrato de instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="39e90-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="39e90-126">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39e90-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="39e90-127">En el campo Grupo de instalaciones, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39e90-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="39e90-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39e90-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="39e90-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39e90-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="39e90-130">En el campo Naturaleza de la instalación, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="39e90-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="39e90-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="39e90-131">Click Save.</span></span>
15. <span data-ttu-id="39e90-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39e90-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="39e90-133">Perfil de contabilización de banco</span><span class="sxs-lookup"><span data-stu-id="39e90-133">Bank posting profile</span></span>
1. <span data-ttu-id="39e90-134">Vaya a Gestión de efectivo y bancos > Configuración > Perfil de registro de documentos bancarios.</span><span class="sxs-lookup"><span data-stu-id="39e90-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="39e90-135">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="39e90-135">Click New.</span></span>
3. <span data-ttu-id="39e90-136">En el campo Número de grupo/cuenta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39e90-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="39e90-137">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39e90-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="39e90-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39e90-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="39e90-139">En el campo Cuenta de pago, seleccione la cuenta principal para realizar el pago.</span><span class="sxs-lookup"><span data-stu-id="39e90-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="39e90-140">En el campo Cuenta de gastos, seleccione la cuenta de las transacciones de gastos.</span><span class="sxs-lookup"><span data-stu-id="39e90-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="39e90-141">En el campo Cuenta de márgenes, seleccione la cuenta para la transacción de márgenes.</span><span class="sxs-lookup"><span data-stu-id="39e90-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="39e90-142">En el campo Cuenta de liquidación, seleccione la cuenta de liquidación para la transacción de la carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="39e90-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="39e90-143">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="39e90-143">Click Save.</span></span>
11. <span data-ttu-id="39e90-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39e90-144">Close the page.</span></span>

