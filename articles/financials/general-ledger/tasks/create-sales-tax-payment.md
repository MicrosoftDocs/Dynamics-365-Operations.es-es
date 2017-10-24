--- 
title: Crear un pago de impuestos
description: "El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6ee84da7fd055c8b0b50c43f134c0fc048ecfaeb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="1052d-103">Crear un pago de impuestos</span><span class="sxs-lookup"><span data-stu-id="1052d-103">Create a sales tax payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1052d-104">El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.</span><span class="sxs-lookup"><span data-stu-id="1052d-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="1052d-105">Vaya a Impuestos > Declaraciones > Impuestos > Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="1052d-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="1052d-106">En el campo Período de liquidación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1052d-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1052d-107">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1052d-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1052d-108">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="1052d-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="1052d-109">Si la opción de incluir correcciones no está seleccionada en la página de parámetros de contabilidad general, la liquidación se puede procesar para diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="1052d-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="1052d-110">El original es la primera liquidación para un intervalo de períodos y puede procesarse solo una vez para un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="1052d-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="1052d-111">Las últimas correcciones liquidarán las transacciones de impuestos que se hayan registrado después de crear la versión original.</span><span class="sxs-lookup"><span data-stu-id="1052d-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="1052d-112">En el campo Fecha de transacción, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="1052d-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="1052d-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1052d-113">Click OK.</span></span>


