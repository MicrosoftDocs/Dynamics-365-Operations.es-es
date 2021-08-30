---
title: Distribuir y programar cuestionarios
description: En este artículo se explica cómo distribuir los cuestionarios que diseña, de modo que estén disponibles para la persona o el grupo de personas que lo van a completar.
author: andreabichsel
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60354a3e7fed5403321d5ec4440cece84b13233bef80fcd5c5f61d72e5e3aa85
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755524"
---
# <a name="distribute-and-schedule-questionnaires"></a>Distribuir y programar cuestionarios

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este artículo se explica cómo distribuir los cuestionarios que diseña, de modo que estén disponibles para la persona o el grupo de personas que lo van a completar. 

Hay varias manera de distribuir un cuestionario:

-   Marcar el cuestionario como activo. El cuestionario estará entonces disponible para todos los empleados, a menos que se configure un grupo de cuestionarios para restringir el acceso al mismo.
-   Asigne derechos a un grupo de cuestionarios. El cuestionario estará entonces disponible para todos los miembros del grupo seleccionado.
-   Crear sesiones de respuestas planificadas. El cuestionario está entonces disponible solo para una persona concreta.
-   Crear una programación. El cuestionario estará entonces disponibles para varias personas.

## <a name="marking-a-questionnaire-as-active"></a>Marcar un cuestionario como activo

Al establecer el campo **Activo** en **Sí** en la página **Cuestionarios**, pone el cuestionario a disposición de todos los empleados para que lo completen. Los encuestados pueden completar el cuestionario varias veces. Esta función resulta útil si desea recopilar comentarios continuos a lo largo del año. Por ejemplo, puede crear un cuestionario que los empleados usen para dar comentario sobre el servicio de almuerzo en la cafetería.

## <a name="questionnaire-groups"></a>Grupos de cuestionarios

Puede configurar los grupos de cuestionarios e incluir a continuación a los encuestados a los que se debe distribuir un cuestionario. 

Puede crear grupos de cuestionarios a partir de las páginas siguientes:

-   **Grupos de cuestionarios**: solo las personas de un grupo de cuestionarios pueden completar un cuestionario seleccionado. Por ejemplo, su público de destino son contratistas, por lo que crea un grupo de cuestionarios que sea específico para dichos encuestados.
-   **Miembros del grupo de cuestionarios**: puede agregar personas a grupos de cuestionarios.

Para asignar un grupo de cuestionarios a un cuestionario, en la página **Cuestionarios**, haga clic en **Derechos del usuario**. Una vez que se guarda el cuestionario como activo, los miembros del grupo de cuestionarios pueden completar el cuestionario. Esta función resulta de utilidad si desea probar un cuestionario en un grupo seleccionado de personas antes de extenderlo a un grupo mayor, o si desea que el público de un cuestionario sea muy específico.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sesión de respuestas planificadas en un cuestionario

Las sesiones de respuesta planificadas son cuestionarios diseñados por usted y para las que ha seleccionado los encuestados. 

> [!NOTE]
> Para poder configurar sesiones de respuesta planificadas debe diseñar un cuestionario. 

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

Use la página **Tipos de referencia** para configurar tipos de referencia para un cuestionario. Cada tipo de referencia se corresponde con una tabla en Microsoft Dynamics 365 Finance. Al crear programaciones de cuestionarios, puede especificar los registros individuales en la tabla o un intervalo de registros con los que el cuestionario esté asociado. 

Por ejemplo, si selecciona la tabla Cursos, puede decidir para qué curso específico será el cuestionario. Al configurar un tipo de referencia para la tabla Cursos, algunos campos y botones de la página **Cursos** pueden hacerse disponibles.

### <a name="questionnaire-schedules"></a>Programaciones de cuestionarios

Puede usar programaciones del cuestionario para generar varias sesiones de respuesta planificadas para un grupo de usuarios, en función de un tipo de referencia. Cree una programación en la página **Programaciones de cuestionarios**. Seleccione el tipo de planificación para clasificar la programación, y también seleccionar el tipo de referencia que se debe usar para consultar el sistema para usuarios específicos. Por ejemplo, si establece el tipo de referencia en la tabla Cursos, puede seleccionar un curso específico en el campo **Referencia**. 

Haga clic en **Detalles de configuración** para seleccionar el cuestionario y otros criterios. Por ejemplo, especifique el nombre del instructor como criterio si el cuestionario es una evaluación del instructor. Una vez que haya terminado de especificar los detalles de la configuración, el sistema genera sesiones de respuestas planificadas para los usuarios que se incluyen en la consulta. 

Haga clic en **Sesiones de respuestas planificadas** para ver las sesiones de respuesta para la programación. A continuación, puede crear manualmente sesiones de respuestas planificadas adicionales o eliminar sesiones de respuestas planificadas que no se han respondido. 

Haga clic en **Funciones** &gt; **Iniciar** para que el cuestionario esté disponible para los usuarios en sesiones de respuestas planificadas relacionadas. Haga clic en **Respuestas** para ver las respuestas completadas para el cuestionario. Puede copiar opcionalmente la configuración de la programación de cuestionarios, las sesiones de respuestas planificadas y las respuestas a una nueva programación de cuestionarios.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Notificación de los encuestados sobre los cuestionarios que tienen a su disposición
Al distribuir un cuestionario, debe notificar a los encuestados que tienen los cuestionarios a su disposición. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Notificación de los encuestados acerca de una sesión de respuestas planificadas

Si usa una sesión de respuestas planificadas, debe notificar a la persona directamente, por ejemplo, por teléfono o correo electrónico.

### <a name="notifying-respondents-about-a-scheduling"></a>Notificación de los encuestados acerca de una programación

Use la página **Programaciones de cuestionarios** para preparar y enviar correo electrónico a todos los encuestados asignados al cuestionario. Escriba el texto del correo electrónico en la pestaña **Correo electrónico del autoservicio del empleado**. Una vez iniciada la programación, haga clic en **Funciones** &gt; **Enviar correo electrónico** para generar y enviar mensajes de correo electrónico a los encuestados. A continuación, los encuestados pueden iniciar sesión en el sitio Web y completar el cuestionario. 

> [!NOTE]
> Para poder usar la función de correo electrónico, el administrador de TI debe especificar la configuración de correo electrónico en la página **Parámetros del correo electrónico**.

## <a name="ending-a-scheduled-questionnaire"></a>Finalización de un cuestionario programado

Puede finalizar un cuestionario programado una vez que todas las personas que respondan al mismo hayan completado las sesiones de preguntas que les hayan sido asignadas. Cuando finaliza un cuestionario programado, no puede copiar su configuración en una programación nueva. 

> [!NOTE]
>   Si uno o varios de los encuestados no han completado el cuestionario, pero aun así desea finalizar la programación, antes deberá eliminar a esos encuestados de la lista en la página **Sesión de respuestas planificadas**. A continuación, puede finalizar la programación.

## <a name="completing-questionnaires"></a>Completando cuestionarios

Una vez que haya diseñado y haya distribuido un cuestionario, los encuestados seleccionados lo pueden completar. Puede completar los cuestionarios a su disposición desde dos ubicaciones:

-   En el panel de navegación, haga clic en **Cuestionarios** &gt; **Distribuir** &gt; **Completar un cuestionario**.
-   En Autoservicio para empleados, haga clic en **Cuestionarios que deben completarse**.

Los cuestionarios se pueden poner a disposición de usuarios o grupos de usuarios específicos, o de todos los usuarios conectados a una red.




[!INCLUDE[footer-include](../includes/footer-banner.md)]