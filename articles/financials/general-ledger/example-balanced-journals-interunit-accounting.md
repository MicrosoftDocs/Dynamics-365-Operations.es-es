---
title: Diarios equilibrados para la contabilidad interunidad
description: "Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f45d180dc8dcafb0579e76b890dd5d516df5b8c0
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="46f8f-103">Diarios equilibrados para la contabilidad interunidad</span><span class="sxs-lookup"><span data-stu-id="46f8f-103">Balanced journals for interunit accounting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="46f8f-104">Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="46f8f-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="46f8f-105">Si los asientos contables no se equilibran en el nivel de los valores de la dimensión financiera, se crean automáticamente asientos contables adicionales para equilibrar el diario.</span><span class="sxs-lookup"><span data-stu-id="46f8f-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="46f8f-106">Estos asientos contables usan los tipos de registro **Interunidad: débito** y**Interunidad: crédito** de la página **Cuentas para transacciones automáticas** para determinar la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="46f8f-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="46f8f-107">Por ejemplo, Sucursal, que es el segundo segmento de la cuenta contable, se selecciona como dimensión financiera de compensación y los asientos contables siguientes que se van a crear.</span><span class="sxs-lookup"><span data-stu-id="46f8f-107">For example, Branch, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="46f8f-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="46f8f-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="46f8f-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="46f8f-109">100.00 DR</span></span> |
| <span data-ttu-id="46f8f-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="46f8f-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="46f8f-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="46f8f-111">100.00 DR</span></span> |
| <span data-ttu-id="46f8f-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="46f8f-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="46f8f-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="46f8f-113">200.00 CR</span></span> |

<span data-ttu-id="46f8f-114">En este caso, se determinan los saldos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46f8f-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="46f8f-115">Para la sucursal MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="46f8f-115">For Branch MSP = 100.00 CR</span></span>
-   <span data-ttu-id="46f8f-116">Para la sucursal NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="46f8f-116">For Branch NY = 100.00 DR</span></span>

<span data-ttu-id="46f8f-117">Por lo tanto, los siguientes asientos contables se crean automáticamente para equilibrar el diario en el nivel de los valores de la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="46f8f-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="46f8f-118">(Interunidad: débito): MSP: OU\_256</span><span class="sxs-lookup"><span data-stu-id="46f8f-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="46f8f-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="46f8f-119">100.00 DR</span></span> |
| <span data-ttu-id="46f8f-120">(Interunidad: crédito): NY: OU\_249</span><span class="sxs-lookup"><span data-stu-id="46f8f-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="46f8f-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="46f8f-121">100.00 CR</span></span> |






