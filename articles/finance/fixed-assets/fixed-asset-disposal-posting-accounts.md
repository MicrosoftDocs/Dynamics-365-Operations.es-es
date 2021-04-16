---
title: Cuentas de registro de cancelación de activos fijos
description: En este tema se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d1d6a3dc6348e64bcf247544bc7b56c5314db4c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826867"
---
# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="eb35b-103">Cuentas de registro de cancelación de activos fijos</span><span class="sxs-lookup"><span data-stu-id="eb35b-103">Fixed asset disposal posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb35b-104">En este tema se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.</span><span class="sxs-lookup"><span data-stu-id="eb35b-104">This topic explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="eb35b-105">En la página Perfiles de contabilización de activos fijos, en la ficha desplegable Cuentas contables, seleccione Venta y Cancelación para configurar los registros en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="eb35b-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="eb35b-106">Para los dos tipos de transacciones, la cuenta contable se abona para el valor de cancelación del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="eb35b-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="eb35b-107">El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="eb35b-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="eb35b-108">Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="eb35b-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="eb35b-109">Haga clic en Cancelación, después en Venta o residual y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="eb35b-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="eb35b-110">También puede especificar información en los campos Valor contable y Valor de ventas en la página Parámetros de cancelación.</span><span class="sxs-lookup"><span data-stu-id="eb35b-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="eb35b-111">La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado.</span><span class="sxs-lookup"><span data-stu-id="eb35b-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="eb35b-112">Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.</span><span class="sxs-lookup"><span data-stu-id="eb35b-112">However, when the sale of an asset exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]