---
title: Programación y realimentación de la entrevista
description: Este tema proporciona información acerca de la programación de la entrevista y las actividades de realimentación en Attract.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: shielas
ms.openlocfilehash: 39b14f3ca855ca283a7484e480ff2547623938ef
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519015"
---
# <a name="interview-scheduling-and-feedback"></a>Programación y realimentación de la entrevista

[!include[banner](../includes/banner.md)]

## <a name="scheduler-activity"></a>Actividad de programación

La actividad del programador es opcional y tiene dos componentes: Solicitud de disponibilidad del candidato y programación. El componente disponibilidad del candidato le permite utilizar el correo electrónico para solicitar la disponibilidad de un candidato. El componente Programación proporciona la capacidad de programar entrevistas con el candidato y el equipo de contratación.

Para configurar la actividad del programador para incluir o limitar los candidatos que se programarán, seleccione un valor en el campo **A quién está programando**. Las opciones disponibles son **Todos los candidatos**, **Candidatos externos** y **Candidatos internos**. Por ejemplo, si desea omitir candidatos internos en la primera ronda de programación, puede asignar la actividad de la programación solo a los candidatos externos estableciendo **A quién está programando** en **Candidatos externos**.

### <a name="candidate-availability-request"></a>Solicitud de disponibilidad del candidato

Para enviar mensajes de correo electrónico a los candidatos para solicitar su disponibilidad, seleccione el campo **Solicitar disponibilidad del candidato**. Si el campo no se selecciona, este paso no se mostrará en el proceso de contratación para el trabajo.

Para registrar la disponibilidad de la solicitud, haga clic en **Enviar solicitud**, elija las fechas disponibles y una plantilla de correo electrónico y mande el correo al candidato.

[![Vista del reclutador de Attract para enviar la solicitud de disponibilidad del candidato](./media/scheduler-candidate-request.png)](./media/scheduler-candidate-request.png)

Cuando el candidato recibe un mensaje de correo electrónico para responder a la solicitud, pueden iniciar sesión en su portal del candidato, elegir las fechas que coinciden con su disponibilidad y hacer clic en **Enviar**.

### <a name="schedule"></a>Programación
Existen varias configuraciones disponibles para que el programador de la entrevista utilice y cree y registre rápidamente el bucle de la entrevista a los entrevistadores y el candidato.

1. Haga clic en **Crear programación**, y en la casilla **Agregar entrevistadores**, aparecerá una lista de todos los entrevistadores que van a formar parte del bucle de la entrevista.
[![Vista del reclutador de Attract para programar un bucle de entrevista](./media/schedule-start-over.png)](./media/schedule-start-over.png)   
    Si el candidato ha respondido a la disponibilidad de la solicitud de la entrevista, el campo **Fecha de la entrevista** se rellenará con su selección. Puede seleccionar una fecha distinta si es necesario.
    
    Si selecciona el campo **Convertir en entrevista de panel**, se traslada al grupo de entrevistadores de la izquierda a un único bucle de panel para crear la entrevista. A continuación deberá definir una secuencia específica para las entrevistas.
    
    La programación de la entrevista se debe organizar para que coincida lo mejor posible con la disponibilidad de los participantes. Si es un candidato interno, puede incluir su disponibilidad como parte de la recomendación de la programación.
    
    Para tener una conferencia en línea, seleccione el campo **Agregar reuniones de Skype** y cada evento de la entrevista tendrá un vínculo **Skype Empresarial** disponible.

2. Seleccione la duración de la entrevista para cada evento de la entrevista y, a continuación hacen clic en **Aceptar** para iniciar la programación.

    Si se selecciona **Recomendaciones**, las sugerencias se mostrarán y se preparará la cuadrícula de la entrevista. Podrá ver la disponibilidad del calendario actual de toda los entrevistadores seleccionados. También podrá ver el calendario del candidato si es un candidato interno. Para los entrevistadores y candidatos internos, puede ver sus franjas horarias No disponibles, el horario laboral, sus horas fuera de la oficina y también identificar si han marcado sus calendarios como trabajando en otra parte para las franjas horarias específicas. 

3. Si no hay sugerencias disponibles, en la columna **Entrevistadores**, haga clic en una franja horaria, proporcione el título de la entrevista, detalles y rellene los detalles de la ubicación, según sea necesario. Puede elegir incluir el vínculo **Skype Empresarial** para la entrevista.

4. Para incluir a entrevistadores adicionales, haga clic en la columna de la cuadrícula **Agregar entrevista** para seleccionar uno o más entrevistadores. Puede usar la opción de los puntos suspensivos (...) para quitar una entrevista del bucle.
    
