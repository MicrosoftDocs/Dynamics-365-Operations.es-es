---
title: "Configuración de una tarea manual en un flujo de trabajo"
description: "Este tema explica cómo configurar las propiedades para una tarea manual."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a62b56bd2ac0a7484471190c5f342a1db335ab07
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="configure-a-manual-task-in-a-workflow"></a>Configuración de una tarea manual en un flujo de trabajo

[!include[banner](../includes/banner.md)]


Este tema explica cómo configurar las propiedades para una tarea manual.

Para configurar una tarea manual en el editor de flujo de trabajo, haga clic con el botón secundario en la tarea y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, use los siguientes procedimientos para configurar las propiedades de la tarea manual.

## <a name="name-the-task"></a>Asignación de un nombre a la tarea
Siga estos pasos para asignar un nombre a la tarea manual.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, especifique un nombre único para la tarea.

## <a name="enter-a-subject-line-and-instructions"></a>Especificación de una línea de asunto e instrucciones
Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados a la tarea. Por ejemplo, si está configurando una tarea para solicitudes de compra, el usuario asignado a la tarea ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**. La línea de asunto se muestra en una barra de mensajes de la página. A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones. Siga estos pasos para escribir una línea de asunto e instrucciones.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.
3.  Para personalizar la línea de asunto, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

4.  Para agregar traducciones de la línea de asunto, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.
    6.  Haga clic en **Cerrar**.

5.  En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.
6.  Para personalizar las instrucciones, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

7.  Para agregar traducciones de las instrucciones, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.
    6.  Haga clic en **Cerrar**.

## <a name="assign-the-task"></a>Asignación de la tarea
Siga estos pasos para especificar a quién se debe asignar la tarea manual.

1.  En el panel izquierdo, haga clic en **Asignación**.
2.  En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opción</th>
    <th>Usuarios a los que está asignada la tarea</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td><ol>
    <li>Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar la tarea.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar la tarea.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td><ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar la tarea.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede asignar la tarea. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:
    <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol></li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar la tarea:
    <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: la tarea se asigna a todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: la tarea se asigna únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: la tarea no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios del flujo de trabajo actual</td>
    <td><ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Usuario</td>
    <td>Usuarios específicos de Microsoft Dynamics 365 for Operations</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea asignar la tarea y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Cola</td>
    <td>Una cola de elementos de trabajo</td>
    <td><ol>
    <li>Tras seleccionar <strong>Cola</strong>, haga clic en la pestaña <strong>Basado en cola</strong>.</li>
    <li>Para asignar la tarea a una cola específica, siga estos pasos:
    <ol>
    <li>En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo</strong>.</li>
    <li>En la lista <strong>Nombre de cola</strong>, seleccione la cola.</li>
    </ol></li>
    <li>Si la cola a la que se debe asignar la tarea debe estar determinada por una condición específica, siga estos pasos:
    <ol>
    <li>En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo condicional</strong>.</li>
    <li>En la lista <strong>Nombre de cola</strong>, seleccione <strong>Cola condicional</strong>.</li>
    </ol></li>
    </ol>
    <strong>Nota:</strong> Esta opción solo se usa para algunos flujos de trabajo, como Gestión de casos.</td>
    </tr>
    </tbody>
    </table>

3.  En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para completar la tarea. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas de las que dispone el usuario para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días de los que dispone el usuario para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para completar la tarea.
    -   **Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana de diciembre.

    Si el usuario no completa la tarea en el tiempo asignado, la tarea se considera vencida. Las tareas vencidas se pueden remitir a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Especificación de la acción que se realiza cuando vence la tarea
Si un usuario no completa la tarea manual en el tiempo asignado, la tarea se considera vencida. Las tareas vencidas se pueden remitir a una instancia superior o asignar a otro usuario de forma automática. Si la tarea ha vencido, siga estos pasos para remitirla a una instancia superior.

1.  En el panel izquierdo, haga clic en **Remisión a una instancia superior**.
2.  Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior. De manera automática, el sistema asigna la tarea a los usuarios que forman parte de la ruta de remisión a una instancia superior. La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.
    | Secuencia | Ruta de remisión a una instancia superior      |
    |----------|----------------------|
    | 1        | Asignar a rol: Donna     |
    | 2        | Asignar a rol: Erin      |
    | 3        | Acción final: Rechazar |

    En este ejemplo, el sistema asigna la tarea vencida a Donna. Si Donna no completa la tarea en el tiempo asignado, el sistema la asigna a Erin. Si Erin no completa la tarea en el tiempo asignado, el sistema rechaza el documento que se debía procesar.
3.  Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**. En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opción</th>
    <th>Usuarios a los que se remite la tarea</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td><ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir la tarea para una instancia superior.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede remitir la tarea para una instancia superior. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:
    <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol></li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir la tarea para una instancia superior:
    <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: la tarea se remite para una instancia superior para todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: la tarea se remite para una instancia superior únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: esta tarea no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios del flujo de trabajo actual</td>
    <td><ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Usuario</td>
    <td>Usuarios específicos de Dynamics 365 for Operations</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea remitir la tarea para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para completar la tarea. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas de las que dispone el usuario para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días de los que dispone el usuario para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para completar la tarea.
    -   **Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana de diciembre.

