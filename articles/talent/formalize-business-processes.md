---
title: Formalizar procesos empresariales
description: Este tema explica cómo puede utilizar la característica del proceso empresarial para crear una plantilla del proceso empresarial para los procesos que deben completarse en la organización.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.openlocfilehash: 85950a1413cfd8745bb78a52eb9f7c81b8976605
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "859722"
---
# <a name="formalize-business-processes"></a>Formalizar procesos empresariales

[!include[banner](includes/banner.md)]

La característica del proceso empresarial le permite crear una plantilla del proceso empresarial para los procesos empresariales que deban completarse en la organización. Por ejemplo, su empresa completa una auditoria de Recursos Humanos (RR. HH.) cada año. En este caso, puede crear una plantilla que realice un seguimiento de todas las tareas de las que consta el proceso de auditoría. Esta plantilla puede ayudar a garantizar que todas las tareas se realicen cada vez que se haga la auditoría. Asimismo, si las tareas deben completarse en un orden específico, la plantilla puede ayudar a garantizar que se hacen en el orden correcto.

Las plantillas se pueden volver a usar para procesos que se repiten. También se pueden copiar y usar como punto de inicio para crear nuevas plantillas.

Una vez creada una plantilla de proceso empresarial, se puede iniciar un proceso empresarial y realizar un seguimiento en el espacio de trabajo **Proceso empresarial**. Cuando se inicia un proceso empresarial, las tareas se asignan a las personas adecuadas e incluyen una fecha de vencimiento.

## <a name="business-process-templates"></a>Plantillas de proceso empresarial
Una plantilla del proceso empresarial muestra un grupo de tareas que conforma un proceso empresarial. De forma predeterminada, los administradores de RR. HH. y los asistentes pueden crear procesos empresariales. Sin embargo, puede cambiar los roles que puede crear procesos empresariales mediante la modificación del deber **Mantener procesos empresariales genéricos** en la configuración de seguridad.

Para cada proceso empresarial, puede definir a un propietario de proceso. El propietario del proceso tiene visibilidad en todas las tareas del proceso, y puede reasignar tareas o cambiar fechas de vencimiento. Por ejemplo, el director de RR. HH. crea una plantilla de proceso empresarial para una revisión de prestaciones y especifica al administrador de compensaciones y prestaciones como el propietario del proceso. El administrador de compensaciones y prestaciones tiene visibilidad en las tareas que deben completarse como parte de la revisión.

Un propietario de proceso no puede crear nuevos procesos empresariales o plantillas de procesos empresariales, ni eliminar procesos empresariales activos o plantillas de procesos empresariales.

## <a name="tasks"></a>Tareas
Un proceso empresarial comprende a menudo varias tareas. Algunas tareas, como una revisión de ofertas internas de curso, se pueden completar en Dynamics 365 for Talent[?]. En este caso, se selecciona una opción en el campo **Vínculo de tareas**. Otras tareas pueden implicar revisar o completar las páginas de un sitio web. En este caso, la dirección **URL** se seleccciona en el campo **Vínculo de la tarea** y, a continuación, se puede introducir la dirección web. Puede especificar direcciones URL para sitios externos e internos. También puede crear tareas para actividades que complete manualmente, como una revisión de la accesibilidad de todas las estructuras. En este caso, no se requiere un vínculo de tarea. Esta flexibilidad le permite realizar un seguimiento de varias clases de tareas en un proceso completo.

Las tareas se pueden asignar a un trabajador específico o a un puesto. Por ejemplo, el responsable de compensaciones y prestaciones siempre será la persona que realiza una revisión de las primas de seguros. Por tanto, cuando cree esta tarea, seleccione **Puesto** en el campo **Tipo de asignación** y, a continuación, seleccione **Responsable de compensaciones y prestaciones** en la lista **Puesto**. Cuando se inicia el proceso empresarial, la tarea se asigna al trabajador que se encuentra en el puesto **Responsable de compensaciones y prestaciones**. Para asignar una tarea a un trabajador específico, seleccione **Trabajador** en el campo **Tipo de asignación** y, a continuación, seleccione a la persona adecuada.

