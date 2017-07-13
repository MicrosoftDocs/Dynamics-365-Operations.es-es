---
title: "Gráfico de Gantt para la programación de trabajos"
description: "El gráfico de Gantt está diseñado para permitir a los planificadores de producción controlar y optimizar el plan de producción. El gráfico de Gantt hace que el flujo de operaciones sea transparente y facilita el ajuste de la previsión de producción mientras tiene en cuenta la escasez de materiales o recursos. Esto ayuda a los planificadores a realizar el mejor uso de los recursos disponibles, minimizar el trabajo en curso y optimizar los tiempos de capacidad de proceso para pedidos de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 55631c4d588c699b9e47f73190d5b01d6da3b9ec
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# Gráfico de Gantt para la programación de trabajos
<a id="gantt-chart-for-job-scheduling" class="xliff"></a>

[!include[banner](../includes/banner.md)]


El gráfico de Gantt está diseñado para permitir a los planificadores de producción controlar y optimizar el plan de producción. El gráfico de Gantt hace que el flujo de operaciones sea transparente y facilita el ajuste de la previsión de producción mientras tiene en cuenta la escasez de materiales o recursos. Esto ayuda a los planificadores a realizar el mejor uso de los recursos disponibles, minimizar el trabajo en curso y optimizar los tiempos de capacidad de proceso para pedidos de producción.

El gráfico de Gantt está diseñado para permitir a los planificadores de producción controlar y optimizar el plan de producción. El gráfico de Gantt hace que el flujo de operaciones sea transparente y facilita el ajuste de la previsión de producción mientras tiene en cuenta la escasez de materiales o recursos. Esto ayuda a los planificadores a realizar el mejor uso de los recursos disponibles, minimizar el trabajo en curso y optimizar los tiempos de capacidad de proceso para pedidos de producción.

Un gráfico de Gantt es una representación visual de actividades programadas dentro de un intervalo de tiempo definido. Las actividades se programan en recursos cuya capacidad viene definida por un calendario de capacidad. Los siguientes tipos de actividades se pueden mostrar en el gráfico de Gantt.

-   Trabajos de los pedidos de producción que son trabajos programados.
-   Trabajos de los pedidos de producción planificados.
-   Actividades de proyecto de trabajos programados de tipo Previsiones de horas.

El gráfico de Gantt se puede abrir en dos vistas diferentes, **Vista de pedidos** y **Vista de recursos**[.](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true)En la **Vista de pedidos**, las actividades se agrupan en pedidos de producción. Esto puede ser útil, por ejemplo, si desea mantener una visión general de todos los trabajos que pertenecen a los mismos pedidos. En la **Vista de recursos**, todos los trabajos se agrupan en recursos individuales. Esta vista puede ser útil al optimizar el plan en un nivel del recurso, por ejemplo, una máquina o un grupo de máquinas. Los gráficos de Gantt mostrados en las ilustraciones siguientes muestran la **Vista de pedidos** y la **Vista de recursos** con estos elementos clave:

1.  Actividad del gráfico de Gantt
2.  Icono de escasez de material
3.  Icono de disponibilidad de material
4.  Icono de fecha de entrega del pedido
5.  Barra de capacidad

## Vista de pedidos
<a id="order-view" class="xliff"></a>

[![orderview](./media/orderview.png)](./media/orderview.png)

## Vista de recursos
<a id="resource-view" class="xliff"></a>
[![resview](./media/resview.png)](./media/resview.png)

## Actividades
<a id="activities" class="xliff"></a>
Las actividades aparecen como barras y se organizan en una cuadrícula de la escala de tiempo con una hora inicial y final programada, haciendo que la longitud de las barras sea proporcional al tiempo necesario para completar la actividad. Las actividades se muestran según una escala de tiempo. Puede ajustar la escala de tiempo en el menú donde selecciona una fecha inicial y final y una unidad de tiempo, por ejemplo, horas o días. Ajustando la escala de tiempo puede establecer el foco en un intervalo de tiempo en el que desee gestionar actividades. 

Para obtener una mejor visión general, hay diferentes opciones para controlar el color de las actividades. Puede configurar un color individual de las actividades, usar el color de tema que es el tema de color general utilizado para la aplicación o configurar el color de cuyo control se encargará el código de color para pedidos de producción. 

El intervalo de tiempo para las actividades tiene una sombra de fondo. Los períodos con una sombra blanca indican un intervalo de tiempo con capacidad definida en el recurso para la actividad, mientras que los períodos con una sombra gris indican intervalos de tiempo sin capacidad definida. 

