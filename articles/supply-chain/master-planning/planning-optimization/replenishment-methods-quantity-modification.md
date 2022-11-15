---
title: Métodos de reabastecimiento y modificación de cantidades
description: Este artículo proporciona información acerca de los métodos de reabastecimiento. También explica cómo la cantidad de pedido múltiple de un producto afecta el resultado.
author: t-benebo
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1e0fe6c1f49bc0f6887f1b29118c1fee7a6222f
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739767"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Métodos de reabastecimiento y modificación de cantidades

[!include [banner](../../includes/banner.md)]

Este artículo proporciona información acerca de los métodos de reabastecimiento. También explica cómo la cantidad de pedido múltiple de un producto afecta el resultado.

Los métodos de reabastecimiento también se conocen como métodos de cobertura y métodos de dimensionamiento de lotes.

## <a name="coverage-codes"></a>Códigos de cobertura

La planificación maestra se puede configurar para utilizar varios métodos de reabastecimiento. Los métodos de reabastecimiento son las técnicas que utiliza el sistema para calcular los requisitos de un producto. Los métodos de reabastecimiento se definen mediante códigos de cobertura que puede configurar en el grupo de cobertura o en el producto.

Se pueden utilizar los siguientes códigos de cobertura:

- **Período**: el método de reabastecimiento combina toda la demanda durante un período en un pedido del producto. El pedido se planificará se para el primer día del período y la cantidad satisfará los requisitos netos durante el período establecido. El período comienza con la primera demanda del producto y cubre la longitud definida de tiempo. El período siguiente comenzará con los siguientes requisitos del producto. El código de cobertura *Período* se utiliza a menudo para la extracción de inventario no predecible, productos influenciados por la temporada o productos de alto costo. En la ilustración siguiente se muestra un ejemplo.

    ![Ejemplo de uso del código de cobertura del período.](./media/coverage-code-period.png "Ejemplo de uso del código de cobertura del período")

- **Requisito**: en el método de reabastecimiento, el sistema crea una compra, una transferencia, o un pedido de producción planificados de acuerdo con el requisito del producto. Este método se utiliza para productos costosos que tienen una demanda intermitente. El código de cobertura *Requisito* se usa a menudo para productos configurables o escenarios de fabricación bajo pedido. En la ilustración siguiente se muestra un ejemplo.

    ![Ejemplo de uso del código de cobertura de requisito.](./media/coverage-code-requirement.png "Ejemplo de uso del código de cobertura de requisito")

- **Mín./Máx.** - El método de reabastecimiento se basa en el nivel de inventario. Define la reposición del inventario hasta un nivel específico cuando el nivel disponible previsto está por debajo de un umbral específico. La cantidad de reabastecimiento será la diferencia entre el nivel máximo y el nivel disponible previsto. El código de cobertura *Mínimo/Máximo* se utiliza a menudo para obtener un inventario predecible, productos de alto rendimiento o productos menos costosos. En la ilustración siguiente se muestra un ejemplo.

    ![Ejemplo de uso del código de cobertura de mínimo/máximo.](./media/coverage-code-min-max.png "Ejemplo de uso del código de cobertura de mínimo/máximo")

- **Manual**: en el método de reabastecimiento, el sistema no sugiere pedidos de compra, transferencia o producción para el producto. En cambio, el planificador del producto es responsable de crear los pedidos necesarios para el reabastecimiento del producto. El código de cobertura *Manual* se usa a menudo para productos para los que no se necesitan pedidos planificados generados por el sistema.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Impacto de la cantidad de pedido de la configuración de pedido predeterminada

En la página **Configuración de orden predeterminada** para un producto lanzado, puede especificar cada uno de los siguientes ajustes de cantidad en las fichas depslegables **Orden de compra**, **Inventario** y **Órdenes de venta**. (La ficha desplegable **Inventario** se utiliza tanto para órdenes de transferencia como para órdenes de producción).

