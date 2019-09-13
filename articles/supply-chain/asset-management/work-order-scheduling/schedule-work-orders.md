---
title: Programar órdenes de trabajo
description: En este tema se explica cómo programar órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: b6fad4d57b8e08c839ac0ffac2324c02304335ef
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887237"
---
# <a name="schedule-work-orders"></a>Programar órdenes de trabajo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En este tema se explica cómo programar órdenes de trabajo en Administración de activos. El número necesario de horas para una orden de trabajo se define mediante la suma de horas previstas en las tareas de la orden de trabajo menos las horas registradas. Si se requiere más tiempo, la previsión en la orden de trabajo debe ajustarse según corresponda. En **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**, puede ver o editar previsiones en una orden de trabajo seleccionando la orden de trabajo y haciendo clic en **Pronóstico** en la pestaña **Orden de trabajo**. Cuando se hayan creado y estimado las órdenes de trabajo, el paso siguiente es asignar los trabajadores de mantenimiento y las herramientas que se necesitan para completar las órdenes de trabajo.

Solo se pueden programar las órdenes de trabajo con un estado de ciclo de vida que permite la programación. La configuración para permitir la programación se realiza en la ficha desplegable **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Estados de ciclo de vida** > **General** > botón de alternancia **Permitir programación**.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo**.

2. Selecciones las órdenes de trabajo que desea programar en la lista. Por ejemplo, puede ordenar la lista por **Estado actual del ciclo de vida**.

3. En la pestaña **General**, haga clic en **Programar**.

4. En el diálogo **Programar órdenes de trabajo**, puede agregar selecciones relativas a la fecha de inicio prevista y el nivel de servicio, si es necesario. Si el proceso de programación debe respetar las limitaciones de capacidad respecto a los recursos ya programados para otros trabajos, asegúrese de que los botones de alternar **Activo**, **Herramienta** y **Trabajador** están configurados en "Sí".

>[!NOTE]
>Si establece los botones de alternancia **Activo**, **Herramienta** y **Trabajador** en "No", se ignorarán las reservas existentes. En el registro de información se mostrará una lista de programas de órdenes de trabajo superpuestas, y puede hacer clic en los mensajes para abrir una orden de trabajo y volver a programarla, si es necesario.

5. Para ver información detallada sobre los procesos de programación, seleccione "Sí" en el botón de alternar **Detallado**. Esto significa que la información detallada sobre las puntuaciones calculadas en las órdenes de trabajo y los trabajadores de mantenimiento se mostrarán en el registro de información.

6. Haga clic en **Aceptar** para iniciar el proceso de programación.

7. Cuando se complete la programación, un registro de información muestra el número de órdenes de trabajo programadas, así como información más detallada si el botón de alternancia **Detallado** se estableció en "Sí".

>[!NOTE]
>Las órdenes de trabajo se programan en un ciclo por orden de trabajo, no por tarea de una orden de trabajo. También puede abrir el diálogo **Programar órdenes de trabajo** directamente en **Administración de activos** > **Periódico** > **Órdenes de trabajo** > **Programar órdenes de trabajo**. Haga sus selecciones y haga clic en **Aceptar** para iniciar la programación de la orden de trabajo. Es posible configurar la programación de la orden de trabajo como un trabajo por lotes en el diálogo **Programar órdenes de trabajo** > ficha desplegable **Ejecutar en segundo plano**.

*Ejemplo:* en la ilustración siguiente, la fórmula insertada en el campo **Inicio previsto** generará la programación de la orden de trabajo para todas las órdenes de trabajo con fecha de inicio prevista de aquí a una semana y posteriormente. Esta fórmula puede ser útil cuando ejecute la programación de una orden de trabajo de forma continua, pero desea asegurarse de que las órdenes de trabajo programadas para los próximos 5-6 días no se vuelvan a programar.

![Figura 1](media/03-work-order-scheduling.png)

El tipo de orden de trabajo relacionada con órdenes de trabajo puede configurar la programación para un trabajador de mantenimiento (botón de alternancia **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Tipos de órdenes de trabajo** > **Un trabajador de mantenimiento** establecido en "Sí"). Esto significa que si se utiliza el tipo de orden del trabajo en una orden de trabajo, el botón de alternancia **Un trabajador de mantenimiento** se establece automáticamente en "Sí" en la página de detalles **Todas las órdenes de trabajo** > vista **Encabezado** > ficha desplegable **Programar**. Durante la programación de la orden de trabajo, todas las tareas de la orden de trabajo creados en la orden de trabajo se programarán posteriormente al mismo trabajador de mantenimiento. Si es necesario, puede editar la selección en el botón de alternancia **Un trabajador de mantenimiento** en **Todas las órdenes de trabajo** para permitir la programación de varios trabajadores o de un trabajador en los trabajos de la orden de trabajo.

El proceso de programación en Administración de activos incluye varios factores en el cálculo de la programación:

