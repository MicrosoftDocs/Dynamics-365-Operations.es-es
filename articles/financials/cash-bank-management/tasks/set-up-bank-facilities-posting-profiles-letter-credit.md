---
title: Configuración de créditos bancarios y perfiles de contabilización para créditos documentarios
description: Este procedimiento le muestra cómo crear un perfil de registro e instalaciones bancarias, necesario para procesar cartas de crédito.
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
ms.openlocfilehash: 0d3d35bd265ad31da083d2437fae886569766085
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841906"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="d385d-103">Configuración de créditos bancarios y perfiles de contabilización para créditos documentarios</span><span class="sxs-lookup"><span data-stu-id="d385d-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d385d-104">Este procedimiento le muestra cómo crear un perfil de registro e instalaciones bancarias, necesario para procesar cartas de crédito.</span><span class="sxs-lookup"><span data-stu-id="d385d-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="d385d-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d385d-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="d385d-106">Parámetro de contabilidad general</span><span class="sxs-lookup"><span data-stu-id="d385d-106">General ledger parameter</span></span>
1. <span data-ttu-id="d385d-107">Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.</span><span class="sxs-lookup"><span data-stu-id="d385d-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="d385d-108">Expanda la sección Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="d385d-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="d385d-109">Seleccione la opción Habilitar créditos documentarios de importación.</span><span class="sxs-lookup"><span data-stu-id="d385d-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="d385d-110">Seleccione la opción Habilitar créditos documentarios de exportación.</span><span class="sxs-lookup"><span data-stu-id="d385d-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="d385d-111">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d385d-111">Click Save.</span></span>
6. <span data-ttu-id="d385d-112">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d385d-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="d385d-113">Creación de instalaciones bancarias</span><span class="sxs-lookup"><span data-stu-id="d385d-113">Create Bank facility</span></span>
1. <span data-ttu-id="d385d-114">Vaya a Gestión de efectivo y bancos > Configuración > Instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="d385d-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="d385d-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d385d-115">Click New.</span></span>
3. <span data-ttu-id="d385d-116">En el campo Grupo de instalaciones, indique el nombre del grupo de instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="d385d-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="d385d-117">En el campo Descripción, escriba la descripción del grupo de instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="d385d-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="d385d-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d385d-118">Click Save.</span></span>
6. <span data-ttu-id="d385d-119">Haga clic en la ficha Tipos de instalación.</span><span class="sxs-lookup"><span data-stu-id="d385d-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="d385d-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d385d-120">Click New.</span></span>
8. <span data-ttu-id="d385d-121">En el campo Tipo de instalación, especifique un código único.</span><span class="sxs-lookup"><span data-stu-id="d385d-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="d385d-122">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d385d-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="d385d-123">En el campo Grupo de instalaciones, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d385d-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="d385d-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d385d-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="d385d-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d385d-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="d385d-126">En el campo Naturaleza de la instalación, seleccione la naturaleza de las instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="d385d-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="d385d-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d385d-127">Click Save.</span></span>
15. <span data-ttu-id="d385d-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d385d-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="d385d-129">Perfil de contabilización de banco</span><span class="sxs-lookup"><span data-stu-id="d385d-129">Bank posting profile</span></span>
1. <span data-ttu-id="d385d-130">Vaya a Gestión de efectivo y bancos > Configuración > Perfil de registro de documentos bancarios.</span><span class="sxs-lookup"><span data-stu-id="d385d-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="d385d-131">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d385d-131">Click New.</span></span>
3. <span data-ttu-id="d385d-132">En el campo Número de grupo/cuenta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d385d-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d385d-133">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d385d-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d385d-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d385d-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d385d-135">Seleccione la cuenta principal de liquidación.</span><span class="sxs-lookup"><span data-stu-id="d385d-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="d385d-136">Esta cuenta se usa para calcular la previsión de flujo de efectivo.</span><span class="sxs-lookup"><span data-stu-id="d385d-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="d385d-137">En el campo Cuenta de gastos, seleccione la cuenta de las transacciones de gastos.</span><span class="sxs-lookup"><span data-stu-id="d385d-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="d385d-138">En el campo Cuenta de márgenes, seleccione la cuenta de las transacciones de márgenes.</span><span class="sxs-lookup"><span data-stu-id="d385d-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="d385d-139">Al registrar el margen de apertura, se crea un adeudo en la cuenta. Al registrar el pago, se realiza un abono.</span><span class="sxs-lookup"><span data-stu-id="d385d-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="d385d-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d385d-140">Click Save.</span></span>

