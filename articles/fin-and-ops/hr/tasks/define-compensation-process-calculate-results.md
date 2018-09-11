--- 
title: "Definición del proceso de compensación y el cálculo de resultados"
description: "Los procesos de compensación se usan para determinar nuevas concesiones e importes de compensación para los empleados inscritos en planes de compensación variable y fija."
author: kherr75
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ba28cf1fa6a8e9a4497d3bac1a2161098ec53db1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="define-compensation-process-and-calculate-results"></a>Definición del proceso de compensación y el cálculo de resultados

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los procesos de compensación se usan para determinar nuevas concesiones e importes de compensación para los empleados inscritos en planes de compensación variable y fija. Los procesos de compensación se pueden ejecutar varias veces para realizar análisis hipotéticos, para comprobar que todos los cambios y la configuración son correctos. Este procedimiento creará un proceso de compensación, ejecutará el proceso y verá los resultados. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-compensation-process"></a>Crear un proceso de compensación
1. Vaya a Recursos humanos > Compensación > Proceso > Procesos de compensación.
2. Haga clic en Nuevo.
3. En el campo Proceso, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo de proceso, seleccione una opción.
    * Un ciclo especifica el período de tiempo evaluado para determinar la compensación. La evaluación considera qué puestos ocuparon los empleados, qué índices de rendimiento se incluirán, el cálculo del porcentaje de tiempo que el empleado estuvo contratado durante el ciclo, etc. Un ejemplo de una fecha de inicio del ciclo podría ser el primer día del último ejercicio.  
6. En el campo Inicio del ciclo, especifique una fecha.
    * La fecha final del ciclo es importante porque es la fecha que se usa para determinar qué empleados estuvieron activos e inscritos en uno o varios planes de compensación.  
7. En el campo Fin del ciclo, especifique una fecha.
    * La fecha activa de la transacción es la fecha en que las nuevas cuotas de compensación deben surtir efecto. Muchas empresas incluyen algunos meses entre su final de un ciclo y el tiempo en que las nuevas cuotas de compensación entran en vigor. El tiempo adicional se usa para procesar y revisar la nueva compensación.  
8. En el campo Fecha de activación de transacción, especifique una fecha.
    * La fecha de referencia se usa para los planes de compensación variable que determinan el importe de la prima de un empleado basado en su índice de compensación en este momento.  
    * La fecha de contratación prorrateada fija se usa con los planes de compensación fija con una regla de contratación de porcentaje.  Los empleados contratados entre el inicio del ciclo y la fecha de contratación prorrateada fija recibirán el 100 % de su incremento de compensación calculado, en lugar del porcentaje prorrateado.  
9. En el campo Fecha de contratación prorrateada fija, especifique una fecha.
    * El plazo de revisión es la fecha límite en la que todos los resultados de procesos deben revisarse para que se puedan cargar en el registro de compensación de un empleado antes de la fecha activa de la transacción. Este campo es únicamente informativo.  
10. En el campo Revisar fecha límite, escriba una fecha.
11. Haga clic en Guardar.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Configurar las acciones y los planes de compensación para un proceso de compensación
1. Haga clic en Configurar.
    * La página Configuración se usa para seleccionar qué planes procesar como parte de este proceso de compensación, además de las acciones que se deben realizar con cada plan.  
2. En el campo Plan, especifique o seleccione un valor.
3. Haga clic en Guardar.
4. Haga clic en Agregar.
5. En el campo Acción, seleccione un tipo de acción Recursos propios.
6. Haga clic en Agregar.
7. En el campo Acción, seleccione un tipo de acción Méritos.
    * Las acciones de compensación se pueden “encadenar” de manera conjunta con el campo Utilizar resultado anterior para indicar si la acción seleccionada debe usar el pago base de los empleados o el resultado de la acción anterior como punto de partida para el cálculo de esta acción.  
8. Seleccione Sí en el campo Utilizar resultado anterior.
9. Haga clic en Agregar.
10. En el campo Acción, seleccione un tipo de acción General.
    * Distintos tipos de acción de compensación habilitan diferentes campos. Para un tipo de acción de compensación general, se puede especificar un importe o un porcentaje de incremento.  
11. Seleccione la opción Seleccionar importe de incremento.
12. En el campo Importe de incremento, escriba un número.
13. Haga clic en Agregar.
14. En el campo Acción, seleccione un tipo de acción Promoción.
    * Los tipos de acción Promoción y Otro cambio de nivel permiten a los usuarios realizar ajustes manuales a la compensación del empleado. Se pueden habilitar recomendaciones para estos tipos de acción, además de otros tipos de acción para que pueda especificar un nuevo valor de compensación recomendado para un empleado.  
15. Haga clic en Agregar.
16. En el campo Tipo, seleccione una opción.
    * Los planes de compensación fijos y variables se pueden ejecutar en el mismo proceso de compensación.  
17. En el campo Plan, especifique o seleccione un valor.
    * Use la casilla Habilitar salario variable por rendimiento para determinar si los importes fijos y de compensación variable se deben ajustar en función de la evaluación del rendimiento del empleado.  
    * El endeudamiento se puede anular en los planes de compensación variable.  
18. Haga clic en Guardar.
19. Haga clic en Agregar.
20. Cierre la página.

## <a name="run-the-compensation-process"></a>Ejecutar el proceso de compensación
1. Haga clic en Ejecutar proceso.
    * El control Mostrar resultados de procesamiento le permite ver los mensajes de procesamiento para el proceso de compensación completo cuando ha terminado el procesamiento.  
2. Seleccione Sí en el campo Mostrar resultados de procesamiento.
3. Haga clic en Aceptar

## <a name="view-the-results"></a>Ver los resultados
1. Haga clic en Procesar resultados.
2. Haga clic en Resultados de empleados.
3. En la lista, busque y seleccione el registro deseado.
4. Expanda la sección Compensación fija.
    * Expanda las fichas desplegables para ver los resultados del proceso. Si Habilitar recomendaciones se marcó para una acción de compensación, los campos Recomendación se habilitarán para esa acción.  
5. En la lista, busque y seleccione el registro deseado.
    * Los resultados para un empleado único se pueden ver haciendo clic en el botón Ver resultados.  
    * Puede sobrescribir el importe calculado de compensación calculado ajustando el porcentaje o el importe de incremento en los campos Recomendación.  
6. En el campo recomendado de porcentaje, escriba un número.
7. En la lista, busque y seleccione el registro deseado.
8. En el campo recomendado de porcentaje, escriba un número.
    * Volver a calcular se puede usar para ignorar los cambios realizados al registro existente y generar un nuevo resultado de compensación para el empleado seleccionado.  
    * Cuando se completen todos los cambios para un empleado, cambie el estado a Aprobado.  
9. Haga clic en Cambiar estado.
10. Haga clic en Aprobado.
    * Después de que se haya aprobado el registro, se puede ser cargar al registro de compensación oficial del empleado. La nueva compensación estará vigente a partir de la fecha de transacción establecida en el proceso de compensación.  


