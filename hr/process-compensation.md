---
title: Procesar compensaciones
description: "El procesamiento de compensación le permite calcular los nuevos importes de compensación básicos para sus empleados en función de los ajustes de recursos propios, los objetivos de aumento por mérito y el rendimiento."
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6e30357b0bca8745b69bff19a55828b180c3b829
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Procesar compensaciones
<a id="process-compensation" class="xliff"></a>
El procesamiento de compensación le permite calcular los nuevos importes de compensación básicos para sus empleados en función de los ajustes de recursos propios, los objetivos de aumento por mérito y el rendimiento. Este artículo del blog cubrirá el flujo básico de procesamiento de compensación para los planes de compensación fija sin tener en cuenta el rendimiento.

## Planifique los nuevos importes y presupuestos de la compensación
<a id="plan-the-new-compensation-amounts-and-budgets" class="xliff"></a>
Para dar a sus empleados un aumento por méritos, debe configurar un presupuesto de incremento fijo para cada uno de sus departamentos: Gestión de compensación > Vínculos > los Objetivos de aumento por méritos. (Como alternativa, puede abrir este formulario a través del departamento: Organización > Departamentos.) Aquí puede especificar si los empleados afliados a cierto sindicato o en una ubicación determinada deberán obtener otro porcentaje de aumento. Los campos **Presupuesto** y **Divisa** son informativos y se pueden usar para anotar un importe de divisa del presupuesto.

## Configure el proceso de compensación
<a id="set-up-the-compensation-process" class="xliff"></a>
Un evento de proceso le permite especificar parámetros para el procesamiento de compensación. Esto incluye el período de fechas que debe evaluarse para determinar los importes de compensación.  y la fecha en que los nuevos importes de compensación deberían entrar en vigor.

También puede incluir una Fecha de contratación prorrateada fija si cualquiera de sus planes de compensación fija usan una regla porcentual asociada a la contratación. Para dichos planes, cualquier persona que fuese contratada después de la fecha inicial del ciclo y antes de la fecha de contratación prorrateada fija recibirá el 100 % de su mérito calculado o incremento general. Cualquiera que fuese contratada después de la fecha de contratación prorrateada fija y antes de la fecha final del ciclo recibirá una parte de su aumento calculado en función de cuántos días fuera de los días totales del ciclo fueron empleados. Por ejemplo, si nuestro ciclo va del 1 de enero al 31 de diciembre y tenemos una fecha de contratación prorrateada fija de 1 de abril, un empleado que fuera contratado en marzo recibirá el incremento completo calculado, mientras que un empleado contratado el 1 de julio recibirá aproximadamente la mitad del incremento calculado.

La **Fecha de referencia** del evento de proceso se usa solo para procesar ciertos planes de compensación variable y no se tratará en este artículo del blog. **Fecha límite de revisión** es la fecha límite para hacer todas las recomendaciones para poder cargar nuevos importes de compensación en el registro del empleado. La fecha de revisión es sólo informativa.

Una vez que los parámetros del evento de proceso se han guardado, puede hacer clic en el botón **Configuración** para indicar los planes que desea incluir en esta ejecución de proceso y qué acciones de compensación fija deben aplicarse a cada plan.

Haga clic en el botón **Añadir** en la ficha superior para agregar un plan de compensación al evento de proceso. Las columnas **Utilizar otro endeudamiento**, **Factor de endeudamiento** y **Descripción del endeudamiento** se usan únicamente para los planes de compensación variable y no se van a tratar en este tema.

Guarde el registro, haga clic en el botón **Añadir** en la ficha inferior para agregar las acciones de compensación fija del plan seleccionado. Utilice la opción Habilitar recomendaciones si desea poder especificar otro importe distinto del incremento calculado para la acción. Si desea que una acción se calcule según el resultado de la acción anterior para vincular varias acciones de compensación, marque la opción Utilizar resultado anterior. Las acciones de compensación fija son tipos de lógica de compensación a los que puede dar nombres descriptivos. Para los planes de categoría y de banda, sólo puede agregar acciones de compensación fija de los siguientes tipos:

| Tipo de acción de compensación fija | Funcionalidad                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Recursos propios                        | Las acciones de recursos propios comparan el índice de pago del empleado en la fecha final del ciclo con el punto de referencia más bajo para el nivel indicado en el trabajo del empleado. Si el índice de pago del empleado es inferior al punto de referencia mínimo, el aumento necesario para llevar al empleado al punto mínimo del intervalo será calculado.                                                                                |
| Méritos                         | Las acciones de mérito calcularán un aumento basado en el índice de pago del empleado en la fecha final del ciclo y el porcentaje de aumento perteneciente al presupuesto de incremento fijo para el departamento, el sindicato y la ubicación del empleado.                                                                                                                                                                                         |
| General                       | Las acciones generales calcularán un aumento basándose en un porcentaje o dando a los empleados un importe fijo. Esto se determina en función de la compensación fija de los valores de la ficha General.                                                                                                                                                                                                                        |
| Promoción                     | Las acciones de promoción le ofrecen un lugar denominado donde puede conceder aumentos, así que asegúrese de marcar la opción **Habilitar recomendaciones** para poder especificar una recomendación para los empleados que recibirán promociones.  A los empleados sin un incremento recomendado no se les añadirá la acción de promoción a sus registros de compensación fija.                                                                       |
| Otro cambio de nivel            | En el ejemplo anterior, Degradación es el nombre de nuestra acción de compensación fija con un tipo de cambio Otro nivel. Esto genera un aumento de criterio 0 (cambio cero) para que pueda especificar un importe recomendado para ajustar el índice de pago del empleado. (Asegúrese de marcar la opción **Habilitar recomendaciones**). A los empleados sin recomendación no se les añadirá esta acción a sus registros de compensación fija. |

