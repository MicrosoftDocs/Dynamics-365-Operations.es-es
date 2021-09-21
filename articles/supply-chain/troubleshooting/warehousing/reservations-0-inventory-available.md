---
title: No se pueden hacer reservas de inventario porque 0,00 están disponibles en el inventario
description: Recibe un error de que el sistema no puede hacer reservas porque solo hay 0,00 en el inventario. Este problema probablemente se deba al trabajo abierto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477555"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>El sistema no puede hacer reservas porque 0,00 están disponibles en el inventario

## <a name="symptoms"></a>Síntomas

Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas. Recibirá el siguiente mensaje de error:

> Sitio físico disponible=%1, Almacén=%2, Estado de inventario=Disponible, Número de lote=%3, Propietario=%4: %5 no se puede reservar porque solo 0.00 están disponibles en el inventario.

## <a name="resolution"></a>Resolución

Este problema probablemente se deba al trabajo abierto. Completar el trabajo o recibir sin creación de trabajo. Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad. Por ejemplo, estas transacciones pueden ser pedidos de calidad, registros de bloqueo de inventario o pedidos de salida abiertos.
