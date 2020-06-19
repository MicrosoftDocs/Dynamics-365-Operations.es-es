---
title: Distribuir cuestionarios mediante la programación
description: La programación del cuestionario le permite planear y distribuir los cuestionarios a múltiples encuestados.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d233938fe553dbd7da7fcc5477097fd885665102
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429507"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuir cuestionarios mediante la programación

La programación del cuestionario le permite planear y distribuir los cuestionarios a múltiples encuestados. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

## <a name="create-a-questionnaire-schedule"></a>Cree una programación del cuestionario

1. Vaya a Cuestionario > Distribuir > Programaciones de cuestionarios.

2. Haga clic en Nuevo.

3. En el campo Programación, escriba un valor.

4. En el campo Descripción, escriba un valor.
    * Defina la programación en anónima si las respuestas se debe registrar sin nombres asociados a la respuesta.  
    * Permitir resultados anónimos se debe configurar primero en los parámetros de RR. HH.  

5. En el campo Tipo, seleccione el tipo de planificación.  En este ejemplo utilizaremos el tipo de satisfacción.

6. En la lista, busque y seleccione el registro deseado.

7. En la lista, haga clic en el vínculo de la fila seleccionada.

8. En el campo Fecha, escriba una fecha.

9. Expanda la sección Correo electrónico para autoservicio de empleados.

10. En el campo Asunto, escriba un valor.

    * Ejemplo: Cuestionario disponible  

11. Escriba el cuerpo de su mensaje de correo electrónico en el campo Texto. Tenga en cuenta que la variable se puede utilizar para sustituir los valores del sistema.

    * Ejemplo: Estimado/a %P%, inicie sesión en Autoservicio Empleado para completar el cuestionario Estados de salud de los trabajadores.  Contoso  

12. Haga clic en Guardar.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Use los Detalles de configuración para seleccionar los cuestionarios que se responderán junto con cualquier consulta que se usará para seleccionar encuestados.

1. Haga clic en Detalles de configuración.

2. En la lista, seleccione la consulta que desee usar para encontrar encuestados para el cuestionario en el sistema.

    * Ejemplo: Trabajadores  

3. Haga clic en Ver o modificar consulta para seleccionar personas específicas o ajustar la consulta para buscar las personas que coinciden con criterios específicos.

    * Tenga en cuenta que todos los encuestados también deben ser usuarios en el sistema.  

4. En la lista, marque la fila por persona.

5. En el campo Criterios, especifique o seleccione un valor.

    * Seleccione Julia Funderburk  

6. Seleccione Julia Funderburk en la lista.

7. Haga clic en Aceptar

8. Haga clic en la ficha Cuestionarios.

9. En el árbol, expanda "el nodo para el tipo de cuestionario de la encuesta de satisfacción".

10. En el árbol, compruebe "Evaluación del estado de salud de los trabajadores".

11. Haga clic en Aceptar

12. Haga clic en Sesión de respuestas planificadas.

    * Tenga en cuenta que se han creado sesiones de respuestas planificadas para cada usuario seleccionado o consultado.  

13. Cierre la página.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Inicie la programación de cuestionario para que el cuestionario esté disponible para que lo completen los encuestados.

1. Haga clic en Funciones.

2. Haga clic en Inicio.

3. Haga clic en Aceptar

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Envíe el mensaje de correo electrónico para informar a los encuestados del cuestionario disponible.

1. Haga clic en Funciones.

2. Haga clic en Enviar correo electrónico.

3. Haga clic en Cancelar.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Use las sesiones de respuesta planificadas para supervisar quién debe completar el cuestionario.

1. Haga clic en Sesión de respuestas planificadas.

    * Elimine cualquier sesión de respuestas planificadas restante cuando esté listo para finalizar la sesión programada.  

2. Haga clic Eliminar.

3. Haga clic en Sí.

4. Cierre la página.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Finalice la programación cuando todos los encuestados hayan completado el cuestionario y/o se hayan eliminado todas las sesiones de respuestas planificadas restantes.

1. Haga clic en Funciones.
2. Haga clic en Fin.
3. Haga clic en Aceptar

