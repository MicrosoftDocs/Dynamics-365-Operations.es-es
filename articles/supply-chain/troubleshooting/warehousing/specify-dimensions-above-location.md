---
title: No se puede liberar una carga para una cantidad parcial con la jerarquía por encima del lote
description: Cuando se utiliza un artículo con la jerarquía de reserva de lote anterior, las líneas de carga deben especificar dimensiones por encima de la ubicación para que se asigne el inventario.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477499"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>No se puede liberar una carga para una cantidad parcial con la jerarquía de reservas por encima del lote

## <a name="symptoms"></a>Síntomas

Cuando utiliza un artículo que tiene una jerarquía de reserva *batch-above* el comando **Liberar al almacén** en la página **Banco de trabajo de planificación de carga** no funcionará si intenta liberar una carga para una cantidad parcial. Podría recibir el siguiente mensaje de error:

> Para ser asignado a la ola, las líneas de carga deben especificar las dimensiones por encima de la ubicación. Para asignar estas dimensiones, reserve y vuelva a crear la línea de carga.

Sin embargo, si utiliza un artículo que tiene una jerarquía de reserva *batch-below*, puede liberar una carga para una cantidad parcial desde la página **Banco de trabajo de planificación de carga**.

## <a name="cause"></a>Causa

Cuando una dimensión está por encima de la dimensión **Ubicación** en la jerarquía de reservas, debe especificarse antes del lanzamiento al almacén. El inventario se puede asignar correctamente solo si no hay espacios en las dimensiones anteriores a la ubicación.

## <a name="resolution"></a>Resolución

Asegúrese de que todas las dimensiones por encima de **Localización** han sido asignadas reservando y recreando la línea de carga.
