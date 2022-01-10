---
title: El sistema no puede encontrar un pedido planificado durante las operaciones en varios pedidos
description: Se produce un error "El pedido planificado no existe" cuando realiza operaciones en varios pedidos planificados y al menos dos pedidos pertenecen al mismo ID de artículo.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920815"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>El sistema no puede encontrar un pedido planificado durante las operaciones en varios pedidos

Código de error: SYS24774

## <a name="symptoms"></a>Síntomas

Recibe el siguiente mensaje de error cuando intenta realizar una operación en varios pedidos planificados al mismo tiempo y al menos dos de los pedidos pertenecen al mismo identificador de artículo. Por ejemplo, el error puede ocurrir cuando los pedidos se firman o se cambia su tipo de pedido.

> El pedido planificado %1 no existe.

## <a name="cause"></a>Causa

Cuando el sistema reafirma o cambia el tipo de pedido, debe reconsiderar los pedidos planificados existentes para el artículo, para asegurarse de que el suministro planificado coincide con la demanda y el suministro existente. Como parte de este proceso, el sistema vuelve a crear pedidos planificados para el artículo. Por lo tanto, la segunda orden previsional que el sistema espera procesar ya no existe.

## <a name="workaround"></a>Solución alternativa

Apruebe los pedidos antes de procesarlos. De esta forma, los pedidos no se eliminarán cuando el sistema procese el primer pedido del artículo.
