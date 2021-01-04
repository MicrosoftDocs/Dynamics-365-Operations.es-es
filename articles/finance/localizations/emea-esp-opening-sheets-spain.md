---
title: Entradas especiales y hojas de apertura
description: Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerOpeningSheet_ES
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 261334
ms.search.region: Spain
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6440ada086b1acc0182972bfca23b13933539b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407807"
---
# <a name="special-entries-and-opening-sheets"></a><span data-ttu-id="ef267-103">Entradas especiales y hojas de apertura</span><span class="sxs-lookup"><span data-stu-id="ef267-103">Special entries and opening sheets</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef267-104">Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="ef267-104">Legal entities in Spain can post special entries as opening entries for the current period, while adapting accounts to changes in accounting rules.</span></span>

<span data-ttu-id="ef267-105">Mediante hojas de apertura, puede indicar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef267-105">By using opening sheets, you can indicate the following:</span></span>

-   <span data-ttu-id="ef267-106">Aumentar el valor de activos fijos financieros específicos.</span><span class="sxs-lookup"><span data-stu-id="ef267-106">Increase the value of specific financial fixed assets.</span></span>
-   <span data-ttu-id="ef267-107">Cambiar el valor de materias primas específicas si el valor ha cambiado significativamente durante el año y cuando el material cumple criterios específicos.</span><span class="sxs-lookup"><span data-stu-id="ef267-107">Change the value of specific raw materials when the value has changed significantly during the year and when the material meets specific criteria.</span></span>

<span data-ttu-id="ef267-108">Al cerrar las entradas del ejercicio anterior, puede crear varias líneas configurando el campo **Tipo** como **Apertura**..</span><span class="sxs-lookup"><span data-stu-id="ef267-108">When you close the entries for the previous fiscal year, you can create several lines by setting the **Type** field to **Opening**.</span></span> <span data-ttu-id="ef267-109">De esta forma, puede registrar entradas de apertura especiales para el ejercicio actual.</span><span class="sxs-lookup"><span data-stu-id="ef267-109">This allows special opening entries for the current fiscal year to be posted.</span></span> <span data-ttu-id="ef267-110">Puede realizar ajustes en la hoja de apertura para el ejercicio fiscal de la página **Hojas de apertura**.</span><span class="sxs-lookup"><span data-stu-id="ef267-110">You can make adjustments to the opening sheet for the fiscal year on the **Opening sheets** page.</span></span>

## <a name="create-a-new-opening-sheet"></a><span data-ttu-id="ef267-111">Crear una nueva hoja de apertura</span><span class="sxs-lookup"><span data-stu-id="ef267-111">Create a new opening sheet</span></span>
<span data-ttu-id="ef267-112">Para crear una nueva **Hoja de apertura**, haga clic en **Nueva** en la página **Hojas de apertura**, y especifique lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ef267-112">To create a new **Opening sheet,** click **New** on the **Opening sheets** page, and specify the following.</span></span>

|                    |                                                                                                                                                                                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ef267-113">**Campo**</span><span class="sxs-lookup"><span data-stu-id="ef267-113">**Field**</span></span>          | <span data-ttu-id="ef267-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ef267-114">**Description**</span></span>                                                                                                                                                                                                                                                                                   |
| <span data-ttu-id="ef267-115">**Hojas de apertura**</span><span class="sxs-lookup"><span data-stu-id="ef267-115">**Opening sheets**</span></span> | <span data-ttu-id="ef267-116">Escriba un código para la hoja de apertura.</span><span class="sxs-lookup"><span data-stu-id="ef267-116">Enter a code for the opening sheet.</span></span> <span data-ttu-id="ef267-117">Puede crear varias hojas de apertura para cada año, pero cada una debe tener un identificador exclusivo en el campo **Hojas de apertura**.</span><span class="sxs-lookup"><span data-stu-id="ef267-117">You can create several opening sheets for each year, but each must have a unique identifier in the **Opening sheets** field.</span></span>                                                                                                                                  |
| <span data-ttu-id="ef267-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ef267-118">**Name**</span></span>           | <span data-ttu-id="ef267-119">Nombre para la hoja de apertura.</span><span class="sxs-lookup"><span data-stu-id="ef267-119">Name for the opening sheet.</span></span>                                                                                                                                                                                                                                                                       |
| <span data-ttu-id="ef267-120">**Capa de registro**</span><span class="sxs-lookup"><span data-stu-id="ef267-120">**Posting layer**</span></span>  | <span data-ttu-id="ef267-121">Seleccione la capa de registro para las transacciones.</span><span class="sxs-lookup"><span data-stu-id="ef267-121">Select the posting layer for the transactions.</span></span>                                                                                                                                                                                                                                                    |
| <span data-ttu-id="ef267-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ef267-122">**Type**</span></span>           | <span data-ttu-id="ef267-123">Seleccione **Apertura** para realizar ajustes de todo el ejercicio que se han mantenido por separado de los registros diarios en el último período del año.</span><span class="sxs-lookup"><span data-stu-id="ef267-123">Select **Opening** to make adjustments for the entire year that were maintained separately from the daily postings in the last period of the year.</span></span> <span data-ttu-id="ef267-124">Si selecciona **Apertura**, debe usar el campo **Período fiscal de apertura** en la ficha **General** para especificar el período de apertura en el que registrar.</span><span class="sxs-lookup"><span data-stu-id="ef267-124">If you select **Opening**, you should use the **Opening fiscal period** field on the **General** tab to specify the opening period to post to.</span></span> |
| <span data-ttu-id="ef267-125">**Desde … Hasta**</span><span class="sxs-lookup"><span data-stu-id="ef267-125">**From … To**</span></span>      | <span data-ttu-id="ef267-126">Especifique el período al que deben aplicarse los ajustes.</span><span class="sxs-lookup"><span data-stu-id="ef267-126">Specify the period that the adjustments apply to.</span></span>                                                                                                                                                                                                                                                 |
| <span data-ttu-id="ef267-127">**Registrar**</span><span class="sxs-lookup"><span data-stu-id="ef267-127">**Post**</span></span>           | <span data-ttu-id="ef267-128">Especifique la fecha de registro de los ajustes.</span><span class="sxs-lookup"><span data-stu-id="ef267-128">Specify the posting date for the adjustments.</span></span>                                                                                                                                                                                                                                                     |

<span data-ttu-id="ef267-129">Tras especificar información general sobre la hoja de apertura, deberá especificar las cuentas principales que se incluirán en la hoja de apertura.</span><span class="sxs-lookup"><span data-stu-id="ef267-129">After you enter the general information about the opening sheet, you'll need to specify the main accounts to include in the opening sheet.</span></span> <span data-ttu-id="ef267-130">Para ello, haga clic en **Cuentas de apertura** &gt; **Cargar saldos** en la página **Hojas de apertura**.</span><span class="sxs-lookup"><span data-stu-id="ef267-130">To do this, click **Opening accounts** &gt; **Load balances** on the **Opening sheets** page.</span></span> <span data-ttu-id="ef267-131">Haga clic en **Registrar** para registrar todos los saldos de cuentas contables en la hoja de apertura.</span><span class="sxs-lookup"><span data-stu-id="ef267-131">To post all ledger account balances and adjustments to the opening sheet, click **Post**.</span></span>



