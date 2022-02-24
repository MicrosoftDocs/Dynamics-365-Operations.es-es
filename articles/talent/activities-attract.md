---
title: Agregar actividades a un proceso de contratación
description: Este tema proporciona información sobre los distintos tipos de actividades que se pueden agregar a un proceso de contratación en Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ce8c0bd74a41b9857538b37d0875583d06e8c11d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462502"
---
# <a name="add-activities-to-a-hiring-process"></a>Agregar actividades a un proceso de contratación

[!include [banner](includes/banner.md)]

Las actividades se pueden agregar como parte del proceso de contratación de Microsoft Dynamics 365 Talent: Attract. Las actividades se pueden agregar a una plantilla de proceso, o se pueden agregar directamente al proceso de contratación en el trabajo. Cuando se define un trabajo, se selecciona una plantilla de proceso, y las actividades que se incluyen en la plantilla se aplican al trabajo. Si no se selecciona una plantilla, se usará la plantilla predeterminada. El proceso de contratación también se puede modificar en el trabajo después de que se aplique la plantilla.

> [!NOTE] 
> Las plantillas de proceso están disponibles con el complemento de contratación completa. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Actividad de candidatos potenciales

La actividad del candidato potencial controla si los candidatos potenciales se pueden agregar a un trabajo. De forma predeterminada, los candidatos potenciales se pueden agregar a un trabajo. Para desactivar la actividad del candidato potencial, establezca la opción **Habilitar candidatos viables** en **Desactivado**. Cuando está activada la actividad de candidatos potenciales, los administradores de contratación pueden agregar y ver candidatos potenciales, y la pestaña **Candidato viable** se muestra en el trabajo.

> [!NOTE]
> Para permitir que se agreguen candidatos a un trabajo de LinkedIn, debe establecer la opción **Habilitar clientes potenciales** en **Activado**.

## <a name="application-activity"></a>Actividad de solicitud

La actividad de solicitud se requiere en la plantilla de proceso de contratación. Para enviar mensajes de correo electrónico a los candidatos cuando presentan su solicitud o se agregan a la etapa de solicitud, establezca la opción **Enviar correo al candidato** en **Activado**.

## <a name="interview-schedule-and-feedback-activity"></a>Programación de entrevista y actividad de comentarios

Esta actividad tiene tres componentes: solicitud de disponibilidad del candidato, programación y comentarios. Use la actividad de la entrevista en la plantilla de trabajo si desea incluir la solicitud, la programación, y los comentarios del candidato como parte del proceso en lugar de usarlas individualmente como parte del proceso de contratación. Para obtener más información acerca de la programación, consulte [Programación de entrevista y comentarios](interview-scheduling-feedback.md).

## <a name="power-apps-activity"></a>Actividad de Power Apps

La actividad de Power Apps le permite insertar una aplicación de Microsoft Power Apps en su proceso de contratación. La aplicación puede ser necesaria para todos los candidatos, los candidatos internos únicamente, los candidatos externos únicamente, o ningún candidato. Si la aplicación se marca como necesaria, se debe realizar para que la etapa pueda avanzar. Para ser considerado completado, el campo **JobApplicationStatus** se debe establecer en **Completado**. Este campo se encuentra en la entidad de JobApplicationActivity, por lo que la aplicación de Power Apps deberá actualizar este campo antes de que la etapa se pueda avanzada. Si la aplicación no se marca como necesaria, la actividad es un paso opcional, y la etapa puede avanzar incluso si la aplicación no se completa.

Para guardar la actividad de Power Apps en el proceso de contratación, debe especificar un identificador de Power Apps. Para buscar el identificador de Power Apps, vaya a [Power Apps](https://web.powerapps.com), seleccione **Aplicaciones**, y después seleccione **Detalles**.

De forma predeterminada, la actividad de Power Apps está disponible para el jefe de contratación, el reclutador y sus delegados. Si selecciona la opción **Permitir agregar participantes a esta actividad**, se pueden agregar participantes adicionales desde el equipo de contratación a una solicitud que utilice la actividad de Power Apps. Por ejemplo, una organización ha creado una aplicación de Power Apps que es una biblioteca de preguntas de entrevistas para roles técnicos. La organización ahora está contratando un nuevo programador de software y ha agregado la actividad de Power Apps al proceso de contratación para el rol del programador de software. Si la opción **Permitir agregar participantes para esta actividad** está seleccionada, un reclutador o un jefe de contratación que esté viendo un candidato para el rol del programador de software puede agregar entrevistadores a la actividad de Power Apps. Estas personas pueden a su vez ver la aplicación que tiene las preguntas de la entrevista.

> [!NOTE]
> La actividad de Power Apps está disponible únicamente con el complemento de contratación completo. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Actividad de YouTube

La actividad de YouTube le permite compartir un vídeo de YouTube como parte del proceso de contratación. Para guardar la actividad de YouTube al proceso de contratación, debe especificar la dirección URL del vídeo de YouTube. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como la actividad de Power Apps, puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el vídeo sólo se muestra como parte de la experiencia del candidato y no en el proceso de contratación.

> [!NOTE]
> La actividad de YouTube está disponible únicamente con el complemento de contratación completo. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Actividad de contenido web

La actividad de contenido Web permite insertar contenido en línea en su proceso de contratación. Para guardar la actividad de contenido web al proceso de contratación, debe especificar la dirección URL del contenido. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como las actividades de Power Apps y YouTube puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el contenido Web solo se muestra como parte de la experiencia del candidato y no en el proceso de contratación. Puede elegir el tamaño del contenido que se muestra.

> [!NOTE]
> La actividad de contenido web está disponible únicamente con el complemento de contratación completo. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Actividad de Microsoft Forms

La actividad de Microsoft Forms le permite insertar una actividad de Microsoft Forms en su proceso de contratación. Microsoft Forms le permite crear cuestionario, encuestas y, sondeos. Para guardar la actividad de Microsoft Forms al proceso de contratación, debe especificar la dirección URL del formulario. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como las actividades de Power Apps, YouTube y contenido Web, puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el formulario sólo se muestra como parte de la experiencia del candidato y no en el proceso de contratación.

En Microsoft Forms, los autores pueden cambiar su configuración para permitir que usuarios de fuera de la organización respondan a su encuesta o cuestionario. En este caso, los usuarios envían las respuestas anónimamente. Si desea ver quién ha completado la encuesta o cuestionario, puede requerir que los encuestados especifiquen sus nombres como parte de la encuesta o cuestionario.

> [!NOTE]
> La actividad de Microsoft Forms está disponible únicamente con el complemento de contratación completo. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Actividad de Offer

La plantilla de proceso de contratación requiere la actividad de Offer. Para usar la aplicación integrada de administración de la propuesta, establezca **Iniciar aplicación de administración de Offer al preparar Offer** en **Activado**. Si el valor es desactivado, el candidato no aparecerá en la aplicación de Offer, por lo que se tuvo que las actualizaciones de seguimiento hasta la actividad de la propuesta de un candidato manualmente. Para definir si los administradores de contratación pueden preparar la propuesta para el candidato en la aplicación Offer, establezca **Administradores de contratación pueden preparar oferta** en **Activado**. Si el trabajo tiene varios puestos asociados a él, puede decidir si desea preparar varias propuestas con el mismo número de puesto. Si desea permitir sólo una propuesta según el puesto por trabajo, establezca **Permitir que los puestos se vuelven a usar dentro de trabajo** en **Desactivado**.

> [!NOTE]
> La aplicación integrada de administración de Offer está disponible únicamente con el complemento de contratación completo. Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).


