---
title: Gráfico de Gantt para la programación de trabajos
description: Los planificadores de producción pueden controlar y optimizar los planes de producciones mediante diagramas de Gantt.
author: johanhoffmann
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 301db69fce18c2ed32e201e7418e628ac57db543
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571849"
---
# <a name="gantt-chart-for-job-scheduling"></a>Gráfico de Gantt para la programación de trabajos

[!include [banner](../includes/banner.md)]

El gráfico de Gantt está diseñado para permitir a los planificadores de producción controlar y optimizar el plan de producción. El gráfico de Gantt hace que el flujo de operaciones sea transparente y facilita el ajuste de la previsión de producción mientras tiene en cuenta la escasez de materiales o recursos. Esto ayuda a los planificadores a realizar el mejor uso de los recursos disponibles, minimizar el trabajo en curso y optimizar los tiempos de capacidad de proceso para pedidos de producción.

Un gráfico de Gantt es una representación visual de actividades programadas dentro de un intervalo de tiempo definido. Las actividades se programan en recursos cuya capacidad viene definida por un calendario de capacidad. Los siguientes tipos de actividades se pueden mostrar en el gráfico de Gantt.

-   Trabajos de los pedidos de producción que son trabajos programados.
-   Trabajos de los pedidos de producción planificados.
-   Actividades de proyecto de trabajos programados de tipo Previsiones de horas.

El gráfico de Gantt se puede abrir en dos diferentes vistas, **Vista de pedidos** y **Vista de recursos**[](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true). En **Vista de pedidos**, las actividades se agrupan en pedidos de producción. Esto puede ser útil, por ejemplo, si desea mantener una visión general de todos los trabajos que pertenecen a los mismos pedidos. En la **Vista de recursos**, todos los trabajos se agrupan en recursos individuales. Esta vista puede ser útil al optimizar el plan en un nivel del recurso, por ejemplo, una máquina o un grupo de máquinas. Los gráficos de Gantt mostrados en las ilustraciones siguientes muestran la **Vista de pedidos** y la **Vista de recursos** con estos elementos clave:

1.  Actividad del gráfico de Gantt
2.  Icono de escasez de material
3.  Icono de disponibilidad de material
4.  Icono de fecha de entrega del pedido
5.  Barra de capacidad

## <a name="order-view"></a>Vista de pedidos

