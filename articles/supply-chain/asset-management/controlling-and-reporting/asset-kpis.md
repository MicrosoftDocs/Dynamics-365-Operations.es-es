---
title: KPI de activo
description: Este tema explica los KPI de activos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4fc32d337be1f71932555fcb062a8d05c9ca9bda
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918427"
---
# <a name="asset-kpis"></a>KPI de activo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede calcular los distintos indicadores clave de rendimiento (KPI) para activos y tipos de activos. Use los KPI para obtener una visión general del rendimiento sobre los activos en relación con, por ejemplo, el tiempo de actividad, el tiempo de inactividad, el tiempo de reparación y el tiempo promedio entre fallos(MTBF).

1. Haga clic en **Administración de activos** > **Consultas** > **Activos** > **KPI del activo**.

2. En el diálogo **Calcular el KPI del activo**, seleccione la **Escala de tiempo** que se utilizará en el cálculo y un período en los campos **Desde fecha** y **Hasta fecha**. 

3. En la ficha desplegable **Registros a incluir**, puede seleccionar activos específicos y tipos de activos que se incluirán en el cálculo, si procede.

4. Haga clic en **Aceptar** para iniciar el cálculo.

5. En la ficha desplegable **Visión general**, los resultados del cálculo se muestran en la vista de cuadrícula. Cada activo se muestra en una línea independiente.

6. En la ficha desplegable **KPI para la línea seleccionada**, verá los cálculos para el activo seleccionado en la ficha desplegable **Visión general**. Los valores del KPI se clasifican según **Tiempo**, **Disponibilidad**, **Órdenes de trabajo**, **Mantenimiento**, **Defectos**, **tiempo de inactividad por mantenimiento** y **Coste**.

En la siguiente tabla, aparecerá una descripción de los campos de la página **KPI del activo**.

