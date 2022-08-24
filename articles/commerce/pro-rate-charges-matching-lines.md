---
title: Prorratear los cargos de encabezado con las líneas de ventas coincidentes
description: Este artículo describe las capacidades adicionales para calcular y aplicar cargos automáticos a los pedidos del canal de Commerce mediante la función de cargos automáticos avanzada.
author: hhainesms
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 85e75b533e95d149de1cde50c0ef122f58890bbe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279042"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Prorratear los cargos de encabezado con las líneas de ventas coincidentes


[!include [banner](includes/banner.md)]

Este artículo describe la funcionalidad para agrupar cargos automáticos de nivel de encabezado y prorratearlos a las líneas de la venta de Commerce. Esta funcionalidad está disponible para las transacciones que se crean en el punto de venta (POS) en la versión 10.0.1 de Retail y las ventas que se crean en un centro de asistencia telefónica en la versión 10.0.2 de Retail.

Esta funcionalidad solo está disponible si la función [cargos automáticos avanzados](/dynamics365/unified-operations/retail/omni-auto-charges) está activada mediante la opción en la página **Parámetros de Commerce**. Además, el método de cálculo ampliado para cargos automáticos se puede aplicar solo a los pedidos de ventas que se crean mediante canales de commerce (PDV, un centro de asistencia telefónica y la plataforma de e-commerce de Dynamics).

Esta nueva funcionalidad da a las organizaciones mayor flexibilidad en el modo en que calculan y se aplican los cargos automáticos de nivel de cabecera en las transacciones de ventas.

En las versiones de la aplicación que sean anteriores a la versión 10.0.1, se calculan los gastos automáticos de nivel de encabezado que tienen un modo específico de relación de entrega solo si hay una coincidencia con el modo de entrega que está definido en el encabezado de pedido de ventas.

Por ejemplo, se definen los gastos automáticos de nivel de encabezado para el modo de entrega **99** y el modo de entrega **11**. Se crea un pedido de ventas, y se define el modo de entrega **99** en el encabezado del pedido. Sin embargo, algunas de las líneas de ventas se configuran para enviarlos mediante el modo de entrega **11**. En este caso, sólo se tienen en cuenta y se aplican al pedido de ventas los gastos de nivel de encabezado que están vinculados al modo de entrega **99**.

En Commerce, los cargos de nivel de encabezado tienen una característica adicional que permite definir una [configuración de gastos con varios niveles](/dynamics365/unified-operations/retail/configure-call-center-delivery) que está basada en el valor del pedido. Por ejemplo, si el valor del pedido está entre $50,00 y $200,00, una organización puede desear cobrar u gasto de flete de $5,00. Sin embargo, si el valor del pedido esTÁ entre $200,01 y $500,00 el cargo del flete podría ser $4,00.

Algunas organizaciones desean los beneficios que ofrece el cálculo de cargos con varios niveles que se ofrece con los cargos de nivel de encabezado. Sin embargo, en las situaciones que implican modos mixtos de entrega, también desean asegurarse de que los gastos que se calculan se basan en una correlación con el modo de entrega que está definido en cada línea de ventas.

Ahora puede configurar a gastos autmáticos de nivel de encabezado de modo que todos los modos de entrega del pedido se tengan en cuenta cuando se calculan los cargos. Esta funcionalidad requiere una lógica más compleja de cálculo para calcular los gastos de nivel de encabezado. La lógica agrupa conjuntamente todos los artículos que se envían utilizando el mismo modo de entrega, y trata a ese grupo como el grupo de cálculo para los artículos cuando se calculan los gastos automáticos de nivel de encabezado. Para los artículos con el mismo modo de entrega, los gastos automáticos se calculan según el valor de ventas de los artículos combinado. De esta manera, se determina el nivel apropiado de gasto automático.

