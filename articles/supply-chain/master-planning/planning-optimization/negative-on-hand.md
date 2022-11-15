---
title: Planificación con cantidades negativas disponibles
description: Este artículo explica cómo se maneja el negativo disponible.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b4fc8b37fd800e3b4652513f150f9806bf1d5d67
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741132"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planificación con cantidades negativas disponibles

[!include [banner](../../includes/banner.md)]

Si el sistema muestra una cantidad agregada negativa disponible, el motor de planificación trata la cantidad como 0 (cero) para ayudar a evitar el exceso de oferta. Así es como funciona esta funcionalidad:

1. La planificación maestra agrega cantidades disponibles en el nivel más bajo de dimensiones de cobertura. (Por ejemplo, si *ubicación* no es una dimensión de cobertura, la planificación maestra agrega cantidades disponibles en el nivel *almacén*).
1. Si la cantidad disponible en el nivel más bajo de las dimensiones de cobertura es negativa, el sistema supone que la cantidad disponible es realmente 0 (cero).

> [!IMPORTANT]
> El sistema de planificación solo puede ser tan preciso como los datos de entrada. Si los datos de entrada son inexactos, los registros negativos disponibles indicarán que la información de inventario en Microsoft Dynamics 365 Supply Chain Management no está sincronizada con el mundo real. Por lo tanto, el resultado de la planificación será defectuoso. Para obtener un resultado de planificación preciso, debe minimizar la cantidad de registros que muestran una cantidad disponible negativa.

## <a name="example-1"></a>Ejemplo 1

El almacén 13 se configura de la siguiente manera:

- **Código de cobertura:** Mín./Máx.
- **Mínimo:** 15 unidades (uds.)
- **Máximo:** 25 uds.

El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:

- **Sitio 1, almacén 13, ubicación 1:** 20 uds.
- **Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.

Por lo tanto, la cantidad total disponible para el almacén 13 es de 12 unidades. (= 20 uds. &minus; 8 uds.).

En este caso, el motor de planificación utiliza una cantidad total disponible de 12 unidades. para almacén 13.

El resultado es un pedido planificado de 13 uds. (= 25 uds. &minus; 12 uds.) para rellenar el almacén 13 desde 12 uds. a 25 unidades.

## <a name="example-2"></a>Ejemplo 2

El almacén 13 se configura de la siguiente manera:

- **Código de cobertura:** Mín./Máx.
- **Mínimo:** 15 uds.
- **Máximo:** 25 uds.

El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:

- **Sitio 1, almacén 13, ubicación 1:** 4 uds.
- **Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.

Por lo tanto, la cantidad total disponible para el almacén 13 es de &minus;4 unidades. (= 4 uds. &minus; 8 uds.). En otras palabras, es menor de 0 (cero).

En este caso, el motor de planificación supone que la cantidad disponible para el almacén 13 es 0 unidades. en lugar de &minus;4 uds.

El resultado es un pedido planificado de 25 uds. (= 25 uds. &minus; 0 uds.) para rellenar el almacén 13 desde 0 uds. a 25 unidades.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planificación cuando hay una reserva contra el inventario disponible negativo

Si ajusta el inventario mientras existen reservas físicas, puede provocar una situación en la que un pedido se reserve físicamente frente a un inventario negativo. En este caso, debido a que existe una reserva física, debe tener suministro para cubrir la cantidad reservada. Por lo tanto, se requiere el reabastecimiento, por lo que el sistema creará un pedido planificado para reabastecer la cantidad que no se pudo cubrir con el inventario disponible existente o lo cubrirá con un pedido existente para el artículo.

En el siguiente ejemplo se muestra este escenario.

### <a name="example"></a>Ejemplo

El sistema se configura de la siguiente manera:

- El producto *FG* existe y tiene *10* unidades de inventario disponible.
- La configuración del producto permite un inventario físico negativo.
- Existe un pedido de ventas por una cantidad de *10* unidades del producto *FG*.
- La cantidad del pedido de ventas se reserva físicamente contra el inventario disponible existente.

Luego ajuste la cantidad del producto *FG* de modo que el inventario disponible se convierte en 5. Debido a que el inventario de productos disponibles es 5, la cantidad del pedido de ventas ahora se reserva para la cantidad que no está disponible (sería similar si el producto disponible fuera 0, en cuyo caso el pedido de ventas se reservaría para el inventario negativo). Si ejecuta la planificación maestra ahora, se creará un pedido planificado de la cantidad 5 para *FG* para suministrar el pedido de cliente, porque la optimización maestra siempre utilizará el suministro existente o creará un nuevo pedido planificado para suministrar la reserva física.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
