---
title: Perfil y niveles de búfer
description: Este artículo proporciona información sobre los perfiles y niveles de búfer, que determinan los niveles mínimos y máximos de existencias que deben mantenerse para cada punto de desacoplo.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: d254b949d31d0b15141646503c64760062b77fc7
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689169"
---
# <a name="buffer-profile-and-levels"></a>Perfil y niveles de búfer

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Una vez que haya identificado sus puntos de desacoplo (elementos clave que estratégicamente mantendrá en existencias), debe decidir cuántas existencias (búfer) mantendrá en cada uno de ellos. Esta tarea es el segundo paso de la planificación de requisitos de basada en la demanda (DDMRP).

## <a name="buffer-levels-and-zones"></a>Niveles y zonas de búfer

En DDMRP, cada búfer de existencias se define con tres valores: la cantidad mínima, la cantidad máxima y el punto de realización de nuevo pedido. Estos valores establecen tres zonas de diferencia, que se identifican con los siguientes códigos de colores:

- **Zona roja** – El área por debajo de la cantidad mínima. La cantidad mínima también se conoce como "máximo rojo" y su estrategia de planificación debe estar diseñada para garantizar que los niveles de existencias estén siempre por encima de este punto.
- **Zona amarilla** – El área entre la cantidad mínima y el punto de realización de nuevo pedido. El punto de realización de nuevo pedido también se conoce como "máximo amarillo". Cuando se alcanza este punto, el sistema debe realizar un nuevo pedido.
- **Zona verde** – El área entre el punto de realización de nuevo pedido y la cantidad máxima. La cantidad máxima también se conoce como "máximo verde". Este punto es el nivel máximo al que se repondrán las existencias.

La siguiente ilustración muestra las tres zonas de colores y cómo se relacionan con la cantidad mínima, la cantidad máxima y el punto de realización de nuevo pedido.

![Zonas y niveles de búfer de DDMRP.](media/ddmrp-buffer-levels.png "Zonas y niveles de búfer de DDMRP")

## <a name="calculating-the-buffer-zones"></a>Cálculo de las zonas de búfer

Esta sección explica cómo se calcula la altura de cada zona de búfer.

La zona amarilla normalmente se calcula primero. Esta zona representa la cantidad que usted consume desde que realiza el pedido hasta que llega el pedido. En otras palabras, es el consumo esperado durante el plazo de reabastecimiento. Se calcula mediante la ecuación siguiente:

- **Zona amarilla** = *Uso diario promedio (ADU)* × *Plazo de entrega desacoplado*

El *plazo de entrega desacoplado* representa el tiempo que se requiere para producir o recibir un artículo si los puntos de desacoplo están siempre en existencias. Suele ser mucho más corto que el *plazo acumulativo* que se utiliza tradicionalmente en la planificación maestra. La configuración correcta del búfer es clave para garantizar que los puntos de desacoplo siempre estén realmente en existencias pero no en exceso.

La zona roja se calcula mediante las ecuaciones siguientes:

- **Base roja** = *ADU* × *Plazo de entrega desacoplado* × *Factor de plazo de entrega*
- **Seguridad roja** = *Base roja* × *Factor de variabilidad*
- **Zona roja** = *Base roja* + *Seguridad roja*

La zona verde se calcula como el resultado máximo de las siguientes tres ecuaciones:

- *Cantidad mínima del pedido*
- *ADU* × *Ciclo de pedidos*
- *ADU* × *Plazo de entrega desacoplado* × *Factor de plazo de entrega*

## <a name="calculating-average-daily-usage"></a>Calcular el uso diario promedio

El sistema utiliza uno de los tres enfoques para calcular la cantidad que consume por día:

- **Uso diario promedio (pasado)** – Este enfoque se basa en el consumo pasado real.
- **Uso diario promedio (futuro)** – Este enfoque se basa en el consumo futuro previsto.
- **Uso diario promedio (combinado)** – Este enfoque se basa en una combinación ponderada de consumo pasado y previsto.

### <a name="average-daily-usage-past"></a>Uso diario promedio (pasado)

El ADU pasado se calcula como promedio sumando las cantidades que se usan cada día durante un número específico de días pasados y luego dividiendo el total por la cantidad de días. La siguiente ilustración muestra cómo funciona este enfoque cuando el cálculo tiene en cuenta tres días del pasado.

![Gráfico de uso diario promedio (pasado).](media/ddmrp-adu-past.png "Gráfico de uso diario promedio (pasado)")

