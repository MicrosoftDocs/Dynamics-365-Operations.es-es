---
title: Procesar compensaciones
description: El procesamiento de compensación le permite calcular los nuevos importes de compensación básicos para sus empleados en función de los ajustes de recursos propios, los objetivos de aumento por mérito y el rendimiento.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7c72f866886f320d8a7fa22d6ccfa7e43284b5bf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071579"
---
# <a name="process-compensation"></a>Procesar compensaciones


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

El procesamiento de compensación le permite calcular los nuevos importes de compensación básicos para sus empleados en función de los ajustes de recursos propios, los objetivos de aumento por mérito y el rendimiento. Este tema cubre el flujo básico de procesamiento de compensación para los planes de compensación fija sin tener en cuenta el rendimiento de un empleado.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planifique los nuevos importes y presupuestos de la compensación
Para dar a sus empleados un aumento por méritos, debe configurar un presupuesto de incremento fijo para cada uno de sus departamentos: **Gestión de compensación** > **Vínculos** > **Objetivos de aumento por méritos**. (Como alternativa, puede abrir esta página a través del departamento: **Organización** > **Departamentos**). Aquí puede especificar si los empleados afliados a determinado sindicato o en una ubicación determinada deberán obtener otro porcentaje de aumento. Los campos **Presupuesto** y **Divisa** son informativos y se pueden usar para anotar un importe de divisa del presupuesto.

## <a name="set-up-the-compensation-process"></a>Configure el proceso de compensación
En la página **Procesos de compensación**, puede especificar los parámetros para el procesamiento de compensación. Esto incluye el período de fechas que debe evaluarse para determinar los importes de compensación y la fecha en la que deben entrar en vigencia los nuevos importes de compensación.

Opcionalmente, también puede incluir una **Fecha de contratación prorrateada fija** si cualquiera de sus planes de compensación fija usan una regla porcentual de contratación. Para dichos planes, cualquier persona contratada después de la fecha de **Inicio del ciclo** y antes de la **Fecha de contratación prorrateada fija** recibirá el 100 % de su mérito o incremento general calculado. Cualquiera contratado después de la **Fecha de contratación prorrateada fija** y antes de la **Fecha final del ciclo** recibirá una parte de su aumento calculado en función de cuántos días fuera de los días totales del ciclo estuvo empleado. Por ejemplo, si su ciclo va del 1 de enero al 31 de diciembre y existe una fecha de contratación prorrateada fija de 1 de abril, un empleado que fuera contratado en marzo recibirá el incremento completo calculado, mientras que un empleado contratado el 1 de julio recibirá aproximadamente la mitad del incremento calculado.

La fecha de **referencia** del evento de proceso se usa para procesar solo ciertos planes de compensación variable y no se tratará aquí. **Fecha límite de revisión** es la fecha límite para hacer todas las recomendaciones para poder cargar nuevos importes de compensación en el registro del empleado. La fecha de revisión es sólo informativa.

Una vez que los parámetros del evento de proceso se han guardado, puede hacer clic en el botón **Configuración** para seleccionar los planes a incluir cuándo se ejecuta este proceso y qué acciones de compensación fija deben aplicarse a cada plan.

Haga clic en el botón **Añadir** de la pestaña **Planes** para agregar un plan de compensación al evento de proceso. Las columnas **Utilizar otro endeudamiento**, **Factor de endeudamiento** y **Descripción del endeudamiento** se usan únicamente para los planes de compensación variable y no se van a tratar en este tema.

Guarde el registro, haga clic en el botón **Añadir** de la pestaña **Acciones** para agregar las acciones de compensación fija al plan seleccionado. Utilice la opción **Habilitar recomendaciones** para especificar un importe distinto del incremento calculado para la acción. Para calcular una acción que se basa en el resultado de la acción anterior para vincular varias acciones de compensación, marque la opción **Usar resultado anterior**. Las acciones de compensación fija son tipos de lógica de compensación a los que puede dar nombres descriptivos. Para los planes de **categoría** y de **banda**, sólo puede agregar acciones de compensación fija de los siguientes tipos:

| Tipo de acción de compensación fija | Funcionalidad                  |
|-------------------------------|-------------------------------------------------------------------------|
| Recursos propios                        | Las acciones de recursos propios comparan el índice de pago del empleado en la fecha final del ciclo con el punto de referencia más bajo para el nivel indicado en el trabajo del empleado. Si el índice de pago del empleado es inferior al punto de referencia mínimo, el aumento necesario para llevar al empleado al punto mínimo del intervalo será calculado.                                                                                |
| Méritos                         | Las acciones de mérito calcularán un aumento basado en el índice de pago del empleado en la fecha final del ciclo y el porcentaje de aumento perteneciente al presupuesto de incremento fijo para el departamento, el sindicato y la ubicación del empleado.                                                                                                                                                                                         |
| General                       | Las acciones generales calcularán un aumento basándose en un porcentaje o dando a los empleados un importe fijo. Esto se determina en función de la configuración **Compensación fija** en la ficha **General**.                                                                                                                                                                                                                        |
| Promoción                     | Las acciones de promoción le brindan un lugar designado donde puede conceder aumentos. Marque la opción **Habilitar recomendación** para introducir una recomendación para los empleados que recibirán promociones.  A los empleados sin un incremento recomendado no se les añadirá la acción de **Promoción** a sus registros de compensación fija.                                                                       |
| Otro cambio de nivel            | En el ejemplo anterior, **Degradación** es el nombre la acción de **Compensación fija** con un tipo de **Otro cambio de nivel**. Esto genera un aumento de criterio 0 (cambio cero) para que pueda especificar un importe recomendado para ajustar el índice de pago del empleado. (Seleccione la opción **Habilitar recomendaciones**). A los empleados sin recomendación no se les añadirá esta acción a sus registros de compensación fija. |

