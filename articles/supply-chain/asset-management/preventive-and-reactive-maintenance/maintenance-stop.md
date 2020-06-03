---
title: Tiempo de inactividad por mantenimiento
description: En este tema se explica el tiempo de inactividad por mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c1b219d352b6b090c5c2cd3c063d7f890beaa35c
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383536"
---
# <a name="maintenance-downtime"></a>Tiempo de inactividad por mantenimiento

[!include [banner](../../includes/banner.md)]

 

El tiempo de inactividad por mantenimiento se utiliza para obtener una visión general de la capacidad necesaria para llevar a cabo trabajos de mantenimiento en determinados activos durante un período concreto. Por ejemplo, puede crear un registro de tiempo de inactividad por mantenimiento para la Línea de producción 10 en la Sala de producción 29-A del sitio de producción 02. El registro de tiempo de inactividad por mantenimiento tiene una fecha de inicio y una hora de finalización que indican el periodo en el que los activos relacionados con la parada por mantenimiento no están disponibles para la producción.

**Actividades del tiempo de inactividad por mantenimiento** es una visión general de las líneas del programa de mantenimiento y los trabajos de mantenimiento de la orden de trabajo en activos relacionados durante un período especificado. Todas las líneas relacionadas con los trabajos de mantenimiento de la orden de trabajo tienen una fecha de inicio prevista dentro del período de parada por mantenimiento. Puede extraer información útil y realizar ajustes en los trabajos de mantenimiento planificados:

- Obtener una visión general de los períodos de parada necesaria de los equipos de producción (activos).  
- Obtener una visión general del mantenimiento planificado (horas), agrupados por competencias (trabajadores o grupos de trabajadores responsables del mantenimiento), por ejemplo, carga de capacidad en electricistas, herreros u otros grupos de trabajo de mantenimiento necesarios para realizar los trabajos de mantenimiento planificados.  
- Realizar ajustes en las líneas del programa de mantenimiento o en los trabajos de mantenimiento de la orden de trabajo relacionados con los activos, por ejemplo, cambiar las horas de inicio y finalización previstas en una línea, o seleccionar otros trabajadores de mantenimiento para optimizar el flujo de trabajo para trabajadores y grupos de trabajadores de mantenimiento.

Cuando se hayan seleccionado activos en un registro de tiempo de inactividad por mantenimiento, todas las líneas del programa de mantenimiento abiertas y los trabajos de mantenimiento de la orden de trabajo relacionados con órdenes de trabajo activas se incluyen en el registro de tiempo de inactividad por mantenimiento.

## <a name="maintenance-downtime-activities"></a>Actividades de tiempo de inactividad por mantenimiento

Haga clic en **Administración de activos** > **Común** > **Actividades del tiempo de inactividad por mantenimiento** > **Todas las actividades del tiempo de inactividad por mantenimiento** para abrir una lista de todas las actividades del tiempo de inactividad por mantenimiento y consultar parte de la información relacionada con las actividades. Haga clic en un vínculo de la columna **Actividades del tiempo de inactividad por mantenimiento** para abrir la vista de detalles. La ilustración siguiente muestra un ejemplo de lista de **Actividades de tiempo de inactividad por mantenimiento**.