- **Múltiple** - Los pedidos planificados serán un múltiplo de esta cantidad.

    Por ejemplo, si el campo **Múltiple** está configurado en *5*, un pedido puede ser por una cantidad de 5, 10, 15, 20, etc.

- **Cantidad de pedido mínima** - Los pedidos planificados no serán inferiores al valor especificado.

    Por ejemplo, si el campo **Cantidad de pedido mínima** está configurado en *10*, se creará un pedido planificado para una cantidad de 10, incluso si solo se requieren cuatro para satisfacer la demanda.

- **Cantidad de pedido máxima** - Los pedidos planificados no serán superiores al valor especificado. Si la demanda es mayor que el valor **Max. ordene la cantidad**, se crearán varios pedidos planificados para cubrirlo.

    Por ejemplo, si el campo **Max. ordene la cantidad** está configurado en *100* y la demanda es 450, se crearán cuatro órdenes previsionales para una cantidad de 100 y una orden previsional para una cantidad de 50.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Ejemplos de reabastecimiento que utilizan los valores Mín. / Máx. código de cobertura

Si no especifica un valor en el campo **Múltiple** para un producto en la página **Configuración de orden predeterminada** y si está utilizando el método de reabastecimiento *Mínimo/máximo*, la planificación maestra reabastecerá el inventario hasta un nivel específico cuando el nivel disponible previsto está por debajo de un umbral específico.

Si define una cantidad múltiple para un producto, el método de reabastecimiento *Mínimo/máximo* cambia su comportamiento y considera el valor **Múltiple**.

En otras palabras, planificación maestra aún repondrá el inventario hasta el nivel máximo definido cuando el nivel disponible previsto sea menor que el nivel mínimo definido. Sin embargo, la cantidad de reabastecimiento debe ser un múltiplo del valor **Múltiple**.

Si la cantidad de reabastecimiento (la diferencia entre el nivel máximo y el nivel disponible previsto) no es un múltiplo de la cantidad múltiple definida, planificación maestra utiliza el primer valor posible que, junto con el nivel disponible previsto, estará por debajo el nivel máximo. Si la suma es menor que el nivel mínimo, planificación maestra utiliza el primer valor que, junto con el disponible previsto, estará por encima del nivel máximo.

Las siguientes subsecciones proporcionan algunos ejemplos que muestran cómo la cantidad de pedido múltiple para un producto afecta el resultado del *Mínimo/máximo* método de reabastecimiento.

### <a name="example-1"></a>Ejemplo 1

Un producto tiene la siguiente configuración:

- **Código de cobertura**: *Mín./Máx*.
- **Mínimo:** *15*
- **Máximo:** *22*
- **Múltiple:** *0*

Hay 10 piezas de inventario disponibles para el producto y no hay otra demanda ni oferta.

Cuando se ejecuta la planificación maestra, se crea una orden planificada de 12 piezas para reabastecer el inventario hasta la cantidad máxima.

### <a name="example-2"></a>Ejemplo 2

Un producto tiene la siguiente configuración:

- **Código de cobertura**: *Mín./Máx*.
- **Mínimo:** *15*
- **Máximo:** *22*
- **Múltiple:** *5*

Hay 10 piezas de inventario disponibles para el producto y no hay otra demanda ni oferta.

Cuando se ejecuta la planificación maestra, se crea una orden planificada de 10 piezas (porque 15 piezas de reabastecimiento más 10 piezas de inventario disponible excederán la cantidad máxima).

### <a name="example-3"></a>Ejemplo 3

Un producto tiene la siguiente configuración:

- **Código de cobertura**: *Mín./Máx*.
- **Mínimo:** *21*
- **Máximo:** *24*
- **Múltiple:** *5*

Hay 10 piezas de inventario disponibles para el producto y no hay otra demanda ni oferta.

Cuando se ejecuta la planificación maestra, se crea la orden planificada de 15 piezas (porque 10 piezas de reabastecimiento más 10 piezas de inventario disponible serán inferiores a la cantidad mínima).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