Una vez que se hayan recopilado los gastos adecuados de nivel de encabezado para las líneas de ventas que se envían con el mismo modo de entrega, los cargos calculados se prorratearán hasta el nivel de línea de ventas. Dado que estos gastos se encuentran en el nivel de línea y no se mantienen en el nivel de encabezado, un vínculo más específico se establece entre el artículo y el valor del gasto que se calcula para él. Este comportamiento puede ser útil en los escenarios de devoluciones parciales, donde una organización desea devolver sólo una parte del gasto en lugar de los gastos en general cuando sólo se devuelven algunos artículos.

## <a name="scenarios"></a>Situaciones

Las dos casos de ejemplo siguientes describen cómo calcular estos gastos cuando se usa la nueva funcionalidad y cuando no se utiliza.

### <a name="scenario-1"></a>Escenario 1

Esta situación delinea el comportamiento cuando la opción **Prorratear con líneas de ventas coincidentes** se establece en **No** en la configuración de cargos automáticos. (El comportamiento es equivalente al comportamiento de gastos nivel de encabezado en las versiones de la aplicación anteriores a la versión 10.0.1).

En este escenario, la organización ha definido los gastos de nivel de encabezado para la relación de modo de entrega **99** y la relación de modo de entrega **11**. No se configura ningún gasto automático para el modo de entrega **21**.

![Cargos automáticos para el modo de entrega 99 cuando se desactiva el prorrateo de línea que coincide.](media/99_disabled.png)

![Cargos automáticos para el modo de entrega 11 cuando se desactiva el prorrateo de línea que coincide.](media/11_disabled.png)

Se crea un pedido de ventas en el centro de asistencia telefónica y el modo de entrega se establece en **99**. Este pedido incluye cinco artículos. Dos líneas de pedido se han configurado para usar el modo de entrega **99**, dos líneas se han configurado para usar el modo de entrega **11** y una línea se ha configurado usar el modo de entrega **21**, como se muestra en la tabla siguiente.

| Artículo  | Cantidad de línea | Modo de entrega | Precio por unidad |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 $            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

En este escenario, la totalidad del pedido se evalúa con la tabla de gasto automático para el modo de entrega **99**. El total completo de todas las líneas de ventas se usa para determinar un nivel coincidente en la configuración de cargo automático, y este gasto se aplica en el nivel de cabecera de pedido. En este ejemplo, el total de pedido es $165,00, y se aplican los gastos de flete de $15,00 a la cabecera del pedido. Nunca se hace referencia ni se aplican los gastos automáticos configurados para el modo de entrega **11**.

En esta situación, si el cliente devuelve algunos de los artículos del pedido, y si [se ha configurado el código del gasto de modo que se devuelva](/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), se aplica el gasto total de nivel de encabezado sistemáticamente a la devolución, incluso si sólo algunos de los artículos se devuelven.

### <a name="scenario-2"></a>Escenario 2

En este escenario, los gastos de nivel de encabezado se definen para la relación de modo de entrega **99** y la relación de modo de entrega **11**. Sin embargo, la opción **Prorratear con líneas de ventas coincidentes** está configurada en **Sí** para estas tablas de gasto automático.

![Cargos automáticos para el modo de entrega 99 cuando se activa el prorrateo de línea que coincide.](media/99_enabled.png)

![Cargos automáticos para el modo de entrega 11 cuando se activa el prorrateo de línea que coincide.](media/11_enabled.png)

Esta situación utiliza el mismo pedido de ventas que contiene cinco líneas. El modo de entrega en el encabezado del pedido se establece en **99**, pero el modo de entrega de cada artículo del pedido de ventas está configurado como se muestra en la tabla siguiente.

| Artículo  | Cantidad de línea | Modo de entrega | Precio por unidad |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | $10            |
| 81332 | 1             | 99            | 50 $            |
| 81333 | 2             | 11            | $30            |
| 81334 | 3             | 99            | $10            |
| 81334 | 3             | 21            | $5             |

