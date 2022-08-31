---
title: Visualización de carga de trabajo de salida
description: Este artículo proporciona información acerca de la visualización de la carga de trabajo. Esta funcionalidad permite a los gerentes y supervisores del almacén crear gráficos de carga de trabajo personalizados que se pueden usar para monitorear el progreso del trabajo actual y la cantidad que queda. Los gerentes de almacén pueden crear múltiples vistas y configurar la actualización automática según lo requieran.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 78d0d81095bb52a314936dd7590a5690d94ecb15
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334427"
---
# <a name="outbound-workload-visualization"></a>Visualización de carga de trabajo de salida

[!include [banner](../includes/banner.md)]

Capacidades de configuración avanzada a las que se puede acceder desde la página **Visualización de carga de trabajo saliente** permite a los gerentes y supervisores del almacén crear gráficos de carga de trabajo personalizados que se pueden usar para monitorear el progreso del trabajo actual y la cantidad que queda. Los gerentes de almacén pueden crear múltiples vistas y configurar la actualización automática según lo requieran. Las visualizaciones de cargas de trabajo salientes son adecuadas para mostrarse en las páginas de rendimiento del almacén.

Esta funcionalidad se puede utilizar para realizar un seguimiento del progreso del trabajo de picking. La función está integrada con la gestión de mano de obra y, si se configura la gestión de mano de obra, las visualizaciones de carga de trabajo de salida pueden mostrar un cálculo del número de horas que quedan para el trabajo de picking que se muestra (filtrado).

## <a name="turn-the-outbound-workload-visualization-feature-on-or-off"></a>Activar o desactivar la característica de visualización de carga de trabajo

Para usar esta característica, debe estar activada para su sistema. A partir de la versión 10.0.25 de Supply Chain Management, la característica está activada de forma predeterminada. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Visualización de carga de trabajo de salida* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-outbound-workload-visualizations"></a>Configurar las visualizaciones de carga de trabajo de salida

Para configurar sus visualizaciones, crea una colección de filtros (vistas) y diseña cada filtro para que muestre un tipo de análisis diferente. Usa la página **Configurar filtros** para diseñar los filtros.

Para configurar una visualización de carga de trabajo saliente, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Informes de seguimiento de almacén \> Visualización de carga de trabajo saliente**.

    Aparece la página **Visualización de carga de trabajo saliente**. Después de crear algunos filtros, esta página mostrará su visualización. Puede crear tantas filtros como quiera. Todos los filtros que crea se guardan en su cuenta de usuario, para que pueda usarlos más tarde. En otras palabras, cada usuario tendrá su propio conjunto de filtros que creó. Esos filtros no se compartirán con otros usuarios.

1. Sobre la página **Visualización de carga de trabajo saliente**, en el Panel de acciones, en la pestña **Filtros**, seleccione **Configurar filtros**.
1. Sobre la página **Configurar filtros**, en el Panel de acciones, seleccione **Nuevo** para agregar un filtro y luego establecer los siguientes campos para él:

    - **Tabla de grupos del eje X**: seleccione la tabla que contiene el campo que debe usarse para agrupar los valores del eje X.
    - **Campo de grupo del eje X**: de entre los campos de la tabla que seleccionó en el campo **Tabla de grupos del eje X**, seleccione el campo que debe usarse para agrupar los valores del eje X.
    - **Tabla de valores del eje X**: seleccione la tabla que contiene el campo que debe usarse para analizar más los grupos.
    - **Campo de valor del eje X**: de entre los campos de la tabla que seleccionó en el campo **Tabla de valores del eje X**, seleccione el campo que proporciona los valores que deben analizarse para cada grupo.
    - **Autorefrescar**: seleccione si la visualización debe actualizarse automáticamente.
    - **Intervalo de actualización (minutos)**: ingrese el número de minutos entre actualizaciones automáticas.
    - **Nivel de visualización**: seleccione si el gráfico debe mostrar líneas abiertas o recuentos de encabezados abiertos.
    - **Tipo de picking**: si configura el campo **Nivel de visualización** como _Líneas abiertas_, seleccione si el recuento de líneas de trabajo abiertas en el gráfico debe incluir selecciones iniciales, selecciones por etapas o tanto selecciones iniciales como selecciones por etapas.
    - **Sitio**: seleccione el sitio para el que cargar el gráfico.
    - **Almacén**: seleccione el sitio para el que cargar el gráfico.
    - **Días para incluir**: ingrese el número de días pasados para los que se debe generar el gráfico.
    - **Tipo de orden de trabajo**: seleccione los tipos de órdenes de trabajo salientes para filtrar.

    ![Configurar la página de filtros.](media/work-viz-filters-1.png "Configurar la página de filtros")