En la ilustración anterior, si hoy es la mañana del 11 de junio, el ADU de los tres días anteriores (8, 9 y 10 de junio) es 21.

- **ADU (pasado)** = (29 + 11 + 23) ÷ 3 = 21

Las siguientes transacciones se tienen en cuenta para el cálculo del uso diario promedio (pasado):

- Transacciones que disminuyen la cantidad del artículo (en la tabla `inventtrans` donde la cantidad es menor que cero)
- Transacciones con un estado de *En orden*, *Reservado ordenado*, *Físico reservado*, *Escogido*, *Deducido*, o *Vendido*
- Transacciones con fecha dentro del período hacia atrás elegido (el uso diario promedio del período anterior)
- Transacciones que no sean trabajo de almacén, cuarentena, cotizaciones de venta o extractos (`WHSWork`, `WHSQuarantine`, `SalesQuotation`, o `Statement`)
- Transacciones que no sean diarios de transferencia que estén dentro de la misma dimensión de cobertura

### <a name="average-daily-usage-forward"></a>Uso diario promedio (futuro)

Para un producto nuevo, es posible que no tenga datos de uso anteriores. Por lo tanto, en su lugar, puede usar el ADU proyectado hacia delante (por ejemplo, basado en la demanda prevista). La siguiente ilustración muestra cómo funciona este enfoque cuando el cálculo tiene en cuenta tres días del futuro (incluido hoy).

![Gráfico de uso diario promedio (futuro).](media/ddmrp-adu-forward.png "Gráfico de uso diario promedio (futuro)")

En la ilustración anterior, si hoy es la mañana del 11 de junio, el ADU de los tres días siguientes (11, 12 y 13 de junio) es 21.66.

- **ADU (futuro)** = (18 + 18 + 29) ÷ 3 = 21,66

Las siguientes transacciones se tienen en cuenta para el cálculo del uso diario promedio (hacia adelante):

- Transacciones de pronóstico para el artículo donde se selecciona el pronóstico en el plan maestro
- Transacciones con fecha dentro del período hacia adelante elegido (el uso diario promedio del período hacia adelante)

### <a name="average-daily-usage-blended"></a>Uso diario promedio (combinado)

El ADU combinado combina el uso pasado promedio y el uso futuro promedio, como se muestra en la siguiente ilustración.

![Gráfico de uso diario promedio (combinado).](media/ddmrp-adu-blended.png "Gráfico de uso diario promedio (combinado)")

En la ilustración anterior, si hoy es la mañana del 11 de junio, el ADU combinado de los tres días anteriores y siguientes (8 a 13 de junio) es 21,33.

