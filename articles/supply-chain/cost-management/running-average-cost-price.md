---
title: Ejecución del precio de coste promedio móvil
description: El proceso de cierre de inventario de liquida las transacciones de emisión con las transacciones de recepción en función del método de valoración de inventario seleccionado en el grupo de modelos del artículo. Sin embargo, antes de ejecutar el cierre de inventario, el sistema calcula un precio de coste promedio móvil que se usa normalmente al registrar transacciones de emisión.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d324324312ce9e47b07de8e3de952b8d7c53647
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672189"
---
# <a name="running-average-cost-price"></a>Ejecución del precio de coste promedio móvil

[!include [banner](../includes/banner.md)]

El proceso de cierre de inventario de liquida las transacciones de emisión con las transacciones de recepción en función del método de valoración de inventario seleccionado en el grupo de modelos del artículo. Sin embargo, antes de ejecutar el cierre de inventario, el sistema calcula un precio de coste promedio móvil que se usa normalmente al registrar transacciones de emisión.

El sistema calcula este precio de coste promedio móvil de un artículo mediante la fórmula siguiente:

Precio estimado = (importe físico + importe financiero) ÷ (cantidad física + cantidad financiera)

## <a name="default-item-cost"></a>Coste de elemento predeterminado

El costo de artículo predeterminado para un producto lanzado se puede configurar de una de dos maneras en la página **Detalles del producto publicado**:

- Cree un costo estándar seleccionando **Precio del articulo** en el grupo **Configurar** de la ficha **Administrar costos** del Panel de acciones. Si usa este método, debe usar una versión de cálculo de costos estándar y el costo debe estar activado.
- Defina un precio de costo de artículo predeterminado para un producto lanzado ingresando un valor en el campo **Precio** en la ficha desplegable **Administrar costos**.

Además de ingresar o crear un precio, puede seleccionar la casilla de verificación **Utilizar último precio de coste** en la ficha desplegable **Administrar costos** de la página **Detalles del producto publicado**. En este caso, el sistema actualizará automáticamente el campo **Precio** cuando publica una actualización financiera. Por ejemplo, si registra una factura de orden de compra, el campo se establecerá en el precio de compra de esa factura.

Si tiene un precio de coste en una versión de gestión de costes activa e introduce un precio en la ficha desplegable **Administrar costos**, el sistema utilizará el precio de la versión de gestión de costes activa antes de utilizar el precio definido en la ficha rápida **Administrar costos**.

## <a name="using-the-running-average-cost-price"></a>Uso del precio de coste promedio móvil

En la tabla siguiente se muestra cuándo el sistema registra transacciones de inventario mediante el precio de coste promedio móvil y cuándo usa el precio de coste definido en el registro maestro de artículos.

| Condición | El sistema usa el precio de coste promedio móvil estimado | El sistema usa el precio de coste de artículo predeterminado |
| --- | --- | --- |
| Tanto el numerador\* como el denominador\*\* son positivos. | Sí | No |
| El numerador\*, el denominador\*\* o ambos son negativos. | No | Sí |
| El denominador\*\* es 0 (cero). | No | Sí |

\* Numerador = (Importe físico + Importe financiero)  
\*\* Denominador = (Cantidad física + Cantidad financiera)

