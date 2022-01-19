---
title: Administración de tareas
description: Este tema explica la funcionalidad de administración de tareas que está disponible en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 614f37236bbd0239925e37ebf29f59ac006d09cd
ms.sourcegitcommit: 4f84540e6121ca3d5ae52ee07e414116d423cefa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2022
ms.locfileid: "7948799"
---
# <a name="task-management"></a>Administración de tareas

La administración de tareas le permite crear tareas que deben completarse para contratar (incorporar), despedir (expulsar) y transferir (transición) empleados. La gestión de tareas utiliza el concepto de listas de verificación. Una lista de verificación es una lista de tareas de incorporación, retirada o transición. La gestión de tareas utiliza listas de verificación para agrupar tareas y asignarlas a individuos o grupos. La funcionalidad de la lista de verificación para la incorporación, la retirada y las transiciones es similar.

## <a name="checklist-overview"></a>Descripción general de la lista de verificación

Una lista de verificación es un grupo de tareas. Las listas de verificación le brindan una forma flexible de agrupar tareas y pueden reutilizarse (por ejemplo, cuando contrata empleados adicionales). Puede crear tantas listas de verificación como necesite y puede asignar las mismas tareas a varias listas de verificación.

### <a name="examples"></a>Ejemplo

Los siguientes ejemplos muestran cómo se pueden usar las listas de verificación en el proceso de incorporación. Sin embargo, debido a que la funcionalidad de la lista de verificación para la incorporación, la retirada y las transiciones es similar, la información también se aplica a los procesos de baja y transición.

Como parte del proceso de incorporación, los profesionales de recursos humanos (RR. HH.) pueden crear tareas que realicen un seguimiento del progreso de incorporación de los empleados entrantes y recientemente contratados. Debido a que el proceso de incorporación puede variar, según el puesto o la ubicación geográfica del empleado, puede crear varias listas de verificación de incorporación para adaptarse a diferentes situaciones de contratación.

**Ejemplo 1**

Todo empleado que sea contratado en los Estados Unidos debe completar tareas como llenar formularios de retención de impuestos. Sin embargo, tareas como asignar un automóvil de la empresa pueden ser aplicables solo al personal de nivel ejecutivo. En este caso, se pueden crear dos listas de verificación de incorporación: **empleados con sede en EE. UU.** y **Solo ejecutivos**. Luego, cuando se contrata a un gerente de nivel medio en los Estados Unidos, la lista de comprobación **empleados con sede en EE. UU.** se selecciona. Sin embargo, cuando se contrata a un ejecutivo en los Estados Unidos, se seleccionan ambas listas de verificación para garantizar que se completen todas las tareas de incorporación requeridas.

**Ejemplo 2**

Una empresa tiene empleados temporales y empleados regulares a tiempo completo. Aunque algunas tareas (como verificar la hora de llegada del nuevo empleado) se aplican a los empleados de ambos tipos, algunas tareas adicionales se aplican solo a los empleados regulares de tiempo completo. En este caso, puede crear dos listas de verificación. Ambas listas de verificación incluyen las tareas que se aplican tanto a los empleados regulares de tiempo completo como a los de temporada, pero solo una lista de verificación incluye las tareas que son específicas de los empleados regulares de tiempo completo.

## <a name="task-management-workspace"></a>Espacio de trabajo para la gestión de tareas

El espacio de trabajo **Administración de tareas** enumera todas las tareas que se han asignado a las personas en los procesos de incorporación, baja y transición. Para ver las tareas de un proceso, seleccione la pestaña correspondiente en la esquina superior izquierda: **Incorporación**, **Retirada**, o **Transiciones**. De forma predeterminada, solo los profesionales de recursos humanos pueden acceder al espacio de trabajo **Administración de tareas**.

La pestaña **Inducción** contiene una lista **Comenzando pronto** que muestra los empleados entrantes y una lista **Contrataciones recientes** que muestra los empleados recientemente contratados. En ambas listas, puede seleccionar solo un empleado. Cuando selecciona un empleado, todas las tareas relacionadas con la incorporación de ese empleado se muestran en el lado derecho de la página. La pestaña **Inducción** también contiene una lista **Todas las tareas** que muestra todas las tareas de todos los empleados entrantes o contratados recientemente. Finalmente, contiene una lista de tareas atrasadas y una lista de tareas que están asignadas al usuario actual.

