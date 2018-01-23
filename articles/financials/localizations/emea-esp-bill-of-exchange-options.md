---
title: "Opciones de letras de cambio españolas"
description: "Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters, BankBillOfExchangeTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264644
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a523ff097eedf9a4a2cb0341b3be9d05abfa09fa
ms.openlocfilehash: cece7488d505bf02a6b65e09aa4394b09f6e974a
ms.contentlocale: es-es
ms.lasthandoff: 01/23/2018

---

# <a name="spanish-bill-of-exchange-options"></a><span data-ttu-id="508e9-103">Opciones de letras de cambio españolas</span><span class="sxs-lookup"><span data-stu-id="508e9-103">Spanish bill of exchange options</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="508e9-104">Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para las entidades jurídicas en España.</span><span class="sxs-lookup"><span data-stu-id="508e9-104">This topic describes specific options and changes in basic bill of exchange process implemented in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition for legal entities in Spain.</span></span>

<span data-ttu-id="508e9-105">Para las entidades jurídicas en España, la funcionalidad de letra de cambio tiene opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="508e9-105">For legal entities in Spain, the bill of exchange functionality has additional options:</span></span>

-   <span data-ttu-id="508e9-106">Validación de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-106">Validation for bill of exchange journals</span></span>
-   <span data-ttu-id="508e9-107">Fechas de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-107">Dates in bill of exchange journals</span></span>

## <a name="accounts-receivable-parameters-for-spanish-bills-of-exchange"></a><span data-ttu-id="508e9-108">Parámetros de clientes para letras de cambio españolas</span><span class="sxs-lookup"><span data-stu-id="508e9-108">Accounts receivable parameters for Spanish bills of exchange</span></span>
<span data-ttu-id="508e9-109">Para configurar los parámetros para letras de cambio de entidades jurídicas en España, vaya a **Parámetros de clientes** &gt; **Letra de cambio ES**.</span><span class="sxs-lookup"><span data-stu-id="508e9-109">To set up the parameters for bills of exchange for legal entities in Spain, go to **Accounts receivable parameters** &gt; **Bill of exchange ES**.</span></span>

## <a name="validation-for-bill-of-exchange-journals"></a><span data-ttu-id="508e9-110">Validación de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-110">Validation for bill of exchange journals</span></span>
<span data-ttu-id="508e9-111">Si el parámetro **Validación del diario de letra de cambio** está establecido en **Sí**, no se registra una letra de cambio cuando las transacciones tienen el mismo número de asiento y distintas fechas de transacción.</span><span class="sxs-lookup"><span data-stu-id="508e9-111">If the **Validation on bill of exchange journal** parameter is set to **Yes**, a bill of exchange isn't posted when transactions have the same voucher number and different transaction dates.</span></span> <span data-ttu-id="508e9-112">Este parámetro se aplica a las transacciones del diario contable.</span><span class="sxs-lookup"><span data-stu-id="508e9-112">This parameter applies to ledger journal transactions.</span></span> <span data-ttu-id="508e9-113">Este parámetro solo se utiliza cuando el diario admite un número de asiento y cuando la opción **Validación del diario de letra de cambio** está seleccionada en la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="508e9-113">This parameter is used only when the journal allows one voucher number, and when the **Validation on bill of exchange journals** option is selected on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="508e9-114">El parámetro **Validación del diario de letra de cambio** afecta a los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="508e9-114">The **Validation on bill of exchange journal** parameter affects the following documents:</span></span>

-   <span data-ttu-id="508e9-115">Diario de creación de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-115">Draw bill of exchange journal</span></span>
-   <span data-ttu-id="508e9-116">Diario de envíos</span><span class="sxs-lookup"><span data-stu-id="508e9-116">Remittance journal</span></span>
-   <span data-ttu-id="508e9-117">Diario de impago de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-117">Protest bill of exchange journal</span></span>
-   <span data-ttu-id="508e9-118">Diario de renegociación de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-118">Redraw bill of exchange journal</span></span>
-   <span data-ttu-id="508e9-119">Diario de liquidación de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-119">Settle bill of exchange journal</span></span>
-   <span data-ttu-id="508e9-120">Diario de pagos</span><span class="sxs-lookup"><span data-stu-id="508e9-120">Payment journal</span></span>

## <a name="dates-in-bill-of-exchange-journals"></a><span data-ttu-id="508e9-121">Fechas de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-121">Dates in bill of exchange journals</span></span>
<span data-ttu-id="508e9-122">Si el parámetro **Tratamiento de fecha en diario de letra de cambio** está establecido en **Sí**, la fecha de transacción de los diarios de letra de cambio se actualiza a la fecha de vencimiento cuando se usa una propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="508e9-122">If the **Date treatment on bill of exchange journal** parameter is set to **Yes**, the transaction date on bill of exchange journals is updated to the due date when a payment proposal is used.</span></span> <span data-ttu-id="508e9-123">El parámetro **Tratamiento de fecha en diario de letra de cambio** afecta a los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="508e9-123">The **Date treatment on bill of exchange journal** parameter affects the following documents:</span></span>

-   <span data-ttu-id="508e9-124">Diario de envíos</span><span class="sxs-lookup"><span data-stu-id="508e9-124">Remittance journal</span></span>
-   <span data-ttu-id="508e9-125">Diario de impago de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-125">Protest bill of exchange journal</span></span>
-   <span data-ttu-id="508e9-126">Diario de renegociación de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="508e9-126">Redraw bill of exchange journal</span></span>





