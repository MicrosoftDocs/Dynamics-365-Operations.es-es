---
title: Cumplimiento de existencias de seguridad para los artículos
description: En este artículo se describe el cumplimiento de existencias de seguridad y cómo configurar la cantidad de existencias de seguridad para los artículos.
author: t-benebo
ms.date: 8/23/2021
ms.topic: article
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 70461ad1de94c984cb41e6b1d46af9e310a928d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887410"
---
# <a name="safety-stock-fulfillment-for-items"></a>Cumplimiento de existencias de seguridad para los artículos

[!include [banner](../includes/banner.md)]

Las existencias de seguridad indican una cantidad adicional de un artículo que se mantiene en el inventario para reducir el riesgo de que el artículo se agote. Las existencias de seguridad se usan como existencias de reserva en caso de que vengan pedidos de ventas y el proveedor no pueda entregar los artículos adicionales para cumplir con la fecha de envío solicitada por el cliente. Cuando se usan las existencias de seguridad para satisfacer un pedido de ventas, las existencias de seguridad se reducirán. Puede usar la planificación maestra para que el inventario vuelva automáticamente al nivel de seguridad.

## <a name="set-up-safety-stock-levels-for-items"></a>Establecer niveles de existencias de seguridad para los artículos

Las existencias de seguridad se configuran como parte de la cobertura del artículo en la página **Cobertura de artículos** en **Productos liberados \> Plan \> Cobertura**.

En el campo **Mínimo**, escriba el nivel de existencias de seguridad que desee mantener para el artículo. El valor se expresa en unidades de inventario. Si se deja el campo en blanco, el valor predeterminado es cero. Este campo está disponible si selecciona **Período**, **Requerimiento** o **Mín./Máx.** en la lista **Tipo de cobertura**. El límite del nivel de existencias se aplica al inventario disponible, lo que significa que las reservas y las marcas pueden desencadenar el reabastecimiento de existencias de seguridad antes de que la cantidad física vaya por debajo del nivel mínimo especificado.

> [!NOTE]
> Debe definir todas las otras dimensiones de cobertura planificadas para poder definir el campo **Mínimo**. Esto impide el uso de un registro no válido durante la planificación maestra. Esta situación podría surgir, por ejemplo, si un grupo de dimensiones se amplía con una dimensión de cobertura planificada adicional para la que aún no se han definido las cantidades mínimas y máximas de inventario.

Puede usar las claves mínimas para manejar las fluctuaciones de demanda por temporada. Por ejemplo, puede reducir el nivel de inventario mínimo para un artículo en la temporada baja y aumentar entonces el nivel gradualmente durante los otros meses. Se crea una clave mínima en **Planificación maestra \> Configuración \> Cobertura \> Claves mínimas/máximas**. Especifique la clave mínima para ajustar el nivel de existencias de seguridad por estacionalidad en el campo **Clave mínima** en la página **Cobertura de artículos** .

## <a name="example-minimum-key"></a>Ejemplo: Clave mínima

El siguiente procedimiento es un ejemplo que muestra cómo configurar una clave mínima que tenga en cuenta el aumento de la demanda estacional durante los meses de primavera y verano.

1. Vaya a **Planificación maestra \> Configuración \> Cobertura \> Claves mínimas/máximas**.
1. Seleccione **Nuevo** para crear una clave mínima/máxima.
1. En el campo **Clave mínima o máxima**, ingrese un identificador para la clave. En el campo **Nombre**, especifique un nombre para la clave.
1. Establezca la opción **Utilice la fecha de vigencia** en *Sí* y deje el campo **Fecha efectiva** en blanco para que la clave sea válida desde el primer día del año actual.

    > [!NOTE]
    > La combinación de las opciones **Utilice la fecha de vigencia** y **Fecha efectiva** define la fecha a partir de la cual es válida la clave.
    >
    > - Cuando la opción **Utilice la fecha de vigencia** está configurada en *No*, la clave es válida desde la fecha actual o la fecha del sistema.
    > - Cuando la opción **Utilice la fecha de vigencia** está establecida en *Sí*, la clave es válida a partir de la fecha definida en el campo **Fecha efectiva**.