- **ADU combinado** = (*ADU pasado* + *ADU futuro*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Factores de cálculo del búfer

Para cada artículo, puede definir dos factores para ajustar el tamaño que deben tener las zonas roja y verde. De esta forma, puede compensar el plazo previsto y la variabilidad de la demanda.

![Factores de plazo de entrega y variabilidad.](media/ddmrp-zone-factors.png "Factores de plazo de entrega y variabilidad")

El primer factor es el *factor de plazo de entrega*. El valor es un valor decimal de 0 a 1. Cuanto mayor sea el plazo de entrega, menor debe ser el valor. El Demand Driven Institute recomienda los siguientes rangos:

- **Plazo largo:** 0,20–0,40
- **Plazo medio:** 0,41–0,60
- **Plazo corto:** 0,61–1,00

El segundo factor es el *factor de variabilidad*. El valor es un valor decimal de 0 a 1. Cuanto más alta sea la variabilidad de la demanda, menor debe ser el valor. El Demand Driven Institute recomienda los siguientes rangos:

- **Variabilidad baja:** 0,20–0,40
- **Variabilidad media:** 0,41–0,60
- **Variabilidad alta:** 0,61–1,00

## <a name="buffer-calculation-examples"></a>Ejemplos de cálculo del búfer

Este ejemplo continúa el ejemplo de producción de almohadas que se proporciona en [Posicionamiento de inventario](ddmrp-inventory-positioning.md). En ese ejemplo, seleccionó puntos de desacoplo que redujeron el plazo de entrega de 21 días a cinco días, como se muestra en la siguiente ilustración.

![Ejemplo de plazo de entrega desacoplado.](media/ddmrp-bom-decoupled-lead-time-example.png "Ejemplo de plazo de entrega desacoplado")

Para este ejemplo, supongamos que el ADU se calculó como 23 piezas y, como se muestra en la ilustración anterior, el plazo de entrega desacoplado es de cinco días. Con estos valores puede calcular la zona amarilla usando la siguiente ecuación:

- **Zona amarilla** = *ADU* × *Plazo de entrega desacoplado* = 115

![Ejemplo de cálculo de zona amarilla.](media/ddmrp-example-calc-yellow.png "Ejemplo de cálculo de zona amarilla")

El cálculo de la zona roja se parece al cálculo de la zona amarilla, pero se ha rellenado para tener en cuenta la variabilidad y el plazo de entrega. Para este ejemplo, supongamos que ha observado un plazo de entrega medio (factor = 0,50) y una alta variabilidad de la demanda (factor = 0,8). Si utiliza estos valores junto con los componentes de la ecuación de la zona amarilla, puede calcular la zona roja con las siguientes ecuaciones:

- **Base roja** = *ADU* × *Plazo de entrega desacoplado* × *Factor de plazo de entrega* = 57,5
- **Seguridad roja** = *Base roja* × *Factor de variabilidad* = 46
- **Zona roja** = *Base roja* + *Seguridad roja* = 103,5

El sistema redondeará la zona roja a 104 piezas (ea), porque las piezas se cuentan en números enteros.

![Ejemplo de cálculo de zona roja.](media/ddmrp-example-calc-red.png "Ejemplo de cálculo de zona roja")

El cálculo de la zona verde también incluye los componentes de la ecuación de la zona amarilla, pero permite un tamaño de pedido mínimo, un ciclo de pedido y un factor de plazo de entrega. Para este ejemplo, supongamos que no hay un ciclo de pedidos (por tanto, no tiene restricciones de tiempo sobre la frecuencia con la que realiza el pedido) y la cantidad mínima de pedido es de 10 piezas. La zona verde se calcula como el resultado máximo de las siguientes tres ecuaciones:

- *Cantidad mínima de pedido* = 10
- *ADU* × *Ciclo de pedidos* = 0
- *ADU* × *Plazo de entrega desacoplado* × *Factor de plazo de entrega* = 57,5

El sistema redondeará la zona verde a 58 piezas (ea), porque las piezas se cuentan en números enteros.

![Ejemplo de cálculo de zona verde.](media/ddmrp-example-calc-green.png "Ejemplo de cálculo de zona verde")

La siguiente ilustración resume estos resultados de cálculo de zona utilizando el gráfico de embudo que se usa a menudo en DDMRP.

![Resumen de resultados de cálculo de zona.](media/ddmrp-example-calc-summary.png "Resumen de resultados de cálculo de zona")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Ajustes dinámicos

Los ajustes dinámicos le permiten aplicar un *factor de ajuste de la demanda* durante periodos de alta o baja demanda. Este factor multiplica el ADU en todos los cálculos para el período seleccionado. A continuación, las zonas de búfer se modifican a su vez. Por lo general, aplicará este factor después de generar sus valores de búfer iniciales, de modo que pueda ajustarlos con el tiempo y en respuesta a las condiciones cambiantes. Esta tarea es el tercer paso de DDMRP.

Por ejemplo, podría haber más demanda de un producto de almohada en agosto, ya que la gente se va de vacaciones. Por lo tanto, se espera que las ventas sean mayores. En este caso, puede cambiar el valor de **Factor de ajuste de la demanda** del producto a *1,5* para todas las semanas de agosto.

De esta forma, puede calcular los valores del búfer a lo largo del tiempo y luego ajustarlos basándose en algo más que la información que tiene el sistema. En una implementación completa de DDMRP, calculará nuevos valores de búfer todos los días a través de un trabajo por lotes y aceptará automáticamente los valores. A continuación, ejecutará la planificación como un trabajo por lotes y revisará los pedidos planificados todos los días para rellenar los búferes.

## <a name="implement-buffers-in-supply-chain-management"></a>Implementar búferes en Supply Chain Management

Esta sección describe cómo implementar su estrategia de zona de búfer en Microsoft Dynamics 365 Supply Chain Management. Se da por sentado que ya ha realizado los análisis y cálculos que se describen en la primera mitad de este artículo.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Configurar búferes para un artículo de punto de desacoplo

Siga estos pasos para configurar valores de búfer para un punto de desacoplo.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione un elemento liberado que esté configurado como punto de desacoplo. (Para obtener más información, consulte [Posicionamiento de inventario](ddmrp-inventory-positioning.md).)
1. En el panel de acciones, en la pestaña **Plan**, seleccione **Cobertura de artículos**.
1. En la página **Cobertura de artículos**, seleccione un registro de cobertura de artículos que cree un punto de desacoplo. (Este registro mostrará el nombre de un grupo de cobertura que está configurado para crear puntos de desacoplo).
1. Seleccione la ficha **General**.
1. Si desea que el sistema vuelva a calcular los valores del búfer todos los días o todas las semanas, según su historial de ventas, previsiones y configuraciones de grupos de cobertura, siga estos pasos:

    1. Establezca la opción **Valores del búfer a lo largo del tiempo** como *Sí*.
    1. Un cuadro de mensaje le notifica que su configuración de búfer manual (**Mínimo**, **Punto de hacer nuevo pedido** y **Máximo**) se restablecerá si continúa. Seleccione **Sí** para mantener la nueva configuración.

    Alternativamente, si prefiere calcular o ingresar la configuración de su búfer solo una vez, siga estos pasos:

    1. Establezca la opción **Valores del búfer a lo largo del tiempo** como *No*.
    1. Seleccione los campos **Mínimo**, **Punto de hacer nuevo pedido** y **Máximo** con los valores de búfer que ha calculado para el artículo, como se describe anteriormente en este artículo.

1. Establezca los siguientes campos para terminar de configurar los cálculos de DDMRP para el artículo:

    - **Ciclo de pedidos** – Especifique el número de días que deben transcurrir entre los pedidos de compra del artículo. Establezca el valor en *0* (cero) si no existen restricciones de pedido. Este campo afecta al búfer de cantidad máxima, como se discutió anteriormente en este artículo.
    - **Uso diario promedio** – Opcionalmente, puede ingresar un ADU estimado para el artículo. La finalidad de este campo es meramente informativa. Por lo general, el valor se calcula automáticamente como parte de los cálculos del búfer.
    - **Umbral de picos de pedidos** – Especifique el número mínimo de ventas diarias del artículo que califican como pico de ventas (demanda inusualmente alta). El sistema usa este campo para aumentar la cantidad de nuevo pedido para pedidos planificados en períodos de alta demanda. Para obtener más información consulte [Planificación basada en la demanda](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Calcular o introducir plazos de entrega desacoplados

Para los artículos en los que elige permitir que el sistema [calcule sus zonas de búfer automáticamente](#set-up-buffers), siga estos pasos para calcular o introducir plazos de entrega desacoplados para un artículo de punto de desacoplo.

1. Abre la página **Cobertura de artículos** para su artículo de punto de desacoplo. (Para más información, vea [Configurar búferes para un elemento de punto de desacoplo](#set-up-buffers) .)
1. Seleccione un registro de cobertura de artículos que cree un punto de desacoplo.
1. Seleccione la pestaña **Valores de búfer**.
1. Si no se muestran períodos de tiempo en la cuadrícula, en el Panel de acciones, en la pestaña **Valores de búfer**, seleccione **Agregar periodos de tiempo**. El sistema rellena la cuadrícula con filas para cada período de tiempo diario o semanal, dependiendo de si el campo **Mínimo, máximo y período del punto de hacer nuevo pedido** para el [grupo de cobertura](ddmrp-inventory-positioning.md) se establece en *Diariamente* o *Semanalmente*. El sistema agregará suficientes filas para alcanzar el límite de tiempo especificado para el grupo de cobertura asignado al elemento.
1. Seleccione el período de tiempo en el que desea calcular el plazo de entrega desacoplado. (Por lo general, este período de tiempo es el período que incluye la fecha de hoy).
1. En el Panel de acciones, en la pestaña **Valores de búfer**, seleccione **Calcular plazo de entrega desacoplado**.
1. En el cuadro de diálogo **Calcular plazo de entrega desacoplado**, establezca los siguientes campos:

    - **L. MAT** – Seleccione la lista de materiales (BOM) en la que desea ejecutar el cálculo.
    - **Fecha** – Seleccione la fecha en la que desea ejecutar el cálculo. El conjunto de listas de materiales disponibles se filtrará para que solo se muestren las listas de materiales que están activas para la fecha seleccionada.
    - **Cantidad** – Introduzca la cantidad para la que desea ejecutar el cálculo. El conjunto de listas de materiales disponibles se filtrará para que solo se muestren las listas de materiales que se aplican a la cantidad especificada.

1. Seleccione **Aceptar** para ejecutar el cálculo y cerrar el cuadro de diálogo **Calcular el plazo de entrega desacoplado**. La columna **Plazo de entrega desacoplado** para el período de tiempo seleccionado ahora muestra el valor calculado.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Calcular o introducir el uso diario promedio

Para los artículos en los que elige permitir que el sistema [calcule sus zonas de búfer automáticamente](#set-up-buffers), siga estos pasos para calcular o introducir el ADU para un artículo de punto de desacoplo.

1. Abre la página **Cobertura de artículos** para su artículo de punto de desacoplo. (Para más información, vea [Configurar búferes para un elemento de punto de desacoplo](#set-up-buffers) .)
1. Seleccione un registro de cobertura de artículos que cree un punto de desacoplo.
1. Seleccione la pestaña **Valores de búfer**.
1. Si no se muestran períodos de tiempo en la cuadrícula, en el Panel de acciones, en la pestaña **Valores de búfer**, seleccione **Agregar periodos de tiempo**. El sistema rellena la cuadrícula con filas para cada período de tiempo diario o semanal, dependiendo de si el campo **Mínimo, máximo y período del punto de hacer nuevo pedido** para el [grupo de cobertura](ddmrp-inventory-positioning.md) se establece en *Diariamente* o *Semanalmente*. Además, los valores predeterminados para los campos **Factor de plazo de entrega** y **Factor de variabilidad** se toman del grupo de cobertura. Puede editar estos valores para cada fila según sea necesario.
1. Seleccione un período de tiempo en el que desea calcular el ADU.
1. En el Panel de acciones, en la pestaña **Valores de búfer**, seleccione **Calcular el uso diario promedio**. El sistema trata de recopilar los datos que se requieren para el cálculo del ADU, como se define para el [grupo de cobertura](ddmrp-inventory-positioning.md).
1. Siga uno de estos pasos:

    - Si los datos requeridos están disponibles, los resultados del cálculo se agregan a la columna **Uso diario promedio**. En este caso, no se requiere ninguna acción.
    - Si los datos requeridos no están disponibles, no se agregan valores automáticamente. En este caso, ingrese manualmente los valores estimados para cada fila donde planea calcular los valores de búfer.

### <a name="calculate-and-apply-buffer-values"></a>Calcular y aplicar valores de búfer

Para los artículos en los que elige permitir que el sistema [calcule sus zonas de búfer automáticamente](#set-up-buffers), puede desencadenar el cálculo de valores de búfer siguiendo estos pasos.

1. Para el artículo de punto de desacoplo relevante, [configure el cálculo del búfer](#set-up-buffers), [calcule o introduzca plazos de entrega desacoplados](#calc-lead-time) y [calcule o introduzca el uso diario promedio](#calc-adu) para todos los períodos de tiempo relevantes, como se describió anteriormente en este artículo.
1. Abre la página **Cobertura de artículos** para su artículo de punto de desacoplo.
1. Seleccione la pestaña **Valores de búfer**, que ya debería mostrar una lista de períodos de tiempo.
1. Seleccione el período de tiempo en el que desea calcular valores de búfer. (Por lo general, este período de tiempo será el período que incluye hoy). La fila que seleccione ya debe tener valores distintos de cero en las columnas **Uso diario promedio** y **Plazo de entrega desacoplado**.
1. Edite el campo **Factor de ajuste de la demanda** para una o más filas según sea necesario. El sistema aplicará este factor al valor **Uso diario promedio** en todos los cálculos de búfer donde se utiliza ese valor. Este factor le permite ajustar la forma en que la demanda fluctúa por fecha (por ejemplo, para días festivos o artículos de temporada).
1. En el Panel de acciones, en la pestaña **Valores de búfer**, seleccione **Calcular las cantidades mínima, máxima y del punto de realizar nuevo pedido**. El sistema calcula y rellena las columnas **Mínimo calculado**, **Punto de realización de nuevo pedido calculado** y **Máximo calculado** en la cuadrícula de la página **Cobertura de artículos**.
1. Cuando haya terminado de revisar los valores calculados, debe aplicarlos. De lo contrario, no tendrán ningún efecto. Cuando aplica un cálculo para una o más filas, los valores de los campos **Mínimo calculado**, **Nuevo pedido calculado** y **Máximo calculado** se copian en las columnas **Mín.**, **Punto de hacer nuevo pedido** y **Máx.**, respectivamente. En el panel de acciones, en la pestaña **Valores de búfer**, en el grupo **Realizar acción**, seleccione uno de los siguientes botones:

    - **Aceptar todos los cálculos** – Aplica todos los valores calculados en la cuadrícula.
    - **Aceptar cálculos para las filas seleccionadas** – Aplica valores calculados solo para las filas seleccionadas.
    - **Descartar todos los cálculos** – Descarta todos los valores calculados para cantidades mínimas, cantidades máximas y puntos de realización de nuevo pedido en la cuadrícula.
    - **Descartar cálculos para filas seleccionadas** – Descarta todos los valores calculados para cantidades mínimas, cantidades máximas y puntos de realización de nuevo pedido para las filas seleccionadas.

### <a name="schedule-automatic-buffer-value-calculations"></a>Programar cálculos automáticos del valor del búfer

Una vez que haya configurado completamente los ajustes de DDMRP y haya confirmado que funcionan como esperaba, conviene probablemente configurar un trabajo por lotes para recalcular periódicamente el ADU y los valores de búfer relacionados según sea necesario, en función de los datos de consumo reales y/o las previsiones actualizadas. Este procedimiento se aplica solo a elementos en los que elige permitir que el sistema [calcule automáticamente sus zonas de búfer](#set-up-buffers).

Siga estos pasos para programar cálculos automáticos del valor del búfer.

1. Vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Calcular valores de búfer**.
1. En el cuadro de diálogo **Calcular valores de búfer**, establezca los siguientes campos:

    - **Calcular uso diario promedio** – Establezca esta opción en *Sí* para volver a calcular el ADU de los artículo del punto de desacoplo cada vez que se ejecuta el trabajo. Configúralo en *No* para omitir este cálculo. Por lo general, debe configurar esta opción en *Sí*.
    - **Calcular el plazo de entrega desacoplado** – Establezca esta opción en *Sí* para volver a calcular los plazos de entrega desacoplados cada vez que se ejecuta el trabajo. Configúralo en *No* para omitir este cálculo. Por lo general, debe configurar esta opción en *Sí*.
    - **Calcular valores de búfer** – Establezca esta opción en *Sí* para volver a calcular los valores del búfer cada vez que se ejecuta el trabajo. Configúralo en *No* para omitir este cálculo. Por lo general, debe configurar esta opción en *Sí*.
    - **Aceptar cálculos para el mínimo, el máximo y el punto de realizar nuevo pedido** – Establezca esta opción en *Sí* para aprobar y aplicar automáticamente los valores de búfer recalculados cada vez que se ejecuta el trabajo. Configúrela en *No* para dejar los valores recalculados sin aplicar. En este caso, los valores recalculados no surtirán efecto a menos que alguien los aplique manualmente posteriormente desde la página **Cobertura de artículos** de cada producto. Por lo general, debe configurar esta opción en *Sí*.
    - **Plan Maestro** – Seleccione un plan maestro que incluya los elementos que se verán afectados por el cálculo. El cálculo se aplicará a todos los artículos en el filtro del plan, que estará más limitado por la configuración de **Filtro** de este cuadro de diálogo.

1. Para limitar el conjunto de registros en el que debe ejecutarse este trabajo por lotes, en la ficha desplegable **Registros a incluir** seleccione el botón **Filtrar** para abrir el cuadro de diálogo **Consulta**. Este cuadro de diálogo funciona como otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia se deben realizar los cálculos seleccionados para los artículos seleccionados. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para agregar un nuevo trabajo a una cola por lotes para ejecución.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Revisar y recalcular los plazos de entrega desacoplados para todos los artículos

Siga estos pasos para revisar y recalcular todos los plazos de entrega desacoplados que están disponibles en su entidad legal (empresa).

1. Vaya a **Planificación maestra \> Planificación maestra \> DDMRP \> Plazo de entrega desacoplado**.
1. En la página **Plazo de entrega desacoplado**, navegue y filtre la lista según sea necesario para encontrar la información que está buscando. Para ver aún más información sobre un artículo, seleccione su vínculo en la columna **Número de artículo**.
1. Si desea recalcular el plazo de entrega desacoplado para cualquier artículo, seleccione el artículo y luego seleccione **Calcular el plazo de entrega desacoplado** en el Panel de acciones. Aparecerá el cuadro de diálogo **Calcular el plazo de entrega desacoplado**. Este cuadro de diálogo funciona igual que cuando [calcula los plazos de entrega desacoplados](#calc-lead-time) por el mismo artículo en la página **Cobertura de artículos**.