En el lado izquierdo del gráfico hay información adicional sobre la actividad, por ejemplo, el recurso en el que está programada la actividad y el número de pedido de producción. La conexión entre trabajos que pertenecen al mismo pedido se muestra con una flecha. 

Puede obtener más información sobre una actividad en el cuadro de diálogo de la actividad. Para abrir el cuadro de diálogo, haga doble clic en la actividad o seleccione el menú de **información**. En el cuadro de diálogo de la actividad puede ver la fecha inicial y final programada e información de tiempo sobre los materiales que la actividad tiene previsto consumir. 

Las actividades se pueden agrupar en niveles de agrupación. Los niveles de agrupación son jerárquicos y se pueden usar para crear una agrupación lógica de actividades. Por ejemplo, si tiene un diseño en el que las actividades de fabricación se agrupan por Sitio, Unidades de producción, Grupos de recursos y Recursos, puede usar los niveles de agrupación para agrupar las actividades según ese diseño. Los niveles de agrupación se pueden expandir y contraer en el nivel de agrupación individual o para todos los niveles del gráfico con los botones **Expandir todo** y **Contraer todo** del menú. También puede configurar los niveles de agrupación que se expandirán o contraerán al abrirse el gráfico.

### Disponibilidad de material
<a id="material-availability" class="xliff"></a>

El gráfico de Gantt se puede configurar para proporcionar el planificador con información detallada sobre el estado del material para las actividades individuales. Por ejemplo, esto puede resultar útil si el material se retrasa y afecta al plan de producción. En este caso, los problemas de material se resaltarán en el gráfico de Gantt para ayudar al planificador a comprender las consecuencias y crear los ajustes necesarios. 

Un trabajo aparecerá con un icono de escasez de material si la fecha inicial de programación del trabajo es posterior a la fecha disponibilidad de material para los materiales consumidos por el trabajo. La fecha de disponibilidad de material se calcula en función de la información del diagrama de árbol del plan maestro dinámico. El icono de escasez de material aparecerá por ejemplo en un trabajo que consume un material vinculado con un pedido de compra cuya recepción es posterior a la fecha inicial planificada del trabajo.

### Indicador de fecha de disponibilidad de material
<a id="indicator-of-material-availability-date" class="xliff"></a>

Al configurar el gráfico para mostrar trabajos con escasez de materiales, también puede aparecer un icono para mostrar la fecha de disponibilidad de material para el trabajo. El icono solo se mostrará si la fecha de disponibilidad de material se encuentra dentro del intervalo de tiempo definido del gráfico. Si la fecha de disponibilidad de material se encuentra fuera del intervalo de tiempo definido, puede recuperarse información de disponibilidad de material más detallada de la lista de materiales del cuadro de diálogo del trabajo. En la lista también hay un icono que muestra los materiales entregados tarde para el trabajo. Puede volver a programar un trabajo mediante la fecha de disponibilidad de material como fecha inicial.

### Indicador de fecha de entrega del pedido
<a id="indicator-of-order-delivery-date" class="xliff"></a>

Este icono indica la fecha de entrega de un pedido de producción. El icono solo está visible en la Vista de pedidos.

### Barra de capacidad
<a id="capacity-bar" class="xliff"></a>

Puede configurar el gráfico para mostrar una barra de capacidad de recursos. Esta barra proporciona una visión general de la capacidad de recursos de una actividad en el intervalo de tiempo definido del gráfico. La barra de capacidad no se muestra en los períodos de tiempo en los que no se reserva el recurso. En los períodos en los que se reserva el recurso hasta cubrir la capacidad, la barra de capacidad se muestra como barra sólida. En los períodos en los que se satura el recurso, la barra se mostrará más gruesa y en rojo. Por ejemplo, si dos trabajos se superponen, la barra de capacidad indicará una saturación del intervalo de tiempo en el que existe una superposición. La barra de capacidad se actualiza dinámicamente al programar un trabajo. Habilita la barra de capacidad en el menú **Mostrar barra de capacidad**. Solo se puede mostrar en la **Vista de recursos**. Si desea obtener una visión más detallada de la carga de capacidad de un recurso, use el gráfico **Carga de capacidad**, que se puede abrir desde el menú o el menú contextual para una actividad seleccionada.

## Programación de trabajos en el gráfico de Gantt
<a id="job-scheduling-in-the-gantt-chart" class="xliff"></a>
El gráfico de Gantt ofrece diferentes opciones para realizar ajustes al plan de producción. En el gráfico de Gantt, puede volver a programar actividades como interacción de arrastrar y colocar o desde un menú de la programación. En el proceso de planificación, puede tener en cuenta la capacidad de recursos, las capacidades de recursos y las restricciones de materiales.

