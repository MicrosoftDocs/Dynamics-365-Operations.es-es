---
title: Acciones en los procesos de aprobación de flujo de trabajo
description: Este artículo explica las acciones que cada participante de un proceso de aprobación de flujo de trabajo puede realizar.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5750ac5814525351e6688b0aa49eee3811f7785775a91f3394c1a481de8adf2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749373"
---
# <a name="actions-in-workflow-approval-processes"></a>Acciones en los procesos de aprobación de flujo de trabajo

[!include [banner](../includes/banner.md)]

Este artículo explica las acciones que cada participante de un proceso de aprobación de flujo de trabajo puede realizar.

Un flujo de trabajo puede incluir varios grupos de personas: el originador, los usuarios asignados a la tarea, los responsables de la toma de decisiones y los aprobadores. Por ejemplo, en el siguiente flujo de trabajo de informes de gastos, Sam es el originador, los miembros de la cola son los usuarios asignados a la tarea, John es el responsable de la toma de decisiones y Frank, Sue y Ann son los aprobadores.

[![Flujo de trabajo\_WithManualDecision.](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)

En las siguientes secciones, se explican las acciones de flujo de trabajo que puede realizar cada grupo.

## <a name="actions-that-an-originator-can-perform"></a>Acciones que puede realizar un originador

El originador da inicio a una instancia de flujo de trabajo al enviar un documento para que se lo procese. Por ejemplo, para enviar su informe de gastos, Sam debe hacer clic en el botón **Enviar** de la página **Informe de gastos**.

## <a name="actions-that-a-task-assignee-can-perform"></a>Acciones que puede realizar un usuario asignado a una tarea

Una tarea puede estar asignada a varias personas o a una cola de elementos de trabajo que supervisan varias personas. Sin embargo, solo una de ellas puede completar la tarea. Por ejemplo, supongamos que Sam ha enviado un informe de gastos y que ha remitido sus recibos al departamento Informes de gastos de su organización para que los revisen.

Los miembros del departamento Informes de gastos de Adventure Works supervisan la cola. Supongamos ahora que Julie, una de las integrantes de ese departamento, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Puede llevar a cabo una de las siguientes acciones: completar la tarea, rechazarla, delegarla, solicitar un cambio o liberarla.

> [!NOTE]
> Las acciones disponibles variarán en función de la forma en que el programador de software haya diseñado la tarea.

### <a name="complete"></a>Completar

Cuando un usuario completa una tarea, el documento enviado para ser procesado se asigna al siguiente usuario del flujo de trabajo, si lo hay. Si no se requiere procesamiento adicional, el proceso de flujo de trabajo finaliza.

Por ejemplo, supongamos que Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Cuando Julie completa su revisión, el documento se asigna a John.

### <a name="reject"></a>Rechazar

Cuando un usuario rechaza un documento, el proceso de flujo de trabajo finaliza.

Por ejemplo, supongamos que Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Si Julie rechaza el informe de gastos, el proceso de flujo de trabajo finaliza.

Sam podrá volver a enviar el informe de gastos. Puede realizar cambios primero o volver a enviar la versión original. Si Sam lo vuelve a enviar, el proceso de flujo de trabajo comienza en la tarea de revisión manual.

### <a name="delegate"></a>Delegado

Cuando un usuario delega una tarea, se la asigna a otro usuario.

Por ejemplo, supongamos que Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Julie delega la tarea a Tim, su ayudante.

Tim actúa, entonces, en representación de Julie, Así, cuando Tim completa su revisión, el informe de gastos se asignará a John, tal como si Julie hubiera completado la tarea.

### <a name="request-change"></a>Solicitar cambio

Cuando un usuario solicita un cambio en un documento enviado, el documento se envía de nuevo al originador.

Por ejemplo, supongamos que Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Julie detecta algunos errores en el informe de gastos y solicita que se realicen algunos cambios. El informe de gastos se vuelve a enviar a Sam.

Sam podrá volver a enviar el informe de gastos. Puede realizar los cambios solicitados primero o volver a enviar la versión original. Si Sam reenvía el informe de gastos, uno de los miembros de la cola de elementos de trabajo debe volver a revisar el informe de gastos y los recibos.

### <a name="reassign"></a>Volver a asignar

Los miembros de una cola de elementos de trabajo pueden volver a asignar documentos de la cola a otra cola.

Por ejemplo, Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, está supervisando la cola. Para ayudar a hacer la carga de trabajo más equitativa, puede volver a asignar el informe de gastos y los recibos que este incluye a otra cola.

### <a name="release"></a>Liberar

En ocasiones, un miembro de una cola de elementos de trabajo podrá aceptar una tarea, pero decidir luego que no puede completar la tarea. En este caso, la persona que ha aceptado la tarea puede liberar el documento de nuevo a la cola de elementos de trabajo.

Por ejemplo, supongamos que Julie, una de las integrantes del departamento Informes de gastos de Adventure Works, ha aceptado la tarea de revisar el informe de gastos y los recibos de Sam. Si Julie determina que no puede completar la tarea, puede liberar el documento. El informe de gastos se vuelve a colocar en la cola para que alguno de los demás miembros del departamento Informes de gastos de Adventure Works pueda completar la tarea.

## <a name="actions-that-a-decision-maker-can-perform"></a>Acciones que puede realizar un responsable de la toma de decisiones

Normalmente, el motivo por el que un documento se asigna a un responsable de toma de decisiones es que la persona debe dar una respuesta. Por lo general, la respuesta a la pregunta es, o bien **Sí** o **No**, o bien **Verdadero** o **Falso**. Si esta persona no selecciona ninguna de las opciones, puede delegar la decisión.

### <a name="choice-1-or-choice-2"></a>\[Elección 1\] o \[Elección 2\]

El responsable de la toma de decisiones debe responder a una pregunta relacionada con el documento. Por lo general, la respuesta a la pregunta es, o bien **Sí** o **No**, o bien **Verdadero** o **Falso**. La respuesta que esta persona proporciona determina la rama del flujo de trabajo que se usa para procesar el documento.

Por ejemplo, el informe de gastos de Sam se asigna a John. John debe decidir si, dada la información que contiene el documento, se debe realizar una llamada al director de Sam. Si John decide que este es el caso, el informe de gastos se asigna a Aretha, quien debe llamar después al director de Sam. Si John decide que la llamada no es necesaria, el informe de gastos se asigna a Frank para que lo apruebe.

### <a name="delegate"></a>Delegar

Cuando una persona responsable de tomar decisiones delega una decisión, el documento se asigna a otro usuario, quien estará a cargo de tomar la decisión.

Por ejemplo, el informe de gastos de Sam se asigna a John. John delega la decisión a Maria, su ayudante.

Maria actúa, entonces, en representación de John. Si Maria decide que se debe realizar una llamada al director de Sam, el informe de gastos se asigna a Aretha, quien debe llamar al director de Sam. Si Maria decide que la llamada no es necesaria, el informe de gastos se asigna a Frank para que lo apruebe.

## <a name="actions-that-an-approver-can-perform"></a>Acciones que puede realizar un aprobador

Cuando un documento se asigna a un aprobador, este puede realizar una de las siguientes acciones: aprobarlo, rechazarlo, delegarlo o solicitar un cambio.

### <a name="approve"></a>Aprobar

Cuando un aprobador aprueba un documento, este se asigna al siguiente usuario del flujo de trabajo, si hay uno definido. Si no se requiere procesamiento adicional, el proceso de flujo de trabajo finaliza.

Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 6.000 USD que, en este momento, está asignado a Frank. Cuando Frank aprueba el documento, se lo asigna a Sue para que lo apruebe. Una vez que María apruebe el informe de gastos, se finalizará el proceso de flujo de trabajo.

### <a name="reject"></a>Rechazar

Cuando un aprobador rechaza un documento, el proceso de flujo de trabajo finaliza.

Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 12.000 USD que, en este momento, está asignado a Sue. Si Sue rechaza el informe de gastos, el proceso de flujo de trabajo finaliza.

Sam podrá volver a enviar el informe de gastos. Puede realizar los cambios solicitados primero o volver a enviar la versión original del informe de gastos. Si lo vuelve a enviar, el proceso de flujo de trabajo comienza en el punto del proceso de aprobación.

### <a name="delegate"></a>Delegar

Cuando un aprobador delega un documento, se lo asigna a otro usuario para que lo apruebe.

Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 12.000 USD que, en este momento, está asignado a Frank. Frank delega el informe de gastos a Ann.

Ann actúa, entonces, en representación de Frank, Así pues, cuando Ann apruebe el documento, este se asignará a Sue para que lo apruebe, tal como si hubiera sido Frank quien lo aprobara. Una vez que Sue aprueba el documento, se lo envía a Ann para que lo apruebe.

### <a name="request-change"></a>Solicitar cambio

Cuando un aprobador solicita que se realice un cambio en un documento, este se devuelve al originador.

Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 12.000 USD que, en este momento, está asignado a Sue. Si Sue solicita un cambio, el informe de gastos se devuelve a Sam.

Sam podrá volver a enviar el informe de gastos. Puede realizar los cambios solicitados primero o volver a enviar la versión original del informe de gastos. Si Sam lo vuelve a enviar, se envía a Frank para que lo apruebe porque él es el primer aprobador del proceso de aprobación.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]