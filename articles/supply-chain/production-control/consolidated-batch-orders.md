---
title: Pedidos de lote consolidados
description: "Este artículo describe el concepto de pedidos de lote consolidados."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 45c83752b4dc50a615e3bb64320cb22b7fc6dec0
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="consolidated-batch-orders"></a>Pedidos de lote consolidados

[!include[banner](../includes/banner.md)]


Este artículo describe el concepto de pedidos de lote consolidados.

Un artículo masivo producido se considera artículo principal, mientras que un artículo empaquetado se considera artículo secundario. La relación entre el artículo masivo y el artículo empaquetado se expresa mediante una conversión de artículos masivos. Esta conversión de artículos masivos se define en el artículo masivo en sí.  

Los artículos empaquetados se pueden empaquetar en contenedores de un solo tamaño o de varios tamaños, que se consideran como una sola unidad. Al consolidar los pedidos para un artículo masivo, se pueden ver todos los pedidos de lote relacionados en una única vista que ayuda a determinar el trabajo pendiente por completar.  

Un pedido de lote consolidado puede incluir cualquier combinación de las órdenes siguientes:

-   Un único pedido masivo y varios pedidos empaquetados
-   Varios pedidos masivos y varios pedidos empaquetados
-   Varios pedidos masivos y un solo pedido empaquetado
-   Solo pedidos empaquetados





