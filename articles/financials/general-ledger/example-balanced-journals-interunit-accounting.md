---
title: Diarios equilibrados para la contabilidad interunidad
description: Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e84d96b5467b38e07a9ed31f142c27b638289284
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839362"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="87508-103">Diarios equilibrados para la contabilidad interunidad</span><span class="sxs-lookup"><span data-stu-id="87508-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87508-104">Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor.</span><span class="sxs-lookup"><span data-stu-id="87508-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="87508-105">Si los asientos contables no se equilibran en el nivel de los valores de la dimensión financiera, se crean automáticamente asientos contables adicionales para equilibrar el diario.</span><span class="sxs-lookup"><span data-stu-id="87508-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="87508-106">Estos asientos contables usan los tipos de registro **Interunidad: débito** y**Interunidad: crédito** de la página **Cuentas para transacciones automáticas** para determinar la cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="87508-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="87508-107">Por ejemplo, Unidad de negocio, que es el segundo segmento de la cuenta contable, se selecciona como dimensión financiera de compensación y los asientos contables siguientes que se van a crear.</span><span class="sxs-lookup"><span data-stu-id="87508-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

|                      |           |
|----------------------|-----------|
| <span data-ttu-id="87508-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="87508-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="87508-109">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="87508-109">100.00 DR</span></span> |
| <span data-ttu-id="87508-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="87508-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="87508-111">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="87508-111">100.00 DR</span></span> |
| <span data-ttu-id="87508-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="87508-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="87508-113">200,00 CR</span><span class="sxs-lookup"><span data-stu-id="87508-113">200.00 CR</span></span> |

<span data-ttu-id="87508-114">En este caso, se determinan los saldos siguientes:</span><span class="sxs-lookup"><span data-stu-id="87508-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="87508-115">Para Unidad de negocio MSP = 100.00 CR</span><span class="sxs-lookup"><span data-stu-id="87508-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="87508-116">Para Unidad de negocio NY = 100.00 DR</span><span class="sxs-lookup"><span data-stu-id="87508-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="87508-117">Por lo tanto, los siguientes asientos contables se crean automáticamente para equilibrar el diario en el nivel de los valores de la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="87508-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

|                                   |           |
|-----------------------------------|-----------|
| <span data-ttu-id="87508-118">(Interunidad: débito): MSP: OU\_256</span><span class="sxs-lookup"><span data-stu-id="87508-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="87508-119">100,00 DR</span><span class="sxs-lookup"><span data-stu-id="87508-119">100.00 DR</span></span> |
| <span data-ttu-id="87508-120">(Interunidad: crédito): NY: OU\_249</span><span class="sxs-lookup"><span data-stu-id="87508-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="87508-121">100,00 CR</span><span class="sxs-lookup"><span data-stu-id="87508-121">100.00 CR</span></span> |





