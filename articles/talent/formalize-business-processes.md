---
title: Formalizar procesos empresariales
description: "La característica del proceso empresarial permite crear una plantilla del proceso empresarial para los procesos que necesiten completarse en la organización."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1b50a97f5e2fc94255ff71702faf91ab36e68eb4
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="formalize-business-processes"></a>Formalizar procesos empresariales
La característica del proceso empresarial permite crear una plantilla del proceso empresarial para los procesos que necesiten completarse en la organización. Por ejemplo, la empresa puede completar una auditoría de RR. HH. de cada año. Una plantilla se puede crear para controlar todas las tareas que comprende la auditoría para ayudar a garantizar que todas las tareas se realizan cada vez que se completa el proceso y, si es necesario, para ayudar a garantizar que las tareas están efectuadas en el orden correcto. Las plantillas se pueden volver a utilizar para los procesos que se repiten o copiar para usarlas como punto de partida para crear nuevas tareas.

Una vez creada una plantilla, se puede iniciar un proceso y realizar un seguimiento en el espacio de trabajo del proceso empresarial.  Cuando se inicia un proceso empresarial, las tareas se asignan a las personas adecuadas e incluyen una fecha de vencimiento. Cubriremos estos componentes en detalle a continuación.

## <a name="business-process-template"></a>Plantilla de proceso empresarial
Una plantilla del proceso empresarial muestra un grupo de tareas que conforma un proceso empresarial. Los administradores de recursos humanos y los asistentes pueden crear procesos empresariales de forma predeterminada.  Sin embargo, esto se puede modificar en la configuración de seguridad editando el derecho Mantener los procesos empresariales genéricos.

El propietario de proceso puede ser definido para cada proceso. El propietario del proceso tendrá visibilidad en todas las tareas del proceso, y puede reasignar tareas o cambiar fechas de vencimiento.  Por ejemplo, el director de RR. HH. ha podido crear una plantilla del proceso empresarial para una revisión de prestaciones.  El administrador de COMP y de prestaciones se puede establecer como propietario de proceso, de modo que esta persona pueda tener penetración en las tareas que deben completarse como parte de la revisión.  El propietario de proceso no puede crear o eliminar los procesos empresariales activos o plantillas del proceso empresarial.

## <a name="task"></a>Tarea
Un proceso empresarial comprende a menudo varias tareas. Algunas tareas se pueden completar en Dynamics 365 for Talent, por ejemplo revisar ofertas internas de curso. En esta instancia, se selecciona un elemento de menú en el campo de vínculo de la tarea. Otras tareas pueden implicar revisar o completar los formularios de un sitio web. La selección de dirección URL en el campo de vínculo de tarea permite especificar la dirección web. Puede especificar direcciones URL para sitios externos e internos en este campo. También puede crear tareas para actividades que complete manualmente, por ejemplo revisar la accesibilidad de todas las estructuras. En esta instancia no se requiere un vínculo de tarea. Esta flexibilidad le permite realizar un seguimiento de varias clases de tareas en un proceso completo.

Las tareas se pueden asignar a un trabajador específico o a un puesto. Por ejemplo, el responsable de compensación y beneficios siempre será la persona que lleve a cabo una revisión de las primas de seguros.   Al realizar esta tarea, seleccione puesto para el tipo de asignación, y después seleccione el administrador de compensaciones y prestaciones en la lista del puesto. Cuando se inicia el proceso, la tarea se asignará al trabajador que se encuentra en el puesto de administrador de compensaciones y prestaciones. También puede asignar una tarea a un trabajador específico seleccionando el trabajador en el campo de tipo de asignación, y a continuación, seleccionando a la persona adecuada.

