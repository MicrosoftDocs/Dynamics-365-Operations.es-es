---
title: Cantidad de inventario no actualizada debido a transacciones insuficientes
description: La cantidad de inventario -1% no se puede actualizar porque no hay suficientes transacciones de inventario para el artículo %2 que tengan las dimensiones especificadas.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477475"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>El sistema no puede actualizar la cantidad de inventario debido a transacciones insuficientes

## <a name="symptoms"></a>Síntomas

Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas. Recibirá el siguiente mensaje de error:

> Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2 con dimensiones Tamaño=%3, Color=%4, Adiciones=%5, Sitio=%6, Almacén=%7, Ubicación=%8, Estado de inventario=Disponible, Matrícula=%9, Número de lote=%10 para ID de referencia %11 en ID de lote %12.

## <a name="resolution"></a>Resolución

Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad. Por ejemplo, estas transacciones pueden abrir pedidos de calidad, registros de bloqueo de inventario o pedidos de salida.