Puede agregar sólo acciones de compensación fija con un tipo de plan Paso a paso.

| Tipo de acción de compensación fija | Funcionalidad                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paso                           | En la ficha General, indique si esta acción de Paso debe avanzar a los empleados 0, 1 o 2 pasos.                                                                                  |
|                                | **0 pasos**: el empleado recibirá la tasa de pago del paso actual donde se encuentre.                                                                                                                      |
|                                | **1 paso**: el sistema comprobará si el empleado ya está en el último punto de referencia de su nivel.                                                                                             |
|                                | **2 pasos**: el sistema avanzará al empleado dos pasos en su nivel actual. Puede que el sistema sólo mueva al empleado uno o cero pasos si alcanza el último punto de referencia de su nivel. |

## Ejecutar el proceso de compensación
<a id="run-the-compensation-process" class="xliff"></a>
Una vez que el evento de proceso se haya configurado con los campos de fecha, los planes y las acciones necesarios, puede hacer clic en **Ejecutar proceso** en la página del evento de proceso. Al hacerlo se abre el cuadro de diálogo de eventos de Ejecutar proceso de compensación. Dentro de este diálogo, puede hacer clic en la opción **Mostrar resultados de procesamiento** para ver cómo se calcularon los importes de la compensación de cada empleado. Al hacer clic en **Aceptar** se ejecuta el proceso de compensación para todos los empleados cuyos planes de compensación se encuentren en la fecha final del ciclo.

## Ver los resultados del proceso
<a id="view-the-process-results" class="xliff"></a>
Para ver los resultados del proceso, abra la página **Resultados de proceso** . Cada vez que se ejecuta el evento de proceso, se crea un evento de compensación nuevo. De esta manera, puede hacer ejecuciones de prueba, realizar ajustes y ejecutar varias veces el evento de compensación para ver cómo los distintos cambios afectan a la compensación del empleado.

La página de Resultados de proceso contiene información acerca de la ejecución de proceso, incluido cuándo se produjo la ejecución, el usuario que ejecutó el proceso y si hay se ha producido algún error cuando el proceso se ejecutó. También puede marcar la opción **Bloqueado** de deshabilitar el botón **Cargar compensación** e impedir que los usuarios carguen los eventos de compensación a los registros del empleado. Si hace clic en el botón **Resultados de los empleados** se mostrará la lista de empleados incluidos en la ejecución.

Los resultados de los empleados muestran información acerca del proceso en sí, junto con cualquier acción de compensación efectuada en el proceso. La sección de compensación fija contendrá un registro de cada acción incluida en el evento de proceso para el plan de compensación. Las columnas de Criterio actual y Recomendación presentarán más información sobre la acción seleccionada en la sección de compensación fija. Si la acción tenía marcada la opción Habilitar recomendaciones, los campos de recomendación se podrán editar. Esto le permitirá ajustar manualmente los importes del empleado. Nota: si ha marcado Utilizar resultado anterior para la acción en el evento de proceso, debe actualizar manualmente los importes de las acciones dependientes.

Una vez que los importes de compensación para un empleado se han revisado y los ajustes en los valores recomendados se han efectuado, puede cambiar **Estado** en la línea **Evento del empleado** para indicar si el evento se ha aprobado o debe omitirse. Opcionalmente, puede borrar cualquier modificación realizada en la recomendación del empleado haciendo clic en el botón **Recalcular** . Esto marcará el evento del empleado existente con un estado de Ignorar y creará un nuevo evento del empleado con valores actualizados.

## Cargar cambios de compensación aprobados
<a id="loading-approved-compensation-changes" class="xliff"></a>
Una vez que se ha actualizado el estado de uno o más eventos del empleado a Aprobado, pueden cargarse a los registros de compensación fija de los empleados. Esto se puede hacer seleccionando cada evento del empleado sucesivamente y haciendo clic en el botón Cargar compensación del empleado en la página de resultados de los empleados, o haciendo clic en **Cargar compensación** en la página de resultados de proceso para cargar todos los eventos de empleado aprobados a la vez.

Al hacer clic en **Aceptar** en el diálogo **Cargar compensación** se agregarán las líneas de acción de compensación que no estén vacías a la página **Compensación fija del empleado** .