> [!NOTE]
> Nota: Si la opción **Incluir valor físico en coste** no se selecciona para un artículo, el sistema usa 0 (cero) para el importe y la cantidad físicos. Para obtener más información sobre esta opción, vea [Incluir valor físico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evitar amplificación de precio

En algunas ocasiones, el sistema asigna el precio a varias emisiones antes de tener bastantes recibos en los que basar el precio. Este escenario puede hacer que las estimaciones del precio de coste promedio móvil se inflen excesivamente. Sin embargo, existen pasos para evitar la amplificación de precios o para reducir su impacto cuando se produzca.

**Escenario**: las siguientes transacciones se producen para un artículo para el que ha seleccionado la opción **Incluir valor físico en coste**:

1. Financieramente recibe una cantidad de 100 a 100,00 USD.
2. Emite financieramente una cantidad de 200.
3. Financieramente recibe una cantidad de 101 a 202,00 USD.

Cuando se examina el precio de coste promedio móvil estimado para el artículo, se espera un precio de coste de 1,51 dólares. En su lugar, se detecta un promedio móvil estimado de 102,00 dólares, basado en la siguiente fórmula:

Precio estimado = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

Esta ampliación del precio ocurre porque, cuando en el paso 2 se han emitido financieramente 200 artículos, el sistema se ve forzado a determinar el precio de 100 de los artículos antes de tener los recibos correspondientes. Esta situación genera inventario negativo. El sistema estima a continuación un precio unitario de 1,00 USD, como se podría esperar. Sin embargo, cuando llegan los 100 recibos correspondientes, se encuentran en un precio unitario de 2,00 USD cada uno.

> [!NOTE]
> Aunque las emisiones provocan un inventario negativo, el inventario es positivo cuando se calcula el precio de emisión. Por tanto, el precio de coste promedio móvil se usa en lugar del precio del maestro de artículos. En este momento, el sistema tiene una compensación de valor de inventario de 100,00 dólares. Aunque la compensación se ha creado para 100 artículos, donde había una compensación unitaria de 1,00 dólar cada uno, ahora solo hay una unidad en el inventario. Por tanto, la compensación de 100,00 dólares se asigna a esta única unidad. El resultado es el precio de coste estimado excesivo.
>
> Para comparar, tenga en cuenta que si los pasos 2 y 3 se invierten en el escenario, se emitirán 200 artículos a un precio unitario de 1,51 dólares, y quedará una unidad por un precio unitario de 1,51 dólares. Puesto que el escenario de amplificación de precios puede ocurrir cuando haya un inventario negativo implicado, es difícil de evitar en los casos siguientes:
>
> - Se deben estimar los precios de emisión según el valor y la cantidad disponibles.
> - Se deben ajustar el valor y la cantidad disponibles según emisiones y recibos.
> - El modelo empresarial permite enviar o determinar el precio de más unidades de las que se dispone.
> - Se debe aceptar cualquier valor y cantidad de recepción que se le haya enviado.

No obstante, si el modelo empresarial permite las siguientes prácticas, pueden ayudarle a evitar las cantidades negativas que hacen posible el escenario de amplificación de precios:

- Si selecciona la opción **Incluir valor físico en coste** para un artículo, desactive la casilla **Inventario negativo físico** en la página **Grupos de modelos de artículo**.
- Si **no** selecciona la opción **Incluir valor físico en coste** para un artículo, desactive la casilla **Inventario negativo financiero** en la página **Grupos de modelos de artículo**.

Además, tenga en cuenta también que la compensación máxima del valor de inventario físico está limitada por el número de transacciones físicas y las diferencias entre precios físicos y financieros. Siempre que todas las transacciones físicas se actualicen financieramente, el valor físico no puede llegar a niveles extremos. Por último, tenga en cuenta que el efecto de amplificación se reduce significativamente cuando la compensación acumulada se extiende a varias unidades disponibles, en lugar de solo una.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Evite un precio de costo cero en los problemas

Cuando la opción **Incluir valor físico** no está seleccionada en la página **Grupo de modelo de artículo**, una salida del inventario puede tener un precio de costo cero si no hay recibos actualizados financieramente en el inventario. Para ayudar a evitar este escenario, considere las opciones siguientes:

- Seleccione la opción **Incluir valor físico** en la página **Grupo de modelos de artículo**. Esta opción evitará un precio de costo cero en una emisión, siempre que el recibo esté físicamente actualizado. Si no permite el inventario físico negativo, los problemas calcularán el promedio móvil de las transacciones actualizadas físicamente.
- Cree un precio de costo de artículo predeterminado activando una versión de gestión de costos que tenga un costo estándar, o ingrese el precio en la ficha rápida **Administrar costos** de la página **Detalles del producto publicado**. Esta opción es mejor cuando la opción **Incluir valor físico** no está seleccionada en el **Grupo de modelo de artículo** porque el sistema siempre tendrá un precio alternativo para usar.
- Seleccione la opción **Utilizar último precio de coste** en la ficha rápida **Administrar costos** de la página **Detalles del producto publicado**. Esta opción mantendrá el campo **Precio** actualizado cada vez que actualice financieramente un recibo. Si selecciona esta opción, pero no ingresa un precio predeterminado ni activa un costo en una versión de cálculo de costos estándar, aún puede tener un costo cero en una emisión.

Si tiene transacciones de emisión que tienen costo cero, el proceso *Cierre y ajuste de inventario* corregirá el precio de costo creando un ajuste después de que los recibos se actualicen financieramente. Tenga en cuenta que el período financiero en el que se produce esta actualización puede diferir del período financiero en el que se recibieron o emitieron físicamente los artículos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
