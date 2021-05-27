---
title: El informe de costes indirectos en curso incluye pedidos de producción eliminados
description: El informe de costes indirectos en curso presenta información sobre los pedidos de producción que se procesaron parcialmente y luego se eliminaron.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026882"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>El informe de costes indirectos en curso incluye pedidos de producción eliminados

Número de KB: 4612748

## <a name="symptoms"></a>Síntomas

El informe **Costes indirectos en curso** presenta información sobre los pedidos de producción que se procesaron parcialmente y luego se eliminaron.

## <a name="resolution"></a>Resolución

Cuando revierte un pedido de producción, también revierte todas las transacciones de ese pedido de producción. Cuando elimina el pedido de producción, las tablas del libro mayor auxiliar y la contabilidad general conservan todas las transacciones relacionadas con él. Los informes mostrarán las transacciones en las tablas del libro mayor auxiliar. Para el pedido de producción específico, el valor neto debe ser 0,00.