### Programar un trabajo como interacción de arrastrar y colocar
<a id="schedule-a-job-as-a-drag-and-drop-interaction" class="xliff"></a>

Puede volver a programar el trabajo dentro del intervalo de tiempo definido como interacción de arrastrar y colocar. Solo puede volver a programar el trabajo en el mismo recurso, mientras que solo puede programar un trabajo al mismo tiempo.

### Programar un trabajo desde el menú
<a id="schedule-a-job-from-the-menu" class="xliff"></a>

En el menú **Programar trabajos**, puede programar uno o varios trabajos seleccionados en el gráfico en función de una dirección de programación y una fecha y hora de programación. Existen tres direcciones disponibles de programación.

-   A partir de la fecha de programación
-   Regresivo a partir de la fecha de programación
-   Reenviar a partir de fecha de disponibilidad de material

No es posible programar un trabajo fuera del intervalo de tiempo definido del gráfico de Gantt. Si lo hace, el trabajo se dejará desprogramado y recibirá el mensaje de error “No se pudo programar el trabajo en el período de tiempo cargado”.

### Programar trabajos anteriores
<a id="schedule-previous-jobs" class="xliff"></a>

En una red de actividades, como los trabajos que pertenecen al mismo pedido de producción, puede usar la función **Programar trabajos anteriores** para programar los trabajos anteriores en relación con un trabajo seleccionado en la red. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado.

<table>
<tr>
<td>
Antes
</td>
<td rowspan=2>
<img src='./media/schprevjob3.png'/>
</td>
</tr>
<tr>
<td>
Posterior
</td>
</tr>
</table>

### Programar trabajos posteriores
<a id="schedule-next-jobs" class="xliff"></a>

Puede usar la función **Programar trabajos posteriores** para programar los trabajos posteriores relativos a un trabajo seleccionado en una red de actividades. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado.

<table>
<tr>
<td>
Antes
</td>
<td rowspan=2>
<img src='./media/schnxtjob.png'/>
</td>
</tr>
<tr>
<td>
Posterior
</td>
</tr>
</table>

### Programación en torno al trabajo
<a id="schedule-around-job" class="xliff"></a>

Puede usar la función **Programación en torno al trabajo** para programar el trabajo posterior y el trabajo anterior relativos a un trabajo seleccionado en una red de actividades. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado.

<table>
<tr>
<td>
Antes
</td>
<td rowspan=2>
<img src='./media/scharoundjob1.png'/>
</td>
</tr>
<tr>
<td>
Posterior
</td>
</tr>
</table>

### Organizar trabajos
<a id="arrange-jobs" class="xliff"></a>

Puede usar la función **Organizar** para organizar actividades seleccionadas en el mismo recurso. Estas actividades pueden estar en la misma red de actividades, pero también pueden pertenecer a redes distintas. Cuando use la función Organizar, los espacios de tiempo entre las actividades seleccionadas se eliminarán. Puede utilizar esta función para optimizar el uso de capacidad de los recursos.

<table>
<tr>
<td>
Antes
</td>
<td rowspan=2>
<img src='./media/arrangejobs1.png'/>
</td>
</tr>
<tr>
<td>
Posterior
</td>
</tr>
</table>

### Reasignar actividades de un recurso a otro
<a id="reassign-activities-from-one-resource-to-another" class="xliff"></a>

Puede reasignar un trabajo de un recurso a otro. Esto puede resultar útil en situaciones en las que un equipo se encuentra fuera de servicio o está saturado, y se debe encontrar otro recurso disponible que pueda realizar el trabajo.

### Reasignación de una actividad como interacción de arrastrar y colocar
<a id="reassigning-an-activity-as-a-drag-and-drop-interaction" class="xliff"></a>

En el Vista de **recursos**, puede reasignar una actividad un recurso diferente del gráfico de Gantt como interacción de arrastrar y colocar. Esto se hace seleccionando la fila en la que está programada la actividad. Una vez seleccionada la fila, puede arrastrarla al recurso del gráfico agrupado en un nivel de agrupación de recursos diferente.

### Reasignación de una actividad desde el menú Programar trabajos
<a id="reassigning-an-activity-from-the-schedule-jobs-menu" class="xliff"></a>

Puede reasignar un trabajo desde el cuadro de diálogo **Programar trabajo** abierto desde el menú **Programar trabajo**. Desde este menú solo puede reasignar un trabajo a un recurso ya cargado en el gráfico de Gantt. Si solo selecciona un trabajo, el menú desplegable para el recurso se ordenará por recursos aplicables. Si selecciona más trabajos, no habrá información sobre recursos aplicables desde la lista de recursos.

