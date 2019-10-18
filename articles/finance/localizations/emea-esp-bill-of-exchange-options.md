---
title: Opciones de letras de cambio españolas
description: Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Microsoft Dynamics 365 Finance para las entidades jurídicas en España.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, BankBillOfExchangeTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264644
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 11ad5bef0972476ddf9953080842105dbfa99ece
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183592"
---
# <a name="spanish-bill-of-exchange-options"></a><span data-ttu-id="4a08a-103">Opciones de letras de cambio españolas</span><span class="sxs-lookup"><span data-stu-id="4a08a-103">Spanish bill of exchange options</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a08a-104">Este tema describe opciones y cambios específicos en el proceso de letra de cambio básico implementado en Dynamics 365 Finance para las entidades jurídicas en España.</span><span class="sxs-lookup"><span data-stu-id="4a08a-104">This topic describes specific options and changes in the basic bill of exchange process implemented in Dynamics 365 Finance for legal entities in Spain.</span></span>

<span data-ttu-id="4a08a-105">Para las entidades jurídicas en España, la funcionalidad de letra de cambio tiene opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="4a08a-105">For legal entities in Spain, the bill of exchange functionality has additional options:</span></span>

-   <span data-ttu-id="4a08a-106">Validación de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-106">Validation for bill of exchange journals</span></span>
-   <span data-ttu-id="4a08a-107">Fechas de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-107">Dates in bill of exchange journals</span></span>

## <a name="accounts-receivable-parameters-for-spanish-bills-of-exchange"></a><span data-ttu-id="4a08a-108">Parámetros de clientes para letras de cambio españolas</span><span class="sxs-lookup"><span data-stu-id="4a08a-108">Accounts receivable parameters for Spanish bills of exchange</span></span>
<span data-ttu-id="4a08a-109">Para configurar los parámetros para letras de cambio de entidades jurídicas en España, vaya a **Parámetros de clientes** &gt; **Letra de cambio ES**.</span><span class="sxs-lookup"><span data-stu-id="4a08a-109">To set up the parameters for bills of exchange for legal entities in Spain, go to **Accounts receivable parameters** &gt; **Bill of exchange ES**.</span></span>

## <a name="validation-for-bill-of-exchange-journals"></a><span data-ttu-id="4a08a-110">Validación de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-110">Validation for bill of exchange journals</span></span>
<span data-ttu-id="4a08a-111">Si el parámetro **Validación del diario de letra de cambio** está establecido en **Sí**, no se registra una letra de cambio cuando las transacciones tienen el mismo número de asiento y distintas fechas de transacción.</span><span class="sxs-lookup"><span data-stu-id="4a08a-111">If the **Validation on bill of exchange journal** parameter is set to **Yes**, a bill of exchange isn't posted when transactions have the same voucher number and different transaction dates.</span></span> <span data-ttu-id="4a08a-112">Este parámetro se aplica a las transacciones del diario contable.</span><span class="sxs-lookup"><span data-stu-id="4a08a-112">This parameter applies to ledger journal transactions.</span></span> <span data-ttu-id="4a08a-113">Este parámetro solo se utiliza cuando el diario admite un número de asiento y cuando la opción **Validación del diario de letra de cambio** está seleccionada en la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="4a08a-113">This parameter is used only when the journal allows one voucher number, and when the **Validation on bill of exchange journals** option is selected on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="4a08a-114">El parámetro **Validación del diario de letra de cambio** afecta a los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="4a08a-114">The **Validation on bill of exchange journal** parameter affects the following documents:</span></span>

-   <span data-ttu-id="4a08a-115">Diario de creación de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-115">Draw bill of exchange journal</span></span>
-   <span data-ttu-id="4a08a-116">Diario de envíos</span><span class="sxs-lookup"><span data-stu-id="4a08a-116">Remittance journal</span></span>
-   <span data-ttu-id="4a08a-117">Diario de impago de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-117">Protest bill of exchange journal</span></span>
-   <span data-ttu-id="4a08a-118">Diario de renegociación de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-118">Redraw bill of exchange journal</span></span>
-   <span data-ttu-id="4a08a-119">Diario de liquidación de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-119">Settle bill of exchange journal</span></span>
-   <span data-ttu-id="4a08a-120">Diario de pagos</span><span class="sxs-lookup"><span data-stu-id="4a08a-120">Payment journal</span></span>

## <a name="dates-in-bill-of-exchange-journals"></a><span data-ttu-id="4a08a-121">Fechas de los diarios de letra de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-121">Dates in bill of exchange journals</span></span>
<span data-ttu-id="4a08a-122">Si el parámetro **Tratamiento de fecha en diario de letra de cambio** está establecido en **Sí**, la fecha de transacción de los diarios de letra de cambio se actualiza a la fecha de vencimiento cuando se usa una propuesta de pago.</span><span class="sxs-lookup"><span data-stu-id="4a08a-122">If the **Date treatment on bill of exchange journal** parameter is set to **Yes**, the transaction date on bill of exchange journals is updated to the due date when a payment proposal is used.</span></span> <span data-ttu-id="4a08a-123">El parámetro **Tratamiento de fecha en diario de letra de cambio** afecta a los siguientes documentos:</span><span class="sxs-lookup"><span data-stu-id="4a08a-123">The **Date treatment on bill of exchange journal** parameter affects the following documents:</span></span>

-   <span data-ttu-id="4a08a-124">Diario de envíos</span><span class="sxs-lookup"><span data-stu-id="4a08a-124">Remittance journal</span></span>
-   <span data-ttu-id="4a08a-125">Diario de impago de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-125">Protest bill of exchange journal</span></span>
-   <span data-ttu-id="4a08a-126">Diario de renegociación de letras de cambio</span><span class="sxs-lookup"><span data-stu-id="4a08a-126">Redraw bill of exchange journal</span></span>




