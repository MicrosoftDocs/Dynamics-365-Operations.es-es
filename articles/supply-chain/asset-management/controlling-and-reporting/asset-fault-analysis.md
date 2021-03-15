---
title: Análisis de defectos de activos
description: Este tema explica el análisis de los defectos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 674e10b94711b00e526af4af0e0c0afddd05e62c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022390"
---
# <a name="asset-fault-analysis"></a>Análisis de defectos de activos

[!include [banner](../../includes/banner.md)]

 

En Administración activos, puede analizar los registros de defectos del activo para obtener una visión general del número total de errores registrados durante un período específico. Los registros de defectos se pueden analizar desde perspectivas diferentes, por ejemplo con el enfoque en los activos, los tipos de activos, las ubicaciones técnicas, los síntomas del error o los tipos de errores.

1. Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Análisis de los defectos de activos** para abrir la lista.

2. En el diálogo **Cálculo del análisis de defectos de activos**, puede utilizar el campo **Nivel** para indicar el nivel de detalle que desea que tengan las líneas de defectos con respecto a las ubicaciones técnicas. 

    Por ejemplo, si especifica el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas las líneas de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. 
        
    Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de defectos del activo en todo el nivel de la ubicación técnica con el que están relacionadas.

3. Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de defectos, causas del defecto y soluciones para el defecto en la ficha desplegable **Registros a incluir**.

4. Haga clic en **Aceptar** para iniciar el cálculo.

5. En la pestaña **Análisis de errores de activos**, haga clic en uno o más botones **Agrupar por…** para mostrar el nivel de detalle que desea ver. Se resaltarán los botones activados. Haga clic en los botones para activarlos o desactivarlos.

6. Haga clic en **Actualizar cálculos** para mostrar sus selecciones en la pantalla. 

>[!NOTE]
>Cada vez que active o desactive un botón **Agrupar por**, recuerde hacer clic en el botón **Actualizar cálculos**. Es obligatorio porque se procesan grandes cantidades de datos cuando se recalcula la probabilidad de defectos.

## <a name="examples"></a>Ejemplo

Existen varias maneras de analizar los registros de error. Esta sección tiene cinco ejemplos de cómo distintas selecciones de datos pueden proporcionar más información y detalles al analizar los registros de errores de activos.

### <a name="group-by-symptoms"></a>Agrupar por síntomas

En el captura de pantalla abajo, solo se selecciona el botón **Síntoma**.

- Los registros de defectos se han hecho sobre tres síntomas de defecto: "Escape de aire", "Fusible fundido", y "Equipo atascado".  
- En la columna **Porcentaje de probabilidad**, todos porcentajes suman 100 %. La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.

![Figura 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a>Agrupar por síntomas y período de tiempo

En el captura de pantalla de abajo, **Año** y **Mes** se agregan para mostrar cómo puede ver los registros de defectos durante un período seleccionado.

- Los síntomas de los defectos ahora se mostrarán a modo de registros de año/mes.  
- En la columna **Porcentaje de probabilidad**, si agrega todos los porcentajes de cada mes, sumarán 100 %. La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos. Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.

![Figura 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a>Agrupar por múltiples síntomas y activos

La combinación de activos y un tipo de activo se usará como base para los cálculos mostrados en las tres capturas de pantalla de más abajo, que incrementarán el nivel de detalle.  

Normalmente, los botones en los grupos del panel Acciones **Agrupar por fecha**, **Agrupar por activo** y **Agrupar por ubicación técnica**, así como el botón **Error** (id. de error), contienen períodos o relaciones de activos. Los botones **Síntoma**, **Área**, **Tipo**, **Causa** y **Remedio** son clasificaciones utilizadas en la administración de defectos para analizar los registros de defectos del activo e identificar las áreas problemáticas.  

**Agrupar por síntoma, activo y tipo de activo**

En el captura de pantalla de abajo, **Activo** y **Tipo de activo** se han agregado para proporcionar más detalle en relación con los registros de defectos.

- Los síntomas de error ahora se dividen en las combinaciones **Activo** / **Tipo de activo** / **Síntoma**.  
- En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** respectivamente, cada uno de ellos sumará 100 %. La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos. Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.

![Figura 3](media/08-controlling-and-reporting.png)

**Agrupar por dos síntomas, activo y tipo de activo**

En el captura de pantalla de abajo, **Área** se agregó a **Síntoma**, **Activo** y **Tipo de activo** para proporcionar más detalle en relación con los registros de defectos.

- En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %. La probabilidad se basa en la combinación de **Síntoma** y **Área** en este análisis de defectos. Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de área de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicha área del defecto.  

![Figura 4](media/09-controlling-and-reporting.png)

**Agrupar por tres síntomas, activo y tipo de activo**

En el captura de pantalla de abajo, **Tipo** se ha agregado y se muestra el cálculo más detallados de este ejemplo.
 
- En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %. La probabilidad se basa en la combinación de **Síntoma**, **Área** y **Tipo** en este análisis de defectos. Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de tipo de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho tipo del defecto.

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
>Para obtener una visión general de todos los registros de defecto creados en las órdenes de trabajo y solicitudes de mantenimiento, haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Defectos de activos**. En la página **Defectos activo** , seleccione un registro de defectos de activo y expanda el panel **Información relacionada** para ver la información relativa a la orden de trabajo o a la solicitud de mantenimiento relacionadas.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]