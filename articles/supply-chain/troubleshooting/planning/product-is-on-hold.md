---
title: El producto está en espera para las transacciones
description: Después de confirmar los pedidos de planificación, recibe un mensaje de error que indica que un artículo está en espera para transacciones.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301288"
---
# <a name="product-is-on-hold-for-transactions"></a>El producto está en espera para las transacciones

Código de error: SYS13295

## <a name="symptoms"></a>Síntomas

Después de confirmar pedidos planificados, recibe el siguiente mensaje de error:

> El artículo %1 está en bloqueo para transacciones en %2.

## <a name="cause"></a>Causa

Al describir los artículos bloqueados, el sistema utiliza los términos *obstruido*, *detenido* y *en espera* indistintamente. Este error significa que el elemento está configurado como **Detenido** en su configuración de orden predeterminada.

Si un artículo está bloqueado y lo agrega a una orden de compra o una línea de orden de venta, recibirá un mensaje de advertencia. Si un artículo está bloqueado, las transacciones de inventario relacionadas con la línea del pedido de compra o ventas no se pueden modificar (por ejemplo, al registrar un albarán o una factura). Puede bloquear un artículo adquirido y venderlo de manera simultánea. En ese caso, la casilla **Detenido** se selecciona en un pedido de compra, pero el artículo no se bloquea en el inventario ni en el pedido de ventas.

Estas son algunas de las condiciones que pueden hacer que se bloquee la venta de un número de artículo:

- El artículo aún está en desarrollo o fabricación. Por lo tanto, no desea que se venda ni se reserve.
- Ha recibido muchos artículos defectuosos y los defectos deben corregirse antes de que el artículo pueda venderse.

En casos como este, puede bloquear el artículo hasta que se resuelva el problema.

Si un artículo está bloqueado y crea una línea de pedido de devolución, recibe un mensaje. No puede bloquear una serie o un lote de un artículo. Si debe bloquear partes del artículo, puede hacerlo moviendo el inventario o bloqueando todas las existencias del artículo durante este período.

## <a name="resolution"></a>Resolución

- Abra la página **Configuración de orden predeterminada** del elemento y borre la casilla **Detenido**.