1. Cierre la página **Configurar filtros** para volver a la página **Visualizaciones de cargas de trabajo salientes**.

    Ahora la página **Visualizaciones de cargas de trabajo salientes** muestra datos, basados en su nueva configuración de filtro. Su nuevo filtro ya está disponible y está seleccionado en el campo **Filtro**. Los siguientes campos están disponibles en la parte superior del gráfico:

    - **Filtro**: este campo incluye todos los filtros que ha creado hasta ahora. Seleccione un filtro para ver sus datos en el gráfico.
    - **Última actualización**: este campo muestra la fecha y la hora en que se actualizó por última vez la información del gráfico.
    - **Tiempo estimado/real**: si los estándares laborales están configurados en su sistema, configure esta opción en *Sí* para mostrar los tiempos de recolección estimados acumulados en la parte superior de cada columna del gráfico. Si no utiliza las normas laborales, esta opción no está disponible.

    ![Visualización de ejemplo.](media/work-viz-chart.png "Visualización de ejemplo")

1. Seleccione cualquier barra del gráfico para ver los detalles de la línea de trabajo asociada.

    ![Detalles de línea de trabajo.](media/work-viz-work-details.png "Detalles de línea de trabajo")

## <a name="example-outbound-workload-visualization-for-zones"></a>Ejemplo: Visualización de carga de trabajo de salida para zonas

Para este ejemplo, desea configurar una visualización que muestre las líneas de trabajo para cada zona y el estado de cada línea de trabajo (_Abierto_, _Cerrado_ o _Cancelado_). En este caso, puede configurar un filtro que tenga la siguiente configuración:

- **Nombre del filtro**: ingrese un nombre para este filtro (como _Zona frente a estado laboral_).
- **Descripción**: ingrese una breve descripción para este filtro (como _Zona frente a estado laboral_).
- **Tabla de grupos del eje X**: seleccione _Ubicaciones._
- **Grupo del eje X**: seleccione _ID de zona_.
- **Tabla de valores del eje X**: seleccione _Trabajo_, porque desea ver el trabajo por zona.
- **Campo de valores del eje X**: seleccione _Estado de trabajo_, porque desea ver el estado de trabajo.
- **Autorefrescar**: seleccione si la visualización debe actualizarse automáticamente.
- **Tipo de picking**: seleccione _Selecciones iniciales y selecciones por etapas_, porque desea incluir tanto las selecciones iniciales como las selecciones de las ubicaciones de preparación. En otras palabras, esencialmente desea incluir todas las líneas de trabajo de picking que tiene.
- **Nivel de visualización**: seleccione _Líneas abiertas_, porque desea ver la información por línea, no por encabezado de trabajo.

La ilustración siguiente muestra un ejemplo del gráfico resultante.

![Visualización de zona frente a estado de trabajo.](media/work-viz-chart.png "Visualización de zona frente a estado de trabajo")

Este gráfico muestra dos zonas que se nombran **FLOOR** y **BULK**, más una zona que se llama **En blanco**. La zona **En blanco** representa todas las líneas de trabajo que no son miembros de ninguna zona. El gráfico siempre muestra todos los datos filtrados no relacionados como **En blanco**, para proporcionar la mayor visibilidad posible. En la zona **FLOOR**, el gráfico muestra tres líneas cerradas y cuatro líneas abiertas. En la zona **BULK**, el gráfico muestra cuatro líneas cerradas, una línea abierta y 24 líneas canceladas. Finalmente, el gráfico muestra ocho líneas cerradas que no forman parte de ninguna zona y, por lo tanto, se enumeran como **En blanco**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]