Puede agregar sólo acciones de **Compensación fija** con un tipo de plan Paso a paso.

| Tipo de acción de compensación fija | Funcionalidad                |
|--------------------------------|------------------------------|
| Paso                           | En la pestaña **General**, indique si esta acción de Paso debe hacer avanzar a los empleados 0, 1 o 2 pasos.                                                                                  |
|                                | **0 pasos**: el empleado recibirá la tasa de pago del paso actual donde se encuentre.                                                                                                                      |
|                                | **1 paso**: el sistema comprobará si el empleado ya está en el último punto de referencia de su nivel.                                                                                             |
|                                | **2 pasos**: el empleado avanzará al empleado dos pasos en su nivel actual. El empleado podría mover sólo al empleado uno o cero pasos si alcanza el último punto de referencia de su nivel. |

## <a name="run-the-compensation-process"></a>Ejecutar el proceso de compensación
Una vez que el evento de proceso se haya configurado con los campos de fecha, los planes y las acciones necesarios, puede hacer clic en **Ejecutar proceso** en la página **Evento de proceso**, lo que abre el cuadro de diálogo **Ejecutar eventos de proceso de compensación**. Haga clic en la opción **Mostrar resultados de procesamiento** para ver cómo se calcularon los importes de la compensación de cada empleado. Al hacer clic en **Aceptar** se ejecuta el proceso de compensación para todos los empleados cuyos planes de compensación se encuentren en la fecha final del ciclo.

## <a name="view-the-process-results"></a>Ver los resultados del proceso
Para ver los resultados del proceso, abra la página **Resultados de proceso** . Cada vez que se ejecuta el evento de proceso, se crea un evento de compensación nuevo. Esto permite realizar ejecuciones de prueba, realizar ajustes y ejecutar varias veces el evento de compensación para ver cómo los distintos cambios afectan a la compensación del empleado.

La página de **Resultados de proceso** contiene información acerca de la ejecución de proceso, incluido cuándo se produjo la ejecución, el usuario que ejecutó el proceso y si hay se ha producido algún error cuando el proceso se ejecutó. Seleccione la opción **Bloqueado** para deshabilitar el botón **Cargar compensación** e impedir que los usuarios carguen los eventos de compensación a los registros del empleado. Si hace clic en el botón **Resultados de los empleados** se mostrará la lista de empleados incluidos en la ejecución.

La opción **Resultados de empleados** muestra información sobre el propio proceso, así como cualquier acción de compensación efectuada en el proceso. La sección **Compensación fija** contendrá un registro para cada acción, incluido en el evento de proceso para el plan de compensación. Las columnas de **Criterio actual** y **Recomendación** presentarán más información sobre la acción seleccionada en la sección **Compensación fija**. Si la acción tenía marcada la opción **Habilitar recomendaciones**, los campos **Recomendación** se podrán editar. Esto le permitirá ajustar manualmente los importes del empleado. Tenga en cuenta que si ha marcado **Utilizar resultado anterior** para la acción en el evento de proceso, debe actualizar manualmente los importes de las acciones dependientes.

Cuando los importes de compensación para un empleado se hayan revisado y los ajustes en los valores recomendados se hayan efectuado, puede cambiar **Estado** en la línea **Evento del empleado** para indicar si el evento se ha aprobado o debe omitirse. Opcionalmente, puede borrar cualquier modificación realizada en la recomendación del empleado haciendo clic en el botón **Recalcular** . Esto marcará el evento del empleado existente con un estado de Ignorar y creará un nuevo evento del empleado con valores actualizados.

## <a name="loading-approved-compensation-changes"></a>Cargar cambios de compensación aprobados
Cuando se haya actualizado el estado de uno o más eventos del empleado a **Aprobado**, pueden cargarse a los registros de compensación fija de los empleados. Esto se puede hacer seleccionando cada evento del empleado sucesivamente y haciendo clic en el botón **Cargar compensación del empleado** en la página **Resultados de los empleados**, o haciendo clic en **Cargar compensación** en la página **Resultados de proceso** para cargar todos los eventos de empleado aprobados a la vez.

Al hacer clic en **Aceptar** en el diálogo **Cargar compensación** se agregarán las líneas de acción de compensación que no estén vacías a la página **Compensación fija del empleado** .


[!INCLUDE[footer-include](../includes/footer-banner.md)]
