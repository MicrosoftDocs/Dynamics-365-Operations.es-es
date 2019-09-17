---
title: Actividades en los procesos en Microsoft Dynamics 365 for Talent - Attract
description: Este tema proporciona información sobre los distintos tipos de actividades que se pueden usar en el proceso de contratación en Microsoft Dynamics 365 for Talent - Attract.
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
ms.openlocfilehash: 4d52f3a384ad2a54986d1bd23baeefbaae30c9e2
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739733"
---
# <a name="activities-in-hiring-processes"></a>Actividades en los procesos de contratación

[!include[banner](../includes/banner.md)]

Las actividades se pueden agregar como parte del proceso de contratación de Microsoft Dynamics 365 for Talent: Attract. Las actividades se pueden agregar a una plantilla de proceso, o se pueden agregar directamente al proceso de contratación en el trabajo. Cuando se define un trabajo, se selecciona una plantilla de proceso, y las actividades que se incluyen en la plantilla se aplican al trabajo. Si no se selecciona una plantilla, se usará la plantilla predeterminada. El proceso de contratación también se puede modificar en el trabajo después de que se aplique la plantilla.

> [!NOTE] 
> Las plantillas de proceso están disponibles con el complemento de contratación completa. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Actividad de candidatos potenciales

La actividad del candidato potencial controla si los candidatos potenciales se pueden agregar a un trabajo. De forma predeterminada, los candidatos potenciales se pueden agregar a un trabajo. Para desactivar la actividad del candidato potencial, establezca la opción **Habilitar candidatos viables** en **Desactivado**. Cuando está activada la actividad de candidatos potenciales, los administradores de contratación pueden agregar y ver candidatos potenciales, y la pestaña **Candidato viable** se muestra en el trabajo.

> [!NOTE]
> Para permitir que se agreguen candidatos a un trabajo de LinkedIn, debe establecer la opción **Habilitar clientes potenciales** en **Activado**.

## <a name="application-activity"></a>Actividad de solicitud

La actividad de solicitud se requiere en la plantilla de proceso de contratación. Para enviar mensajes de correo electrónico a los candidatos cuando presentan su solicitud o se agregan a la etapa de solicitud, establezca la opción **Enviar correo al candidato** en **Activado**.

## <a name="interview-schedule-and-feedback-activity"></a>Programación de entrevista y actividad de comentarios

