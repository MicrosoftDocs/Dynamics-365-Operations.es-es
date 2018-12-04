---
title: Actividades en los proceso
description: "Este tema proporciona información sobre los distintos tipos de actividades que se pueden usar en el proceso de contratación."
author: 
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: ccd9e2d0ff1f7fb6825c6823936b4013b3054f5d
ms.contentlocale: es-es
ms.lasthandoff: 10/22/2018

---

# <a name="activities-in-the-hiring-processes"></a>Actividades en los procesos de contratación

[!include[banner](../includes/banner.md)]

Las actividades se pueden agregar como parte del proceso de contratación de Microsoft Dynamics 365 for Talent: Attract. Las actividades se pueden agregar a una plantilla de proceso, o se pueden agregar directamente al proceso de contratación en el trabajo. Cuando se define un trabajo, se selecciona una plantilla de proceso, y las actividades que se incluyen en la plantilla se aplican al trabajo. Si no se selecciona una plantilla, se usará la plantilla predeterminada. El proceso de contratación también se puede modificar en el trabajo después de que se aplique la plantilla.

> [!NOTE] 
> Las plantillas de proceso están disponibles con el complemento de contratación completa.

## <a name="prospect-activity"></a>Actividad de candidatos potenciales

La actividad del candidato potencial controla si los candidatos potenciales se pueden agregar a un trabajo. De forma predeterminada, los candidatos potenciales se pueden agregar a un trabajo. Para desactivar la actividad del candidato potencial, establezca la opción **Habilitar candidatos viables** en **Desactivado**. Cuando está activada la actividad de candidatos potenciales, los administradores de contratación pueden agregar y ver candidatos potenciales, y la pestaña **Candidato viable** se muestra en el trabajo.

## <a name="application-activity"></a>Actividad de solicitud

La actividad de solicitud se requiere en la plantilla de proceso de contratación. Para enviar mensajes de correo electrónico a los candidatos cuando presentan su solicitud o se agregan a la etapa de solicitud, establezca la opción **Enviar correo al candidato** en **Activado**.

## <a name="scheduler-activity"></a>Actividad de programación

La actividad del programador es opcional. Esta actividad tiene dos componentes: Disponibilidad del candidato y programación. El componente disponibilidad del candidato le permite utilizar el correo electrónico para solicitar la disponibilidad de un candidato. El componente Programación proporciona la capacidad de programar entrevistas con el candidato y el equipo de contratación. En la actividad del programador, las siguientes opciones se pueden configurar: **Solicitar disponibilidad del candidato**, **Conferencia en línea**, y **Enviar correo al candidato**.

- Para enviar mensajes de correo electrónico a los candidatos para solicitar su disponibilidad, establezca la opción **Solicitar disponibilidad del candidato** en **Activado**. Si establece la opción en **Desactivado**, este paso no se mostrará en el proceso de contratación en el trabajo.
- Para tener una llamada o una conferencia en directo con Skype Empresarial, establezca el campo **Conferencia en línea** en **Skype Empresarial**. Se agregará el vínculo **Unirse a reunión en Skype** a la solicitud de reunión de entrevista que se envía a las entrevistadores.
- Para enviar mensajes de correo electrónico a los candidatos para finalizar la programación, establezca la opción **Enviar correo al candidato** en **Activado**. Si establece la opción en **Desactivado**, los candidatos recibirán la programación de la entrevista solo si firman en el portal del candidato.

## <a name="feedback-activity"></a>Actividad de valoración

La actividad de valoración es opcional. Esta actividad permite a los participantes a una entrevista especificar recomendaciones para un candidato. También pueden especificar cualquier comentario valorativo que tengan. Si se activa la opción **Heredar participantes de comentarios del equipo de contratación**, se especifica automáticamente el reclutador, el administrador de contratación, y los entrevistadores en la actividad de valoración. Las organizaciones pueden permitir a los entrevistadores ver los comentarios de otras personas antes enviar su propio comentario. Las organizaciones pueden también permitir que los entrevistadores editen sus comentarios después de enviarlos.

## <a name="interview-activity"></a>Actividad de entrevista

La actividad de entrevista es opcional. Esta actividad tiene tres componentes: Disponibilidad del candidato, programación y comentarios. El componente disponibilidad del candidato le permite utilizar el correo electrónico para solicitar la disponibilidad de un candidato. El componente Programación proporciona la capacidad de programar entrevistas con el candidato y el equipo de contratación. En la actividad del programador, las siguientes opciones se pueden configurar: **Solicitar disponibilidad del candidato**, **Conferencia en línea**, y **Enviar correo al candidato**.

