---
title: Pedidos de lote consolidados
description: Este artículo describe el concepto de pedidos de lote consolidados.
author: johanhoffmann
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
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e15c7def40abdccc7686b0eb34448c951402809
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570330"
---
# <a name="consolidated-batch-orders"></a>Pedidos de lote consolidados

[!include [banner](../includes/banner.md)]

Este artículo describe el concepto de pedidos de lote consolidados.

Un artículo masivo producido se considera artículo principal, mientras que un artículo empaquetado se considera artículo secundario. La relación entre el artículo masivo y el artículo empaquetado se expresa mediante una conversión de artículos masivos. Esta conversión de artículos masivos se define en el artículo masivo en sí.  

Los artículos empaquetados se pueden empaquetar en contenedores de un solo tamaño o de varios tamaños, que se consideran como una sola unidad. Al consolidar los pedidos para un artículo masivo, se pueden ver todos los pedidos de lote relacionados en una única vista que ayuda a determinar el trabajo pendiente por completar.  

Un pedido de lote consolidado puede incluir cualquier combinación de las órdenes siguientes:

-   Un único pedido masivo y varios pedidos empaquetados
-   Varios pedidos masivos y varios pedidos empaquetados
-   Varios pedidos masivos y un solo pedido empaquetado
-   Solo pedidos empaquetados






[!INCLUDE[footer-include](../../includes/footer-banner.md)]