Las fechas de vencimiento de la tarea dependen de la fecha especificada fijada al comienzo del proceso. Algunas tareas se deben terminar antes de la fecha fijada, y algunas podrían completarse después de la fecha fijada.  Al definir una tarea, puede escribir una fecha de vencimiento que esté en relación con la fecha fijada en la contrapartida de la fecha de vencimiento del campo de la fecha fijada. Por ejemplo, supongamos que responsable de compensación y beneficios debe realizar una revisión de las primas de seguros 10 días antes de que se complete la auditoría de RR. HH. La tarea creada tendrá una fecha de vencimiento en relación con la fecha de vencimiento de -10. Por lo tanto, si el proceso se inicia el 13 de mayo, la tarea vencerá el 3 de mayo. Nota: Las fechas de vencimiento también pueden ser ajustadas después de iniciarse el proceso.

Las tareas complejas pueden requerir varios pasos o necesitar que la persona que realiza las tareas proporcione información adicional. Puede agregar instrucciones a la tarea, e incruir formato de texto enriquecido para las instrucciones, también. Las directrices pueden proporcionar información adicional sobre cómo completar la tarea a la persona a la que se ha asignado su ejecución.

## <a name="starting-a-process"></a>Iniciar un proceso
Un proceso se puede iniciar dentro de una plantilla del proceso empresarial seleccionando Iniciar proceso.  Cuando se inicia un proceso, se crearán tareas para los trabajadores y/o puestos seleccionados definidos en las tareas que se incluyen en la plantilla del proceso empresarial. Una fecha de vencimiento también se asignará a cada tarea agregando o restando los días compensados a partir de la fecha fijada (consulte la información relacionada con días compensados en la sección de la tarea). Los procesos empresariales activos se pueden ver en el espacio de trabajo de los procesos empresariales. 

## <a name="employee-self-service"></a>Autoservicio para empleados
Cuando una tarea se asigna a un empleado, sus tareas asignadas se pueden ver en la página de autoservicio de empleado. Los empleados que tienen asignada una tarea del proceso empresarial pueden consultar la tarea, su descripción, las instrucciones para completarla y el nombre de una persona de contacto y pueden abrir la página Dynamics365 o la página Web asociada desde su página de Autoservicio para empleados. Las tareas se pueden marcar como en curso, canceladas o completadas.

## <a name="business-process-workspace"></a>Espacio de trabajo de proceso empresarial
Los profesionales de RR. HH. pueden ver los procesos empresariales activos desde el espacio de trabajo de los procesos empresariales. El espacio de trabajo muestra todos los procesos activos y las tareas asociados entre sí. La lista de tareas completas se puede filtrar por fecha de vencimiento. La página también muestra tareas vencidas, así como tareas asignadas específicamente al profesional de recursos humanos. También pueden actualizar el estado de todas las tareas y en caso necesario, vuelve a asignar tareas para ayudar a que siga avanzando el proceso empresarial general.

## <a name="my-business-processes-workspace"></a>Espacio de trabajo de mis procesos empresariales
Los propietarios del proceso pueden ver los procesos de negocio activos que se les asignan desde el espacio de trabajo de mi proceso empresarial. El espacio de trabajo muestra todos los procesos activos y las tareas asociadas propiedad de dicho usuario.  La lista de tareas completas se puede filtrar por fecha de vencimiento. La página también muestra las tareas asignadas específicamente al propietario de proceso. El propietario de proceso también puede actualizar el estado de todas las tareas, así como reasignar cualquier tarea.

## <a name="navigating-business-processes"></a>Navegando por los procesos empresariales
1. Para agregar una plantilla del proceso empresarial, desplácese a los vínculos de los procesos empresariales – gestión de los procesos empresariales.
   - a.   Nuevo creará una nueva plantilla.
   - b.   La copia desde plantilla copiará la plantilla seleccionada a una nueva.
   - c.   Iniciar el proceso comenzará el proceso empresarial seleccionado, asignará tareas y calculará las fechas de vencimiento.  
2. Para ver procesos activo y tareas asociadas desplácese al espacio de trabajo de los procesos empresariales.

