---
title: "Ejecución del precio de coste promedio móvil"
description: "El proceso de cierre de inventario de liquida las transacciones de emisión con las transacciones de recepción en función del método de valoración de inventario seleccionado en el grupo de modelos del artículo. Sin embargo, antes de ejecutar el cierre de inventario, el sistema calcula un precio de coste promedio móvil que se usa normalmente al registrar transacciones de emisión."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Ejecución del precio de coste promedio móvil

El proceso de cierre de inventario de liquida las transacciones de emisión con las transacciones de recepción en función del método de valoración de inventario seleccionado en el grupo de modelos del artículo. Sin embargo, antes de ejecutar el cierre de inventario, el sistema calcula un precio de coste promedio móvil que se usa normalmente al registrar transacciones de emisión.

El sistema estima este precio de coste promedio móvil de un artículo mediante la fórmula siguiente: Precio estimado = (Importe físico + Importe financiero) ÷ (Cantidad física + Cantidad financiera)

## <a name="using-the-running-average-cost-price"></a>Uso del precio de coste promedio móvil
En la tabla siguiente se muestra cuándo el sistema registra transacciones de inventario mediante el precio de coste promedio móvil y cuándo usa el precio de coste definido en el registro maestro de artículos.

| Condición                                               | El sistema usa el precio de coste promedio móvil estimado | El sistema usa el precio de coste definido en el maestro de artículos |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Tanto el numerador\* como el denominador\*\* son positivos.  | Sí                                                      | No                                                                |
| El numerador\*, el denominador\*\* o ambos son negativos. | No                                                       | Sí                                                               |
| El denominador\*\* es 0 (cero).                        | No                                                       | Sí                                                               |

\* Numerador = (Importe físico + Importe financiero) \*\* Denominador = (Cantidad física + Cantidad financiera) **Nota:** Si la opción **Incluir valor físico en coste** no está seleccionada para un artículo, el sistema usa 0 (cero) tanto para el importe físico como para la cantidad física. Para obtener más información sobre esta opción, vea [Incluir valor físico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evitar amplificación de precio
En algunas ocasiones, el sistema asigna el precio a varias emisiones antes de tener bastantes recibos en los que basar el precio. Este escenario puede hacer que las estimaciones del precio de coste promedio móvil se inflen excesivamente. Sin embargo, existen pasos para evitar la amplificación de precios o para reducir su impacto cuando se produzca. **Escenario** Las siguientes transacciones se producen para un artículo para el que ha seleccionado la opción **Incluir valor físico en coste**:

1.  Financieramente recibe una cantidad de 100 a 100,00 USD.
2.  Emite financieramente una cantidad de 200.
3.  Financieramente recibe una cantidad de 101 a 202,00 USD.

Cuando se examina el precio de coste promedio móvil estimado para el artículo, se espera un precio de coste de 1,51 dólares. En su lugar, encuentra un promedio móvil estimado de 102,00 USD, basado en la siguiente fórmula: Precio estimado = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102. Esta amplificación de precios se produce porque, cuando se emiten 200 artículos financieramente en el paso 2, el sistema debe fijar el precio de 100 de los artículos antes de tener los recibos correspondientes. Esta situación genera inventario negativo. El sistema estima a continuación un precio unitario de 1,00 USD, como se podría esperar. Sin embargo, cuando llegan los 100 recibos correspondientes, se encuentran en un precio unitario de 2,00 USD cada uno. **Nota:** Aunque las emisiones provocan un inventario negativo, el inventario es positivo cuando se calcula el precio de emisión. Por tanto, el precio de coste promedio móvil se usa en lugar del precio del maestro de artículos. En este momento, el sistema tiene una compensación de valor de inventario de 100,00 dólares. Aunque la compensación se ha creado para 100 artículos, donde había una compensación unitaria de 1,00 dólar cada uno, ahora solo hay una unidad en el inventario. Por tanto, la compensación de 100,00 dólares se asigna a esta única unidad. El resultado es el precio de coste estimado excesivo. **Nota:** Para comparar, tenga en cuenta que si los pasos 2 y 3 se invierten en el escenario, se emitirán 200 artículos a un precio unitario de 1,51 dólares, y quedará una unidad por un precio unitario de 1,51 dólares. Puesto que el escenario de amplificación de precios puede ocurrir cuando haya un inventario negativo implicado, es difícil de evitar en los casos siguientes:

-   Se deben estimar los precios de emisión según el valor y la cantidad disponibles.
-   Se deben ajustar el valor y la cantidad disponibles según emisiones y recibos.
-   El modelo empresarial permite enviar o determinar el precio de más unidades de las que se dispone.
-   Se debe aceptar cualquier valor y cantidad de recepción que se le haya enviado.

No obstante, si el modelo empresarial permite las siguientes prácticas, pueden ayudarle a evitar las cantidades negativas que hacen posible el escenario de amplificación de precios:

-   Si selecciona la opción **Incluir valor físico en coste** para un artículo, desactive la casilla **Inventario negativo físico** en la página **Grupos de modelos de artículo**.
-   Si *no* selecciona la opción **Incluir valor físico en coste** para un artículo, desactive la casilla **Inventario negativo financiero** en la página **Grupos de modelos de artículo**.

Además, tenga en cuenta también que la compensación máxima del valor de inventario físico está limitada por el número de transacciones físicas y las diferencias entre precios físicos y financieros. Siempre que todas las transacciones físicas se actualicen financieramente, el valor físico no puede llegar a niveles extremos. Por último, tenga en cuenta que el efecto de amplificación se reduce significativamente cuando la compensación acumulada se extiende a varias unidades disponibles, en lugar de solo una.