5. Si las entrevistas se programan en una zona horaria diferente, seleccione la ciudad o la zona horaria necesarias de la lista desplegable en la parte superior derecha. La cuadrícula de disponibilidad del entrevistador se actualizará para reflejar la nueva zona horaria. Esta selección de la zona horaria también mostrará en la vista **Resumen de la entrevista**, que será compartida con los entrevistadores y el candidato. 

6. Haga clic en **Enviar a los entrevistadores** para enviar invitaciones a la reunión a los entrevistadores implicados.

    Una vez que las solicitudes de la entrevista se han enviado a los entrevistadores, pueden responder directamente al correo electrónico de invitación que reciben.

    >[!NOTE]
    > Para todas las entrevistas personales, se envían avisos a los entrevistadores cada 24 horas si el entrevistador no ha respondido (aceptado o rechazado) a la solicitud de la entrevista.

    > Para todas las entrevistas de panel, no hay avisos automatizados para la solicitud de la entrevista. Para activar un aviso manualmente, edite la entrevista y use la opción **Actualizar y registrar** para enviar la solicitud de nuevo a los entrevistadores.

    Se capturan las respuestas de entrevistador y se muestran en Attract. Si un entrevistador rechaza la invitación, se le notificará para realizar un cambio. Para ver su respuesta en la vista de cuadrícula **Programador**, haga clic en el icono de la burbuja.

[![Vista del reclutador de Attract de la respuesta de un entrevistador](./media/schedule-interviewer-response2.png)](./media/schedule-interviewer-response2.png)

7. Una vez que la programación de la entrevista está lista para compartirse con el candidato, haga clic en **Enviar al candidato**. Puede elegir ocultar o mostrar los nombres y las franjas del entrevistador con el candidato.

8. Seleccione una plantilla de correo electrónico y envíe el resumen de la entrevista al candidato. El candidato puede ver esta información en su correo electrónico así como en su portal del candidato.
    
>[!NOTE] 
> El calendario de disponibilidad de un candidato se muestra si el candidato es interno. Del mismo modo, solo los candidatos internos pueden ser utilizados para ampliar recomendaciones de la programación de la entrevista. Actualmente, los candidatos (internos o externos) no reciben un correo electrónico con la invitación a la reunión, en su lugar el candidato recibe sólo un resumen de las entrevistas.

Los candidatos recibirán un correo electrónico con el resumen del bucle de su entrevista. Los correos electrónicos contienen un archivo .ics que se pueda guardar en los calendarios personales para un acceso más fácil y ver las notificaciones sobre la entrevista.

>[!TIP] 
> En caso de que se vuelva a enviar la programación de la entrevista al candidato, este recibirá otro archivo adjunto .ics. Es recomendable actualizar las plantillas de correo electrónico para el resumen de la entrevista del candidato para garantizar que los candidatos eliminan los eventos anteriormente agregados de la entrevista y no ven duplicados en su calendario. 

## <a name="feedback-activity"></a>Actividad de comentarios

La actividad de comentarios es opcional en una plantilla de trabajo. Esta actividad permite a los participantes en una entrevista añadir recomendaciones o comentarios para un candidato. 

Para incluir o limitar los candidatos sobre los que proporcionar comentarios, seleccione un valor en el campo **De quién deben hacer comentarios los entrevistadores**.  Las opciones disponibles son **Todos los candidatos**, **Candidatos externos** y **Candidatos internos**. Por ejemplo, si desea omitir candidatos internos en la primera ronda de programación, establezca **De quién deben hacer comentarios los entrevistadores** en **Candidatos externos**.

Si se selecciona el campo **Heredar participantes de comentarios del equipo de contratación**, se especifica automáticamente el reclutador, el administrador de contratación, y los entrevistadores en la actividad de comentarios. Las organizaciones pueden permitir a los entrevistadores ver los comentarios de otras personas antes enviar su propio comentario. Las organizaciones pueden también permitir que los entrevistadores editen sus comentarios después de enviarlos. Se recuerdaa los entrevistadores registrar los comentarios de las entrevistas que han realizado recientemente según la configuración preestablecida como parte de la plantilla de trabajo. El administrador de contratación o un reclutador en el trabajo puede elegir también para recordar manualmente a un entrevistador enviar comentarios.

## <a name="interview-activity"></a>Actividad de entrevista

La actividad de la entrevista es una actividad opcional con tres componentes: **Solicitud de disponibilidad del candidato**, **Programación** y **Comentarios**. Use la actividad de la entrevista en la plantilla de trabajo si desea toda la solicitud, la programación y los comentarios del candidato en lugar de usarlos individualmente.

Para incluir o limitar los candidatos que se entrevistarán con, seleccione un valor en el campo **A quién está entrevistando**. Las opciones disponibles son **Todos los candidatos**, **Candidatos externos** y **Candidatos internos**. Por ejemplo, si desea omitir candidatos internos en la primera ronda de entrevistas, establezca **A quién está entrevistando** en **Candidatos externos**.
