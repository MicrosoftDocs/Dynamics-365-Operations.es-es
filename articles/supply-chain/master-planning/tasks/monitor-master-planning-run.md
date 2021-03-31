---
title: Supervisar una ejecución de planificación maestra
description: Este tema explica cómo el planificador de la producción puede ver si una ejecución de la planificación maestra está en curso.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2dea87ac106e79339b8cb6bb2c28e36e35de4a1a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226108"
---
# <a name="monitor-a-master-planning-run"></a>Supervisar una ejecución de planificación maestra

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Usar un gráfico de Gantt para visualizar el progreso de la planificación maestra

En la página **Ver el progreso de la planificación maestra**, puede ver los detalles de las ejecuciones históricos de la planificación maestra como gráfico de Gantt. Esta función puede ayudarle a comprender el tiempo que se emplea en las distintas fases de la planificación maestra. Para un trabajo de planificación de activo actual, la página **Ver el progreso de la planificación maestra** se puede usar para realizar el seguimiento del progreso y ver el tiempo estimado restante.

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a>Activar y usar la función de la visualización del progreso del plan maestro

Para usar esta funcionalidad, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, en la pestaña **Nuevo**, seleccione **Visualización del progreso de la planificación maestra** en la lista. Si la característica no aparece en la pestaña **Nuevo**, mire en las pestañas **No habilitado** y **Todo**.
1. Seleccione **Habilitar ahora**. Como alternativa, seleccione **Programación** y el tiempo en que desea que la función esté activada.

La página **Ver el progreso de la planificación maestra** puede mostrar trabajos históricos de planificación y trabajos activos de planificación. 

Para ver los trabajos históricos de planificación, hay dos opciones. 

1. Vaya a **Planificación maestra \> Configuración \> Planes \> Planes maestros** y, después en el panel Acciones, seleccione **Historial**. Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.
1. Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el mosaico de planificación maestra hacen clic en **Historial**. Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.

Para ver los trabajos activos de planificación, hay dos opciones. 
1. Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el panel de Acciones, seleccione **Proceso de planificación inacabado**. Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.
1. Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el mosaico de planificación maestra hacen clic en **Ver progresos**. Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.

Nota: Puede ver trabajos activos solo cuando un trabajo de planificación se está procesando.

### <a name="analyze-a-master-planning-job"></a>Analizar un trabajo de planificación maestra

En el gráfico de Gantt, puede expandir cada uno de los procesos de planificación siguientes para ver los detalles adicionales sobre el tiempo dedicado:

- Inicializando
- Eliminando e insertando datos
- Planificación de la cobertura
- Retrasos
- Mensajes de acción
- Finalización
- Puesta en firme automática

El gráfico de Gantt es una herramienta útil si desea ver el impacto de usar mensajes de acción.

#### <a name="navigation-in-the-gantt-chart"></a>Exploración en el gráfico de Gantt

- Para ampliar el grupo seleccionado y mostrar los detalles, seleccione el signo más (**+**) en la vista de árbol.
- Para contraer el grupo seleccionado, seleccione el signo menos (**–**) en la vista de árbol.
- Puede usar la teclado para la exploración. Use las teclas **Flecha arriba** y **Flecha abajo** para desplazarse entre las filas. Use las teclas **Flecha derecha** y **Flecha izquierda** para expandir y contraer los grupos.
- Para abrir o cerrar todos los niveles en el gráfico de Gantt, seleccione **Ampliar todo** o **Contraer todo**.
- Para ver el tiempo de procesamiento relacionado, mantenga el puntero sobre la tarea. (Las tareas son el nivel inferior en el gráfico de Gantt).

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Ver una ejecución adicional de la planificación maestra para comparar trabajos

Si se selecciona un trabajo de planificación maestra en el campo **Mostrar ejecución adicional de planificación maestra**, puede ver una ejecución adicional de la planificación maestra en el gráfico de Gantt y comparar los dos trabajos.

#### <a name="bom-level-display"></a>Presentación a nivel de L.MAT

Los niveles la lista de materiales (L.MAT) se muestran de forma distinta para la cobertura de la planificación, los retrasos, las acciones y la puesta en firme.

- **Planificación de cobertura**: los niveles de L.MAT se muestran como esperado. Se calculan de arriba hacia abajo.

    **Ejemplo**: nivel 0, 1, 2 de la L.MAT

- **Retrasos**: los niveles de L.MAT se muestran como los niveles de planificación de L.MAT multiplicados por –1. Es decir (tienen un signo negativo).

    **Ejemplo**: nivel –2, –1, 0 de la L.MAT

- **Mensaje de acción**: los niveles de L.MAT se muestran como esperado. Se calculan de arriba hacia abajo.

    **Ejemplo**: nivel 0, 1, 2 de la L.MAT

- **Puesta en firme automática**: los niveles de L.MAT aparecen como 999 menos el nivel de L.MAT de planificación de cobertura.

    **Ejemplo**: nivel 999, 998, 997 de la L.MAT

En la tabla siguiente se resume el comportamiento.

| Nivel de L.MAT que se muestra | Artículo final | Subcomponente | Materia prima |
|---|---|---|---|
| Planificación de la cobertura | 0 | 1 | 2 |
| Retrasos | 0 | –1 | –2 |
| Mensaje de acción | 0 | 1 | 2 |
| Puesta en firme automática | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Visualizar el progreso

Si ve un trabajo de planificación maestra que se esté ejecutando actualmente, el progreso se muestra con colores en el gráfico de Gantt. Se aplican los siguientes colores al tema azul. Para otros temas de color, los colores serán diferentes.

- **Azul oscuro**: tareas de planificación completadas.
- **Naranja**: la tarea está actualmente en curso.
- **Azul claro**: la previsión de tareas restantes.

El color solo se muestra en el nivel más bajo en el gráfico de Gantt. Seleccione **Ampliar todo** para ver todas las tareas en el trabajo de la planificación maestra. La estimación de tareas restantes se basa en trabajos históricos de planificación maestra.

## <a name="run-master-planning-and-track-processing-time"></a>Ejecutar planificación maestra y hacer un seguimiento del tiempo de procesamiento

1. En el panel predeterminado, seleccione **Planificación maestra**.
1. En el campo **Plan**, especifique o seleccione un valor.
1. Seleccione **Ejecutar**.
1. Establezca la opción **Realizar seguimiento del tiempo de procesamiento** en **Sí**.
1. En el campo **Número de subprocesos**, especifique un número.
1. En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.
1. En la cuadrícula, seleccione la fila donde el campo **Campo** está establecido en **Número de artículo**.
1. En el campo **Criterios**, escriba un valor.
1. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]