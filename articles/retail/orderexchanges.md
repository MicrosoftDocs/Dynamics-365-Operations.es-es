---
title: Configurar y procesar un cambio en un pedido de devolución
description: En este tema se explica cómo configurar un cambio en una devolución en Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 43571099727830e81c41416b6fe250dba398b3f8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561396"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="c17ff-103">Configurar y procesar un cambio en un pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="c17ff-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c17ff-104">En versiones anteriores de Microsoft Dynamics 365 for Retail, las devoluciones relacionadas con pedidos de cliente se procesaban con el documento de pedido de devolución en Retail Headquarters.</span><span class="sxs-lookup"><span data-stu-id="c17ff-104">In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail Headquarters.</span></span> <span data-ttu-id="c17ff-105">Sin embargo, el documento de pedido de devolución se puede usar para procesar solo los productos devueltos.</span><span class="sxs-lookup"><span data-stu-id="c17ff-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="c17ff-106">Los productos devueltos se indican con una cantidad negativa en las líneas de pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="c17ff-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="c17ff-107">En cambio, las ventas se indican con una cantidad positiva.</span><span class="sxs-lookup"><span data-stu-id="c17ff-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="c17ff-108">Sin embargo, el documento de pedido de devolución no admite cantidades positivas.</span><span class="sxs-lookup"><span data-stu-id="c17ff-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="c17ff-109">Debido a esta limitación, las versiones anteriores de Retail no admitían situaciones en las que los cambios de producto se hacen con el documento de pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="c17ff-109">Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="c17ff-110">Ahora se ha agregado funcionalidad para admitir situaciones en las que los cambios se realizan con pedidos de devolución.</span><span class="sxs-lookup"><span data-stu-id="c17ff-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="c17ff-111">Retail usa el documento de pedido de ventas en lugar del documento de pedido de devolución para procesar transacciones de este tipo.</span><span class="sxs-lookup"><span data-stu-id="c17ff-111">Retail now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a><span data-ttu-id="c17ff-112">Configurar Retail para admitir cambios en pedidos de devolución</span><span class="sxs-lookup"><span data-stu-id="c17ff-112">Configure Retail to support exchanges on return orders</span></span>

<span data-ttu-id="c17ff-113">Siga estos pasos para configurar el sistema de forma que admita cambios en pedidos de devolución.</span><span class="sxs-lookup"><span data-stu-id="c17ff-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="c17ff-114">Vaya a **Retail \> Configuración de sede central \> Parámetros \> Parámetros comerciales**.</span><span class="sxs-lookup"><span data-stu-id="c17ff-114">Go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="c17ff-115">En la ficha desplegable **Pedidos de cliente**, establezca la opción **Procesar pedidos de devolución como pedidos de ventas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c17ff-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="c17ff-116">Ejecute el trabajo **Programación de distribución de configuración global** (**1110**).</span><span class="sxs-lookup"><span data-stu-id="c17ff-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="c17ff-117">Realizar un cambio</span><span class="sxs-lookup"><span data-stu-id="c17ff-117">Make an exchange</span></span>

<span data-ttu-id="c17ff-118">Una vez que el sistema se haya configurado de la manera descrita en la sección anterior, el usuario del punto de venta (PDV) seleccionará un pedido de ventas o una factura de ventas para procesar una devolución, como en las versiones anteriores de Retail.</span><span class="sxs-lookup"><span data-stu-id="c17ff-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</span></span> <span data-ttu-id="c17ff-119">Sin embargo, después de agregar los artículos devueltos al carro, el usuario podrá agregar nuevas líneas de ventas al carro.</span><span class="sxs-lookup"><span data-stu-id="c17ff-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="c17ff-120">Para estas nuevas líneas de ventas, el usuario debe definir todos los atributos necesarios para procesar una línea de pedidos de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17ff-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="c17ff-121">Estos atributos incluyen el método de entrega y la ubicación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="c17ff-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="c17ff-122">El pago para la transacción será el valor neto de las líneas de pedido de devolución y las líneas de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c17ff-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="c17ff-123">Si se realiza el pago para la transacción, el pedido de devolución se registrará como un documento de pedido de ventas en Retail Headquarters y el sistema facturará inmediatamente las líneas de devolución.</span><span class="sxs-lookup"><span data-stu-id="c17ff-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail Headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="c17ff-124">Para proporcionar mayor visibilidad de los distintos importes del carro, se han agregado al carro tres nuevos campos de importe.</span><span class="sxs-lookup"><span data-stu-id="c17ff-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="c17ff-125">Puede usar el diseñador de pantalla para hacer que estos campos nuevos estén disponibles en la interfaz de usuario del punto de venta.</span><span class="sxs-lookup"><span data-stu-id="c17ff-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="c17ff-126">**Depósito aplicado**: el importe del depósito que se aplica en una transacción cuando el usuario hace una recogida de pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17ff-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="c17ff-127">Si no hay anulación de depósito y se configura un depósito del 10 por ciento, el importe de este campo es el 90 por ciento del importe total del pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17ff-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="c17ff-128">**Importe de realización**: el importe total de las líneas en las que el modo de entrega se estableció en **Realizar** cuando el pedido de cliente se creó o editó, o durante un cambio de pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17ff-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="c17ff-129">El importe de este campo incluye todos los impuestos y gastos.</span><span class="sxs-lookup"><span data-stu-id="c17ff-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="c17ff-130">**Importe de devolución**: el importe total de las líneas que tienen cantidades negativas durante el cambio de pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17ff-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="c17ff-131">El importe de este campo incluye todos los impuestos y gastos.</span><span class="sxs-lookup"><span data-stu-id="c17ff-131">The amount in this field includes taxes and charges.</span></span>