1. En la sección **Periodos**, cree 12 líneas y establezca los siguientes valores para ellas:

    - **Cambio** - Asigne a cada línea un número único del 1 al 12. Este campo indica el cambio incremental en la unidad de tiempo definida por el campo **Unidad**.
    - **Unidad** - Seleccione *Meses* para cada línea.
    - **Partir de la fecha**, **Hasta la fecha** y **Mes** - Estos campos se configuran automáticamente, según los ajustes **Cambio** y **Unidad**. Los períodos mensuales comienzan desde el primer día del año actual.
    - **Factor** - Especifique los valores que se describen en la tabla siguiente: Este campo define el factor por el que desea multiplicar el inventario mínimo.

        | Línea (cambio) | Factor | Resultado |
        |---|---|---|
        | 1 – 3 | 1 | El inventario mínimo se basa en la configuración de enero a marzo del en la página **Cobertura de artículos**. |
        | 4 – 5 | 2 | El inventario mínimo se multiplica por un factor de 2 de abril a mayo. |
        | 6 – 8 | 2.5 | El inventario mínimo se multiplica por un factor de 2,5 para junio a agosto. |
        | 9 – 12 | 1 | El inventario mínimo vuelve a la configuración de septiembre a diciembre en la página **Cobertura de artículos**. |

    Su configuración ahora debería parecerse a la configuración de la siguiente ilustración.

    ![Períodos clave mínimos o máximos.](media/min-max-key-periods.png "Períodos clave mínimos o máximos")

> [!NOTE]
> También puede utilizar este asistente para crear y establecer una clave mínima/máxima. Sobre la página **Claves mínima o máxima**, en el Panel de acciones, seleccione **Asistente** para abrir el asistente **Claves mínima / máxima**. El asistente lo guiará paso a paso a través del proceso de creación y configuración de la clave mínima / máxima.

Si el tipo de cobertura es *Mín/Máx.*, también puede especificar la cantidad de inventario máxima que desee mantener para un artículo. El valor se expresa también en unidades de inventario. Si el inventario disponible proyectado cae por debajo de la cantidad mínima, la planificación maestra genera un pedido planificado para satisfacer cualquier otro requerimiento abierto y elevar el inventario hasta la cantidad máxima especificada. Al igual que se estableció una cantidad de inventario mínima, debe definir todas las otras dimensiones de cobertura planificadas para poder establecer el campo **Máximo**.

## <a name="example-minmax-coverage-code"></a>Ejemplo: Tipo de cobertura mínimo o máximo

La cantidad mínima es 10 y la máxima, 15. El inventario disponible actual es 4. Por lo tanto, el requisito de cantidad mínimo es de 6. Sin embargo, dado que la cantidad máxima es 15, la planificación maestra genera un pedido planificado de 11 artículos.

Para los artículos que siguen demandas estacionales, es posible que necesite mantener distintos niveles máximos. Para ello, es necesario definir las **Claves máximas** mediante **Planificación maestra \> Configuración \> Cobertura \> Claves mínimas/máximas**. Complete el campo **Clave máxima** en la página **Cobertura de artículos**. Puede ver la información sobre los niveles de existencias de seguridad, definidos mediante las claves mínimas en la pestaña **Mín/Máx.**, en la página **Cobertura de artículos** . Debe asegurarse de que, para un determinado período, los valores mínimos y máximos se mantengan sincronizados.

## <a name="safety-stock-fulfillment"></a>Cumplimiento de existencias de seguridad

El parámetro **Cumplir el mínimo** permite seleccionar la fecha o el periodo durante el cual el nivel de inventario debe satisfacer la cantidad especificada en el campo **Mínimo**. Este campo está disponible si selecciona **Período**, **Requerimiento** o **Mín./Máx.** en la lista **Tipo de cobertura**.

Si **Claver mínimas** esta en uso, seleccione la casilla de verificación **Periodos mínimos** para cumplir con el nivel de inventario mínimo para todos los períodos configurados en la clave mínima. Si desactiva esta casilla, se cumple el inventario mínimo solo para el período actual.

El siguiente escenario muestra cómo funciona este parámetro y cuáles son las diferencias entre sus valores.

> [!NOTE]
> Para todas las ilustraciones en este artículo, el eje X representa el inventario, el eje Y representa días, las barras representan el nivel de inventario, las flechas representan transacciones, como las líneas de pedido de ventas, las líneas de pedido de compra, o pedidos planificados.

[![Escenario común de cumplimiento de existencias de seguridad.](media/Scenario1.png)](media/Scenario1.png)

El parámetro **Cumplir con el mínimo** puede tener los siguientes valores:

### <a name="todays-date"></a>Fecha de hoy

La cantidad mínima especificada se alcanza en la fecha en que se ejecuta la planificación maestra. El sistema intenta cumplir el límite de existencias de seguridad lo más rápidamente posible, aunque es posible que sea poco realista debido al plazo.

