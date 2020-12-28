---
title: Pedidos de lote consolidados
description: Este artículo describe el concepto de pedidos de lote consolidados.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: faeb90aa3366a58b746c0b397dd950bfb8c9024f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437021"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="cc951-103">Pedidos de lote consolidados</span><span class="sxs-lookup"><span data-stu-id="cc951-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc951-104">Este artículo describe el concepto de pedidos de lote consolidados.</span><span class="sxs-lookup"><span data-stu-id="cc951-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="cc951-105">Un artículo masivo producido se considera artículo principal, mientras que un artículo empaquetado se considera artículo secundario.</span><span class="sxs-lookup"><span data-stu-id="cc951-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="cc951-106">La relación entre el artículo masivo y el artículo empaquetado se expresa mediante una conversión de artículos masivos.</span><span class="sxs-lookup"><span data-stu-id="cc951-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="cc951-107">Esta conversión de artículos masivos se define en el artículo masivo en sí.</span><span class="sxs-lookup"><span data-stu-id="cc951-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="cc951-108">Los artículos empaquetados se pueden empaquetar en contenedores de un solo tamaño o de varios tamaños, que se consideran como una sola unidad.</span><span class="sxs-lookup"><span data-stu-id="cc951-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="cc951-109">Al consolidar los pedidos para un artículo masivo, se pueden ver todos los pedidos de lote relacionados en una única vista que ayuda a determinar el trabajo pendiente por completar.</span><span class="sxs-lookup"><span data-stu-id="cc951-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="cc951-110">Un pedido de lote consolidado puede incluir cualquier combinación de las órdenes siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc951-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="cc951-111">Un único pedido masivo y varios pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="cc951-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="cc951-112">Varios pedidos masivos y varios pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="cc951-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="cc951-113">Varios pedidos masivos y un solo pedido empaquetado</span><span class="sxs-lookup"><span data-stu-id="cc951-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="cc951-114">Solo pedidos empaquetados</span><span class="sxs-lookup"><span data-stu-id="cc951-114">Only packed orders</span></span>