![Figura 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Crear actividad de tiempo de inactividad por mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Actividades del tiempo de inactividad por mantenimiento** > **Todas las actividades del tiempo de inactividad por mantenimiento** o **Actividades del tiempo de inactividad por mantenimiento activas**.

2. Haga clic en **Nuevo**.

3. Inserte un identificador en el campo **Actividades del tiempo de inactividad por mantenimiento** y un nombre en el campo **Nombre**.

4. Inserte el período para la parada por mantenimiento en los campos **Fecha/hora de inicio** y **Fecha/hora de finalización**.

5. En la ficha desplegable **Activos de las actividades del tiempo de inactividad por mantenimiento** > haga clic en **Agregar línea** para agregar activos, de uno en uno, a la actividad del tiempo de inactividad por mantenimiento.

6. Haga clic en **Guardar** cuando se hayan agregado todos los activos. La ilustración siguiente muestra un ejemplo de actividad tiempo de inactividad por mantenimiento con los activos y los trabajos de mantenimiento relacionados.

7. Los trabajos de mantenimiento de la orden de trabajo y las líneas del programa de mantenimiento abiertas que se relacionan con los activos seleccionados se muestran en las fichas desplegables **Trabajos de mantenimiento de orden de trabajo resultantes** y **Líneas del programa de mantenimiento**. En la ficha desplegable **General** > grupo **Órdenes de trabajo** > campo **Horas de previsión de mantenimiento** y en la ficha desplegable **General** > grupo **Programa de mantenimiento** > campo **Horas de previsión de mantenimiento**, verá el número total de horas previstas para los trabajos de mantenimiento de orden de trabajo y las líneas del programa de mantenimiento.

La ilustración siguiente muestra un ejemplo de vista detallada de las **Actividades de tiempo de inactividad por mantenimiento**.

![Figura 2](media/20-preventive-maintenance.png)

>[!NOTE]
>Los trabajos de mantenimiento de la orden de trabajo y las líneas del programa de mantenimiento relacionados con los activos seleccionados se actualizan automáticamente si se crean nuevas órdenes de trabajo o líneas del programa de mantenimiento después de que crease la actividad del tiempo de inactividad por mantenimiento. Por ejemplo, si programa planes de mantenimiento o rondas de mantenimiento en los activos relacionados dos días después de que se crease la actividad del tiempo de inactividad por mantenimiento, se agregan automáticamente nuevas líneas del programa de mantenimiento a la actividad del tiempo de inactividad por mantenimiento.

8. En **Todas las actividades del tiempo de inactividad por mantenimiento** > **Actividades de tiempo de inactividad por mantenimiento** > seleccione una actividad de tiempo de inactividad por mantenimiento en la lista y haga clic en **Carga de capacidad** para abrir el cuadro de diálogo **Calcular carga de capacidad**. Use este cuadro de diálogo para obtener una visión general de la carga de capacidad en, por ejemplo, fechas, activos, tipos de activos y tipos de trabajo de mantenimiento. Tenga en cuenta que las fechas que se muestra en el cuadro de diálogo son las fechas de inicio y de finalización seleccionadas en **Actividades del tiempo de inactividad por mantenimiento**. Este cálculo incluye los activos relacionados con la actividad del tiempo de inactividad por mantenimiento.

9. En el cuadro de diálogo **Calcular carga de capacidad**, edite las horas de inicio y de finalización, si es necesario, y seleccione si desea incluir órdenes de trabajo y programas de mantenimiento en el cálculo. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para el cálculo de carga de capacidad con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todos los activos para una ubicación técnica, que se seleccionan en la actividad del tiempo de inactividad por mantenimiento, se mostrarán en el nivel superior. De este modo, las horas en una línea se pueden agregar desde las ubicaciones técnicas situadas en un nivel inferior. Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de carga de capacidad en todos los niveles de la ubicación técnica con el que están relacionadas.

10. Haga clic en **Aceptar** para iniciar el cálculo. El número total de horas se muestra en la visión general **Carga de capacidad**. En la pestaña **Carga de capacidad** > grupos del panel Acciones **Agrupar por…**, haga clic en los botones pertinentes para obtener una visión general más detallada de la asignación de horas previstas. La ilustración siguiente muestra los resultados del cálculo de la **Carga de capacidad**.

![Figura 3](media/21-preventive-maintenance.png)

11. Tras obtener una visión general de carga de capacidad, si desea realizar ajustes en los trabaos de mantenimiento de la orden de trabajo o en las líneas del programa de mantenimiento, regrese a la vista detalles **Activites del tiempo de inactividad por mantenimiento** y seleccione las líneas que desea ajustar en las fichas desplegables **Trabajos de mantenimiento de orden de trabajo resultantes** y **Líneas del programa de mantenimiento**.

12. Haga clic en el botón **Ajustar** y actualice las fechas previstas de inicio o finalización, el nivel de servicio o los trabajadores responsables del mantenimiento para los trabajos de mantenimiento de orden de trabajo o las líneas del programa de mantenimiento seleccionados.

13. Haga clic en **Aceptar** cuando haya hecho los ajustes necesarios. 

>[!NOTE]
>Los trabajos de mantenimiento de orden de trabajo y las líneas del programa de mantenimiento que no se incluyen en el período de tiempo de inactividad por mantenimiento una vez que haya hecho ajustes se eliminan automáticamente de **Actividades del tiempo de inactividad por mantenimiento**.

14. En **Todas las actividades del tiempo de inactividad por mantenimiento** > **Actividades del tiempo de inactividad por mantenimiento** > seleccione una actividad del tiempo de inactividad por mantenimiento en la lista y haga clic en **Previsión de artículos** para abrir el cuadro de diálogo **Calcular previsión de artículos**. Use este cuadro de diálogo para calcular las previsiones de artículos (recambios y otros artículos necesarios) y agrúpelas para obtener una visión general, por ejemplo, por fecha, activo, tipo de activo y tipo de trabajo de mantenimiento. Tenga en cuenta que las fechas que se muestra en el cuadro de diálogo son las fechas de inicio y de finalización seleccionadas en **Actividades del tiempo de inactividad por mantenimiento**. Este cálculo incluye repuestos y artículos relacionados con los activos que se seleccionan en la actividad del tiempo de inactividad por mantenimiento.

15. En el cuadro de diálogo **Calcular previsión de artículo**, edite las horas de inicio y de finalización, si es necesario, y seleccione si desea incluir órdenes de trabajo y programas de mantenimiento en el cálculo. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para el cálculo de carga de capacidad con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todos los activos para una ubicación técnica, que se seleccionan en la actividad del tiempo de inactividad por mantenimiento, se mostrarán en el nivel superior. De este modo, las horas en una línea se pueden agregar desde las ubicaciones técnicas situadas en un nivel inferior. Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de carga de capacidad en todos los niveles de la ubicación técnica con el que están relacionadas.

16. Haga clic en **Aceptar** para iniciar el cálculo. El número total de previsiones de artículos se muestra en la visión general **Previsión de artículo**. En la pestaña **Previsión de artículo** > grupos del panel Acciones **Agrupar por…**, haga clic en los botones pertinentes para obtener una visión general más detallada de la asignación de artículos previstos. La ilustración siguiente muestra los resultados de un cálculo de **Previsión de artículos**.

![Figura 4](media/22-preventive-maintenance.png)

- Puede copiar activos desde una actividad del tiempo de inactividad por mantenimiento a otra. En **Todas las actividades del tiempo de inactividad por mantenimiento**, seleccione el botón **Copiar actividades del tiempo de inactividad por mantenimiento**, cree sus selecciones en los campos **Desde actividades del tiempo de inactividad por mantenimiento** y **A actividades del tiempo de inactividad por mantenimiento** y haga clic en **Aceptar**.
- En **Todas las actividades del tiempo de inactividad por mantenimiento**, haga clic en el botón **Líneas del programa de mantenimiento** o en el botón **Órdenes de trabajo activas** para abrir las listas relacionadas y ver las líneas relacionadas con la actividad del tiempo de inactividad por mantenimiento seleccionada.

