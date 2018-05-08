---
title: Registro de Tiempo y asistencia
description: "Los trabajadores del registro de horas pueden especificar distintos tipos de registros de horas, por ejemplo entrada, salida, registro de actividades indirectas y registro de ausencia. Este tema describe registros, su cálculo, aprobación y uso del flujo de trabajo para agregar la estructura y la aprobación automatizada al proceso de aprobación de hojas de horas."
author: YuyuScheller
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29040d0c96183898672bc405364ec59707bff53a
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="time-and-attendance-registration"></a>Registro de Tiempo y asistencia

[!include [banner](../includes/banner.md)]

Los trabajadores del registro de horas pueden especificar distintos tipos de registros de horas, por ejemplo entrada, salida, registro de actividades indirectas y registro de ausencia. Este tema describe registros, su cálculo, aprobación y uso del flujo de trabajo para agregar la estructura y la aprobación automatizada al proceso de aprobación de hojas de horas. 

<a name="registrations"></a>Registros
-------------

En las empresas que usan Tiempo y asistencia, los trabajadores deben registrar el tiempo que pasan en el trabajo, así como la asistencia. Algunas empresas pueden exigir únicamente que los trabajadores registren la horas de entrada y salida. En otras empresas, los trabajadores también pueden tener que registrar el tiempo dedicado a actividades, así como los descansos. Los usuarios de Tiempo y asistencia son:
-   Trabajadores tienen que registrar el tiempo y la asistencia en intervalos regulares, por ejemplo, diariamente, semanalmente o quincenalmente.
-   Supervisores, gerentes y administrativos de nóminas que calculan, aprueban y transfieren registros de trabajadores para su procesamiento.

| **Nota**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si ejecuta Tiempo y asistencia junto con Fabricación, todos los registros en proyectos, actividades de proyectos, actividades indirectas, códigos de ausencia y horas extra y tiempo flexible se registrarán y se utilizarán para calcular las nóminas en ambos módulos. |

## <a name="time-registrations-workers"></a> Trabajadores con registro de horas
Para poder registrar tiempos y ausencias, los trabajadores deben estar configurados como trabajadores del registro de horas en la empresa en la que están empleados.

Tras la configuración, los trabajadores pueden especificar distintos tipos de registros.

-   Entrada y salida al llegar o salir del trabajo.
-   Tiempo y consumo de artículos en trabajos de producción.
-   Tiempo utilizado en una máquina en la planta, si la máquina se ha definido como recurso.

| **Nota**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Un trabajador puede recibir automáticamente una asignación de registros de tiempo en una máquina concreta de la planta, si el trabajador elige trabajar como ayudante de una máquina cuando inicie el trabajo de producción. |

-   Registro de tiempo en proyectos y actividades de proyectos.
-   Registro de cuotas de proyecto y consumo de artículos mediante los diarios respectivos de cuotas de proyecto y los diarios de artículos de proyecto.
-   Ausencias planificadas.
-   Ausencia por llegar tarde a trabajar o por salir antes de lo previsto.
-   Descansos en el trabajo, registrados manualmente o calculados automáticamente por el sistema.
-   Actividades indirectas, que son actividades no productivas en las que un trabajador puede participar durante un día laborable. Algunos ejemplos de estas actividades son reuniones o la limpieza del espacio de trabajo.
-   Horas extra, que se pueden registrar como horas extra u horario flexible.

## <a name="adding-clock-out-registrations"></a>Agregar registros de hora de salida
Si un trabajador olvida registrar su hora de salida al final de la jornada, el registro que falta se puede agregar ejecutando un trabajo por lotes. El sistema comparará la hora de entrada y salida según el perfil asociado el trabajador, e insertará automáticamente el registro de hora de salida que falta para que coincida con la hora final del perfil. Ambos registros, el de hora de entrada y el de hora de salida, son fundamentales para el cálculo y la aprobación subsiguientes de registros de hora para poder transferirse a la nómina.

## <a name="calculating-registrations"></a>Cálculo de registros
Cuando se asigna a un trabajador de registro un grupo de cálculo relacionado normalmente con un equipo, un turno o un grupo de trabajo específico. El gerente o el supervisor del equipo valida normalmente los registros realizados por los trabajadores, por lo que es también la persona responsable de ejecutar el cálculo para los grupos de cálculo respectivos diariamente. Como parte del proceso de cálculo, el gerente o el supervisor del equipo puede:
-   Corregir registros erróneos. Por ejemplo, cambiar códigos de cambio y ajustar los comentarios en los trabajos de producción.
-   Agregar registros que faltan. Por ejemplo, crear registros de hora de salida y crear transacciones de ausencias.
-   Eliminar registros incorrectos.