[![Requisito en la fecha de hoy.](media/TodayReq.png)](media/TodayReq.png)

El pedido planificado P1 se crea para que la fecha de hoy supere el nivel de inventario disponible de existencias de seguridad en esta fecha. Las líneas de pedido de ventas S1 a S3 continúan bajando el nivel de inventario. Los pedidos planificados P2 a P4 se generan mediante la planificación maestra para que el nivel de inventario vuelva al límite de seguridad después de cada requerimiento de pedido de ventas.

Cuando se utiliza tipo de cobertura **Requerimiento**, se crean múltiples pedidos planificados. Siempre es una buena idea utilizar **Período** o el alcance **Mín/Máx.** para artículos y el material con demanda frecuente, para agrupar el reabastecimiento. En la siguiente ilustración se muestra un ejemplo tipo de cobertura **Periodo**.

[![Período. Fecha actual.](media/TodayPeriod.png)](media/TodayPeriod.png)

En la siguiente ilustración se muestra un ejemplo de tipo de cobertura **Mín./Máx.**.

[![MinMax. Fecha actual.](media/TodayMinMax.png)](media/TodayMinMax.png)

### <a name="todays-date--procurement-time"></a>Fecha de hoy + tiempo de adquisición

La cantidad mínima especificada se alcanza en la fecha cuando se ejecuta la planificación maestra más el tiempo de compra o de producción. Este tiempo incluye los márgenes de seguridad. Si el artículo incorpora un acuerdo comercial y se selecciona la casilla de verificación **Buscar acuerdos comerciales** en la página **Planificación de parámetros maestros**, no se considerará el plazo de entrega del acuerdo comercial. Los plazos se toman de los parámetros de cobertura de artículos o del artículo.

Este modo de cumplimiento creará planes con menos retrasos y menos los pedidos planificados, independientemente del grupo de cobertura configurado en el artículo.

La ilustración siguiente muestra el resultado del plan si el tipo de cobertura es **Requerimiento** o **Período**.

[![Requisito o período. Fecha actual y plazo de entrega.](media/TodayPLTReq.png)](media/TodayPLTReq.png)

La ilustración siguiente muestra el resultado del plan si el tipo de cobertura es **Mín./Máx.**

[![MinMax. Fecha actual y plazo de entrega.](media/TodayPLTMinMax.png)](media/TodayPLTMinMax.png)

### <a name="first-issue"></a>Primera emisión

La cantidad mínima especificada se alcanza en la fecha en la que el inventario disponible va por debajo del nivel mínimo, como se muestra en la siguiente ilustración. Incluso si el inventario disponible está por debajo del nivel mínimo en la fecha en que se ejecuta la planificación maestra, la **Primera emisión** no tratará de cubrirla hasta que no llegue el siguiente requerimiento.

En la siguiente ilustración se muestra un ejemplo de tipo de cobertura **Requerimiento**.

[![Planificación de un artículo con el tipo de cobertura Requerimiento y el cumplimiento de la Primera emisión.](media/FirstIssueReq.png)](media/FirstIssueReq.png)

En la siguiente ilustración se muestra un ejemplo tipo de cobertura **Periodo**.

[![Planificación de un artículo con el tipo de cobertura Período y el cumplimiento de la Primera emisión.](media/FirstIssuePeriod.png)](media/FirstIssuePeriod.png)

En la siguiente ilustración se muestra un ejemplo de tipo de cobertura **Mín./Máx.**.

[![Planificación de un artículo con el tipo de cobertura MinMax y el cumplimiento de la Primera emisión.](media/FirstIssueMinMax.png)](media/FirstIssueMinMax.png)

En la fecha en la que se ejecute la planificación maestra, si el inventario disponible ya se encuentra bajo límite de existencias de seguridad, **Fecha actual** y **Fecha actual + tiempo de compras** el reabastecimiento activará inmediatamente. La **Primera emisión** esperará hasta que haya otra transacción de emisión, como un pedido de ventas y requerimiento de LM, para el artículo y, a continuación activará el reabastecimiento en la fecha de esta transacción.

En la fecha en la que se ejecute la planificación maestra, si el inventario disponible no se encuentra bajo el límite de existencias de seguridad, **Fecha actual** y **Primera emisión** proporcionarán exactamente el mismo resultado, tal y como se muestra en la ilustración siguiente.

[![No por debajo del límite.](media/ReqFirstIssue.png)](media/ReqFirstIssue.png)

