---
title: Distribuir y completar un cuestionario
description: "Este tema explica cómo distribuir cuestionarios que se diseñan, de modo que están disponibles para la entidad o grupo de personas que los completarán."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: 8e09c6b042d557e3b2d608fb5e278169fc3c1d88
ms.lasthandoff: 03/31/2017


---

# <a name="distribute-and-complete-a-questionnaire"></a>Distribuir y completar un cuestionario

Este tema explica cómo distribuir cuestionarios que se diseñan, de modo que están disponibles para la entidad o grupo de personas que los completarán. 

Hay varias manera de distribuir un cuestionario:

-   Marcar el cuestionario como activo. El cuestionario estará entonces disponible para todos los empleados, a menos que se configure un grupo de cuestionarios para restringir el acceso al mismo.
-   Asigne derechos a un grupo de cuestionarios. El cuestionario estará entonces disponible para todos los miembros del grupo seleccionado.
-   Crear sesiones de respuestas planificadas. El cuestionario está entonces disponible solo para una persona concreta.
-   Crear una programación. El cuestionario estará entonces disponibles para varias personas.

## <a name="marking-a-questionnaire-as-active"></a>Marcar un cuestionario como activo
Estableciendo Sí ** activo ** del campo ** ** ** en los cuestionarios ** la página, coloca el cuestionario a disposición para todos los empleados completado. Los encuestados pueden completar varias veces del cuestionario. Esta función es de utilidad si desea realimentación recopilar continua durante todo el año. Por ejemplo, puede crear un cuestionario que los empleados usen para dar comentario sobre el servicio de almuerzo en la cafetería.

## <a name="questionnaire-groups"></a>Grupos de cuestionarios
Puede configurar los grupos de cuestionarios e incluir a continuación a los encuestados a los que se debe distribuir un cuestionario. 

Puede crear grupos de cuestionarios a partir de las páginas siguientes:

-   **Grupos de cuestionarios**: solo las personas de un grupo de cuestionarios pueden completar un cuestionario seleccionado. Por ejemplo, su público de destino son contratistas, por lo que crea un grupo de cuestionarios que sea específico para dichos encuestados.
-   **Miembros del grupo de cuestionarios**: puede agregar personas a grupos de cuestionarios.

Para asignar un grupo de cuestionarios a un cuestionario, en ** cuestionarios ** la página, haga clic ** los derechos de usuario **. Una vez que el cuestionario guardado como activo, los miembros del grupo de cuestionarios se pueden completar el cuestionario. Esta función es de utilidad si desea probar un cuestionario en un grupo de personas seleccione antes de que lo ruede la salida de un grupo mayor, o si desea dirigirse a un cuestionario a un público muy específica.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sesión de respuestas planificadas en un cuestionario
Las sesiones de respuesta planificadas son cuestionarios diseñados por usted y para las que ha seleccionado los encuestados. 

**Nota:** Para poder configurar sesiones de respuesta planificadas, debe diseñar un cuestionario. 

En la página **Sesión de respuestas planificadas**, puede crear una sesión de respuestas planificadas para un empleado. La lista de la página muestra todos los cuestionarios planificados. 

Las sesiones de respuestas planificadas también se utilizan en la página **Programaciones de cuestionarios**, donde puede planificar cuestionarios para varias personas:

-   Empleados
-   Participantes en el curso
-   Unidades organizativas

Cada persona puede responder al cuestionario solo una vez.

## <a name="scheduling-a-questionnaire"></a>Programación de un cuestionario
Puede programar opcionalmente un cuestionario para varios encuestados.

### <a name="planning-types"></a>Tipos de planificación

Los tipos de planificación son obligatorios si desea programar sesiones de respuesta planificadas para varios encuestados. Los tipos de planificación se usan para clasificar las programaciones de cuestionarios. Por ejemplo, puede programar cuestionarios para los fines siguientes:

-   Evaluación
-   Encuesta
-   Pruebas

Puede especificar los tipos de planificación para una programación de cuestionarios en la página **Programaciones de cuestionarios**.

### <a name="reference-types-for-questionnaire"></a>Tipos de referencia para cuestionario

Puede utilizar tipos de referencia para especificar los criterios para los encuestados que podría seleccionar al programar un cuestionario. 

Use la página **Tipos de referencia** para configurar tipos de referencia para un cuestionario. Cada tipo de referencia corresponde a una tabla en Microsoft Dynamics 365 para las operaciones. Al crear programaciones de cuestionarios, puede especificar los registros individuales en la tabla o un intervalo de registros con los que el cuestionario esté asociado. 

