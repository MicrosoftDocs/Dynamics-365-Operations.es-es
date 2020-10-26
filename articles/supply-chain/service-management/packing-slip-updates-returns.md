---
title: Actualizaciones de albaranes para devoluciones
description: Antes de recibir los artículos devueltos en el inventario, es necesario actualizar el albarán del pedido al que pertenecen.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7f5bf5adb603d7edb40960b70cb71e25a2f0456
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983876"
---
# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="abdc9-103">Actualizaciones de albaranes para devoluciones</span><span class="sxs-lookup"><span data-stu-id="abdc9-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="abdc9-104">Antes de recibir los artículos devueltos en el inventario, es necesario actualizar el albarán del pedido al que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="abdc9-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="abdc9-105">Del mismo modo que el proceso de actualización de facturas es la actualización de la transacción financiera, el proceso de actualización de albaranes es la actualización física del registro de inventario; es decir, envía los cambios al inventario.</span><span class="sxs-lookup"><span data-stu-id="abdc9-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="abdc9-106">En el caso de las devoluciones, los pasos que se asignan a la acción de disposición se implementan durante la actualización del albarán.</span><span class="sxs-lookup"><span data-stu-id="abdc9-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="abdc9-107">La actualización del albarán se puede procesar en el diario de recepción de artículos o en el pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="abdc9-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="abdc9-108">Como parte del proceso de registro de albaranes, el número de referencia del albarán de los documentos de envío del cliente también se puede asociar a las líneas de pedido.</span><span class="sxs-lookup"><span data-stu-id="abdc9-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="abdc9-109">Esta asociación es opcional y tiene una finalidad informativa.</span><span class="sxs-lookup"><span data-stu-id="abdc9-109">This association is optional and for reference only.</span></span> <span data-ttu-id="abdc9-110">No crea ninguna actualización transaccional.</span><span class="sxs-lookup"><span data-stu-id="abdc9-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="abdc9-111">Si no llegan todos los artículos de la devolución que se esperaban, se recomienda incluir sólo la cantidad que se ha recibido en la actualización del albarán.</span><span class="sxs-lookup"><span data-stu-id="abdc9-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="abdc9-112">Deje los artículos restantes en el pedido hasta que llegue el resto del envío de la devolución.</span><span class="sxs-lookup"><span data-stu-id="abdc9-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="abdc9-113">Si un artículo se devuelve de la cuarentena al departamento de envíos y recepciones, como sucede cuando el inspector de cuarentena no sabe dónde almacenar el artículo en el inventario, es necesario actualizar el albarán correspondiente para registrarlo correctamente y actuar sobre el código de disposición que se especifica como resultado de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="abdc9-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="abdc9-114">Cuando se actualiza el albarán de un artículo devuelto de un acuerdo de venta, el compromiso del acuerdo de venta de dicho artículo se actualiza automáticamente para reflejar el cambio en la cantidad o el importe.</span><span class="sxs-lookup"><span data-stu-id="abdc9-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="abdc9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abdc9-115">See also</span></span>

[<span data-ttu-id="abdc9-116">Actualizaciones de facturas para devoluciones</span><span class="sxs-lookup"><span data-stu-id="abdc9-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  