## Cargar recursos adicionales al gráfico de Gantt
<a id="load-additional-resources-to-the-gantt-chart" class="xliff"></a>
En la **Vista de recursos**, tiene la opción de cargar recursos adicionales en el gráfico de Gantt. Esto puede ser de utilidad si desea encontrar un recurso alternativo para un trabajo programado en un equipo saturado o desglosado. En la página **Cargar recursos adicionales**, obtendrá una lista de recursos eficaces con respecto a la fecha a partir de la fecha de apertura de la lista. Los recursos aplicables, relativos a un trabajo seleccionado en el gráfico de Gantt, se enumerarán en primer lugar. Si tiene varios trabajos seleccionados, antes de abrir la lista, no aparecerá ninguna indicación de los recursos aplicables. En la página **Cargar recursos adicionales**, puede seleccionar uno o varios recursos, que se cargarán en el gráfico de Gantt al confirmar su selección. Si no hay trabajos programados en el recurso seleccionado en el intervalo de tiempo del gráfico de Gantt, el recurso se colocará bajo un nivel de agrupación de recursos en la parte inferior de la lista de actividades del gráfico de Gantt.

### Tener acceso al gráfico de Gantt
<a id="access-the-gantt-chart" class="xliff"></a>

El gráfico de Gantt se puede abrir desde las siguientes páginas.

| **Página**                                                                                     | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Lista y detalle del pedido de producción**                                                         | En la página **Lista y detalle del pedido de producción**, puede abrir el gráfico de Gantt desde uno o varios pedidos seleccionados. Al abrir el gráfico desde el elemento de menú **Diagrama de Gantt**, se cargarán todos los trabajos relacionados con los pedidos de producción seleccionados, pero también trabajos de otros pedidos de producción programados en los mismos recursos. Al abrir el gráfico desde el elemento de menú **Gráfico de Gantt: vista rápida** cargará únicamente los trabajos relacionados con los pedidos de producción seleccionados. En esta vista, no es posible programar trabajos. |
| **Recurso**                                                                                 | En la página **Recurso**, puede abrir el gráfico de Gantt desde el elemento de menú **Gráfico de Gantt**. Una vez seleccionados, todos los trabajos programados del recurso en un intervalo de tiempo seleccionado se cargarán en el gráfico.                                                                                                                                                                                                                                                                                                   |
| **Grupo de recursos**                                                                           | En la página **Grupo de recursos**, puede abrir el gráfico de Gantt desde el elemento de menú Gráfico de **Gantt**. Una vez seleccionados, todos los trabajos programados en los recursos del grupo de recursos se mostrarán en un intervalo de tiempo seleccionado.                                                                                                                                                                                                                                                                                    |
| **Gráficos de Gantt**                                                                             | En la página **Gráficos de Gantt** puede configurar gráficos de Gantt por recursos y grupos de recursos. Por ejemplo, si desea controlar actividades de producción para conjuntos específicos de recursos o grupos de recursos, puede crear configuraciones individuales de estos en la página **Gráficos de Gantt**. A continuación, puede abrir el gráfico de Gantt desde cada configuración.                                                                                                                                                    |
| **Previsiones de horas** (proyecto)                                                                 | Las actividades de proyecto de tipo **Previsión de horas** pueden programarse por trabajo en los recursos. En la página **Previsión de horas** del menú **Programación**, puede abrir el gráfico de Gantt en un pedido para ver actividades de proyecto de trabajos programados de tipo previsión de horas.                                                                                                                                                                                                                                                             |
| **Trabajo para completar** (mostrado en el espacio de trabajo **Gestión de planta de producción**)                      | Los **trabajos para completar se muestran en el espacio de trabajo Gestión de planta de producción**, donde se muestran trabajos de los pedidos de producción y lote que están en curso en los recursos seleccionados para el espacio de trabajo. En el elemento de menú **Gráfico de Gantt** puede abrir el gráfico de Gantt, en el que todos los trabajos seleccionados en la lista se cargarán en el gráfico.                                                                                                                                                                                |
| **Pedidos de producción para liberar** (abiertos desde el espacio de trabajo **Gestión de planta de producción**) | La página Pedidos de producción para liberar se abre desde el espacio de trabajo **Gestión de planta de producción**. En esta página se muestran los pedidos de producción y lote programados pendientes de emisión. En esta página puede abrir el gráfico de Gantt para los pedidos de producción seleccionados.                                                                                                                                                                                                                                                        |




