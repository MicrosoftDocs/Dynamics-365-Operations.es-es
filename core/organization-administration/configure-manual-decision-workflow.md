---
title: "Configuración de una decisión manual en un flujo de trabajo"
description: "Este tema explica cómo configurar las propiedades de una decisión manual."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ac86ffa794b5fd92ca9aba24537fbc05057fe824
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="configure-a-manual-decision-in-a-workflow"></a>Configuración de una decisión manual en un flujo de trabajo

[!include[banner](../includes/banner.md)]


Este tema explica cómo configurar las propiedades de una decisión manual.

Para configurar una decisión manual, en el editor de flujo de trabajo, haga clic con el botón secundario en la decisión manual y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, use los siguientes procedimientos para configurar las propiedades de la decisión manual.

## <a name="name-the-decision"></a>Asignación de un nombre a la decisión
Siga estos pasos para asignar un nombre a la decisión manual.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, escriba un nombre único para la decisión manual.

## <a name="enter-a-subject-line-and-instructions"></a>Especificación de una línea de asunto e instrucciones
Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados a la decisión manual. Por ejemplo, si está configurando una decisión para solicitudes de compra, el usuario asignado a la decisión ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**. La línea de asunto se muestra en una barra de mensajes de la página. A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones. Siga estos pasos para escribir una línea de asunto e instrucciones.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En la pestaña **Instrucciones** , en el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.
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

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Especificación de los posibles resultados de una decisión
Normalmente, cuando a una persona responsable de tomar decisiones se le asigna un documento, se le formula una pregunta. La respuesta a esta pregunta es generalmente **Sí**o **No**, o bien **Verdadero** o **Falso**. Siga estos pasos para especificar los resultados que podría tener la decisión manual.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En la pestaña **Resultados**, en el campo **Resultado 1**, escriba el nombre del resultado o especifique la opción.
3.  Para agregar traducciones del resultado, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Haga clic en **Cerrar**.

4.  En el campo **Resultado 2**, escriba el nombre del resultado o especifique la opción.
5.  Para agregar traducciones del resultado, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Haga clic en **Cerrar**.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones
Puede enviar notificaciones cuando se haya tomado o delegado una decisión o cuando se la haya remitido a una instancia superior. Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.

1.  En el panel izquierdo, haga clic en **Notificaciones**.
2.  Active las casillas de verificación junto a los eventos que deben notificarse:
    -   **\[Elección 1\]**: el usuario asignado ha optado por la **\[Elección 1\]**.
    -   **\[Elección 2\]**: el usuario asignado ha optado por la **\[Elección 2\]**.
    -   **Delegar**: el usuario asignado ha asignado la decisión a otro usuario.
    -   **Remitir a una instancia superior**: el usuario asignado no ha tomado la decisión en el tiempo previsto.

3.  Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4.  En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.
5.  Para personalizar la notificación, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra la notificación a los usuarios. Para insertar un marcador de posición, siga estos pasos:
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
    <li>En la lista <strong>Participante</strong>, seleccione el grupo al que se deben enviar las notificaciones.</li>
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
    <td>Usuarios específicos de Microsoft Dynamics 365 for Operations</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="assign-a-decision"></a>Asignación de una decisión
Siga estos pasos para especificar a quién se debe asignar una decisión manual.

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
    <th>Usuarios a los que se asigna la decisión</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td><ol>
    <li>Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar la decisión.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar la decisión.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td><ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar la decisión.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede asignar la decisión. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera: <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol></li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar la decisión: <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se asigna a todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se asigna únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
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
    <td>Usuarios específicos de Dynamics 365 for Operations</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea asignar la decisión y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Cola</td>
    <td>Una cola de elementos de trabajo</td>
    <td><ol>
    <li>Tras seleccionar <strong>Cola</strong>, haga clic en la pestaña <strong>Basado en cola</strong>.</li>
    <li>Para asignar la decisión a una cola específica, siga estos pasos: <ol>
    <li>En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo</strong>.</li>
    <li>En la lista <strong>Nombre de cola</strong>, seleccione la cola.</li>
    </ol></li>
    <li>Si la cola a la que se debe asignar la decisión debe estar determinada por una condición específica, siga estos pasos: <ol>
    <li>En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo condicional</strong>.</li>
    <li>En la lista <strong>Nombre de cola</strong>, seleccione <strong>Cola condicional</strong>.</li>
    </ol></li>
    </ol>
    <strong>Nota:</strong> Esta opción solo se usa para algunos flujos de trabajo, como Gestión de casos.</td>
    </tr>
    </tbody>
    </table>

3.  En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.
    -   **Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión. Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión. Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.

    Si el usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida. Las decisiones vencidas se remiten a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Especificación de la acción que se realiza cuando vence una decisión
Si un usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida. Las decisiones vencidas se pueden remitir a una instancia superior, o asignar a otro usuario de forma automática. Si la decisión ha vencido, siga estos pasos para remitirla a una instancia superior.

1.  En el panel izquierdo, haga clic en **Remisión a una instancia superior**.
2.  Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior. De manera automática, el sistema asigna la decisión a los usuarios que forman parte de la ruta de remisión a una instancia superior. La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.
    | Secuencia | Ruta de remisión a una instancia superior            |
    |----------|----------------------------|
    | 1        | Asignar a rol: Donna           |
    | 2        | Asignar a rol: Erin            |
    | 3        | Acción final: \[Elección 1\] |

    En este ejemplo, el sistema asigna la decisión vencida a Donna. Si Donna no toma la decisión en el tiempo asignado, el sistema la asigna a Erin. Si Erin no toma la decisión en el tiempo asignado, el sistema selecciona la **\[Elección 1\]** como decisión.
3.  Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**. Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opción</th>
    <th>Usuarios a los que se remite la decisión</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td><ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir a una instancia superior la decisión.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede remitir la decisión para una instancia superior. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera: <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol></li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir la decisión para una instancia superior: <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se remite para una instancia superior a todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se remite para una instancia superior únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
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
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Operations. Seleccione aquellos a los que desea remitir la decisión para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.
    -   **Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión. Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión. Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.

5.  Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior. El orden de los usuarios se puede modificar.
6.  Si los usuarios de la ruta de remisión a una instancia superior no toman la decisión en el tiempo asignado, lo hace el sistema. Para especificar la opción que el sistema selecciona, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una opción.

## <a name="set-a-time-limit"></a>Definición de un límite de tiempo
Siga estos pasos si la decisión se debe tomar en un plazo específico. **Nota:** Las opciones que seleccione en este procedimiento anulan las opciones elegidas en las áreas **Asignación** y **Remisión a una instancia superior** de la página.

1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Active la casilla **Configurar un límite de tiempo para el elemento de flujo de trabajo**.
3.  En el campo **Duración**, especifique cuándo se debe tomar la decisión. Seleccione una de las siguientes opciones:
    -   **Hora**: escriba la cantidad de horas. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas.
    -   **Meses**: seleccione el día y la semana en los que vence el plazo para tomar la decisión. Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión. Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana de diciembre.

4.  Si se supera el límite de tiempo, el sistema toma la decisión. En la lista **Acción**, seleccione la opción que debe seleccionar el sistema.





