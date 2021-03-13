---
title: Actualizar diarios de asiento único y revalorizaciones de divisa
description: Este tema describe cómo actualizar diarios de asiento único y revalorizaciones de divisa.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3504c01a4ed1571866fd2a0cd83eef86a57d684a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127312"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="67895-103">Actualizar diarios de asiento único y revalorizaciones de divisa</span><span class="sxs-lookup"><span data-stu-id="67895-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67895-104">Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores.</span><span class="sxs-lookup"><span data-stu-id="67895-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="67895-105">En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.</span><span class="sxs-lookup"><span data-stu-id="67895-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="67895-106">Siga estos pasos al actualizar a la versión 1611 de Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="67895-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="67895-107">Antes de actualizar a Finance and Operations, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="67895-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="67895-108">Establezca el campo **Método** en **Fecha de factura**.</span><span class="sxs-lookup"><span data-stu-id="67895-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="67895-109">Se crea una transacción de revalorización que invierte la última revalorización de divisa extranjera.</span><span class="sxs-lookup"><span data-stu-id="67895-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="67895-110">Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.</span><span class="sxs-lookup"><span data-stu-id="67895-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="67895-111">Actualice a la versión 1611.</span><span class="sxs-lookup"><span data-stu-id="67895-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="67895-112">Ejecute de nuevo los procesos de revalorización de divisa extranjera para clientes y proveedores.</span><span class="sxs-lookup"><span data-stu-id="67895-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="67895-113">Esta vez, establezca **Método** en el **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="67895-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="67895-114">Se crea una nueva transacción de revalorización basada en los tipos de cambio actuales.</span><span class="sxs-lookup"><span data-stu-id="67895-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="67895-115">Esta transacción registra las pérdidas/ganancias no realizadas y la cuenta contable de resumen correcta.</span><span class="sxs-lookup"><span data-stu-id="67895-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>
