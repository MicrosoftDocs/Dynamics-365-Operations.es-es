---
title: Márgenes de seguridad
description: Este artículo describe cómo funcionan los márgenes de seguridad durante la planificación maestra.
author: t-benebo
ms.date: 08/09/2022
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
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 87b38276a2723374969a67c5413dde15537d04ec
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740451"
---
# <a name="safety-margins"></a>Márgenes de seguridad

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo funcionan los márgenes de seguridad durante la planificación maestra.

## <a name="safety-margins-overview"></a>Descripción general de los márgenes de seguridad

El propósito de los márgenes de seguridad es habilitar una configuración que proporcione un tiempo de reserva más allá del tiempo de entrega normal. Por ejemplo, cuando el material debe desembalarse o inspeccionarse después de que llega del proveedor, no puede simplemente agregar el tiempo adicional al tiempo de espera de la compra, porque este enfoque le dará tiempo de reserva adicional al proveedor. En este ejemplo, el margen de recepción se puede utilizar para garantizar que el proveedor entregue antes. Este enfoque proporciona un tiempo de reserva para que las mercancías se puedan manipular internamente.

Hay tres tipos de pedidos de márgenes de seguridad:

- **Reordenar margen**: el tiempo de reserva para realizar el pedido de suministro
- **Margen de recepción**: el tiempo de reserva para manejar el suministro entrante
- **Margen de emisión**: el tiempo de reserva para el manejo de envíos

La siguiente ilustración muestra cómo se aplican estos márgenes de seguridad a lo largo del tiempo.

![Márgenes de seguridad.](media/safety-margins-1.png)

Todos los márgenes se definen en días. Un valor predeterminado, *0* (cero) indica que no se aplican márgenes. Si configura varios márgenes, todos se suman al tiempo total del suministro *fecha de pedido* a la demanda *fecha de requisito*. Por ejemplo, una configuración no tiene tiempo de espera y los tres tipos de margen se establecen en un día. En este caso, habrá tres días entre la fecha del pedido de suministro y la fecha del requisito de demanda, por lo que si la fecha de pedido es el 1 de julio, la fecha de requisito sería el 4 de julio.

### <a name="receipt-margin"></a>Margen de recepción

El margen de recepción es probablemente el más utilizado de los tres márgenes de seguridad. Se aplica a la *fecha de entrega* y hacia atrás desde la *fecha de requisito*. En otras palabras, los productos deben recibirse en el número especificado de días de margen de recepción antes de que se requieran.

La siguiente ilustración destaca el margen de recepción.

![Margen de recepción.](media/safety-margins-2.png)

El margen de recepción se usa generalmente como una reserva para asegurar el tiempo para el registro del almacén u otros procesos que requieren mucho tiempo y que no se capturan como parte del tiempo de entrega general en el sistema. Para las compras, una ventaja es que la *fecha de entrega* del pedido de compra se avanza en consecuencia. Si aumenta el tiempo de entrega en lugar de utilizar un margen de seguridad, se le pedirá al proveedor que entregue en el último minuto.

Observe que el margen del recibo no cambia la *fecha de requisito* del suministro. Por lo tanto, el margen de recepción no es directamente visible cuando se comparan las fechas de los requisitos para la oferta y la demanda (por ejemplo, en la página **Requisitos netos**). Por ejemplo, si el margen de recepción se establece en cuatro días, y se programa una línea de pedido de compra para su recepción el día quince del mes, la programación maestra calcula la fecha de recepción ajustada el día diecinueve del mes.

Tenga en cuenta que no se aplica un margen de recepción cuando el inventario disponible se utiliza como suministro. Se supone que todo el inventario disponible está disponible de inmediato, independientemente de cuándo se recibió realmente.

### <a name="reorder-margin"></a>Días de administración

La siguiente ilustración destaca los días de administración.

![Días de administración.](media/safety-margins-3.png)

Los días de administración se agregan antes del plazo del artículo para todos los pedidos planificados durante la programación maestra. Por lo tanto, asegura tiempo adicional para que se realice un pedido de suministro. Este margen se usa generalmente como una reserva para asegurar el tiempo para los procesos de aprobación u otros procesos internos que se requieren durante la creación de pedidos de suministro. Los días de administración se colocan entre la *fecha de pedido* y *fecha de inicio* del suministro.

### <a name="issue-margin"></a>Días de emisión

La siguiente ilustración destaca los días de emisión.

![Días de emisión.](media/safety-margins-4.png)

Los días de emisión se deducen de la fecha de requisito de demanda durante la planificación maestra. Ayuda a garantizar que tenga tiempo para reaccionar y enviar los pedidos entrantes. Este margen se utiliza normalmente como una reserva para asegurar el tiempo de envío y los procesos de salida del almacén relacionados.

Tenga en cuenta que cuando se aplican días de emisión, las fechas de los requisitos de oferta y demanda relacionados no coinciden. En cambio, se diferencian por los días de emisión, porque los días de emisión se suman entre la *fecha de requisito* del suministro y *fecha de requisito* de la demanda.

## <a name="set-up-safety-margins"></a>Configurar márgenes de seguridad

### <a name="turn-safety-margins-on-or-off"></a>Activar o desactivar los márgenes de seguridad