La pestaña **Retirada** contiene una lista de empleados que están saliendo de la empresa y una lista de empleados que ya han salido de la empresa. En ambas listas, puede seleccionar solo un empleado. Cuando selecciona un empleado, todas las tareas relacionadas con la retirada de ese empleado se muestran. La pestaña **Retirada** también contiene una lista **Todas las tareas** que muestra todas las tareas de todos los empleados salientes o que hayan salido recientemente. Finalmente, contiene una lista de tareas atrasadas y una lista de tareas que están asignadas al usuario actual.

La pestaña **Transiciones** contiene una lista **Todas las tareas** que muestra todas las tareas de todos los empleados que cambiarán de puesto o que han cambiado de puesto recientemente. También hay una lista de tareas atrasadas y una lista de tareas que están asignadas al usuario actual.

En las tres pestañas, los asistentes y gerentes de recursos humanos pueden completar las siguientes actividades:

- Aplicar una lista de verificación a un empleado.
- Actualizar el estado de una tarea.
- Reasignar una tarea.
- Actualizar la fecha de vencimiento de una tarea.

> [!NOTE]
> De forma predeterminada, la pestaña **Incorporación** muestra a los empleados que fueron contratados en los últimos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, en el campo **Contrataciones recientes**, introduzca un plazo de tiempo. Los datos en la lista **Contrataciones recientes** se pueden mostrar para un número específico de días, meses o años. Por ejemplo, para ver la lista de empleados que fueron contratados en los últimos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**.
>
> En la página **Parámetros de recursos humanos**, también puede actualizar el rango de fechas para las listas de empleados salientes y dados de baja que se muestran en la pestaña **Retirada**.
>
> Estos ajustes también se aplican al espacio de trabajo **Gestión de personal**.

## <a name="setting-up-tasks"></a>Configuración de tareas

Puede crear tareas individualmente y luego reutilizarlas en múltiples listas de verificación. Para crear una tarea, en la página **Configuración de incorporación**, en la pestaña **Tareas**, seleccione **Nuevo**.

Alternativamente, puede agregar tareas directamente a una lista de verificación. Para agregar una tarea a una lista de verificación, en la página **Configuración de incorporación**, en la pestaña **Lista de Verificación**, cree una nueva lista de verificación para agregar la tarea o agregue la tarea a una lista de verificación existente.

> [!NOTE]
> Si agrega una tarea directamente a una lista de verificación, no puede reutilizarla en otras listas de verificación.

La siguiente tabla describe los campos que están disponibles cuando crea una tarea por cualquier método.