[![Vista de pedidos](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Vista de recursos
[![Vista de recursos](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Actividades
Las actividades aparecen como barras y se organizan en una cuadrícula de la escala de tiempo con una hora inicial y final programada, haciendo que la longitud de las barras sea proporcional al tiempo necesario para completar la actividad. Las actividades se muestran según una escala de tiempo. Puede ajustar la escala de tiempo en el menú donde selecciona una fecha inicial y final y una unidad de tiempo, por ejemplo, horas o días. Ajustando la escala de tiempo puede establecer el foco en un intervalo de tiempo en el que desee gestionar actividades. 

Para obtener una mejor visión general, hay diferentes opciones para controlar el color de las actividades. Puede configurar un color individual de las actividades, usar el color de tema que es el tema de color general utilizado para la aplicación o configurar el color de cuyo control se encargará el código de color para pedidos de producción. 

El intervalo de tiempo para las actividades tiene una sombra de fondo. Los períodos con una sombra blanca indican un intervalo de tiempo con capacidad definida en el recurso para la actividad, mientras que los períodos con una sombra gris indican intervalos de tiempo sin capacidad definida. 

En el lado izquierdo del gráfico hay información adicional sobre la actividad, por ejemplo, el recurso en el que está programada la actividad y el número de pedido de producción. La conexión entre trabajos que pertenecen al mismo pedido se muestra con una flecha. 

Puede obtener más información sobre una actividad en el cuadro de diálogo de la actividad. Para abrir el cuadro de diálogo, haga doble clic en la actividad o seleccione el menú de **información**. En el cuadro de diálogo de la actividad puede ver la fecha inicial y final programada e información de tiempo sobre los materiales que la actividad tiene previsto consumir. 

Las actividades se pueden agrupar en niveles de agrupación. Los niveles de agrupación son jerárquicos y se pueden usar para crear una agrupación lógica de actividades. Por ejemplo, si tiene un diseño en el que las actividades de fabricación se agrupan por Sitio, Unidades de producción, Grupos de recursos y Recursos, puede usar los niveles de agrupación para agrupar las actividades según ese diseño. Los niveles de agrupación se pueden expandir y contraer en el nivel de agrupación individual o para todos los niveles del gráfico con los botones **Expandir todo** y **Contraer todo** del menú. También puede configurar los niveles de agrupación que se expandirán o contraerán al abrirse el gráfico.

### <a name="material-availability"></a>Disponibilidad de material

El gráfico de Gantt se puede configurar para proporcionar el planificador con información detallada sobre el estado del material para las actividades individuales. Por ejemplo, esto puede resultar útil si el material se retrasa y afecta al plan de producción. En este caso, los problemas de material se resaltarán en el gráfico de Gantt para ayudar al planificador a comprender las consecuencias y crear los ajustes necesarios. 

Un trabajo aparecerá con un icono de escasez de material si la fecha inicial de programación del trabajo es posterior a la fecha disponibilidad de material para los materiales consumidos por el trabajo. La fecha de disponibilidad de material se calcula en función de la información del diagrama de árbol del plan maestro dinámico. El icono de escasez de material aparecerá por ejemplo en un trabajo que consume un material vinculado con un pedido de compra cuya recepción es posterior a la fecha inicial planificada del trabajo.

### <a name="indicator-of-material-availability-date"></a>Indicador de fecha de disponibilidad de material

Al configurar el gráfico para mostrar trabajos con escasez de materiales, también puede aparecer un icono para mostrar la fecha de disponibilidad de material para el trabajo. El icono solo se mostrará si la fecha de disponibilidad de material se encuentra dentro del intervalo de tiempo definido del gráfico. Si la fecha de disponibilidad de material se encuentra fuera del intervalo de tiempo definido, puede recuperarse información de disponibilidad de material más detallada de la lista de materiales del cuadro de diálogo del trabajo. En la lista también hay un icono que muestra los materiales entregados tarde para el trabajo. Puede volver a programar un trabajo mediante la fecha de disponibilidad de material como fecha inicial.

### <a name="indicator-of-order-delivery-date"></a>Indicador de fecha de entrega del pedido

Este icono indica la fecha de entrega de un pedido de producción. El icono solo está visible en la Vista de pedidos.

### <a name="capacity-bar"></a>Barra de capacidad

Puede configurar el gráfico para mostrar una barra de capacidad de recursos. Esta barra proporciona una visión general de la capacidad de recursos de una actividad en el intervalo de tiempo definido del gráfico. La barra de capacidad no se muestra en los períodos de tiempo en los que no se reserva el recurso. En los períodos en los que se reserva el recurso hasta cubrir la capacidad, la barra de capacidad se muestra como barra sólida. En los períodos en los que se satura el recurso, la barra se mostrará más gruesa y en rojo. Por ejemplo, si dos trabajos se superponen, la barra de capacidad indicará una saturación del intervalo de tiempo en el que existe una superposición. La barra de capacidad se actualiza dinámicamente al programar un trabajo. Habilita la barra de capacidad en el menú **Mostrar barra de capacidad**. Solo se puede mostrar en la **Vista de recursos**. Si desea obtener una visión más detallada de la carga de capacidad de un recurso, use el gráfico **Carga de capacidad**, que se puede abrir desde el menú o el menú contextual para una actividad seleccionada.

## <a name="job-scheduling-in-the-gantt-chart"></a>Programación de trabajos en el gráfico de Gantt
El gráfico de Gantt ofrece diferentes opciones para realizar ajustes al plan de producción. En el gráfico de Gantt, puede volver a programar actividades como interacción de arrastrar y colocar o desde un menú de la programación. En el proceso de planificación, puede tener en cuenta la capacidad de recursos, las capacidades de recursos y las restricciones de materiales.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Programar un trabajo como interacción de arrastrar y colocar

Puede volver a programar el trabajo dentro del intervalo de tiempo definido como interacción de arrastrar y colocar. Solo puede volver a programar el trabajo en el mismo recurso, mientras que solo puede programar un trabajo al mismo tiempo.

### <a name="schedule-a-job-from-the-menu"></a>Programar un trabajo desde el menú

En el menú **Programar trabajos**, puede programar uno o varios trabajos seleccionados en el gráfico en función de una dirección de programación y una fecha y hora de programación. Existen tres direcciones disponibles de programación.

-   A partir de la fecha de programación
-   Regresivo a partir de la fecha de programación
-   Reenviar a partir de fecha de disponibilidad de material

No es posible programar un trabajo fuera del intervalo de tiempo definido del gráfico de Gantt. Si lo hace, el trabajo se dejará desprogramado y recibirá el mensaje de error “No se pudo programar el trabajo en el período de tiempo cargado”.

### <a name="schedule-previous-jobs"></a>Programar trabajos anteriores

En una red de actividades, como los trabajos que pertenecen al mismo pedido de producción, puede usar la función **Programar trabajos anteriores** para programar los trabajos anteriores en relación con un trabajo seleccionado en la red. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado. El gráfico muestra el antes y después del trabajo anterior programado. 

[![Programar el trabajo anterior](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Programar trabajos posteriores

Puede usar la función **Programar trabajos posteriores** para programar los trabajos posteriores relativos a un trabajo seleccionado en una red de actividades. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado. El gráfico muestra el antes y después del siguiente trabajo programado. 

[![Programar el siguiente trabajo](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Programación en torno al trabajo

Puede usar la función **Programación en torno al trabajo** para programar el trabajo posterior y el trabajo anterior relativos a un trabajo seleccionado en una red de actividades. En el siguiente ejemplo, la actividad resaltada es el trabajo seleccionado. El gráfico muestra el antes y después del trabajo programado. 

[![Programación en torno al trabajo](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Organizar trabajos

Puede usar la función **Organizar** para organizar actividades seleccionadas en el mismo recurso. Estas actividades pueden estar en la misma red de actividades, pero también pueden pertenecer a redes distintas. Cuando use la función Organizar, los espacios de tiempo entre las actividades seleccionadas se eliminarán. Puede utilizar esta función para optimizar el uso de capacidad de los recursos. El gráfico muestra el antes y después del trabajo programado. 

[![Organizar trabajo](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Reasignar actividades de un recurso a otro

Puede reasignar un trabajo de un recurso a otro. Esto puede resultar útil en situaciones en las que un equipo se encuentra fuera de servicio o está saturado, y se debe encontrar otro recurso disponible que pueda realizar el trabajo.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Reasignación de una actividad como interacción de arrastrar y colocar

En el Vista de **recursos**, puede reasignar una actividad un recurso diferente del gráfico de Gantt como interacción de arrastrar y colocar. Esto se hace seleccionando la fila en la que está programada la actividad. Una vez seleccionada la fila, puede arrastrarla al recurso del gráfico agrupado en un nivel de agrupación de recursos diferente.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Reasignación de una actividad desde el menú Programar trabajos

Puede reasignar un trabajo desde el cuadro de diálogo **Programar trabajo** abierto desde el menú **Programar trabajo**. Desde este menú solo puede reasignar un trabajo a un recurso ya cargado en el gráfico de Gantt. Si solo selecciona un trabajo, el menú desplegable para el recurso se ordenará por recursos aplicables. Si selecciona más trabajos, no habrá información sobre recursos aplicables desde la lista de recursos.

## <a name="load-additional-resources-to-the-gantt-chart"></a>Cargar recursos adicionales al gráfico de Gantt
En la **Vista de recursos**, tiene la opción de cargar recursos adicionales en el gráfico de Gantt. Esto puede ser de utilidad si desea encontrar un recurso alternativo para un trabajo programado en un equipo saturado o desglosado. En la página **Cargar recursos adicionales**, obtendrá una lista de recursos eficaces con respecto a la fecha a partir de la fecha de apertura de la lista. Los recursos aplicables, relativos a un trabajo seleccionado en el gráfico de Gantt, se enumerarán en primer lugar. Si tiene varios trabajos seleccionados, antes de abrir la lista, no aparecerá ninguna indicación de los recursos aplicables. En la página **Cargar recursos adicionales**, puede seleccionar uno o varios recursos, que se cargarán en el gráfico de Gantt al confirmar su selección. Si no hay trabajos programados en el recurso seleccionado en el intervalo de tiempo del gráfico de Gantt, el recurso se colocará bajo un nivel de agrupación de recursos en la parte inferior de la lista de actividades del gráfico de Gantt.

### <a name="access-the-gantt-chart"></a>Tener acceso al gráfico de Gantt

El gráfico de Gantt se puede abrir desde las siguientes páginas.


|                                                 <strong>Página</strong>                                                  |                                                                                                                                                                                                                                                            <strong>Descripción</strong>                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   <strong>Lista y detalle del pedido de producción</strong>                                    | En la página <strong>Lista y detalle del pedido de producción</strong>, puede abrir el gráfico de Gantt desde uno o varios pedidos seleccionados. Al abrir el gráfico desde el elemento de menú <strong>Diagrama de Gantt</strong>, se cargarán todos los trabajos relacionados con los pedidos de producción seleccionados, pero también trabajos de otros pedidos de producción programados en los mismos recursos. Al abrir el gráfico desde el elemento de menú <strong>Gráfico de Gantt: vista rápida</strong> cargará únicamente los trabajos relacionados con los pedidos de producción seleccionados. En esta vista, no es posible programar trabajos. |
|                                               <strong>Recurso</strong>                                                |                                                                                                                                                        En la página <strong>Recurso</strong>, puede abrir el gráfico de Gantt desde el elemento de menú <strong>Gráfico de Gantt</strong>. Una vez seleccionados, todos los trabajos programados del recurso en un intervalo de tiempo seleccionado se cargarán en el gráfico.                                                                                                                                                         |
|                                            <strong>Grupo de recursos</strong>                                             |                                                                                                                                                 En la página <strong>Grupo de recursos</strong>, puede abrir el gráfico de Gantt desde el elemento de menú Gráfico de <strong>Gantt</strong>. Una vez seleccionados, todos los trabajos programados en los recursos del grupo de recursos se mostrarán en un intervalo de tiempo seleccionado.                                                                                                                                                 |
|                                             <strong>Gráficos de Gantt</strong>                                              |                                                                                 En la página <strong>Gráficos de Gantt</strong> puede configurar gráficos de Gantt por recursos y grupos de recursos. Por ejemplo, si desea controlar actividades de producción para conjuntos específicos de recursos o grupos de recursos, puede crear configuraciones individuales de estos en la página <strong>Gráficos de Gantt</strong>. A continuación, puede abrir el gráfico de Gantt desde cada configuración.                                                                                 |
|                                       <strong>Previsiones de horas</strong> (proyecto)                                        |                                                                                                                              Las actividades de proyecto de tipo <strong>Previsión de horas</strong> pueden programarse por trabajo en los recursos. En la página <strong>Previsión de horas</strong> del menú <strong>Programación</strong>, puede abrir el gráfico de Gantt en un pedido para ver actividades de proyecto de trabajos programados de tipo previsión de horas.                                                                                                                               |
|           <strong>Trabajo para completar</strong> (mostrado en el espacio de trabajo <strong>Gestión de planta de producción</strong>)            |                                                                                               Los <strong>trabajos para completar se muestran en el espacio de trabajo Gestión de planta de producción</strong>, donde se muestran trabajos de los pedidos de producción y lote que están en curso en los recursos seleccionados para el espacio de trabajo. En el elemento de menú <strong>Gráfico de Gantt</strong> puede abrir el gráfico de Gantt, en el que todos los trabajos seleccionados en la lista se cargarán en el gráfico.                                                                                               |
| <strong>Pedidos de producción para liberar</strong> (abiertos desde el espacio de trabajo <strong>Gestión de planta de producción</strong>) |                                                                                                                                         La página Pedidos de producción para liberar se abre desde el espacio de trabajo <strong>Gestión de planta de producción</strong>. En esta página se muestran los pedidos de producción y lote programados pendientes de emisión. En esta página puede abrir el gráfico de Gantt para los pedidos de producción seleccionados.                                                                                                                                          |

## <a name="additional-resources"></a>Recursos adicionales  
[Programación visual con el gráfico de Gantt para pedidos de producción y lotes (vídeo)](https://youtu.be/BtbuShkGj4I)

[Programación visual para producción (script de demostración)](https://mbs.microsoft.com/customersource/northamerica/365Enterprise/learning/documentation/how-to-articles/365finoptvisschep)

