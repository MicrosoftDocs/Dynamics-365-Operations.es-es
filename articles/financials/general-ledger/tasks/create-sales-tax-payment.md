---
title: Crear un pago de impuestos
description: El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee69cfee672be1571fd5cc630e33601bb5a48eac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846568"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="2d3a2-103">Crear un pago de impuestos</span><span class="sxs-lookup"><span data-stu-id="2d3a2-103">Create a sales tax payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d3a2-104">El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="2d3a2-105">Vaya a Impuestos > Declaraciones > Impuestos > Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="2d3a2-106">En el campo Período de liquidación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2d3a2-107">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2d3a2-108">En el campo Fecha inicial, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="2d3a2-109">Si la opción de incluir correcciones no está seleccionada en la página de parámetros de contabilidad general, la liquidación se puede procesar para diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="2d3a2-110">El original es la primera liquidación para un intervalo de períodos y puede procesarse solo una vez para un intervalo de períodos.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="2d3a2-111">Las últimas correcciones liquidarán las transacciones de impuestos que se hayan registrado después de crear la versión original.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="2d3a2-112">En el campo Fecha de transacción, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="2d3a2-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="2d3a2-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2d3a2-113">Click OK.</span></span>

