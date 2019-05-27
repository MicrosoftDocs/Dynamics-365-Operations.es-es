---
title: Crear esquemas de acumulación
description: Esta guía de tareas describe los pasos de la creación de un esquema de acumulación.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553140"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="fcb24-103">Crear esquemas de acumulación</span><span class="sxs-lookup"><span data-stu-id="fcb24-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fcb24-104">Esta guía de tareas describe los pasos de la creación de un esquema de acumulación.</span><span class="sxs-lookup"><span data-stu-id="fcb24-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="fcb24-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="fcb24-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="fcb24-106">Vaya a Contabilidad general > Configuración de diario > Esquemas de acumulación.</span><span class="sxs-lookup"><span data-stu-id="fcb24-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="fcb24-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fcb24-107">Click New.</span></span>
3. <span data-ttu-id="fcb24-108">En el campo Identificación acumulada, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fcb24-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="fcb24-109">En el campo Descripción del plan de provisión, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fcb24-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="fcb24-110">En el campo Débito, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="fcb24-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="fcb24-111">La cuenta principal definida reemplazará la cuenta principal de débito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.</span><span class="sxs-lookup"><span data-stu-id="fcb24-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="fcb24-112">En el campo Crédito, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="fcb24-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="fcb24-113">La cuenta principal definida reemplazará la cuenta principal de crédito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.</span><span class="sxs-lookup"><span data-stu-id="fcb24-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="fcb24-114">En el campo Asiento, seleccione cómo desea que se determine el asiento cuando se registran las transacciones.</span><span class="sxs-lookup"><span data-stu-id="fcb24-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="fcb24-115">En el campo Descripción, escriba un valor para describir las transacciones que se registrarán.</span><span class="sxs-lookup"><span data-stu-id="fcb24-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="fcb24-116">En el campo Frecuencia de períodos, seleccione la frecuencia con la que se deben producir las transacciones.</span><span class="sxs-lookup"><span data-stu-id="fcb24-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="fcb24-117">En el campo Número de repeticiones por período, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="fcb24-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="fcb24-118">En el campo Registrar transacciones, seleccione cuándo se deben registrar las transacciones, por ejemplo, Mensual.</span><span class="sxs-lookup"><span data-stu-id="fcb24-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

