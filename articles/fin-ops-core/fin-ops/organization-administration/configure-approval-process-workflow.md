---
title: Configurar los procesos de aprobación en un flujo de trabajo
description: Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99a4e131b2afa65152d8e9d41b8405895d997250
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070811"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Configurar los procesos de aprobación en un flujo de trabajo

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación.

Para configurar un proceso de aprobación, en el editor de flujo de trabajo, haga clic con el botón secundario en el elemento de aprobación y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.

## <a name="name-the-approval-process"></a>Asignación de un nombre al proceso de aprobación

Siga estos pasos para asignar un nombre al proceso de aprobación.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Nombre**, especifique un nombre único para el proceso de aprobación.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Especificación de las condiciones en que el sistema realiza una acción automática en el documento

Puede configurar el sistema para que realice alguna acción en el documento de forma automática si se cumplen ciertas condiciones. Por ejemplo, el sistema puede aprobar los informes de gastos con importes totales inferiores a 100 USD. Siga estos pasos para especificar cuándo el sistema realiza una acción en el documento.

1. En el panel izquierdo, haga clic en **Acciones automáticas**.
2. Active la casilla **Habilitar acciones automáticas**.
3. Haga clic en **Agregar condición**.
4. Escriba una condición.
5. Escriba condiciones adicionales, si fuera necesario.
6. Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:

    1. Haga clic en **Probar** para abrir el formulario **Probar la condición del flujo de trabajo**.
    2. Seleccione un registro del área **Comprobar condición** del formulario.
    3. Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.
    4. Haga clic en **Aceptar** o en **Cancelar** para regresar al formulario **Propiedades**.

7. En la lista **Acción de autocompletar**, seleccione la acción que el sistema debe realizar en el documento.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones

Puede enviar notificaciones cuando un documento se ha aprobado, rechazado, delegado o remitido a una instancia superior o cuando se ha solicitado un cambio. Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.

1. En el panel izquierdo, haga clic en **Notificaciones**.
2. Active las casillas de verificación junto a los eventos que deben notificarse:

    - **Delegar**: cuando un documento se ha asignado a otro usuario para que se lo apruebe.
    - **Remitir a una instancia superior**: cuando el usuario asignado no ha realizado ninguna acción en un documento en el tiempo asignado.
    - **Aprobar**: cuando un documento se ha aprobado.
    - **Rechazar**: cuando un documento se ha rechazado.
    - **Solicitar cambio**: cuando el usuario asignado ha solicitado que se realice un cambio en un documento enviado.

3. Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4. Haga clic en la ficha **Texto de la notificación**.
5. En el cuadro de texto, escriba el texto de la notificación.
6. Para personalizar el texto, puede insertar marcadores de posición, que se reemplazan con los datos adecuados cuando se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. Haga clic en el punto del cuadro de texto en el que debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que se abre, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.

7. Para agregar traducciones de la notificación, haga clic en **Traducciones**. En el formulario que aparece, siga estos pasos:

    1. Haga clic en **Agregar**.
    2. En la lista que aparece, seleccione el idioma que usará para escribir el texto.
    3. En el cuadro de texto **Texto traducido**, escriba el texto.
    4. Para personalizar el texto, inserte marcadores de posición.
    5. Haga clic en **Cerrar**.

8. Haga clic en la ficha **Destinatario**.
9. Especifique los destinatarios de las notificaciones. Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 10.

    <table>
    <thead>
    <tr>
    <th>Opción</th>
    <th>Destinatarios de las notificaciones</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><strong>Participante</strong></td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Participante</strong>, haga clic en la ficha <strong>Basado en el rol</strong>.</li>
    <li>En la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Usuario del flujo de trabajo</strong></td>
    <td>Usuarios que participan en el flujo de trabajo actual</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Usuario de flujo de trabajo</strong>, haga clic en la ficha <strong>Usuario de flujo de trabajo</strong>.</li>
    <li>En la lista <strong>Usuario de flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Usuario</strong></td>
    <td>Usuarios concretos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>Seleccione aquellos usuarios a los que enviar notificaciones y, a continuación, muévalos a la lista de <strong>Usuarios seleccionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Repita los pasos 3 a 9 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="specify-a-final-approver"></a>Especificación de un aprobador final

Puede designar un aprobador final para escenarios en los que el aprobador es la persona que envió el documento para su aprobación y se está utilizando la "anulación de la aprobación del remitente". Para especificar un aprobador final, siga estos pasos.

1. En el editor de flujo de trabajo, haga clic con el botón secundario en el elemento de aprobación y, a continuación, seleccione **Propiedades** para abrir el formulario **Propiedades**.
2. En el panel izquiero, haga clic en **Configuración avanzada**.
3. Seleccione la casilla de verificación **Usar aprobador final**.
4. En la lista, seleccione un usuario como aprobador final.

## <a name="set-a-time-limit"></a>Definición de un límite de tiempo

Siga estos pasos si el proceso de aprobación se debe completar en un plazo específico.

> [!NOTE]
> Las opciones que seleccione al realizar estos pasos reemplazarán las opciones que haya seleccionado en las áreas de **Asignación** y **Escalada** de cada paso de aprobación.

1. En el panel izquiero, haga clic en **Configuración avanzada**.
2. Active la casilla **Configurar un límite de tiempo para el elemento de** **flujo de trabajo**.
3. En el campo **Duración**, especifique cuándo se debe completar el proceso de aprobación. Seleccione una de las siguientes opciones:

    - **Horas**: escriba la cantidad de horas disponibles para completar el proceso de aprobación. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Días**: escriba la cantidad de días disponibles para completar el proceso de aprobación. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Semanas**: escriba la cantidad de semanas disponibles para completar el proceso de aprobación.
    - **Meses**: seleccione el día y la semana en los que vence el plazo para completar el proceso de aprobación. Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana del mes.
    - **Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar el proceso de aprobación. Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana de diciembre.

4. Si se supera el límite de tiempo, el sistema realiza una acción en el documento. En la lista **Acción**, seleccione la acción que debe realizar el sistema.

## <a name="specify-which-actions-are-available-to-the-user"></a>Especificación de las acciones de las que dispone el usuario

Cuando se asigna un documento a un usuario para que lo apruebe, este debe realizar alguna acción. Siga estos pasos para especificar las acciones que el usuario puede realizar en el documento enviado.

1. En el panel izquiero, haga clic en **Configuración avanzada**.
2. Active la casilla de verificación **Aprobar** si el usuario puede aprobar el documento.
3. Active la casilla de verificación **Rechazar** si el usuario puede rechazar el documento.
4. Active la casilla de verificación **Solicitar cambio** si el usuario puede solicitar que se realicen cambios en el documento.
5. Active la casilla de verificación **Delegar** si el usuario puede asignar el documento a otro usuario para que lo apruebe.

> [!NOTE]
> La casilla de verificación **Habilitar acciones desde la lista de trabajo de Enterprise Portal** se ha quedado obsoleta.

## <a name="configure-the-approval-steps"></a> Configuración de los pasos de aprobación

Los procesos de aprobación se componen de pasos de aprobación. Realice el siguiente procedimiento para agregar pasos en el proceso de aprobación y configurarlos.

1. En el editor de flujo de trabajo, haga doble clic en el proceso de aprobación. Los pasos del proceso se mostrarán en el editor de flujo de trabajo.
2. Para agregar un paso de aprobación, arrástrelo desde el área de **Elementos del flujo de trabajo** al lienzo.
3. Para configurar un paso de aprobación, vea [Configurar los pasos de aprobación en un flujo de trabajo](configure-approval-step-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]