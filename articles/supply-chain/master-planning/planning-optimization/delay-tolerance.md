---
title: Tolerancia al retraso (días negativos)
description: Este artículo proporciona información sobre el cálculo de la tolerancia de demora y cómo afecta la creación de órdenes planificadas en Planning Optimization.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4bd6042f9dd33ba15773b251911e965cb870c5aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865132"
---
# <a name="delay-tolerance-negative-days"></a>Tolerancia al retraso (días negativos)

[!include [banner](../../includes/banner.md)]

La funcionalidad de tolerancia de retardo permite a Planning Optimization considerar el valor **Días negativos** que se establece para los grupos de cobertura. Se utiliza para extender el período de tolerancia de demora que se aplica durante la planificación maestra. De esta manera, puede evitar la creación de nuevos pedidos de suministro si el suministro existente podrá cubrir la demanda después de un breve retraso. El propósito de la funcionalidad es determinar si tiene sentido crear un nuevo pedido de suministro para una demanda determinada.

## <a name="turn-on-the-feature-in-your-system"></a>Activar la función en el sistema

Para que esta funcionalidad de tolerancia de retraso esté disponible en su sistema, vaya a [Gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la función *Días negativos para Optimización de planificación*.

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerancia de retraso en la optimización de la planificación

La tolerancia de demora representa la cantidad de días más allá del tiempo de entrega que está dispuesto a esperar antes de ordenar un nuevo reabastecimiento cuando el suministro existente ya está planeado. La tolerancia de demora se define mediante el uso de días calendario, no días hábiles.

En el momento de la planificación maestra, cuando el sistema calcula la tolerancia de demora, considera la configuración **Días negativos**. Puede establecer el valor **Días negativos** en la página **Grupos de cobertura** o en la página **Cobertura de artículos**.

El sistema vincula el cálculo de la tolerancia de retardo a la *fecha de reabastecimiento más temprana*, que equivale a la fecha de hoy más el plazo de entrega. La tolerancia de retardo se calcula utilizando la siguiente fórmula, donde *max ()* encuentra el mayor de dos valores:

*max (fecha de reabastecimiento más temprana, fecha de vencimiento de la demanda)* - *Fecha de vencimiento de la demanda* + *Días negativos*

Esta fórmula garantiza que la planificación maestra no cree nuevos pedidos de suministro cuando existe suficiente suministro durante el tiempo de entrega del producto.

> [!NOTE]
> El cálculo de la tolerancia de retraso en la Optimización de planificación siempre utiliza el cálculo de días negativos dinámicos de la planificación maestra incorporada. El valor **Utilice días negativos dinámicos** de la paǵina **Parámetros de planificación maestra** no tiene ningún efecto sobre este comportamiento.

Si el suministro existente implica un retraso en la demanda menor o igual que la tolerancia de retraso calculada, la optimización de planificación relaciona el suministro existente con la demanda. En algunos casos, es mejor retrasar la demanda que terminar con un exceso de oferta.

Las siguientes subsecciones proporcionan ejemplos que muestran cómo la tolerancia de demora afecta la creación de órdenes planificadas en Planning Optimization.

### <a name="example-1"></a>Ejemplo 1

Un producto tiene la siguiente configuración:

- **Plazo:** *10*
- **Días negativos:** *2*

Existe la siguiente oferta y demanda para el producto:

- **Demanda para hoy:** Un pedido de cliente por una cantidad de 10
- **Suministro en 12 días:** Una orden de compra por una cantidad de 10

La oferta existente puede cubrir la demanda en un plazo de 12 días, y ese período es igual a la tolerancia de demora. Por lo tanto, cuando se ejecuta la planificación maestra, no se crean órdenes previsionales.

### <a name="example-2"></a>Ejemplo 2

Un producto tiene la siguiente configuración:

- **Plazo:** *10*
- **Días negativos:** *0*

Existe la siguiente oferta y demanda para el producto:

- **Demanda para hoy:** Un pedido de cliente por una cantidad de 10
- **Suministro en 12 días:** Una orden de compra por una cantidad de 10

La oferta existente puede cubrir la demanda solo después de 12 días. Sin embargo, la tolerancia de retraso es de 10 días. Por lo tanto, cuando se ejecuta la planificación maestra, se crea una orden previsional para una cantidad de 10.

### <a name="example-3"></a>Ejemplo 3

Un producto tiene la siguiente configuración:

- **Plazo:** *10*
- **Días negativos:** *2*

Existe la siguiente oferta y demanda para el producto:

- **Demanda en 11 días:** Un pedido de cliente por una cantidad de 10
- **Suministro en 14 días:** Una orden de compra por una cantidad de 10

La oferta existente puede cubrir la demanda solo después de tres días. Sin embargo, la tolerancia de retraso es de dos días. (En este caso, la tolerancia de demora incluye solo los dos días negativos. La fecha de demanda no se incluye porque es posterior al plazo de entrega del producto). Por lo tanto, cuando se ejecuta la planificación maestra, se crea un pedido planificado para una cantidad de 10.