Para usar esta característica, debe estar activada para su sistema. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Márgenes de Optimización de planificación* en el espacio de trabajo [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="define-safety-margins"></a>Definir márgenes de seguridad

Los márgenes de seguridad tienen una configuración flexible. Se pueden configurar en el *grupo de cobertura* y el *plan maestro*. Es importante que comprenda que los márgenes se suman uno sobre otro. Por ejemplo, un margen de recepción de dos días en el grupo de cobertura y tres días en el plan maestro producirá un margen de recepción efectivo de cinco días.

La capacidad de establecer el margen en el plan maestro puede ser útil cuando desea simular plazos de entrega más largos o hay incertidumbre para un plan específico, pero sin afectar la planificación diaria.

#### <a name="coverage-group-safety-margins"></a>Márgenes de seguridad de grupos de cobertura

Para aplicar un margen de seguridad a un grupo de cobertura, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Grupos de cobertura**.
1. En el panel de la lista, seleccione el grupo de cobertura deseado.
1. En la ficha desplegable **Otro**, en la sección **Márgenes de seguridad en días**, use los siguientes campos para establecer los márgenes de seguridad requeridos (en días):

    - Días de recepción sumados a la fecha de requisito
    - Días de emisión deducidos de la fecha de requisito
    - Días de administración agregados al plazo del artículo

#### <a name="master-plan-safety-margins"></a>Márgenes de seguridad del plan maestro

Para aplicar un margen de seguridad a un plan maestro, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. En el panel de la lista, seleccione el plan maestro deseado.
1. En la ficha desplegable **Márgenes de seguridad en días**, use los siguientes campos para establecer los márgenes de seguridad requeridos (en días):

    - Días de recepción sumados a la fecha de requisito
    - Días de emisión deducidos de la fecha de requisito
    - Días de administración agregados al plazo del artículo

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Definir si los cálculos se basan en días naturales o días laborales

Puede establecer todos los márgenes de seguridad para que se calculen en función de los días naturales o laborales.

1. Vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra**.
1. En la pestaña **General**, en la sección **Márgenes de seguridad en días**, configure la opción **Días laborables** en *Sí* para calcular los márgenes en función de los días laborables. Establezca la opción en *No* para calcular márgenes basados en días naturales.

Por ejemplo, un calendario está abierto de lunes a viernes y cerrado de sábado a domingo. Si hay un margen de recepción de un día, una fecha de requisito un lunes produce una fecha de entrega el viernes anterior, porque el sábado y el domingo no son días hábiles.

El calendario que se utiliza para determinar los días laborables depende de la configuración y el tipo de suministro. Puede ser controlado por los calendarios del grupo de cobertura, el almacén y el proveedor.

> [!NOTE]
> Si *almacén* no es parte de la dimensión de cobertura (en otras palabras, la planificación se basa únicamente en *sitio*), el calendario del almacén no se utiliza.

El sistema puede manejar una configuración donde se definen uno o más calendarios. Las siguientes subsecciones describen las posibles combinaciones que se pueden utilizar para controlar el resultado.

#### <a name="calendar-that-is-used-for-the-duration"></a>Calendario que se usa por la duración

Los calendarios definidos controlan el tiempo de entrega total real en días naturales, desde la fecha del pedido de suministro hasta la fecha del requisito de la demanda. Se utiliza la siguiente priorización de calendario:

- **Plazo de entrega de la compra**: solo se considera el calendario del grupo de cobertura.
- **Margen de recibo**: se utiliza el calendario del grupo de cobertura, si está definido. Si no, se usará el calendario de almacén.
- **Días de emisión**: se utiliza el calendario del grupo de cobertura, si está definido. Si no, se usará el calendario de almacén.
- **Margen del pedido**: solo se considera el calendario del grupo de cobertura.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Calendario que se usa por la fecha final

Se aplican las siguientes reglas para determinar si el motor de planificación puede utilizar una fecha determinada para un tipo de fecha determinado:

- **Fecha de recibo de compra**: se utiliza el calendario del proveedor, si está definido. De lo contrario, se utiliza el calendario del grupo de cobertura, si está definido. Si no se define ninguno de esos calendarios, se utiliza el calendario del almacén.
- **Fecha de recepción de la trasferencia**: se utiliza el calendario del grupo de cobertura, si está definido. Si no, se usará el calendario de almacén.
- **Fecha de recepción del producto**: se utiliza el calendario del grupo de cobertura, si está definido. Si no, se usará el calendario de almacén.
- **Día abierto de emisión de demanda**: se utiliza el calendario del almacén, si está definido. De lo contrario, se utiliza el calendario del grupo de cobertura.
- **Día abierto del pedido**: se utiliza una combinación (intersección) del calendario del grupo de cobertura y el calendario del proveedor. Ambos calendarios deben estar abiertos para usar la fecha. Si solo uno de los calendarios no se define, ese calendario se utilizar de forma independiente.

#### <a name="calendar-setup-overview-matrix"></a>Matriz de descripción general de la configuración del calendario

La siguiente ilustración presenta una matriz que resume qué calendarios se aplican cuando se calculan los márgenes de seguridad. (Seleccione la imagen para abrir una versión de alta resolución). Las siguientes abreviaturas y colores se utilizan para indicar dónde se especifica cada tipo de calendario:

- **Grupo de cobertura (CG)**: verde
- **Almacén (WH)**: amarillo
- **Proveedor (V)**: azul

[![Matriz de descripción general de la configuración del calendario.](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Calcular retrasos

Los tres tipos de márgenes de seguridad se incluyen cuando el sistema determina si un pedido se retrasa.

Por ejemplo, un artículo tiene un plazo de entrega de un día y un margen de recepción de tres días. Un pedido de venta para este artículo se establece como se requiere hoy. En este caso, el retraso se calcula como *tiempo de espera* + *margen de recepción* = cuatro días. Por tanto, si hoy es 14 de agosto, los cuatro días de retraso producen una entrega el 18 de agosto. En la ilustración siguiente se muestra este ejemplo.

![Ejemplo de cálculo de retraso.](media/safety-margins-delays.png)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]