Por ejemplo, si selecciona la tabla Cursos, puede decidir para qué curso específico será el cuestionario. Al configurar un tipo de referencia para la tabla Cursos, algunos campos y botones de la página **Cursos** pueden hacerse disponibles.

### <a name="questionnaire-schedules"></a>Programaciones de cuestionarios

Puede usar programaciones del cuestionario para generar sesiones de respuesta planificadas varios para un grupo de usuarios, en función de un tipo de referencia. Crear una programación en ** las programaciones del cuestionario ** la página. Seleccione el tipo de planificación para categorizar la programación, y seleccione el tipo de referencia que se debe usar para ver el sistema para usuarios específicos. Por ejemplo, si establece el tipo de referencia a los cursos tabla, puede seleccionar un curso específico en ** referencia ** el campo. 

Haga clic en **Detalles de configuración** para seleccionar el cuestionario y otros criterios. Por ejemplo, especifique el nombre del instructor como criterio si el cuestionario es una evaluación del instructor. Una vez que haya terminado de especificar los detalles de la configuración, el sistema genera sesiones de respuesta planificadas para los usuarios incluidos en la consulta. 

Haga clic en **Sesiones de respuestas planificadas** para ver las sesiones de respuesta para la programación. A continuación, puede crear manualmente sesiones de respuestas planificadas adicionales o eliminar sesiones de respuestas planificadas que no se han respondido. 

Haga clic en ** funciones ** &gt; ** inicio ** configurar el cuestionario a disposición de los usuarios de sesiones de respuestas planificadas relacionadas. Haga clic en **Respuestas** para ver las respuestas completadas para el cuestionario. Puede copiar opcionalmente la configuración de la programación de cuestionarios, las sesiones de respuestas planificadas y las respuestas a una nueva programación de cuestionarios.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Notificación de los encuestados sobre los cuestionarios que tienen a su disposición
Al distribuir un cuestionario, debe notificar a los encuestados que tienen los cuestionarios a su disposición. 

** Nota: ** Los encuestados deben ser usuarios de Microsoft Dynamics 365 para las operaciones completar un cuestionario.

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Notificación de los encuestados acerca de una sesión de respuestas planificadas

Si usa una sesión de respuestas planificadas, debe notificar a la persona directamente, por ejemplo, por teléfono o correo electrónico.

### <a name="notifying-respondents-about-a-scheduling"></a>Notificación de los encuestados acerca de una programación

Use la página **Programaciones de cuestionarios** para preparar y enviar correo electrónico a todos los encuestados asignados al cuestionario. Escriba el texto de correo electrónico en la pestaña **Correo electrónico para autoservicio de empleados**. Una vez iniciado la programación, haga clic en ** las funciones ** &gt; ** registran el correo electrónico ** generar y enviar mensajes de correo electrónico a los encuestados. Los encuestados pueden iniciar sesión continuación a la página Web y completar el cuestionario. 

**Nota:** Para poder usar la función de correo electrónico, el administrador de TI debe especificar la configuración de correo electrónico en la página **Parámetros del correo electrónico**.

## <a name="ending-a-scheduled-questionnaire"></a>Finalización de un cuestionario programado
Puede finalizar un cuestionario programado una vez que todas las personas que respondan al mismo hayan completado las sesiones de preguntas que les hayan sido asignadas. Cuando finaliza un cuestionario programado, no puede copiar su configuración en una programación nueva. 

**Note:** Si una o varias de los encuestados no han completado el cuestionario, pero aún así desea finalizar la programación, antes deberá eliminar a esos encuestados de la lista en la página **Sesión de respuestas planificadas**. A continuación, puede finalizar la programación.

## <a name="completing-questionnaires"></a>Completando cuestionarios
Una vez que haya diseñado y haya distribuido un cuestionario, los encuestados seleccionados lo pueden completar. Puede completar los cuestionarios a su disposición desde dos ubicaciones:

-   En el panel de navegación, haga clic ** cuestionarios ** &gt; ** distribuir ** &gt; ** complete un cuestionario **.
-   En Autoservicio para empleados, haga clic en **Cuestionarios que deben completarse**.

Los cuestionarios se pueden poner a disposición de usuarios o grupos de usuarios específicos, o de todos los usuarios conectados a una red.

<a name="see-also"></a>Consulte también
--------

[Diseñar cuestionarios](design-questionnaires.md)

[Uso de cuestionarios](questionnaires.md)

[Ver y evaluación de los resultados de cuestionarios (evaluate-questionnaire-results.md])