5.  Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior. El orden de los usuarios se puede modificar.
6.  Si los usuarios de la ruta de remisión a una instancia superior no completan la tarea en el tiempo asignado, el sistema realiza una acción en la tarea. Para especificar la acción que el sistema realiza, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una acción.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Especificación de las condiciones en que el sistema realiza una acción automática en la tarea
Puede configurar el sistema para que realice alguna acción en la tarea manual si se cumplen ciertas condiciones. Por ejemplo, supongamos que existe una tarea que requiere que un miembro del departamento Informes de gastos revise los recibos que se adjuntan a un informe de gastos. De acuerdo con las directivas de la empresa, esta tarea se debe realizar si el importe total del informe de gastos es superior a 100 USD. Dada esta situación, puede configurar el sistema para que el estado de la tarea cambie a **Completo** si el importe total es menor que 100. Siga estos pasos para especificar cuándo el sistema realiza una acción en la tarea manual.

1.  En el panel izquierdo, haga clic en **Acciones automáticas**.
2.  Active la casilla **Habilitar acciones automáticas**.
3.  Haga clic en **Agregar condición**.
4.  Escriba una condición.
5.  Escriba condiciones adicionales que sean necesarias.
6.  Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:
    1.  Haga clic en **Probar**.
    2.  En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.
    3.  Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.
    4.  Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.

7.  En la lista **Acción de finalización automática**, seleccione la acción que el sistema debe realizar en la tarea.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones
Puede enviar notificaciones cuando una tarea manual se ha delegado, completado, rechazado, remitido a una instancia superior o cuando se ha solicitado un cambio. Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.

1.  En el panel izquierdo, haga clic en **Notificaciones**.
2.  Active las casillas de verificación junto a los eventos que deben notificarse:
    -   **Delegar**: la tarea se ha asignado a otro usuario.
    -   **Remitir a una instancia superior**: el usuario asignado no ha completado la tarea en el tiempo previsto.
    -   **Completar**: el usuario asignado ha completado la tarea.
    -   **Rechazar**: el usuario asignado ha rechazado el documento enviado.
    -   **Solicitar cambio**: el usuario asignado ha solicitado que se realice un cambio en el documento enviado.

3.  Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4.  En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.
5.  Para personalizar la notificación, puede insertar marcadores de posición. Estos se reemplazan con la información adecuada cuando se muestra la notificación a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

6.  Para agregar traducciones de la notificación, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.
    6.  Haga clic en **Cerrar**.

7.  En la pestaña **Destinatario**, especifique a quién se envían las notificaciones. Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opción</th>
    <th>Destinatarios de las notificaciones</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td><ol>
    <li>Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios del flujo de trabajo actual</td>
    <td><ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Usuario</td>
    <td>Usuarios específicos de Dynamics 365 for Operations</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="set-a-time-limit"></a>Definición de un límite de tiempo
Siga estos pasos si la tarea manual se debe completar en un plazo específico. **Nota:** Las opciones que seleccione en este procedimiento anulan las opciones elegidas en las áreas **Asignación** y **Remisión a una instancia superior** de la página.

1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Active la casilla **Configurar un límite de tiempo para el elemento de flujo de trabajo**.
3.  En el campo **Duración**, especifique cuándo se debe completar la tarea. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas disponibles para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días disponibles para completar la tarea. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas en las que se debe completar la tarea.
    -   **Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que la tarea se haya completado antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea. Por ejemplo, tal vez desee que la tarea se haya completado antes del viernes de la tercera semana de diciembre.

4.  Si se supera el límite de tiempo, el sistema realiza una acción en la tarea. En la lista **Acción**, seleccione la acción que debe realizar el sistema.

## <a name="specify-which-actions-are-available-to-the-user"></a>Especificación de las acciones de las que dispone el usuario
Cuando la tarea manual se asigna a un usuario, este debe realizar alguna acción en ella. Siga estos pasos para especificar las acciones que el usuario puede realizar en la tarea. **Nota**: las acciones disponibles variarán en función del diseño de la tarea.

1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Active la casilla de verificación **Completar** si el usuario debe poder cambiar el estado de la tarea a **Completo**.
3.  Active la casilla de verificación **Rechazar** si el usuario debe poder rechazar el documento enviado.
4.  Active la casilla de verificación **Solicitar cambio** si el usuario debe poder solicitar que se realicen cambios en el documento enviado.
5.  Active la casilla de verificación **Delegar** si el usuario debe poder asignar la tarea a otro usuario.
6.  Active la casilla de verificación **Volver a asignar** si el usuario debe poder reasignar la tarea a otro usuario de la cola de elementos de trabajo.
7.  Active la casilla de verificación **Liberar** si el usuario debe poder reasignar la tarea a la cola de elementos de trabajo. Otro usuario podrá encargarse de completar la tarea.





