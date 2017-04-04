---
title: "Gestión de un proceso de contratación"
description: "Este artículo describe un concepto que permite a los empleadores hacer un seguimiento de los pasos de un proceso de contratación, incluidas las tareas para publicitar vacantes y contratar candidatos, hacer un seguimiento de la información del candidato y de la solicitud, entrevistar a candidatos y seleccionar uno o varios candidatos para cubrir vacantes en su organización."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>Gestión de un proceso de contratación

Este tema describe un concepto que los reclutadores pueden usar para realizar los pasos de un proceso de contratación, incluidos esfuerzos para anunciar de puestos abierto y para contratar candidatos, siguiendo el candidato y candidatos de la información de la solicitud, el entrevistarse con, seleccionando uno o varios candidatos los puestos abierto de la organización.

<a name="overview"></a>Visión general
--------

Los proyectos de contratación pueden ayudarle a organizar los pasos que seguir para cubrir vacantes en una entidad jurídica. Un candidato es una persona que solicita un empleo a su empresa.  Una aplicación es la expresión de interés de un candidato en ser un empleado por una empresa y se puede los gastos un proyecto de contratación para expresar interés en una apertura específica.  Un único candidato puede tener varios usos dentro de la misma entidad jurídica o entre varias empresas de su organización.

<a name="recruitment-projects"></a>Proyectos de contratación
--------------------

Los proyectos de contratación permiten a los reclutadores sigan progreso rellenar con una o más puestos abierto.  El proyecto de contratación identifica el departamento y el trabajo para la que una o más puestos sea abierto. Los proyectos de contratación también hacen un seguimiento de esta información con respecto a las vacantes:
-   El número específico de vacantes
-   El jefe de contratación y un contacto alternativo para el puesto
-   La fecha de aprobación de la petición
-   La fecha límite de la solicitud
-   La fecha de inicio estimada

El proyecto de contratación contiene el **Anuncio de trabajo** utilizado en **Autoservicio para empleados** para publicitar la vacante. Para mostrar la vacante a los empleados, el proyecto de contratación debe tener un **Anuncio de trabajo**, el campo** Mostrar en autoservicio para empleados** debe estar establecido en Sí, **Fecha límite de la solicitud** debe estar establecido en una fecha futura y el proyecto de contratación debe tener Iniciado como **Estado del proyecto**. En la tabla siguiente se muestran los estados de proyecto de contratación posibles y su descripción.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Programado | Se preparan esfuerzos de contratación.  El contratación aún no ha iniciado para este proyecto. |
| Iniciado   | Ahora se están aceptando solicitudes para las vacantes de este proyecto.                    |
| Terminado  | Se han cubierto todas las vacantes para este proyecto.                                          |
| Cancelado  | La contratación se ha cancelado para este proyecto.                                           |

Los empleadores también pueden registrar los **Medios** utilizados para publicitar las vacantes a través de canales externos, además de hacer un seguimiento de los **Progresos** en relación con el proyecto o las solicitudes.

<a name="applicants"></a>Candidatos
----------

Un candidato es una persona que solicita un trabajo en su empresa.  Comparten candidatos entre todas las entidades jurídicas de la organización que le proporciona un conjunto de talento mayor para buscar desde. Puede mantener capacidades, referencias, solicitudes de alojamiento e información personal sobre los candidatos. Al crear un registro de candidato, se creará un registro de la persona para dicho candidato en la libreta de direcciones global. Puede usar la página **Candidato** para actualizar la siguiente información de la libreta de direcciones global de candidatos:
-   Información de dirección
-   Información de contacto
-   Información de identificación
-   Detalles del nombre
-   Información personal

## <a name="applications"></a>Aplicaciones
Puede registrar la información de las solicitudes de empleo que reciba en la página **Solicitud**. La aplicación es la expresión de interés del candidato en la apertura de trabajo en su organización.  Para crear una solicitud, el candidato debe existir ya como un candidato o persona en el sistema.
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

La acción de correspondencia de una **solicitud** determina el documento o la plantilla de correo electrónico utilizada para comunicarse con el candidato que envió la solicitud. Puede asociar ** los marcadores de solicitud ** con acciones de correspondencia para permitir que se use valores de las páginas de la aplicación, del candidato, de la entrevista, y del proyecto de contratación en sus comunicaciones con los candidatos.  ** Las plantillas de correo electrónico de solicitud ** se pueden crear para que las acciones de correspondencia registren rápidamente mensajes de correo electrónico a candidatos con una aplicación a una combinación de estado y la acción de correspondencia. Por ejemplo, puede enviar un correo electrónico de confirmación a todas las aplicaciones con un estado ** ** Received y a ** acción de correspondencia ** Received.  Tras publicar el correo electrónico, tiene la opción de actualizar automáticamente el estado de solicitudes.

## <a name="application-routing"></a>Enrutamiento de solicitudes

Si varios trabajadores deben revisar una solicitud, puede usar la página **Enrutamiento de solicitudes** para crear una lista de circulación para gestionar el proceso.

## <a name="interviews"></a>Entrevistas

** El candidato se entrevista con ** puede programar ** de las aplicaciones ** página.  Use ** registrar información de la reunión ** botón para enviar un archivo de calendario con la información de programación de la entrevista en el candidato y el entrevistador.

## <a name="skill-mapping"></a>Distribución de habilidades

**Distribución de habilidades** y **Perfiles de distribución de habilidades** se pueden usar para identificar a los candidatos adecuados para una vacante.

## <a name="hiring-applicants"></a>Contratación de candidatos

Use la página **Solicitudes** para contratar a un candidato. Si contrata a un candidato, el registro de solicitud tendrá un estado **Empleado**, y el registro en la libreta de direcciones global del candidato se asociará al registro de nuevo trabajador. Las modificaciones de la información en la libreta de direcciones global del registro del trabajador nuevo también se mostrarán en el registro del candidato. Esto puede ayudar a reducir la entrada de datos si el nuevo trabajador solicite nunca un trabajo diferente de la empresa.  Para contratar a un trabajador existente en un puesto nuevo, haga clic en ** cambio ** colocar en ** estado de la aplicación ** interrumpen abajo para iniciar el proceso de transferencia.