Dado que la configuración de gasto automático se establece para prorratearse con las líneas de ventas coincidentes, el sistema ejecuta los pasos siguientes de cálculo.

1. Todos los artículos con el mismo modo de entrega se agrupan conjuntamente, y el sistema calcula el valor total de producto de los artículos del grupo.

    **Modo de entrega 11**

    - Artículo 81331, cantidad 1 = $10
    - Artículo 81333, cantidad 2 = $60 neto ($30 por unidad)
    - **Valor total de productos para el modo de entrega 11 = $70**

    **Modo de entrega 99**

    - Artículo 81332, cantidad 1 = $50
    - Artículo 81334, cantidad 3 = $30 neto
    - **Valor total de productos para el modo de entrega 99 = $80**

    **Modo de entrega 21**

    - Artículo 81334, cantidad 3 = $15 neto
    - **Valor total de productos para el modo de entrega 21 = $15**

2. El sistema busca la configuración de los gastos automáticos de nivel de encabezado que coincide con el cliente y la configuración del modo de entrega para cada grupo de artículos. Si se encuentra la configuración, el sistema buscará en la configuración con varios niveles para encontrar el gasto que se va a aplicar, en función del valor total de producto de los artículos en el modo de grupo de entrega.

    **Modo de entrega 11**

    - Valor total de producto = 70 $
    - **Valor de gasto = $7**

    **Modo de entrega 99**

    - Valor total de producto = 80 $
    - **Valor de gasto = $15**

    **Modo de entrega 21**

    - Valor total de producto = 15 $
    - **Valor de gasto = $0** (No se ha configurado ningún gasto automático para esta combinación de cliente y modo de entrega).

    ![Los gastos del modo de entrega 11 se encuentran en el nivel resaltado.](media/step2mode11.png)

    ![Los gastos del modo de entrega 99 se encuentran en el nivel resaltado.](media/step2mode99.png)

3. El sistema calcula el valor del gasto que se debe aplicar a cada línea, en función de la lógica de prorrateo que considera el valor proporcional de la línea en relación con el valor total del producto del grupo.

    **Modo de entrega 11**

    - Valor de gasto = $7
    - Valor de producto de grupo = $70
    - Valor de la línea 1 = $10 (= 14,2857 por ciento del valor del grupo)
    - Valor de la línea 3 = $60 (= 85,7143 por ciento del valor del grupo)
    - **Gasto de línea para la línea 1 = $1**
    - **Gasto de línea para la línea 3 = $6**

    **Modo de entrega 99**

    - Valor de gasto = $15
    - Valor de producto de grupo = $80
    - Valor de la línea 2 = $50 (= 62,5 por ciento del valor del grupo)
    - Valor de la línea 4 = $30 (= 37,5 por ciento del valor del grupo)
    - **Gasto de línea para la línea 2 = $9,38**
    - **Gasto de línea para la línea 4 = $5,62**

    **Modo de entrega 21**

    - Valor de gasto = $0
    - Valor de producto de grupo = $15
    - Valor de la línea 5 = $15 (= 100 por ciento del valor del grupo)
    - **Gasto de línea para la línea 5 = $0**

Por lo tanto, para este ejemplo, al artículo 81334 se le asignará un cargo de flete de $5,62. Puede consultar estos gastos en la página **Mantener gastos** de la línea de ventas. La ilustración siguiente muestra lo que parece esta página para el artículo 81334.

![Cargos prorrateados en la línea de ventas para el artículo 81334.](media/proratedlinecharge.png)

Cuando este método de cálculo se usa en una situación de devolución parcial, si el código de gasto es reembolsable se devolverán sólo la parte del gasto que se asigna a dicha línea cuando se devuelve el artículo.

## <a name="additional-resources"></a>Recursos adicionales

[Cargos automáticos avanzados omnicanal](omni-auto-charges.md)

[Habilitar y configurar cargos automáticos por canal](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
