---
title: "Cuentas de registro de cancelación de activos fijos"
description: "En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 0129eae177d44100b09c2b7bce553dd5bde5ce0c
ms.contentlocale: es-es
ms.lasthandoff: 06/29/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="732f9-103">Cuentas de registro de cancelación de activos fijos</span><span class="sxs-lookup"><span data-stu-id="732f9-103">Fixed asset disposal posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="732f9-104">En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.</span><span class="sxs-lookup"><span data-stu-id="732f9-104">This article explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="732f9-105">En la página Perfiles de contabilización de activos fijos, en la ficha desplegable Cuentas contables, seleccione Venta y Cancelación para configurar los registros en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="732f9-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="732f9-106">Para los dos tipos de transacciones, la cuenta contable se abona para el valor de cancelación del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="732f9-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="732f9-107">El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="732f9-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="732f9-108">Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="732f9-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="732f9-109">Haga clic en Cancelación, después en Venta o residual y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="732f9-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="732f9-110">También puede especificar información en los campos Valor contable y Valor de ventas en la página Parámetros de cancelación.</span><span class="sxs-lookup"><span data-stu-id="732f9-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="732f9-111">La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado.</span><span class="sxs-lookup"><span data-stu-id="732f9-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="732f9-112">Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.</span><span class="sxs-lookup"><span data-stu-id="732f9-112">However, when the sale of an asset is exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>