- Para enviar mensajes de correo electrónico a los candidatos para solicitar su disponibilidad, establezca la opción **Solicitar disponibilidad del candidato** en **Activado**. Si establece la opción en **Desactivado**, este paso no se mostrará en el proceso de contratación en el trabajo.
- Para tener una llamada o una conferencia en directo con Skype Empresarial, establezca el campo **Conferencia en línea** en **Skype Empresarial**. Se agregará el vínculo **Unirse a reunión en Skype** correcto a la solicitud de reunión de entrevista.
- Para enviar mensajes de correo electrónico a los candidatos para finalizar la programación, establezca la opción **Enviar correo al candidato** en **Activado**. Si establece la opción en **Desactivado**, los candidatos recibirán la programación de la entrevista solo si firman en el portal del candidato.

El componente comentarios permite a las personas especificar recomendaciones para un candidato. También pueden especificar cualquier comentario valorativo que tengan. Si se activa la opción **Heredar participantes de comentarios del equipo de contratación**, se especifica automáticamente el reclutador, el administrador de contratación, y los entrevistadores en el componente de valoración. Las organizaciones pueden permitir a los entrevistadores ver los comentarios de otras personas antes enviar su propio comentario. Las organizaciones pueden también permitir que los entrevistadores editen sus comentarios después de enviarlos.

## <a name="powerapps-activity"></a>Actividad de PowerApps

La actividad de PowerApps le permite insertar una aplicación de Microsoft PowerApps en su proceso de contratación. La aplicación puede ser necesaria para todos los candidatos, los candidatos internos únicamente, los candidatos externos únicamente, o ningún candidato. Si la aplicación se marca como necesaria, se debe realizar para que la etapa pueda avanzar. Si la aplicación no se marca como necesaria, la actividad es un paso opcional, y la etapa puede avanzar incluso si la aplicación no se completa.

Para guardar la actividad de PowerApps en el proceso de contratación, debe especificar un identificador de PowerApps. Para buscar el identificador de PowerApps, vaya a [PowerApps](https://web.powerapps.com), seleccione **Aplicaciones**, y después seleccione **Detalles**.

Si selecciona la opción **Permitir agregar participantes a esta actividad**, se pueden agregar contribuidores adicionales a una solicitud que utilice la actividad de PowerApps. Por ejemplo, una organización ha creado una aplicación de PowerApps que es una biblioteca de preguntas de entrevistas para roles técnicos. La organización ahora está contratando un nuevo programador de software y ha agregado la actividad de PowerApps al proceso de contratación para el rol del programador de software. Si la opción **Permitir agregar participantes para esta actividad** está seleccionado, un reclutador o un jefe de contratación que esté viendo un candidato para el rol del programador de software puede agregar personas a la actividad de PowerApps. Estas personas pueden a su vez ver la aplicación que tiene las preguntas de la entrevista.

> [!NOTE]
> La actividad de PowerApps está disponible únicamente con el complemento de contratación completo.

## <a name="youtube-activity"></a>Actividad de YouTube

La actividad de YouTube le permite compartir un vídeo de YouTube como parte del proceso de contratación. Para guardar la actividad de YouTube al proceso de contratación, debe especificar la dirección URL del vídeo de YouTube. Con respecto a la actividad de PowerApps, puede permitir que se agreguen participantes a la actividad. Si selecciona la opción **Mostrar solo al candidato**, el vídeo solo se muestra como parte de la experiencia del candidato. No se muestra en el proceso de contratación en Attract.

> [!NOTE]
> La actividad de YouTube está disponible únicamente con el complemento de contratación completo.

## <a name="web-content-activity"></a>Actividad de contenido web

La actividad de contenido Web permite insertar contenido en línea en su proceso de contratación. Para guardar la actividad de contenido web al proceso de contratación, debe especificar la dirección URL del contenido. Con respecto a las actividades de PowerApps y YouTube, puede permitir que se agreguen participantes a la actividad. Si selecciona la opción **Mostrar solo al candidato**, el contenido solo se muestra como parte de la experiencia del candidato. No se muestra en el proceso de contratación en Attract. Puede seleccionar el tamaño del contenido que se muestra.

> [!NOTE]
> La actividad de contenido web está disponible únicamente con el complemento de contratación completo.

## <a name="microsoft-forms-activity"></a>Actividad de Microsoft Forms

La actividad de Microsoft Forms le permite insertar un formulario de Microsoft Forms en su proceso de contratación. Microsoft Forms le permite crear cuestionario, encuestas y, sondeos. Para guardar la actividad de Microsoft Forms al proceso de contratación, debe especificar la dirección URL del formulario. Con respecto a las actividades de PowerApps, YouTube y contenido web, puede permitir que se agreguen participantes a la actividad. Si selecciona la opción **Mostrar solo al candidato**, el formulario solo se muestra como parte de la experiencia del candidato. No se muestra en el proceso de contratación en Attract.

En Microsoft Forms, los autores pueden cambiar su configuración para permitir que usuarios de fuera de la organización respondan a su encuesta o cuestionario. En este caso, los usuarios envían las respuestas anónimamente. Si desea ver quién ha completado la encuesta o cuestionario, puede requerir que los encuestados especifiquen sus nombres como parte de la encuesta o cuestionario.

> [!NOTE]
> La actividad de Microsoft Forms está disponible únicamente con el complemento de contratación completo.

