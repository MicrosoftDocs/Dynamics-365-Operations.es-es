---
title: "Actualización de revalorización de divisa y asiento único"
description: "Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 13ad43cc77731727525aae1edc4d405c166acbc1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a><span data-ttu-id="35b39-104">Actualización de revalorización de divisa y asiento único</span><span class="sxs-lookup"><span data-stu-id="35b39-104">Single voucher and currency revaluation upgrade</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="35b39-105">Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores.</span><span class="sxs-lookup"><span data-stu-id="35b39-105">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="35b39-106">En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.</span><span class="sxs-lookup"><span data-stu-id="35b39-106">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="35b39-107">Siga estos pasos cuando actualice a Microsoft Dynamics 365 for Operations versión 1611.</span><span class="sxs-lookup"><span data-stu-id="35b39-107">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="35b39-108">Antes de actualizar a Dynamics 365 for Operations, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="35b39-108">Before you upgrade to Dynamics 365 for Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="35b39-109">Establezca el campo **Método** en **Fecha de factura**.</span><span class="sxs-lookup"><span data-stu-id="35b39-109">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="35b39-110">Se crea una transacción de revalorización que invierte la última revalorización de divisa extranjera.</span><span class="sxs-lookup"><span data-stu-id="35b39-110">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="35b39-111">Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.</span><span class="sxs-lookup"><span data-stu-id="35b39-111">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="35b39-112">Actualice a Dynamics 365 for Operations versión 1611.</span><span class="sxs-lookup"><span data-stu-id="35b39-112">Upgrade to Dynamics 365 for Operations version 1611.</span></span>
3.  <span data-ttu-id="35b39-113">Ejecute de nuevo los procesos de revalorización de divisa extranjera para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="35b39-113">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="35b39-114">Esta vez, establezca **Método** en el **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="35b39-114">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="35b39-115">Se crea una nueva transacción de revalorización basada en los tipos de cambio actuales.</span><span class="sxs-lookup"><span data-stu-id="35b39-115">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="35b39-116">Esta transacción registra las pérdidas/ganancias no realizadas y la cuenta contable de resumen correcta.</span><span class="sxs-lookup"><span data-stu-id="35b39-116">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>





