---
title: Planificación basada en prioridades
description: Este tema describe la función de planificación basada en prioridades de Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 41c4f3e9bd41735b213743bd8b4cdd8d9657a073
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777898"
---
# <a name="priority-based-planning"></a>Planificación basada en prioridades

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Este tema describe la función de planificación basada en prioridades de Microsoft Dynamics 365 Supply Chain Management. La función agrega compatibilidad para la planificación basada en la demanda, que es un paso de la Planificación de requisitos de materiales basada en la demanda (DDMRP). La planificación basada en prioridades permite a Optimización de planificación generar pedidos planificados que se basan en prioridades de planificación en lugar de fechas de requisitos.

La planificación basada en prioridades le permite priorizar pedidos de reabastecimiento para garantizar que la demanda urgente tenga prioridad sobre la demanda menos importante. Por ejemplo, un pedido de reabastecimiento agotado tendrá prioridad sobre un pedido de reabastecimiento de relleno estándar. El sistema puede dividir automáticamente los pedidos más grandes en pedidos más pequeños separados donde las líneas de pedido se agrupan por prioridad. Luego, puede procesar primero todos los pedidos de alta prioridad.

Para obtener una descripción general rápida de esta función, vea el siguiente vídeo: [Compatibilidad de optimización de planificación para planificación basada en prioridades en Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Active la planificación basada en prioridades en su sistema

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de característica:** *Compatibilidad de MRP basada en prioridad para la Optimización de planificación*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Dónde y cómo se asignan las prioridades de planificación

La información de *Prioridad de planificación* sobre la oferta y la demanda es la columna vertebral de la planificación basada en prioridades. La prioridad de planificación define la importancia de una línea de oferta o demanda. Optimización de planificación lo usa cuando el campo **Código de cobertura** está configurado en *Prioridad*.

La prioridad de planificación suele ser un número entre 0 (cero) y 100, donde 0 representa la mayor importancia. Se muestra y se establece en el campo **Prioridad de planificación**. Puede encontrar este campo en las siguientes páginas: **Líneas de previsión de demanda**, **Detalles de pedido de venta**, **Detalles de pedido de compra**, **Detalles de pedido de transferencia** y **Detalles de pedido planificado**.

Cuando el campo **Código de cobertura** para el artículo o grupo de cobertura relevante se establece en *Prioridad*, Optimización de planificación equilibra la oferta con la demanda mediante el uso de un enfoque basado en la demanda, ya que calcula la prioridad de planificación y, para cada producto lanzado, considera los valores establecidos para los campos **Mínimo**, **Punto de hacer nuevo pedido** y **Máximo** en la página **Cobertura de artículos**.

> [!NOTE]
> El valor *Prioridad* está disponible para el campo **Código de cobertura** solo cuando la Optimización de planificación está habilitada.

Los *modelos de prioridad de planificación* controlan la prioridad de planificación y dividen los pedidos planificados por rango de prioridad. También le permiten establecer valores de prioridad de planificación predeterminados para cada tipo de oferta o demanda y definir el método de cálculo de prioridad.

## <a name="types-of-priority-calculation-methods"></a>Tipos de métodos de cálculo de prioridad

Cada modelo de prioridad de planificación tiene un ajuste **Método de cálculo de prioridad** que controla cómo la planificación maestra aplica la prioridad a los pedidos planificados. Los valores disponibles son *Porcentaje de cantidad máxima de inventario* y *Rangos de prioridad*. *Rangos de prioridad* representa una versión más avanzada del método *Porcentaje de cantidad máxima de inventario*.

### <a name="percent-of-maximum-inventory-quantity"></a>Porcentaje de cantidad máxima de inventario

En el método de cálculo *Porcentaje de cantidad máxima de inventario*, el cálculo de prioridad de suministro encuentra el *inventario total disponible* (flujo neto) actual como porcentaje del valor de **Cantidad máxima de inventario** que se establece para un artículo. A continuación, se crea un pedido planificado único por artículo y proveedor (a menos que se utilice la cantidad máxima de pedido para forzar una división). La prioridad de planificación del pedido se calcula como porcentaje del máximo.

Se usa la siguiente fórmula:

*Porcentaje del máximo* = (*Posición de flujo neto* × 100) ÷ *Valor máximo de cantidad de inventario de la cobertura del artículo*

En esta fórmula, *Posición de flujo neto* se calcula de la siguiente manera:

*Posición de flujo neto* = *Disponible* + *En pedido* - *Demanda calificada*

- *En pedido* es la oferta esperada.
- *Demanda calificada* representa las necesidades netas que tienen la fecha de requisito dentro del límite de tiempo de planificación.

Durante la ejecución de la planificación maestra, se crean nuevas órdenes planificadas cuando la posición de flujo neto es menor que la cantidad del punto de pedido para un artículo. La cantidad de pedido planificada es la diferencia entre el valor **Cantidad máxima de inventario** que se establece a nivel de artículo y la posición de flujo neto. La prioridad de pedido planificada se calcula como porcentaje de *posición de flujo neto* del valor de **Cantidad máxima de inventario**.

> [!NOTE]
> La prioridad calculada no puede ser negativa, incluso si la demanda supera la oferta total. Si la demanda supera la oferta total, la prioridad calculada se establece en 0 (cero).

### <a name="priority-ranges"></a>Intervalos de prioridad

El método de cálculo *Rangos de prioridad* es más avanzado que el método *Porcentaje de cantidad máxima de inventario* y se configura a nivel del modelo de prioridad de planificación. Se pueden crear varios pedidos de suministro planificadas nuevos para satisfacer la demanda por artículo. Las prioridades del suministro planificado siguen los valores que se definen en la cuadrícula **Planificación de rangos de prioridad** en la página **Modelos de prioridad de planificación**.

Las siguientes reglas adicionales entran en vigencia cuando el campo **Método de cálculo de prioridad** está configurado en *Rangos de prioridad*:

- Si la opción **Considerar la prioridad de la demanda** para el modelo de prioridad planificada se establece en *Sí*, la prioridad que se establece en cada línea de demanda limitará el intervalo de rango de prioridad. La prioridad de cualquier nuevo pedido planificado de suministro no será menor que la prioridad de la demanda. El valor superior del rango se considera un umbral con el que se compara el valor de prioridad de la demanda. Si la prioridad de la demanda está exactamente en el medio entre los valores de umbral superior de dos rangos, se seleccionará el rango que tenga la prioridad más alta (es decir, el valor de prioridad más bajo).
- Si el campo **Creación de pedidos planificados** para el modelo de prioridad planificada se establece en *Suministro único con la prioridad más importante*, solo se creará un suministro para cumplir hasta el máximo. La prioridad se establecerá en la prioridad del primer rango que activará un suministro.
- Si no hay inventario disponible, no hay oferta ni demanda, se utilizará la línea en la cuadrícula **Intervalos de prioridad de planificación** donde el campo **Cantidad inicial** está configurado en *Cero*.
- Si hay demanda, pero no hay inventario disponible ni oferta esperada, se utilizará la línea en la cuadrícula **Intervalos de prioridad de planificación** donde el campo **Cantidad inicial** está configurado en *Cero o menos*.
- Cuando se evalúa el intervalo del que forma parte la demanda, el ajuste de la opción **Considerar la prioridad de la demanda** seguirá teniendo efecto.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Diferencias entre cálculos tradicionales de escala de tiempo y planificación basada en prioridades

La planificación basada en prioridades se diferencia de los cálculos tradicionales de escala de tiempo en las siguientes formas:

- Todos los procesadores regulares de planificación previa todavía están en vigor. Estos preprocesadores incluyen diagrama de árbol de pedidos planificados aprobados frente a demanda de ventas, asignación de solicitudes de compra y lógica de reserva. Solo se procesa la demanda que estos preprocesadores no satisfacen.
- Durante el diagrama de árbol se considera todo el suministro, independientemente de su prioridad. Este suministro incluye el inventario disponible, la oferta liberada y la parte no fijada de los pedidos planificados aprobados.
- No se puede fijar la demanda de "días negativos" a la oferta durante todo el tiempo de cobertura.
- Cuando la oferta está vinculada a la demanda, la oferta que tiene la prioridad más alta (es decir, el valor de prioridad más bajo) se usa primero. Se considera que el suministro disponible tiene un valor de prioridad de 0 (cero). Por lo tanto, se consumirá como primer origen.
- Se crearán nuevas líneas de oferta planificadas de acuerdo con las reglas habituales para el tamaño mínimo del pedido, el tamaño máximo del pedido, el múltiplo de cantidad, etc.

## <a name="planning-priority-models"></a>Modelos de prioridad de planificación

Los *modelos de prioridad de planificación* se asignan a grupos de cobertura y controlan la prioridad de planificación de los pedidos planificados. Definen la lógica que determina cómo se calcula el valor de prioridad de planificación para cada pedido planificado y cómo se asigna la prioridad a pedidos planificados, líneas de oferta y líneas de demanda.

Para trabajar con los modelos de prioridad de planificación, vaya a **Planificación maestra \> Configuración \> Planificación de modelos de prioridad**. Como se analizó anteriormente, una de las configuraciones más importantes de un modelo es el valor **Método de cálculo de prioridad**. Esta configuración controla el método de cálculo que se utiliza cuando la planificación maestra asigna un valor de prioridad a los pedidos planificados.

> [!NOTE]
> Los modelos de prioridad de planificación se aplican en toda la organización, en todas las entidades legales.

### <a name="coverage-group"></a>Grupo de cobertura

Configure un nuevo grupo de cobertura que planea usar para la planificación basada en prioridades, como se describe en [Definir reglas de cobertura para artículos](../tasks/define-coverage-rules-items.md). Una vez que haya creado el grupo de cobertura, configure los siguientes campos adicionales:

- **Código de cobertura** - Seleccione *Prioridad* si el grupo de cobertura utilizará la planificación basada en prioridades.
- **Modelo de prioridad de planificación** - Seleccione cualquier modelo de prioridad de planificación de toda la organización.

### <a name="item-coverage"></a>Cobertura de artículos

Configure los ajustes de cobertura de elementos como se describe en [Configuración de cobertura](../coverage-settings.md). De forma predeterminada, el valor de **Código de cobertura** que se selecciona para el grupo de cobertura se copia a la configuración de cobertura del artículo. Sin embargo, puede reemplazar el valor predeterminado si es necesario. En algunos casos, el campo **Código de cobertura** para un registro de cobertura de artículo se establece en *Planificación*, pero no se define ningún modelo de prioridad de planificación para el grupo de cobertura relacionado. En estos casos, cualquier modelo donde el campo **Método de cálculo de prioridad** está configurado en *Porcentaje de la cantidad máxima de inventario* y el campo **Creación de pedidos planificados** está configurado en *Suministro único con la prioridad más importante* se aplicará de forma predeterminada.

Establezca el campo **Código de cobertura** en *Prioridad* para convertir en disponible el campo **Punto de hacer nuevo pedido** en la configuración de cobertura del artículo. En este campo, ingrese la cantidad de punto de pedido que el sistema debe usar mientras determina cuándo colocar los pedidos planificados que tienen un valor de **Código de cobertura** de *Prioridad*.

La cantidad del punto de pedido a menudo se calcula como la demanda durante el tiempo de entrega más un valor mínimo (stock de seguridad). Debe ser un valor entre los valores **Mínimo** y **Máximo**.

Por ejemplo, puede configurar los campos de la siguiente manera:

- **Mínimo:** *10*
- **Punto de hacer nuevo pedido:** *45*
- **Máximo:** *60*

Para este ejemplo, la cantidad de punto de pedido se basa en un plazo de entrega de siete días y un uso diario promedio de 5. Por lo tanto, la demanda durante el plazo de entrega es de 35. Luego se agrega el valor mínimo de 10 (stock de seguridad) para obtener un punto de pedido de 45. Cuando se utiliza esta configuración, se sugerirá el suministro cuando el nivel disponible proyectado sea inferior a 45. La prioridad del pedido se basará en la configuración de la prioridad de planificación.

### <a name="manage-planning-priority-models"></a>Administrar modelos de prioridad de planificación

Para trabajar con sus modelos de prioridad de planificación. siga estos pasos.

1. Vaya a **Planificación maestra \> Configuración \> Modelos de prioridad de planificación**.
1. Seleccione un modelo existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear un nuevo modelo.
1. En el encabezado del registro, establezca los siguientes campos:

    - **Nombre**: escriba un nombre para el modelo. El nombre debe ser único en todas las entidades legales de su organización.
    - **Descripción**: escriba una descripción del modelo.
    - **Método de cálculo de prioridad** Seleccione uno de los valores siguientes:

        - *Intervalos de prioridad* - Cuando selecciona este valor, la cuadrícula **Intervalos de prioridad de planificación** está disponible. En ella debe establecer varios intervalos de prioridad para definir el valor de prioridad de planificación.
        - *Porcentaje de cantidad máxima de inventario* - Calcule el valor de prioridad de planificación como porcentaje basado en el nivel de inventario proyectado sobre la cantidad máxima de inventario.

    - **Creación de pedido planificado** - Este campo está disponible cuando el campo **Método de cálculo de prioridad** está configurado en *Intervalos de prioridad*. Seleccione uno de los siguientes valores:

        - *Suministro único con la prioridad más importante* - No divida los pedidos planificados en función del intervalo de prioridad. La prioridad de planificación para un pedido planificado se basa en el intervalo de prioridad más importante (es decir, el valor de prioridad de planificación más bajo).
        - *Dividir según rangos de prioridad* - Divida la demanda en varios pedidos planificados, según los rangos de prioridad de planificación. La prioridad de planificación para pedidos planificados individuales se define por la prioridad de planificación del rango de prioridad de planificación relacionado.

    - **Considerar la prioridad de la demanda** - Establezca esta opción en *Sí* para limitar la prioridad de un nuevo pedido planificado que se crea para la oferta. (La prioridad no será menor que la prioridad de la demanda relacionada). Si configura esta opción en *No*, la prioridad del pedido de demanda no se considerará cuando se calcule la prioridad del pedido de suministro.

1. Si configura el campo **Método de cálculo de prioridad** como *Rangos de prioridad*, utilice los botones **Agregar** y **Eliminar** en la barra de herramientas de la ficha desplegable **Planificación de rangos de prioridad** para agregar o eliminar filas de rango de prioridad según lo requiera. Si existen varias filas e inserta una nueva fila, la prioridad de planificación se establecerá automáticamente en el promedio de la fila seleccionada y la fila superior. Para cada fila, establezca los siguientes campos:

    - **Prioridad de planificación** - Ingrese cualquier valor entre 0,00 y 100,00. Este valor representa la prioridad de planificación que se utiliza para la fila. El valor de prioridad más bajo representa la prioridad más alta. Se asigna un valor predeterminado, pero puede cambiarlo si es necesario. El mismo valor de **Prioridad de planificación** no se puede utilizar para más de un intervalo de prioridad de planificación en el mismo modelo de prioridad de planificación.
    - **Descripción** - Introduzca una descripción del intervalo de prioridad de planificación (como *Punto de hacer nuevo pedido* en Máximo).
    - **Cantidad inicial** - El límite inferior del rango de prioridad de planificación. Este valor es de solo lectura y se basa en los valores de **Cantidad final** y **Porcentaje de cantidad final** para el rango de prioridad de planificación anterior.
    - **Cantidad final** - Seleccione el campo de la cobertura del elemento que debe usarse para definir el límite superior del rango. Los siguientes valores son compatibles e influirán en el valor de **Cantidad inicial** del siguiente rango:

        - *Cero* - Este valor representa un rango de negativo a cero (*Cero o menos* para *Cero*). Para las filas donde se selecciona este valor, el campo **Porcentaje de cantidad final** es de solo lectura y siempre se establece en *100* por ciento.
        - *Cantidad mínima de inventario* - Este valor representa el valor **Mínimo** de un artículo en la página **Cobertura de artículos**. Para las filas donde se selecciona este valor, el campo **Porcentaje de cantidad final** es editable y se utiliza para establecer el valor de **Cantidad inicial** del siguiente rango (por ejemplo, a *80% de la cantidad mínima de inventario*).
        - *Punto de hacer nuevo pedido* - Este valor representa el valor de **Punto de hacer nuevo pedido** de un artículo en la página **Cobertura de artículos**. Para las filas donde se selecciona este valor, el campo **Porcentaje de cantidad final** es editable y se utiliza para establecer el valor de **Cantidad inicial** del siguiente rango (por ejemplo, a *80% del punto de hacer nuevo pedido*).
        - *Cantidad máxima de inventario* - Este valor representa el valor **Máxima** de un artículo en la página **Cobertura de artículos**. Para las filas donde se selecciona este valor, el campo **Porcentaje de cantidad final** es editable y se utiliza para establecer la **Cantidad inicial** del siguiente rango (por ejemplo, a *80% de la cantidad mínima de inventario*).
        - *Infinito* - Este valor representa un nivel superior infinito del rango (*Infinito o menos* para *Infinito*). Para las filas donde se selecciona este valor, el campo **Porcentaje de cantidad final** es de solo lectura y siempre se establece en *100* por ciento.

    - **Porcentaje de cantidad final** - Ingrese un valor porcentual que se utiliza para calcular el límite superior del rango de prioridad de planificación, basado en el valor que se selecciona en el campo **Cantidad final**. Por ejemplo, si el campo **Cantidad final** está configurado en *Cantidad mínima de inventario*, y el campo **Porcentaje de cantidad final** está configurado en *50*, el límite superior será el 50 por ciento de la cantidad mínima de inventario de la cobertura del artículo relacionado.

1. En la ficha desplegable **Valores predeterminados de prioridad de planificación**, establezca los campos que necesite para definir las prioridades de planificación predeterminadas para cada tipo de línea de oferta o demanda (pedido de venta, pedido de compra, pedido de transferencia o previsión de demanda). Solo se pueden ingresar valores positivos.

## <a name="view-and-maintain-planning-priority"></a>Ver y mantener prioridad de planificación

La prioridad de planificación se muestra y se establece en el campo **Prioridad de planificación**. Puede encontrar este campo en las páginas que se enumeran en la siguiente tabla. La prioridad se establece como un número entre 0 (cero) y 100, donde 0 representa la mayor importancia.

| Página | Ubicación del campo | Origen del valor |
|---|---|---|
| Líneas de previsión de la demanda | <p>Pestaña **Artículo**</p><p>(Seleccione una línea en la sección superior y luego seleccione la pestaña **Artículo**.)</p> | Valor predeterminado o valor que se establece manualmente |
| Detalles del pedido de ventas | <p>Pestaña **Entrega** en la ficha desplegable **Detalles de línea**</p><p>(Seleccione una línea en la ficha desplegable **Líneas de pedido de venta** y luego, en la ficha desplegable **Detalles de la línea**, seleccione la pestaña **Entrega**.)</p> | Valor predeterminado, valor de empresas vinculadas o valor que se establece manualmente |
| Detalles del pedido de compra | <p>Pestaña **Entrega** en la ficha desplegable **Detalles de línea**</p><p>(Seleccione una línea en la ficha desplegable **Líneas de pedido de compra** y luego, en la ficha desplegable **Detalles de la línea**, seleccione la pestaña **Entrega**.)</p> | Valor que se establece durante la puesta en firme de pedidos planificados, valor de empresas vinculadas o valor que se establece manualmente |
| Detalles de pedido de transferencia | <p>Pestaña **Entrega** en la ficha desplegable **Detalles de línea**</p><p>(Seleccione una línea en la ficha desplegable **Líneas de pedido de transferencia** y luego, en la ficha desplegable **Detalles de la línea**, seleccione la pestaña **Entrega**.)</p> | Valor que se establece durante la puesta en firme de pedidos planificados o valor que se establece manualmente |
| Detalles del pedido planificado | Ficha desplegable **General** | Valor que se calcula durante la planificación maestra o valor que se establece manualmente |

### <a name="intercompany-trade"></a>Comercio entre empresas vinculadas

El valor de **Prioridad de planificación** de las líneas de oferta y demanda entre empresas se comparte entre las entidades vinculadas. La modificación en cualquier lado se reflejará en la línea de pedido vinculada.

A continuación, encontrará algunos ejemplos:

- Un usuario cambia la prioridad de planificación para una línea de pedido de ventas de empresas vinculadas de 20 a 30. Este cambio se refleja en la línea de pedido de compra de empresas vinculadas.
- Un usuario cambia la prioridad de planificación para una línea de pedido de compras de empresas vinculadas de 40 a 50. Este cambio se refleja en la línea de pedido de venta de empresas vinculadas.
