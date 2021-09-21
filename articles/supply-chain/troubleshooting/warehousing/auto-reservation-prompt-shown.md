---
title: El mensaje de reserva automática se muestra con el inventario disponible
description: Cuando usa un artículo en un almacén donde los procesos de almacén no están habilitados, se muestra el mensaje de reserva automática. Especifique todas las dimensiones arriba de Ubicación.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477561"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>El mensaje de reserva automática de número de lote se muestra incluso con el inventario disponible

## <a name="symptoms"></a>Síntomas

Cuando usa un artículo que tiene una jerarquía de reservas *batch-above* en un almacén que no ha habilitado los procesos de almacén y la reserva automática está habilitada, se muestra la solicitud de reserva automática para un número de lote incluso si solo hay un lote disponible para el picking.

Sin embargo, cuando usa el mismo artículo en un almacén donde los procesos de almacén están habilitados, no se muestra el mensaje de reserva automática.

## <a name="resolution"></a>Resolución

Si una jerarquía de reserva se define como *batch-above* o *serial-above*, la dimensión referenciada (**Número de lote** o **Número de serie**) debe especificarse siempre bajo pedido. Es posible que los procesos de almacén puedan completar la información si se dispone de un solo lote o número de serie. Sin embargo, debido a que el almacén no está habilitado para los procesos de almacén, el usuario siempre debe especificar todas las dimensiones sobre **Ubicación**.
