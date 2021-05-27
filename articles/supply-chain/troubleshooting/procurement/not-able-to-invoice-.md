---
title: No puede facturar un pedido de ventas dirigido al cliente
description: Ya no puede facturar el pedido de ventas original y el pedido de compra de entrega directa original después de habilitar la opción Registrar factura automáticamente.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026877"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a><span data-ttu-id="6fbba-103">No puede facturar un pedido de ventas dirigido al cliente</span><span class="sxs-lookup"><span data-stu-id="6fbba-103">You can't invoice a customer-facing sales order</span></span>

<span data-ttu-id="6fbba-104">Número de KB: 4611793</span><span class="sxs-lookup"><span data-stu-id="6fbba-104">KB number: 4611793</span></span>

## <a name="symptoms"></a><span data-ttu-id="6fbba-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6fbba-105">Symptoms</span></span>

<span data-ttu-id="6fbba-106">Ya no puede facturar el pedido de ventas original y el pedido de compra de entrega directa original después de habilitar la opción **Registrar factura automáticamente** en la página **Empresas vinculadas** de un proveedor.</span><span class="sxs-lookup"><span data-stu-id="6fbba-106">You can no longer invoice the original sales order and the original direct delivery purchase order after you enable the **Post invoice automatically** option on the **Intercompany** page for a vendor.</span></span>

## <a name="resolution"></a><span data-ttu-id="6fbba-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="6fbba-107">Resolution</span></span>

<span data-ttu-id="6fbba-108">El comportamiento de sincronización para las facturas de pedidos de entrega directa y de empresas vinculadas está controlado y forzado por los parámetros que se describen en [Configuración de parámetros para registrar un pedido de empresas vinculadas](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span><span class="sxs-lookup"><span data-stu-id="6fbba-108">The synchronization behavior for intercompany and direct delivery order invoices is controlled and forced by the parameters that are described in [Set up parameters to post an intercompany order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).</span></span>

<span data-ttu-id="6fbba-109">Después de establecer esos parámetros, primero debe facturar el pedido de ventas de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="6fbba-109">After you set those parameters, you must invoice the intercompany sales order first.</span></span> <span data-ttu-id="6fbba-110">A continuación, se sincronizarán los pedidos de ventas y los pedidos de compra originales.</span><span class="sxs-lookup"><span data-stu-id="6fbba-110">The original sales orders and purchase orders will then be synchronized.</span></span>
