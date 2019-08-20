---
title: Procesar diario de asignaciones contables
description: Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 087bd4f203e8762447e823b19076b79296a390d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846376"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="39b22-103">Procesar diario de asignaciones contables</span><span class="sxs-lookup"><span data-stu-id="39b22-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39b22-104">Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="39b22-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="39b22-105">Antes de crear un diario de asignaciones, debe haber al menos una regla de asignación de diario activa.</span><span class="sxs-lookup"><span data-stu-id="39b22-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="39b22-106">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="39b22-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="39b22-107">Vaya a Contabilidad general > Asignaciones > Solicitud de asignación de proceso.</span><span class="sxs-lookup"><span data-stu-id="39b22-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="39b22-108">En el campo Regla, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="39b22-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="39b22-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39b22-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="39b22-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39b22-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="39b22-111">En el campo de fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="39b22-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="39b22-112">La fecha inicial es muy importante cuando el libro mayor es el origen de datos para la regla.</span><span class="sxs-lookup"><span data-stu-id="39b22-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="39b22-113">Esta fecha controla los saldos contables que se incluirán para asignación.</span><span class="sxs-lookup"><span data-stu-id="39b22-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="39b22-114">En el campo Origen cero, seleccione Detener.</span><span class="sxs-lookup"><span data-stu-id="39b22-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="39b22-115">Esto detendrá el proceso de asignación y mostrará un mensaje que indique que se seleccionó el importe de origen cero.</span><span class="sxs-lookup"><span data-stu-id="39b22-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="39b22-116">En el campo Opciones de propuesta, seleccione "Sólo propuesta".</span><span class="sxs-lookup"><span data-stu-id="39b22-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="39b22-117">Seleccione Propuesta solo para revisar y aprobar opcionalmente el resultado en los Diarios de asignaciones antes de registrar la asignación en la Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="39b22-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="39b22-118">En el campo Fecha de registro de contabilidad general, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="39b22-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="39b22-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="39b22-119">Click OK.</span></span>
9. <span data-ttu-id="39b22-120">Vaya a Contabilidad general > Asignaciones > Diarios de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="39b22-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="39b22-121">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="39b22-121">Click Lines.</span></span>
11. <span data-ttu-id="39b22-122">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="39b22-122">Click Post.</span></span>
12. <span data-ttu-id="39b22-123">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="39b22-123">Click Post.</span></span>

