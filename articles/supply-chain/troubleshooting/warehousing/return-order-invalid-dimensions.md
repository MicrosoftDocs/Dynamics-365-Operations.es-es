---
title: No se puede crear una línea de carga debido a dimensiones de inventario no válidas
description: Al intentar enviar un pedido de devolución al almacén, es posible que reciba un error sobre dimensiones de inventario no válidas. Elimínelos de la línea de pedido.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119221"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>No se puede crear una línea de carga para el pedido de ventas de devolución debido a dimensiones de inventario no válidas

## <a name="symptoms"></a>Síntomas

Al intentar enviar un pedido de devolución al almacén, puede recibir el siguiente mensaje de error:

> No puede crear una línea de carga para esta línea de pedido porque contiene dimensiones de inventario que no son válidas. No puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión de ubicación en la jerarquía de reservas. Elimine las dimensiones no válidas de la línea de pedido.

## <a name="resolution"></a>Resolución

Desafortunadamente, el producto no admite el procesamiento de carga para un proceso de devolución de ventas. Por lo tanto, no puede enviar el pedido de devolución al almacén.

En las transacciones de pedido de venta, no puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión **Ubicación** en la jerarquía de reservas. La resolución es quitar las dimensiones no válidas de la línea de pedido.
