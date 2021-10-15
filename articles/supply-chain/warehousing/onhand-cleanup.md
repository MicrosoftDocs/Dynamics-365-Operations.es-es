---
title: Trabajo de limpieza de entradas disponibles de gestión de almacén
description: Este tema describe el trabajo de limpieza de entradas disponibles, que ayuda a mejorar el rendimiento del sistema al identificar y eliminar registros relacionados pero innecesarios.
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: d839ed861a24f6ef7267c85e942c275586b4a8c4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565105"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Trabajo de limpieza de entradas disponibles de gestión de almacén

[!include [banner](../includes/banner.md)]

El rendimiento de las consultas que se utilizan para calcular el inventario disponible se ve afectado por el número de registros en las tablas involucradas. Una forma de ayudar a mejorar el rendimiento es reducir el número de registros que la base de datos debe tener en cuenta.

Este tema describe el trabajo de limpieza de entradas disponibles, que elimina registros innecesarios en las tablas InventSum y WHSInventReserve. Estas tablas almacenan información disponible para artículos que están habilitados para el procesamiento de gestión de almacenes. (Estos elementos se denominan elementos WHS). La eliminación de estos registros puede mejorar significativamente el rendimiento de los cálculos disponibles.

## <a name="what-the-cleanup-job-does"></a>Qué hace el trabajo de limpieza

El trabajo de limpieza de entradas disponibles elimina todos los registros de las tablas WHSInventReserve e InventSum donde están todos los valores de campo son *0* (cero). Estos registros se pueden eliminar porque no contribuyen a la información disponible. El trabajo elimina solo los registros que están debajo del nivel **Ubicación**.

Si se permite el inventario físico negativo, es posible que el trabajo de limpieza no pueda eliminar todas las entradas relevantes. La razón de esta limitación es que el trabajo debe contemplar un escenario especial donde una matrícula tiene varios números de serie, y uno de esos números de serie se ha vuelto negativo. Por ejemplo, el sistema tendrá cero en la matrícula cuando una matrícula tenga +1 unidades del números de serie 1 y –1 unidades del número de serie 2. Para este escenario especial, el trabajo realiza una eliminación de primer orden, donde primero intenta eliminar de los niveles inferiores.

## <a name="schedule-and-configure-the-cleanup-job"></a>Programar y configurar el trabajo de limpieza

El trabajo de limpieza de entradas disponibles está disponible en **Gestión de inventario \> Tareas periódicas \> Limpiar \> Limpieza de entradas disponibles de gestión de almacén**. Use la configuración de trabajo estándar para controlar el alcance y la programación de la ejecución del trabajo. Además, se proporcionan las siguientes opciones:

- **Eliminar si no se actualiza durante un cierto número des días**: introduzca el número mínimo de días que el trabajo debe esperar antes de eliminar una entrada disponible que cuya cantidad ha bajado a cero. Use esta configuración para ayudar a reducir el riesgo de eliminar entradas disponibles que todavía se están utilizando. Si desea que se realice la limpieza lo antes posible, introduzca *0* (cero) o deje el campo en blanco.
- **Tiempo máximo de ejecución (horas)**: introduzca el tiempo máximo de ejecución del trabajo de limpieza, en horas. Si el trabajo no se completa antes de que pase este tiempo, guardará el trabajo completado hasta entonces y luego se cerrará. Esta capacidad es especialmente relevante para implementaciones que tengan elevado uso de inventario. En estos casos, debe programar la ejecución del trabajo en momentos en que la carga del sistema sea lo más ligera posible. Si desea que el trabajo por lotes continúe ejecutándose hasta que se complete, introduzca *0* (cero) o deje el campo en blanco. Esta opción solo está disponible si la característica relacionada se ha [activado en el sistema](#max-execution-time).

Aunque puede ejecutar el trabajo durante el horario comercial habitual, le recomendamos que lo haga fuera del horario laboral. De esta forma, ayuda a evitar conflictos que pueden ocurrir si un usuario está trabajando con un registro que también se está limpiando.

Si el trabajo intenta eliminar un registro de un elemento mientras otro usuario está utilizando ese registro, se produce un error de bloqueo en punto muerto tanto para el trabajo de limpieza como para el usuario.

Cuando se ejecuta el trabajo, tiene un tamaño de confirmación de 100. En otras palabras, intentará confirmar una vez por cada 100 eliminaciones. Sin embargo, debido a que algunas eliminaciones se basan en conjuntos, puede haber escenarios en los que se pueden eliminar más de 100 registros en la misma transacción. Por lo tanto, los conflictos de bloqueo todavía pueden seguir ocurriendo.

## <a name="possible-user-impact"></a>Posible impacto en el usuario

Los usuarios pueden verse afectados si el trabajo de limpieza de entradas disponibles elimina todos los registros para un nivel determinado (como al nivel de matrícula). En este caso, la funcionalidad para ver que el inventario estaba disponible previamente en una matrícula podría no funcionar como se esperaba, porque las entradas disponibles relevantes ya no están disponibles. Esto puede experimentarse, por ejemplo, en las siguientes situaciones:

- En el **Inventario disponible**, cuando el usuario anula la selección de la condición **Cantidad \<\> 0** o selecciona la condición **Transacciones cerradas** en la configuración **Presentación de dimensiones**.
- En un informe de **Inventario físico por dimensión de inventario** de períodos pasados, cuando el usuario establece el parámetro **Fecha inicial**.

Sin embargo, la mejora del rendimiento que proporciona el trabajo de limpieza debería compensar estas pequeñas pérdidas de funcionalidad.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Hacer que la opción de Tiempo de ejecución máximo esté disponible

De forma predeterminada, la opción de **Tiempo de ejecución máximo** no está disponible. Si quieres usarla, deberá usar [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la característica relacionada en su sistema. En el espacio de trabajo **Administración de características**, la característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Tiempo de ejecución máximo para el trabajo de limpieza de entradas disponibles de gestión de almacén*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]