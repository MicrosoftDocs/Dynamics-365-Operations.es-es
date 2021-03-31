---
title: Procesar diario de asignaciones contables
description: En este tema se explica cómo procesar una solicitud de asignación en Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a52a5ce2d789757a11c9e443c7f25058bd9d8a91
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222344"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="b9f93-103">Procesar diario de asignaciones contables</span><span class="sxs-lookup"><span data-stu-id="b9f93-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9f93-104">En este tema se explica cómo procesar una solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="b9f93-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="b9f93-105">Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="b9f93-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="b9f93-106">Antes de crear un diario de asignaciones, debe haber al menos una regla de asignación de diario activa.</span><span class="sxs-lookup"><span data-stu-id="b9f93-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="b9f93-107">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="b9f93-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b9f93-108">En el panel de navegación, vaya a **Módulos > Contabilidad general > Asignaciones > Solicitud de asignación de proceso**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="b9f93-109">En el campo **Regla**, seleccione el registro deseado en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="b9f93-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="b9f93-110">En el campo **A partir de la fecha**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="b9f93-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="b9f93-111">El campo **A partir de la fecha** es muy importante cuando el libro mayor es el origen de datos para la regla.</span><span class="sxs-lookup"><span data-stu-id="b9f93-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="b9f93-112">Esta fecha controla los saldos contables que se incluirán para asignación.</span><span class="sxs-lookup"><span data-stu-id="b9f93-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="b9f93-113">En el campo **Origen cero**, seleccione **Detener**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="b9f93-114">Esto detendrá el proceso de asignación y mostrará un mensaje que indique que se seleccionó el importe de origen cero.</span><span class="sxs-lookup"><span data-stu-id="b9f93-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="b9f93-115">En el campo **Opciones de propuesta**, seleccione **Sólo propuesta**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="b9f93-116">Seleccione **Propuesta solo** para revisar y aprobar opcionalmente el resultado en los Diarios de asignaciones antes de registrar la asignación en la Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="b9f93-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="b9f93-117">En el campo Fecha de registro de contabilidad general, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="b9f93-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="b9f93-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-118">Select **OK**.</span></span>
7. <span data-ttu-id="b9f93-119">En el panel de navegación, vaya a **Módulos > Contabilidad general > Asignaciones > Diarios de asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="b9f93-120">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-120">Select **Lines**.</span></span>
9. <span data-ttu-id="b9f93-121">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-121">Select **Post**.</span></span>
10. <span data-ttu-id="b9f93-122">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="b9f93-122">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]