| Campo                   | Descripción                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Activo                   | Identificador del activo.                                                                                                                                                                                                                                                                                             |
| Tiempo total              | Configuración de tiempo total en el calendario usado en el cálculo. Si el activo está relacionado con un recurso, se utiliza el calendario de recursos relacionado. Si el activo no está relacionada con un recurso, se utiliza el calendario seleccionado en el campo **Calendario estándar** en **Parámetros de administración de activos**. |
| Tiempo de actividad                  | Tiempo total menos tiempo de inactividad.                                                                                                                                                                                                                                                                            |
| Tiempo de inactividad                | Registros del tiempo de inactividad por mantenimiento realizados en el activo en el período seleccionado.                                                                                                                                                                                                                              |
| Tiempo de reparación             | Número total de horas de trabajo consumido en órdenes de trabajo de reparación.                                                                                                                                                                                                                                            |
| Disponibilidad en %          | Tiempo de actividad dividido por el tiempo total y multiplicado por 100.                                                                                                                                                                                                                                                   |
| Número de errores        | Número de causas del defecto registradas en los síntomas del defecto en el activo en el período seleccionado.                                                                                                                                                                                                             |
| MTBF                    | El tiempo promedio entre errores, que es el tiempo total dividido por el número de errores registrados en el activo en el período seleccionado. Si el número de errores es cero, MTBF se establece en el tiempo total.                                                                                                                   |
| Tasa de errores               | 1 dividido por MTBF.                                                                                                                                                                                                                                                                                    |
| MRT                     | El tiempo promedio de reparación, que es el tiempo de reparación dividido por el número de errores registrados en el activo en el período seleccionado. Si el número de errores es cero, MRT se establece en el tiempo de reparación.                                                                                                                           |
| Número de paradas         | Número de registros de tiempo de inactividad por mantenimiento creados en el activo.                                                                                                                                                                                                                                     |
| MTBS                    | El tiempo promedio entre paradas, que es el tiempo total dividido por el número de registros de tiempo de inactividad mantenimiento. Si es el número de registros de tiempo de inactividad por mantenimiento es cero en el período seleccionado, el valor de MTBS se establece en el tiempo total.                                                                                      |
| Coste preventivo         | Los costes registrados en el activo relacionados con el tipo de coste "Preventivo" en el período seleccionado. Los tipos de coste se establecen en tipos de órdenes de trabajo.                                                                                                                                                                       |
| Coste correctivo         | Los costes registrados en el activo relacionados con el tipo de coste "Correctivo" en el período seleccionado. Los tipos de coste se establecen en tipos de órdenes de trabajo.                                                                                                                                                                       |
| Valor de sustitución       | Valor definido en el activo como coste de sustitución.                                                                                                                                                                                                                                                  |
| Tipo de activo             | Identificación del tipo de activo seleccionado en el activo.                                                                                                                                                                                                                                             |
| Fabricante           | Identificación del fabricante seleccionado en el activo.                                                                                                                                                                                                                                                 |
| Modelo                   | Identificación del modelo del fabricante seleccionado en el activo.                                                                                                                                                                                                                                           |
| Desde fecha               | Fecha de inicio del cálculo del KPI. Si se creó el activo después de la fecha inicial que se indica para el cálculo, la fecha inicial del activo se muestra en este campo.                                                                                                                                  |
| Hasta fecha                 | Fecha final del cálculo del KPI. Si el activo se ha registrado como inactivo antes de la fecha final seleccionada para el cálculo, la fecha desde la que el activo dejar de estar activo se muestra en este campo.                                                                                               |
| Escala de tiempo              | Durante el cálculo de los KPI, seleccionará la escala de tiempo que se va a utilizar: horas, días o semanas.                                                                                                                                                                                                            |
| Disponibilidad            | El tiempo de actividad dividido por el tiempo total.                                                                                                                                                                                                                                                                         |
| Órdenes de trabajo             | El número total de órdenes de trabajo incluido en el cálculo de KPI.                                                                                                                                                                                                                                          |
| Tiempo de orden de trabajo         | Número total de horas de trabajo consumidas en las órdenes de trabajo.                                                                                                                                                                                                                                               |
| Órdenes de trabajo principales     | Número de órdenes de trabajo principales incluido en el cálculo de KPI.                                                                                                                                                                                                                                        |
| Órdenes de trabajo secundarias   | Número de órdenes de trabajo secundarias incluido en el cálculo de KPI.                                                                                                                                                                                                                                      |
| Órdenes de trabajo de mantenimiento | Número de órdenes de trabajo de mantenimiento incluido en el cálculo de KPI. Una orden de trabajo de mantenimiento es una orden de trabajo sin causas de defecto relacionadas.                                                                                                                                                             |
| Tiempo de mantenimiento        | Número total de horas de trabajo consumido en órdenes de trabajo de mantenimiento.                                                                                                                                                                                                                                       |
| Órdenes de trabajo de reparación      | Número de órdenes de trabajo de reparación incluido en el cálculo de KPI. Una orden de trabajo de reparación es una orden de trabajo con una causa de defecto relacionada.                                                                                                                                                                        |
| Confiabilidad en %           | Cálculo basado en el desarrollo exponencial esperado en los registros de defectos sobre un activo que indica que, con el paso del tiempo, el activo será menos fiable por desgaste. El cálculo de este KPI se basa en el MTBF y el tiempo total.                                                            |
| MTPS                    | El tiempo promedio de paradas de producción, que es el tiempo de inactividad por mantenimiento dividido por el número de registros de tiempo de inactividad mantenimiento. Si es el número de registros de tiempo de inactividad por mantenimiento es cero en el período seleccionado, el valor de MTPS se establece en cero.                                                                               |
| Coste total              | Costes totales registrados en el activo en el período seleccionado.                                                                                                                                                                                                                                              |
| Coste de inversión         | Los costes registrados en el activo relacionados con el tipo de coste "Inversión" en el período seleccionado. Los tipos de coste se establecen en tipos de órdenes de trabajo.                                                                                                                                                                       |

La ilustración siguiente muestra una captura de pantalla de un cálculo de KPI para cuatro activos.

![Figura 1](media/11-controlling-and-reporting.png)

- Puede seleccionar varios activos en **Todos los activos** y hacer clic en el botón **KPI de activo** en la pestaña **General**. A continuación, haga clic en **Aceptar** en el cuadro de diálogo **Calcular los KPI del activo** para calcular los KPI de los activos seleccionados.  
- Los resultados de un cálculo de KPI pueden o no incluir los [registros de tiempo de inactividad por mantenimiento](../work-orders/maintenance-downtime.md), en función de la configuración y el uso de los códigos del motivo del tiempo de inactividad por mantenimiento. 