Las fechas de vencimiento de las tareas dependen de la fecha prevista fijada al comienzo del proceso empresarial. Algunas tareas se deben terminar antes de la fecha fijada, y otras podrían completarse después de la fecha fijada. Al definir una tarea, en el campo **Fecha de vencimiento de compensación a partir de la fecha objetivo**, puede especificar una fecha de vencimiento que esté en relación con la fecha fijada. Por ejemplo, el administrador de compensaciones y prestaciones debe realizar una revisión de las primas de seguros 10 días antes de que se complete la auditoría de RR. HH. En este caso, la tarea que se crea para la revisión tiene un valor **Fecha de vencimiento de compensación a partir de la fecha del objetivo** de **-10**. Por lo tanto, si el proceso empresarial se inicia el 13 de mayo, la tarea vence el 3 de mayo.

> [!NOTE]
> Las fechas de vencimiento también pueden ser ajustadas después de iniciarse el proceso empresarial.

Las tareas complejas pueden requerir varios pasos o que las personas que realizan las tareas tengan que proporcionar información adicional. Para estas situaciones, puede agregar directrices a una tarea. Las directrices pueden proporcionar a la persona a la que se ha asignado la ejecución de la tarea información adicional sobre cómo completarla. Incluso puede incluir formato de texto enriquecido en las directrices.

## <a name="starting-a-business-process"></a>Iniciar un proceso empresarial
En una plantilla de proceso empresarial, puede iniciar un proceso empresarial seleccionando **Iniciar proceso**. Cuando se inicia un proceso, se crean tareas para los trabajadores o puestos seleccionados que se definen en las tareas que se incluyen en la plantilla. Una fecha de vencimiento también se asigna a cada tarea agregando o restando el número de días compensados a partir de la fecha fijada, como se explica en la sección "Tareas". Puede ver procesos empresariales activos en el espacio de trabajo **Procesos empresariales**.

## <a name="employee-self-service"></a>Autoservicio para empleados
Una vez que se asigna una tarea a un empleado, este puede verla, junto con el resto de tareas asignadas, en la página **Autoservicio para empleados**. Para cada tarea del proceso empresarial que se le asigna, el empleado puede ver el nombre y la descripción de la tarea, las instrucciones para completarla y el nombre de una persona de contacto. En la página **Autoservicio para empleados**, el empleado también puede abrir la página asociada en Microsoft Dynamics 365 o la página web asociada, y puede marcar las tareas como en curso, canceladas o completadas.

## <a name="business-process-workspace"></a>Espacio de trabajo de proceso empresarial
Los profesionales de RR. HH. pueden ver los procesos empresariales activos en el espacio de trabajo **Procesos empresariales**. Este espacio de trabajo muestra todos los procesos activos y las tareas asociadas entre sí. La lista de tareas completas se puede filtrar por fecha de vencimiento. El espacio de trabajo también muestra tareas vencidas y tareas asignadas específicamente al profesional de RR. HH. El profesional de RR. HH. también puede actualizar el estado de todas las tareas y, en caso necesario, puede volver a asignar tareas para ayudar a que siga avanzando el proceso empresarial general.

## <a name="my-business-processes-workspace"></a>Espacio de trabajo de mis procesos empresariales
Los propietarios del proceso pueden ver los procesos empresariales activos que se les asignan en el espacio de trabajo **Mi proceso empresarial**. Este espacio de trabajo muestra todos los procesos activos propiedad del usuario, y las tareas asociadas. La lista de tareas completas se puede filtrar por fecha de vencimiento. El espacio de trabajo también muestra las tareas asignadas específicamente al propietario de proceso. El propietario de proceso también puede actualizar el estado de todas las tareas y reasignar cualquier tarea.

## <a name="navigating-business-processes"></a>Navegando por los procesos empresariales
Para crear o copiar una plantilla de proceso empresarial, o para iniciar un proceso empresarial, desplácese a los vínculos de los procesos empresariales – Gestión de los procesos empresariales. A continuación, puede realizar las siguientes acciones:

- Seleccione **Nueva** para crear una nueva plantilla de proceso empresarial.
- Seleccione **Copiar desde plantilla** para copiar la plantilla seleccionada a una nueva plantilla.
- Seleccione **Iniciar proceso** para comenzar el proceso empresarial seleccionado, asignar tareas y calcular las fechas de vencimiento.

Para ver procesos activos y tareas asociadas, abra el espacio de trabajo **Procesos empresariales**.

