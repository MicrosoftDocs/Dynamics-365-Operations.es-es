---
title: Los recibos de productos cancelados no actualizan el estado de transacción a Registrado
description: Después de cancelar las recepciones de productos en una carga entrante, el sistema actualiza automáticamente el estado de la transacción de inventario de Recibido a Pedido.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294171"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="56e5b-103">Los recibos de productos cancelados no actualizan el estado de transacción a Registrado</span><span class="sxs-lookup"><span data-stu-id="56e5b-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="56e5b-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="56e5b-104">Symptoms</span></span>

<span data-ttu-id="56e5b-105">Después de ejecutar la acción para **cancelar recepciones de productos** en una carga entrante, el sistema actualiza automáticamente el estado de las transacciones de inventario de *Recibido* a *Pedido*.</span><span class="sxs-lookup"><span data-stu-id="56e5b-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="56e5b-106">Resolución</span><span class="sxs-lookup"><span data-stu-id="56e5b-106">Resolution</span></span>

<span data-ttu-id="56e5b-107">Cuando se cancelan los albaranes para las cargas salientes, el estado de las transacciones de inventario permanece *Escogido*.</span><span class="sxs-lookup"><span data-stu-id="56e5b-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="56e5b-108">Sin embargo, cuando se cancelan las recepciones de productos de una carga entrante, el estado de las transacciones de inventario no se restaura a *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="56e5b-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="56e5b-109">Por lo tanto, después de que se cancela la recepción de un producto de una carga entrante, el trabajador del almacén debe volver a registrar las cantidades de artículos para las cargas.</span><span class="sxs-lookup"><span data-stu-id="56e5b-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="56e5b-110">Para más información, ver [Registrar cantidades de artículos que llegan en una carga entrante](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="56e5b-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