| Campo           | Description |
|-----------------|-------------|
| Tarea            | Escriba el nombre de la tarea. |
| Description     | Especifique una descripción de la tarea. |
| Opcional        | Especifique si la tarea es opcional y es solo informativa. |
| Vínculo de tareas       | Ingrese la URL de una página web externa o una página específica en la aplicación donde el usuario debe completar la tarea. Para obtener más información, consulte la sección [Enlaces de tareas](#task-links). |
| Tipo de asignación | Las tareas se pueden asignar a un trabajador, puesto o grupo de puestos específicos, al gerente del empleado afectado (es decir, el empleado que forma parte del proceso de incorporación, baja o transición) o al empleado afectado. Seleccione el tipo de asignación. Para obtener más información, consulte la sección [Tipos de asignación](#assignment-types). |
| Asignada a     | Seleccione el trabajador, el puesto o el grupo de puestos específicos para asignar la tarea. |
| Persona de contacto  | Especifique la persona a la que se debe contactar si hay preguntas sobre la tarea. |
| Desplazamiento de fecha de vencimiento | Especifique el número de días antes o después de la fecha de incorporación, finalización o transición en que vence la tarea. Para obtener más información, consulte la sección [Fechas de vencimiento de la tarea y el campo Compensación de fecha de vencimiento](#task-due-dates-and-the-due-date-offset-field). |
| Instrucciones    | Introduzca las instrucciones para completar la tarea. Para obtener más información, consulte la sección [Instrucciones](#instructions). |

### <a name="task-links"></a>Vínculos de tareas

Un vínculo de tarea proporciona un vínculo a una página web externa o una página en la aplicación Dynamics 365. Puede especificar un vínculo de tarea si la persona asignada a una tarea debe ir a una página web específica o una página específica en la aplicación de Dynamics 365 para completar esa tarea. Cuando crea un enlace de tarea, puede seleccionar una de las siguientes opciones:

- **Opción del menú** – Si selecciona esta opción, se muestra una lista de todas las páginas de la aplicación Dynamics 365. Seleccione una página en la lista.
- **URL** – Si selecciona esta opción, introduzca la URL de la página web a la que desea que vaya la persona asignada a la tarea. La página especificada puede ser una página que no sea parte de la aplicación de Dynamics 365.
- **Detalles del trabajador** – Si selecciona esta opción, seleccione una de las siguientes opciones:

    - **Acciones de autoservicio del empleado** – Esta opción muestra una lista de páginas que están disponibles en **Autoservicio para los empleados**. Úselo si la tarea que se asignó al empleado incorporado debe completarse en el **Autoservicio para los empleados**. Por ejemplo, si desea que el empleado ingrese su información de contacto personal, seleccione **Acciones de autoservicio del empleado** y luego seleccione **Detalles personales&gt;Información personal**.
    - **Acciones de gestión de trabajadores** – Esta opción muestra una lista de páginas que están relacionadas con el registro del trabajador, pero que no son accesibles para el empleado. Por ejemplo, si desea que el propietario de la tarea ingrese información específica de un trabajador incorporado, como información de compensación, seleccione **Acciones de gestión de trabajadores** y luego seleccione **Compensación&gt;Compensación fija**.

### <a name="assignment-types"></a>Tipos de asignaciones

Cuando un empleado es contratado, despedido o transferido, se pueden seleccionar una o más listas de verificación. Después de seleccionar una lista de verificación y completar el proceso de contratación, terminación o transferencia, se crean y asignan tareas a los usuarios para realizar un seguimiento del progreso.

Cuando se crea una tarea, se asigna a un usuario específico. El usuario al que se asigna una tarea depende del tipo de asignación que se seleccione para esa tarea. Los siguientes valores están disponibles en el campo **Tipo de asignación**:

- **Trabajador** – Asignar la tarea a un trabajador específico. Después de seleccionar este valor, seleccione el trabajador en el campo **Asignado a**.
- **Puesto** – Asignar la tarea a un puesto específico. Después de seleccionar este valor, seleccione el puesto en el campo **Asignado a**.

    Por ejemplo, un ingeniero de TI siempre será responsable de preparar un ordenador portátil para un nuevo empleado. En este caso, cuando cree esta tarea de configuración de portátil, seleccione **Puesto** como el tipo de asignación y, a continuación, seleccione **Ingeniero de TI** como el puesto. Luego, cuando se contrata a un empleado y se asigna la lista de verificación, la tarea de configuración de la computadora portátil se asigna a cualquier trabajador que esté en el puesto de ingeniero de TI en el momento en que se ingresa la acción de contratación.

- **Grupo** – Asignar la tarea a un grupo de puestos (grupo de asignación). Después de seleccionar este valor, seleccione el grupo en el campo **Asignado a**. Para obtener más información, vea la sección [Configurar grupos de asignación (opcional)](#setting-up-assignment-groups-optional).
- **Gerente** – Asignar la tarea al gerente del empleado que está siendo contratado, despedido o transferido.

    > [!IMPORTANT]
    > Cuando se aplica una lista de verificación, si actualmente no hay ningún puesto asignado al empleado contratado, despedido o transferido, no se puede determinar el gerente. En este caso, la tarea se asigna al propietario de la lista de verificación. Para más información, vea la sección [Configurar listas de comprobación](#setting-up-checklists).

- **Empleado** – Asignar al empleado que se está contratando, desvinculando o trasladando.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Fechas de vencimiento de la tarea y el campo Compensación de fecha de vencimiento

Las fechas de vencimiento de las tareas se basan en la fecha de inicio del empleo, la fecha de finalización o la fecha de transición. Algunas tareas deben completarse antes de la fecha de inicio de un empleado, mientras que otras tareas pueden completarse después. Al definir una tarea, en el campo **Fecha de vencimiento de compensación**, puede especificar una fecha de vencimiento que esté en relación con la fecha de inicio, finalización o transición. Por ejemplo, un ingeniero de TI debe preparar un ordenador portátil para un nuevo empleado dos días antes de la fecha de inicio de ese empleado. En este caso, cuando cree la tarea de configuración de la computadora portátil, establezca el campo **Compensación de la fecha de vencimiento** a **-2**. Entonces, si la fecha de inicio de un empleado es el 5 de mayo, la tarea vencerá el 3 de mayo.

> [!NOTE]
> Las fechas de vencimiento pueden ser ajustadas después de crear la tarea.

Las fechas de vencimiento se calculan según el calendario asociado con la lista de verificación. Para más información, vea la sección [Configurar listas de comprobación](#setting-up-checklists).

### <a name="instructions"></a>Instrucciones

Las tareas complejas pueden requerir varios pasos o que las personas que realizan las tareas tengan que proporcionar información adicional. En el campo **Instrucciones** puede introducir instrucciones o información adicional para ayudar a la persona asignada a la tarea a completarla.

## <a name="setting-up-checklists"></a>Configuración de listas de verificación

Una lista de verificación es un grupo de tareas. Puede crear tantas listas de verificación como necesite y puede asignar las mismas tareas a varias listas de verificación. Cuando crea una lista de verificación, especifica un propietario y un calendario.

Si el campo **Tipo de asignación** para una tarea se establece en **Puesto**, **Gerente**, o **Grupo**, pero no se puede derivar ningún individuo específico del tipo de asignación, la tarea se asignará al propietario de la lista de verificación. Estos son algunos ejemplos de situaciones en las que las tareas se asignarán al propietario de la lista de verificación:

- No se ha asignado ningún puesto al empleado que está siendo contratado o despedido. Debido a que el empleado no tiene una asignación de puesto, no se puede determinar su gerente.
- El campo **Tipo de asignación** se establece en **Puesto**, pero ningún empleado está asignado al puesto en el momento en que se crea la tarea. Por ejemplo, la tarea **Configurar portátil** se asigna al número de puesto 000876 (**Especialista de Soporte Técnico**). En el momento en que se contrata a un empleado, no se asigna ningún empleado al puesto 000876. Por lo tanto, se creará una tarea para el propietario de la lista de verificación.
- El campo **Tipo de asignación** se establece en **Grupo**, pero ningún empleado está asignado a los puestos en el grupo en el momento en que se crea la tarea.

El calendario que se especifica para una lista de verificación se usa para calcular la fecha de vencimiento de las tareas que forman parte de esa lista de verificación. Los días laborables y no laborables se definen en la configuración del calendario. Los días laborables se incluyen cuando se calcula la fecha de vencimiento de las tareas y se excluyen los días no laborables. Los días no laborables incluyen fines de semana y festivos. 

Una vez que se configura un calendario, se asocia con una plantilla de lista de verificación. De esa manera, la fecha de vencimiento de cada tarea en la lista de verificación se calcula de la misma manera. Puede configurar varios calendarios, pero solo se puede asociar un calendario con cada lista de verificación.

## <a name="setting-up-assignment-groups-optional"></a>Configuración de grupos de asignación (Opcional)

A veces, un grupo de personas es responsable de una tarea. Por ejemplo, un grupo de trabajadores de TI podría ser responsable de preparar las computadoras portátiles para las nuevas contrataciones.

Para configurar un grupo de asignación, siga estos pasos:

1. En la página **Asignación de grupo**, seleccione **Nuevo**.
1. Introduzca un nombre (por ejemplo, **Computadora portátil de TI**) y una descripción del grupo.
1. Seleccione **Guardar**.
1. En la ficha desplegable **Miembros**, seleccione **Agregar**.
1. En el campo **Puestos**, seleccione todos los puestos que son responsables de la tarea.

Una vez que se crea un grupo de tareas, está disponible para su selección cuando se crea una tarea. Para seleccionar un grupo específico para una tarea, debe seleccionar **Grupo** en el **Tipo de asignación**. El grupo que ha creado estará disponible para su selección en el campo **Asignado a**.

> [!IMPORTANT]
> Si una tarea se asigna a un grupo, la tarea se marca como **Completada** cuando una persona del grupo la completa. Las tareas se crean en el momento de la contratación, terminación o transición. Se crean para los usuarios que están asignados a los puestos que se incluyen en el grupo.

## <a name="setting-up-task-groups-optional"></a>Configuración de grupos de tareas (Opcional)

Un proceso de incorporación, retirada o transición puede incluir muchas tareas. Para facilitar la asignación de todas las tareas requeridas a una lista de verificación, puede crear grupos de tareas opcionales para categorizar las tareas relacionadas. Por ejemplo, los departamentos de recursos humanos, TI y nómina deben completar tareas específicas para contratar a un nuevo empleado. Por lo tanto, cree los siguientes grupos de tareas: **RR.HH.**, **TI**, y **Nómina**. Luego, cuando crea una tarea, puede asociarle uno de esos grupos de tareas.

Cuando desee agregar una tarea a una lista de verificación, puede filtrar la lista de tareas por el grupo de tareas al que está asignada la tarea deseada. Por ejemplo, cuando crea una plantilla de lista de verificación, puede filtrar la lista para que solo las tareas de TI que están asignadas al grupo de tareas **TI** se muestren. Por lo tanto, puede asegurarse de que solo se seleccionen las tareas de TI relevantes.

## <a name="using-checklists"></a>Uso de listas de verificación

Cuando un trabajador es contratado, despedido o transferido, se pueden seleccionar una o más listas de verificación. Las fechas de vencimiento de tareas y las asignaciones de trabajadores se crean después de que se completa el proceso de contratación, finalización o transición. Por ejemplo, cuando selecciona el botón **Contratar** o **Contratar y agregar detalles**, se crean tareas para individuos, según el tipo de asignación.

Se asigna una fecha de vencimiento a cada tarea sumando o restando la compensación de la fecha de vencimiento de la fecha de inicio del empleado. Para obtener más información, consulte la sección [Fechas de vencimiento de la tarea y el campo Compensación de fecha de vencimiento](#task-due-dates-and-the-due-date-offset-field).

Si utiliza acciones de personal, las tareas se crean cuando se selecciona el botón **Completo** o se aprueba la acción.

En el espacio de trabajo **Administración de tareas**, puede aplicar una lista de verificación a un empleado seleccionando al empleado en la página de lista simple o en la página de detalles y luego seleccionando **Aplicar lista de verificación**. El valor de la **Fecha objetivo** se utilizará para calcular la fecha de vencimiento de las tareas. Por lo general, la fecha objetivo debe coincidir con la fecha de contratación, terminación o transición del empleado.

También puede aplicar una lista de verificación a un empleado abriendo su página **Trabajador** y seleccionando **Listas de verificación** en el menú.

## <a name="completing-tasks"></a>Completando tareas

En la página **Autoservicio para los empleados**, un empleado puede ver todas las tareas que se le han asignado. Para cada tarea asignada, se muestran los valores de **Tarea**, **Descripción**, **Instrucciones**, y **Persona de contacto**. Además, para cada tarea, el empleado puede abrir la página web externa asociada o la página asociada en la aplicación de Dynamics 365.

Las tareas se pueden marcar como **En curso**, **Canceladas** o **Completadas**. Si una tarea se asignó a un grupo, la tarea se marcará como **Completada** cuando una persona del grupo la completa.

Las tareas también se pueden reasignar.