En la fecha en la que se ejecute la planificación maestra, si el inventario disponible no se encuentra bajo el límite de existencias de seguridad, **Fecha actual + tiempo de compras** proporcionarán el siguiente resultado, ya que el cumplimiento se pospone hasta el final del plazo de compra.

![El cumplimiento se pospuso hasta el final del plazo de entrega de adquisiciones.](media/ReqTodayLT.png)

### <a name="coverage-time-fence"></a>Límite de tiempo de cobertura

La cantidad mínima especificada se alcanza dentro del período de tiempo que se especifique en el campo **Tiempo límite de cobertura**. Esta opción es útil cuando la planificación maestra no permite que el inventario disponible se use para pedidos reales, como ventas o transferencias, en un intento por mantener el nivel de seguridad. Sin embargo, en una versión futura, este modo de reabastecimiento ya no será necesario y esta opción se dejará de usar.

## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planificación del reabastecimiento de existencias de seguridad para artículos, primero en caducar primero en salir (FEFO)

En cualquier momento, la recepción de inventario con la última fecha de caducidad se usará para que las existencias de seguridad permitan que la demanda real, como las líneas de ventas o líneas de LM, se cumpla en el orden FEFO (primero en caducar, primero en salir).

Para mostrar cómo funciona esto, considere el escenario siguiente.

[![Escenario FEFO.](media/FEFOScenario.png)](media/FEFOScenario.png)

Cuando se ejecuta la planificación, cubrirá el primer pedido de ventas del inventario disponible existente y un pedido de compra adicional para la cantidad restante.

[![FEFO 1.](media/FEFO1.png)](media/FEFO1.png)

Se crea un pedido planificado para asegurarse de que el inventario disponible vuelve de nuevo al límite de seguridad.

[![FEFO 2.](media/FEFO2.png)](media/FEFO2.png)

Cuando se planifica el segundo pedido de ventas, el pedido planificado creado previamente para cubrir las existencias de seguridad se utiliza para cubrir esta cantidad. Por lo tanto, las existencias de seguridad están en constantemente movimento.

[![FEFO 3.](media/FEFO3.png)](media/FEFO3.png)

Finalmente, se crea otro pedido planificado que cubra las existencias de seguridad.

[![FEFO 4.](media/FEFO4.png)](media/FEFO4.png)

Todos los lotes expiran según corresponda y se crean los pedidos planificados para reabastecer las existencias de seguridad después de que hayan caducado.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Cómo la planificación maestra gestiona la restricción de existencias de seguridad

Las existencias de seguridad se sigue en el sistema como un tipo de requerimiento, tal como las líneas de ventas o los requerimientos de LM. Puede ver la línea de requerimiento de existencias de seguridad en la página **Requerimientos netos** si quita el filtro predeterminado en la columna **Tipo de requerimiento**.

El cumplimiento de la transacción de requisitos de existencias de seguridad no tiene prioridad si el sistema determina que esto causa retrasos en el cumplimiento de la demanda real, como las líneas de ventas, las líneas de LM, requerimientos de transferencia, o líneas de previsión de demanda. Si no, el asegurarse de que el inventario disponible está por encima de la cantidad de existencias de seguridad tiene la misma prioridad que cualqier otro tipo de demanda. Esto garantiza que no haya retrasos en transacciones reales y ayuda a evitar reabastecimiento en exceso y el reabastecimiento antes de tiempo de existencias de seguridad.

Durante la fase de cobertura de planificación maestra, el reabastecimiento de existencias de seguridad no pierde prioridad. El inventario disponible se puede usar antes que cualquier otro tipo de demanda. Durante el cálculo del retraso, se agregará una nueva lógica para repasar las líneas de ventas retrasadas, los requerimientos de las líneas de LM y todos los otros tipos de demanda, para determinar si podrían entregarse a tiempo, siempre que se utilicen existencias de seguridad. Si el sistema identifica que puede minimizar los retrasos mediante las existencias de seguridad, las líneas de ventas o las líneas de LM reemplazarán su cobertura inicial con las existencias de seguridad y el sistema activará el reabastecimiento de las existencias de seguridad.

Si el plan o el artículo no están configurados para el cálculo de retrasos, la restricción de existencias de seguridad tendrá la misma prioridad que cualquier otro tipo de demanda. Esto significa que hay una reserva de inventario y otro inventario disponible antes de que otros tipos de demanda.

## <a name="additional-resources"></a>Recursos adicionales

- [Usar el diario de existencias de seguridad para actualizar la cobertura mínima para artículos](safety-stock-journal.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
