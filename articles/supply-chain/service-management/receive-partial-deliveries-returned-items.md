---
title: Recibir entregas parciales de artículos devueltos
description: Las entregas parciales se definen en términos de líneas de pedidos de devolución, no de envíos de pedidos de devolución.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2b7bfad1e0d80675848353d4118960d44f2dc01
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "363922"
---
# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="8f6da-103">Recibir entregas parciales de artículos devueltos</span><span class="sxs-lookup"><span data-stu-id="8f6da-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8f6da-104">Las entregas parciales se definen en términos de líneas de pedidos de devolución, no de envíos de pedidos de devolución.</span><span class="sxs-lookup"><span data-stu-id="8f6da-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="8f6da-105">Esto significa que si recibe la cantidad completa que se indica en una línea del pedido de devolución pero no recibe ninguna cantidad de las demás líneas del pedido de devolución, ésta no es una entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="8f6da-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="8f6da-106">Sin embargo, si en una línea del pedido de devolución se solicitan 10 unidades de un determinado artículo que se va a devolver pero se reciben sólo cuatro unidades, ésta es una entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="8f6da-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="8f6da-107">Si un envío de devolución contiene una cantidad inferior al total de la cantidad de una línea del pedido de devolución, puede configurar la entrega por separado y esperar a que se reciba el resto de la cantidad devuelta, o registrar la cantidad parcial.</span><span class="sxs-lookup"><span data-stu-id="8f6da-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="8f6da-108">Registro de una cantidad parcial</span><span class="sxs-lookup"><span data-stu-id="8f6da-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="8f6da-109">Tras seleccionar un pedido de devolución de llegada en el formulario **Visión general de llegadas - Almacén: %1, Muelle: %2, nombre de diario: %3**, haga click en **Iniciar llegada** para crear el diario de recepción y, a continuación haga click en **Diarios** \> **Mostrar llegadas a partir de recepciones** para abrir el formulario **Diario de ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8f6da-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="8f6da-110">Seleccione la línea del diario con el que desea trabajar y haga clic en **Líneas** para abrir el formulario **Líneas de diario, ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8f6da-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="8f6da-111">Seleccione la línea del número de artículo del que sólo se ha recibido una cantidad parcial y, a continuación, haga clic en **Funciones** \> **Dividir** para abrir el formulario **Dividir**.</span><span class="sxs-lookup"><span data-stu-id="8f6da-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="8f6da-112">En el campo **Cantidad dividida**, especifique la cantidad correspondiente al número total de artículos recibidos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f6da-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="8f6da-113">En el formulario **Líneas de diario, ubicaciones**, seleccione la línea correspondiente a la cantidad de artículos recibida y, a continuación, haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="8f6da-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="8f6da-114">Puede registrar la línea de la cantidad adicional después de que se reciban los artículos.</span><span class="sxs-lookup"><span data-stu-id="8f6da-114">You can post the line for the additional quantity after the items have arrived.</span></span>