- Calcular puntuaciones para órdenes de trabajo y para trabajadores de mantenimiento. Las puntuaciones de las órdenes de trabajo y los trabajadores de mantenimiento se configuran en **Parámetros de administración de activos**. 
- Comprobar competencias coincidentes, es decir, aptitudes y certificados necesarios para realizar el trabajo. Las aptitudes y los certificados se configuran en los trabajadores de mantenimiento en el módulo **Recursos humanos** (**Recursos humanos** > **Trabajadores** > **Trabajadores** > seleccione el trabajador de la lista > pestaña **Trabajador** > sección **Competencias** > botones **Aptitudes** y **Certificados**). Además, se pueden agregar aptitudes y certificados a los tipos y comercios de trabajo de mantenimiento. Obtenga más información sobre las competencias y los tipos de trabajo de mantenimiento en [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Puntuaciones utilizadas en la programación de una orden de trabajo

El cálculo de las puntuaciones para una tarea de una orden de trabajo se basa en la fecha de inicio prevista y el nivel de servicio de la orden de trabajo.

Cálculo de la **Fecha de inicio**: para cada fecha futura calculada a partir de la fecha de inicio prevista, la puntuación de la fecha de inicio se resta y multiplica por la puntuación, que es "10" en los siguientes ejemplos.

Cálculo de la **Importancia**: puntuación de la importancia multiplicada por la importancia en la orden de trabajo.

Cálculo del **Nivel de servicio**: puntuación de nivel de servicio dividida por el nivel de servicio en la orden de trabajo.

En los siguientes ejemplos, la puntuación de la importancia es "2" y las puntuaciones de nivel de servicio son "5" y "100".

**Ejemplo 1:**

| Id. de orden de trabajo | Fecha inicial prevista | Importancia de la orden de trabajo | Nivel de servicio de orden de trabajo | Cálculo               | Resultado      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Mañana            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Dos días a partir de ahora   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Dos días a partir de ahora   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

Las órdenes de trabajo se programarán en el siguiente orden: WO-000108**16**, WO-000108**18**, WO-000108**17**.

**Ejemplo 2:**

| Id. de orden de trabajo | Fecha inicial prevista | Importancia de la orden de trabajo | Nivel de servicio de orden de trabajo | Cálculo                 | Resultado    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Mañana            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Dos días a partir de ahora   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Dos días a partir de ahora   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Si la puntuación del nivel de servicio se aumenta a '100' en lugar de '5', el orden de programación será: WO-000108**18**, WO-000108**16**, WO-000108**17**.

Todas las puntuaciones relativas al cálculo de los trabajadores de mantenimiento que deben trabajar en las órdenes de trabajo se configuran como números, que se agregan a cada cálculo del trabajador de mantenimiento durante la programación de la orden de trabajo. Se selecciona el trabajador de mantenimiento con la puntuación más alta en la orden de trabajo. A continuación se describen brevemente las puntuaciones del trabajador de mantenimiento:

| Puntuación de trabajador de mantenimiento       | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Trabajador responsable | Si se selecciona al trabajador de mantenimiento como trabajador responsable en la orden de trabajo, se agrega la puntuación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Grupo responsable de trabajadores de mantenimiento | Si se selecciona al trabajador de mantenimiento como parte del grupo de trabajadores responsable del mantenimiento en la orden de trabajo, se agrega la puntuación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Trabajador de mantenimiento preferido         | Si se selecciona al trabajador como trabajador de mantenimiento preferido en el activo, se agrega la puntuación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Grupo de trabajadores de mantenimiento preferido   | Si el trabajador forma parte del grupo de trabajadores de mantenimiento preferido en el activo, se agrega la puntuación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Ubicación                 | Si su empresa usa ubicaciones técnicas, los trabajadores de mantenimiento obtienen la puntuación completa si se encuentran en la ubicación técnica relacionada con el activo. Si la ubicación técnica del activo tiene un activo principal, los trabajadores de mantenimiento en esa ubicación técnica obtienen media puntuación. Si dicha ubicación también tiene un elemento principal, los trabajadores de mantenimiento de dicha ubicación obtienen un tercio de la puntuación. Si dicha ubicación también tiene un elemento principal, los trabajadores de mantenimiento de dicha ubicación obtienen una cuarta parte de la puntuación y así sucesivamente. Si su empresa usa la ubicación del activo, que no es lo recomendable, la ubicación, el área y la zona se utilizan para calcular las puntuaciones de la ubicación. Los trabajadores obtienen la puntuación completa si se encuentran en la ubicación y el área y la zona relacionados con el activo. Si la ubicación del trabajador solo coincide con la ubicación y el área, la puntuación para el trabajador de mantenimiento es de 2/3 de la puntuación completa. Si la ubicación del trabajador de mantenimiento solo coincide con la ubicación, la puntuación para el trabajador de mantenimiento es de 1/3 de la puntuación completa. |
| Primer día de trabajo del trabajador               | Para cada fecha en la que la fecha de inicio programada es posterior a la fecha de inicio prevista, se resta la puntuación.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

>[!NOTE]
>Si una puntuación se establece en "0", esa puntuación no se calcula. Esto resulta útil si, por ejemplo, no desea incluir al trabajador responsable en su programación.

## <a name="competencies-used-in-work-order-scheduling"></a>Competencias utilizadas en la programación de la orden de trabajo

Las aptitudes y los requisitos de certificado se pueden configurar en los tipos de trabajo de mantenimiento (**Administración de activos** > **Configuración** > **Trabajos** > **Tipos de trabajo de mantenimiento**) y los comercios de trabajo de mantenimiento (**Administración de activos** > **Configuración** > **Trabajos** > **Comercio de trabajo de mantenimiento**). Los tipos y los comercios de trabajo de mantenimiento se seleccionan en las tareas de la orden de trabajo. Si se han seleccionado aptitudes o certificados en un tipo o un comercio de trabajo de mantenimiento, y dicho tipo o comercio se utiliza en una tarea de la orden de trabajo, solo se programan los trabajadores de mantenimiento con aptitudes y certificados coincidentes para que trabajen en la orden de trabajo.