Dado que el tiempo registrado debe coincidir con el perfil de tiempo del trabajador para poder calcular los registros, debe sobrescribir el perfil de horario de trabajo de cualquier trabajador que incluya una excepción a su perfil de horario de trabajo estándar. En caso de que el perfil del trabajador sea de turno de día y el trabajador haya acordado trabajar un turno de noche sin pago de horas extra, el gerente o el supervisor del equipo debe sobrescribir el perfil del trabajador predeterminado para calcular el horario de trabajo según la cuota estándar de noche, y no como horas extra. El cálculo también mostrará un error si falta un registro de ausencia. Debe agregarse antes de poder completar el cálculo.

## <a name="approving-registrations"></a>Aprobación de registros
Del mismo modo que asigna un grupo de cálculo a un trabajador con registro de horas, debe asignar un grupo de aprobación también. Por lo general, el grupo será específico de un equipo, un turno o un grupo de trabajo. Debe aprobar los registros de horas calculados correctamente (en los que se ha hecho un cálculo sin errores) antes de poder generar los artículos que después se podrán transferir a un sistema de nóminas. El administrador de nóminas realizará normalmente la aprobación de los registros, y antes de aprobarlos puede:
-   Sobrescribir los acuerdos de sueldo de trabajadores concretos.
-   Agregar bonificaciones manuales.
-   Especificar información adicional sobre el registro de ausencias.

| **Nota**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si se han calculado horas extra para trabajadores concretos, las horas extra se deben asignar a los trabajos concretos durante el día. Esto es relevante si los costes de trabajo se calculan en base al sueldo del trabajador. |

## <a name="approving-registrations-using-workflow"></a> Aprobación de registros mediante el flujo de trabajo
Puede configurar un proceso de aprobación de flujo de trabajo para aprobar automáticamente los registros que cumplen con las reglas de flujo de trabajo, dejando solo por introducir manualmente las desviaciones. Si se activa una aprobación de flujo de trabajo, el gerente o el supervisor del equipo envía los registros calculados para su aprobación. El proceso de flujo de trabajo generará las aprobaciones y tareas adecuadas y las asignará a los usuarios y roles adecuados según se identifique en el flujo de trabajo. Existen dos aprobaciones de flujo de trabajo para tiempo y asistencia.

| Flujo de trabajo                                  | Propósito                                                                                                   | Tipo de registro                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total de días de tiempo y asistencia            | El flujo de trabajo valida los registros en relación, por ejemplo, con el número previsto de horas de trabajo diarias. |                                                                                                                                                                                                                                                       |
| Registros de diario de tiempo y asistencia. | El flujo de trabajo valida cada tipo de registro en relación con la fecha de registro.                           | Tiempo y asistencia • Hora de entrada • Hora de salida • Ausencia • Descanso • Código de cambio • Proyecto • Actividad del proyecto • Trabajos de producción de actividades indirectas • Cola anterior • Configuración • Proceso • Superponer • Transporte • Cola posterior • Iniciar ayudante • Detener ayudante |



## <a name="transferring-approved-registrations"></a>Transferencia de registros aprobados
Tras aprobar los registros, podrá transferirlos a un trabajo de nómina periódico. Un registro transferido se registra en una actividad o trabajo asociado, por ejemplo, a un pedido de producción o proyecto. Las transacciones de nóminas se generan para cada trabajador en función de los registros.  

## <a name="reversing-transferred-registrations"></a>Reversión de registros transferidos
La tarea de revertir transacciones se puede realizar hasta que la transferencia de sueldo periódico de la nómina se ejecute. Esto significa que los datos de las nóminas se han transferido a un archivo externo. Una vez invertidos, se extraen todos los registros, y las transacciones registradas en los pedidos de producción o los proyectos se compensan y neutralizan.

| **Nota**                                                 |
|----------------------------------------------------------|
| El archivo externo se pueden importar a un sistema de nóminas. |

## <a name="registrations-in-electronic-timecards"></a>Registros en tarjetas de registro electrónicas
Los trabajadores con tareas de trabajo que no requieren retroalimentación inmediata, como en el caso de trabajos de producción, pero que trabajan en actividades de proyectos, pueden beneficiarse de usar la tarjeta de registro electrónico. Las tarjetas de registro electrónico ofrecen la flexibilidad de hacer registros en cualquier momento y en el mejor modo según el programa empresarial: diariamente, semanalmente o cuando un trabajador vuelve a la oficina después de estar ausente. Para usar tarjetas de registro electrónicas o estos trabajadores, debe especificar Utilizar tarjeta de registro en los detalles del trabajador. Las tarjetas de registro electrónicas permiten al trabajador registrar:

-   Fecha
-   Tipo de registro
-   La referencia del trabajo, como el proyecto, la actividad indirecta o el pedido de producción.
-   Id Trabajo
-   Consumo de tiempo
-   Cuotas de proyectos
-   Artículos de proyectos





