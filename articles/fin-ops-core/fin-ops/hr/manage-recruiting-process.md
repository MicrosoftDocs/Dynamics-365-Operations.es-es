---
title: Gestión de procesos de contratación
description: Este artículo describe un concepto que los reclutadores pueden usar para realizar un seguimiento de los pasos de un proceso de reclutamiento.
author: twheeloc
ms.date: 01/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ada6dfc9b227c7ae4ca873e8354d1fcc11ecbaf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910330"
---
# <a name="manage-recruiting-processes"></a>Gestionar procesos de contratación

> [!IMPORTANT]
> La funcionalidad de contratación en este artículo se denominará Proyectos de contratación y se centra en los solicitantes, las solicitudes y los proyectos de contratación. 


Este artículo describe un concepto que permite a los empleadores hacer un seguimiento de los pasos de un proceso de contratación, incluidas las tareas para publicitar vacantes y contratar candidatos, hacer un seguimiento de la información del candidato y de la solicitud, entrevistar a candidatos y seleccionar uno o varios candidatos para cubrir vacantes en su organización.

## <a name="overview"></a>Visión general

Los proyectos de contratación pueden ayudarle a organizar los pasos que seguir para cubrir vacantes en una entidad jurídica. Un candidato es una persona que solicita empleo a su empresa. Una solicitud es una expresión de interés por parte de un candidato por un empleo en una empresa, solicitud que puede ir vinculada a un proyecto de contratación a través de una vacante específica. Un único candidato puede optar a varias solicitudes dentro de la misma entidad jurídica o a través de varias empresas en su organización.

## <a name="recruitment-projects"></a>Proyectos de contratación

Los proyectos de contratación permiten a los empleadores seguir el progreso de una o varias vacantes. El proyecto de contratación identifica el departamento y el trabajo para los cuales hay una o varias vacantes. Los proyectos de contratación también hacen un seguimiento de esta información con respecto a las vacantes:

- El número específico de vacantes
- El jefe de contratación y un contacto alternativo para el puesto
- La fecha de aprobación de la petición
- La fecha límite de la solicitud
- La fecha de inicio estimada

El proyecto de contratación contiene el valor **Anuncio de trabajo** utilizado en la página **Autoservicio para empleados** para publicitar la vacante. La vacante se puede mostrar a los empleados solo si el proyecto de contratación tiene un valor de **Anuncio de trabajo**, el campo **Mostrar en autoservicio para empleados** está establecido en **Sí**, el campo **Fecha límite de la solicitud** está establecido en una fecha futura y el proyecto de contratación tiene un valor de **Estado del proyecto** de **Iniciado**. En la siguiente tabla se muestran los posibles estados de un proyecto de contratación y su descripción.

| Estado    | Indica que...                                                                         |
|-----------|-----------------------------------------------------------------------------------------|
| Programado | Se están preparando las tareas de contratación. La contratación aún no ha empezado para este proyecto. |
| Iniciado   | Ahora se están aceptando solicitudes para las vacantes de este proyecto.                   |
| Terminado  | Se han cubierto todas las vacantes para este proyecto.                                         |
| Cancelado  | La contratación se ha cancelado para este proyecto.                                          |

Los empleadores también pueden registrar los **Medios** utilizados para publicitar las vacantes a través de canales externos, además de hacer un seguimiento de los **Progresos** en relación con el proyecto o las solicitudes.

## <a name="applicants"></a>Candidatos

Un candidato es una persona que solicita un trabajo en su empresa. Los solicitantes se comparten entre todas las entidades jurídicas de su organización. Por lo tanto, tiene una gran reserva de talento en la que buscar. Puede mantener capacidades, referencias, solicitudes de alojamiento e información personal sobre los candidatos. Al crear un registro de candidato, se creará un registro de la persona para dicho candidato en la libreta de direcciones global. Puede usar la página **Candidato** para actualizar la siguiente información de la libreta de direcciones global de candidatos:

