---
title: Tolerancia al retraso (días negativos)
description: Este artículo proporciona información sobre el cálculo de la tolerancia de demora y cómo afecta la creación de órdenes planificadas en Planning Optimization.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: fa4d2d1506546cacf5f9a7ec936f17601c5727d2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335387"
---
# <a name="delay-tolerance-negative-days"></a>Tolerancia al retraso (días negativos)

[!include [banner](../../includes/banner.md)]

La funcionalidad de tolerancia de retardo permite a Planning Optimization considerar el valor **Días negativos** que se establece para los grupos de cobertura, cobertura de artículos y/o planes maestros. Se utiliza para extender el período de tolerancia de demora que se aplica durante la planificación maestra. De esta manera, puede evitar la creación de nuevos pedidos de suministro si el suministro existente podrá cubrir la demanda después de un breve retraso. El propósito de la funcionalidad es determinar si tiene sentido crear un nuevo pedido de suministro para una demanda determinada.

## <a name="turn-delay-tolerance-features-on-or-off"></a>Activar o desactivar las características de tolerancia

Para que esta funcionalidad de tolerancia de retraso esté disponible en su sistema, vaya a [Gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las siguientes funciones:

- *Días negativos para la optimización de la planificación* – Esta característica habilita la configuración de días negativos para grupos de cobertura y cobertura de artículos. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar.
- *Automatización de suministro bajo pedido* – Esta característica habilita la configuración de días negativos para planes maestros. (Para más información, vea [Automatización de suministro bajo pedido](../make-to-order-supply-automation.md)).

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerancia de retraso en la optimización de la planificación

La tolerancia de demora representa la cantidad de días más allá del tiempo de entrega que está dispuesto a esperar antes de ordenar un nuevo reabastecimiento cuando el suministro existente ya está planeado. La tolerancia de demora se define mediante el uso de días calendario, no días hábiles.

En el momento de la planificación maestra, cuando el sistema calcula la tolerancia de demora, considera la configuración **Días negativos**. Puede establecer el valor **Días negativos** en la página **Grupos de cobertura** o en la página **Cobertura de artículos** o la página **Planes maestros**. Si se asignan días negativos en más de un nivel, el sistema aplica la siguiente jerarquía para decidir qué configuración usar:

- Si se habilitan días negativos en la página **Planes maestros**, esa configuración anula todas las demás configuraciones de días negativos cuando se ejecuta el plan.
- Si se configuran días negativos en la página **Cobertura de artículos**, esa configuración anula la configuración del grupo de cobertura.
- Los días negativos que se configuran en la página **Grupos de cobertura** se aplica solo si los días negativos no se han configurado para un artículo o plan relevante.

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
