---
title: La inversión de notificar como terminado crea una transacción abierta inesperada
description: La inversión de las notificaciones como terminado que tienen marcas crea una transacción abierta en la que la cantidad invertida tiene las mismas dimensiones de inventario que la transacción invertida.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026893"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>La inversión de notificar como terminado crea una transacción abierta inesperada

Número de KB: 4612469

## <a name="symptoms"></a>Síntomas

Si invierte las notificaciones como terminado que tienen marcas, el sistema crea una transacción abierta en la que la cantidad invertida tiene las mismas dimensiones de inventario que la transacción invertida.

## <a name="resolution"></a>Resolución

Cuando invierte una operación de notificación como terminado, la dimensión de inventario se inicializa desde el diario de producción. Por lo tanto, obtiene el número de lote. Debido a la marca, las transacciones de pedidos de ventas heredarán el número de lote.

La dimensión se puede restablecer cuando se publica la notificación como terminado.