- Información de dirección
- Información de contacto
- Información de identificación
- Detalles del nombre
- Información personal

## <a name="applications"></a>Aplicaciones

Puede registrar la información de las solicitudes de empleo que reciba en la página **Solicitud**. La solicitud es la expresión de interés por parte de un candidato en una vacante en su organización. Para crear una solicitud, el candidato debe existir como candidato o persona en el sistema.

Las solicitudes de empleo enviadas a la web por los candidatos pueden ser solicitadas, en respuesta a una oferta de trabajo, o no solicitadas. Las solicitudes se asocian automáticamente con el proyecto de contratación desde el que se creó la oferta de trabajo. Si no se ha solicitado, la petición de empleo se asocia con el proyecto de contratación que se especifique en el área **Contratación** de la página **Parámetros de recursos humanos**.

### <a name="application-status"></a>Estado de la solicitud

El estado de la solicitud indica el punto del proceso de contratación en el que se encuentra la solicitud. En la siguiente tabla se muestran los posibles estados de una solicitud y su descripción.

| Estado    | Indica que...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Recibido  | La solicitud se ha recibido.                                                             |
| Confirmado | Se puede enviar una notificación al candidato para confirmar la recepción de su solicitud.            |
| Entrevista | Se puede enviar una invitación al candidato.                                     |
| Rechazo | Se puede enviar una carta de rechazo al candidato.                                          |
| Cancelado  | Se puede enviar una confirmación de renuncia al candidato. Este estado se asigna manualmente. |
| Contratado  | Se puede enviar una oferta de empleo al candidato.                                         |

### <a name="correspondence-actions"></a>Acciones de correspondencia

La acción de correspondencia de una solicitud determina el documento o la plantilla de correo electrónico utilizada para comunicarse con el candidato que envió la solicitud. Al asociar **Marcadores de solicitud** con acciones de correspondencia, puede usar valores de las páginas **Solicitud**, **Candidato**, **Entrevista** y **Proyecto de contratación** en sus comunicaciones con los candidatos. Al crear **Plantillas de correo electrónico para solicitudes** para las acciones correspondientes, puede enviar rápidamente mensajes de correo electrónico a los candidatos con una solicitud con determinada combinación de acción de correspondencia y estado. Por ejemplo, puede enviar un mensaje de correo electrónico de confirmación a todas las solicitudes con valor de **Estado** **Recibido** y un valor de **Acción de correspondencia** de **Recibido**. Tras enviar el mensaje de correo electrónico, tiene la opción de actualizar automáticamente el estado de las solicitudes.

## <a name="application-routing"></a>Enrutamiento de solicitudes

Si varios trabajadores deben revisar una solicitud, puede usar la página **Enrutamiento de solicitudes** para crear una lista de circulación para gestionar el proceso.

## <a name="interviews"></a>Entrevistas

**Entrevistas a candidatos** se puede programar desde la página **Solicitudes**. Use el botón **Enviar información de reunión** para enviar un archivo de calendario con la información de programación de entrevistas al candidato y al entrevistador.

## <a name="skill-mapping"></a>Distribución de habilidades

**Distribución de habilidades** y **Perfiles de distribución de habilidades** se pueden usar para identificar a los candidatos adecuados para una vacante.

## <a name="hiring-applicants"></a>Contratación de candidatos

Use la página **Solicitudes** para contratar a un candidato. Si contrata a un candidato, el registro de solicitud tendrá un estado **Empleado**, y el registro en la libreta de direcciones global del candidato se asociará al registro de nuevo trabajador. Las modificaciones de la información en la libreta de direcciones global del registro del trabajador nuevo también se mostrarán en el registro del candidato. Esto puede ayudar a reducir la entrada de datos si el nuevo trabajador solicitase un trabajo diferente en su empresa. Para contratar a un trabajador existente en un nuevo puesto, haga clic en **Cambiar puesto** en la ficha desplegable **Estado de la solicitud** para iniciar el proceso de transferencia.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