Esta actividad tiene tres componentes: solicitud de disponibilidad del candidato, programación y comentarios. Use la actividad de la entrevista en la plantilla de trabajo si desea incluir la solicitud, la programación, y los comentarios del candidato como parte del proceso en lugar de usarlas individualmente como parte del proceso de contratación. Para obtener más información acerca de la programación, consulte [Programación de entrevista y comentarios](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>Actividad de PowerApps

La actividad de PowerApps le permite insertar una aplicación de Microsoft PowerApps en su proceso de contratación. La aplicación puede ser necesaria para todos los candidatos, los candidatos internos únicamente, los candidatos externos únicamente, o ningún candidato. Si la aplicación se marca como necesaria, se debe realizar para que la etapa pueda avanzar. Para ser considerado completado, el campo **JobApplicationStatus** se debe establecer en **Completado**. Este campo se encuentra en la entidad de JobApplicationActivity, por lo que la aplicación de PowerApps deberá actualizar este campo antes de que la etapa se pueda avanzada. Si la aplicación no se marca como necesaria, la actividad es un paso opcional, y la etapa puede avanzar incluso si la aplicación no se completa.

Para guardar la actividad de PowerApps en el proceso de contratación, debe especificar un identificador de PowerApps. Para buscar el identificador de PowerApps, vaya a [PowerApps](https://web.powerapps.com), seleccione **Aplicaciones**, y después seleccione **Detalles**.

De forma predeterminada, la actividad de PowerApps está disponible para el jefe de contratación, el reclutador y sus delegados. Si selecciona la opción **Permitir agregar participantes a esta actividad**, se pueden agregar participantes adicionales desde el equipo de contratación a una solicitud que utilice la actividad de PowerApps. Por ejemplo, una organización ha creado una aplicación de PowerApps que es una biblioteca de preguntas de entrevistas para roles técnicos. La organización ahora está contratando un nuevo programador de software y ha agregado la actividad de PowerApps al proceso de contratación para el rol del programador de software. Si la opción **Permitir agregar participantes para esta actividad** está seleccionado, un reclutador o un jefe de contratación que esté viendo un candidato para el rol del programador de software puede agregar entrevistadores a la actividad de PowerApps. Estas personas pueden a su vez ver la aplicación que tiene las preguntas de la entrevista.

> [!NOTE]
> La actividad de PowerApps está disponible únicamente con el complemento de contratación completo. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Actividad de YouTube

La actividad de YouTube le permite compartir un vídeo de YouTube como parte del proceso de contratación. Para guardar la actividad de YouTube al proceso de contratación, debe especificar la dirección URL del vídeo de YouTube. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como la actividad de PowerApps, puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el vídeo sólo se muestra como parte de la experiencia del candidato y no en el proceso de contratación.

> [!NOTE]
> La actividad de YouTube está disponible únicamente con el complemento de contratación completo. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Actividad de contenido web

La actividad de contenido Web permite insertar contenido en línea en su proceso de contratación. Para guardar la actividad de contenido web al proceso de contratación, debe especificar la dirección URL del contenido. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como las actividades de PowerApps y YouTube, puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el contenido Web solo se muestra como parte de la experiencia del candidato y no en el proceso de contratación. Puede elegir el tamaño del contenido que se muestra.

> [!NOTE]
> La actividad de contenido web está disponible únicamente con el complemento de contratación completo. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Actividad de Microsoft Forms

La actividad de Microsoft Forms le permite insertar una actividad de Microsoft Forms en su proceso de contratación. Microsoft Forms le permite crear cuestionario, encuestas y, sondeos. Para guardar la actividad de Microsoft Forms al proceso de contratación, debe especificar la dirección URL del formulario. Puede elegir mostrar el contenido al **Equipo de contratación**, **Candidatos internos únicamente**, **Candidatos externos solamente**, o **Todos los candidatos**. Como las actividades de PowerApps, YouTube y Web, puede permitir que se agreguen participantes del equipo de contratación a la actividad. Si elige mostrar el contenido a los candidatos, el formulario sólo se muestra como parte de la experiencia del candidato y no en el proceso de contratación.

En Microsoft Forms, los autores pueden cambiar su configuración para permitir que usuarios de fuera de la organización respondan a su encuesta o cuestionario. En este caso, los usuarios envían las respuestas anónimamente. Si desea ver quién ha completado la encuesta o cuestionario, puede requerir que los encuestados especifiquen sus nombres como parte de la encuesta o cuestionario.

> [!NOTE]
> La actividad de Microsoft Forms está disponible únicamente con el complemento de contratación completo. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Actividad de Offer

La plantilla de proceso de contratación requiere la actividad de Offer. Para usar la aplicación integrada de administración de la propuesta, establezca **Iniciar aplicación de administración de Offer al preparar Offer** en **Activado**. Si el valor es desactivado, el candidato no aparecerá en la aplicación de Offer, por lo que se tuvo que las actualizaciones de seguimiento hasta la actividad de la propuesta de un candidato manualmente. Para definir si los administradores de contratación pueden preparar la propuesta para el candidato en la aplicación Offer, establezca **Administradores de contratación pueden preparar oferta** en **Activado**. Si el trabajo tiene varios puestos asociados a él, puede decidir si desea preparar varias propuestas con el mismo número de puesto. Si desea permitir sólo una propuesta según el puesto por trabajo, establezca **Permitir que los puestos se vuelven a usar dentro de trabajo** en **Desactivado**.

> [!NOTE]
> La aplicación integrada de administración de Offer está disponible únicamente con el complemento de contratación completo. Para más información consulte [Capacidades complementarias de contratación completa de Attract](./attract-comprehensive-hiring.md).


