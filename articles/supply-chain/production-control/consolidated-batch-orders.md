---
title: Pedidos de lote consolidados
description: Este artículo describe el concepto de pedidos de lote consolidados.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7656889b69cfd1dcffb45b52eb649bce59629
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809239"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="00aeb-103">Pedidos de lote consolidados</span><span class="sxs-lookup"><span data-stu-id="00aeb-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00aeb-104">Este artículo describe el concepto de pedidos de lote consolidados.</span><span class="sxs-lookup"><span data-stu-id="00aeb-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="00aeb-105">Un artículo masivo producido se considera artículo principal, mientras que un artículo empaquetado se considera artículo secundario.</span><span class="sxs-lookup"><span data-stu-id="00aeb-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="00aeb-106">La relación entre el artículo masivo y el artículo empaquetado se expresa mediante una conversión de artículos masivos.</span><span class="sxs-lookup"><span data-stu-id="00aeb-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="00aeb-107">Esta conversión de artículos masivos se define en el artículo masivo en sí.</span><span class="sxs-lookup"><span data-stu-id="00aeb-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="00aeb-108">Los artículos empaquetados se pueden empaquetar en contenedores de un solo tamaño o de varios tamaños, que se consideran como una sola unidad.</span><span class="sxs-lookup"><span data-stu-id="00aeb-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="00aeb-109">Al consolidar los pedidos para un artículo masivo, se pueden ver todos los pedidos de lote relacionados en una única vista que ayuda a determinar el trabajo pendiente por completar.</span><span class="sxs-lookup"><span data-stu-id="00aeb-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="00aeb-110">Un pedido de lote consolidado puede incluir cualquier combinación de las órdenes siguientes:</span><span class="sxs-lookup"><span data-stu-id="00aeb-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="00aeb-111">Un único pedido masivo y varios pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="00aeb-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="00aeb-112">Varios pedidos masivos y varios pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="00aeb-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="00aeb-113">Varios pedidos masivos y un solo pedido empaquetado</span><span class="sxs-lookup"><span data-stu-id="00aeb-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="00aeb-114">Solo pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="00aeb-114">Only packed orders</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]