---
title: No se pudo liberar el pedido de venta con las operaciones de almacén de salida
description: Hay varias razones por las que puede recibir un mensaje de error que indique que no se pudo liberar un pedido de cliente. Esta página explica por qué y cómo mitigar el problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477539"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>No se pudo liberar el pedido de venta con las operaciones de almacén de salida

## <a name="symptoms"></a>Síntomas

Al trabajar con operaciones de almacén de salida, es posible que reciba el siguiente mensaje de error:

> No se pudo liberar el pedido de ventas.

## <a name="cause"></a>Causa

Este problema puede ocurrir por varias razones. Por ejemplo, el pedido está en espera de gestión de crédito y no se pueden crear envíos hasta que se ingrese una dirección postal válida para todas las líneas de ventas asociadas con un pedido. Alternativamente, existe una retención de pedido que debe abordarse antes de que el pedido pueda enviarse al almacén. Esta retención puede ser específica de un pedido o puede estar en la cuenta del cliente.

## <a name="resolution"></a>Resolución

Agregue o actualice la dirección en la orden de venta y las líneas de orden y luego libere la orden en el almacén. Los pedidos se pueden enviar al almacén solo si tienen una dirección de entrega válida (según la configuración del formato de dirección en el módulo **Administración de la organización**).

Investigue la orden retenida y resuelva los problemas. Luego elimine la retención del pedido o del cliente y libere el pedido al almacén.
