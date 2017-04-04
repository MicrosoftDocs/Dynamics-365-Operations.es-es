---
title: "Configuración de un proceso de aprobación en un flujo de trabajo"
description: "Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 579e393ef64bc5ad72d129ac08ac215c524d5c55
ms.lasthandoff: 03/31/2017


---

# <a name="configure-an-approval-process-in-a-workflow"></a>Configuración de un proceso de aprobación en un flujo de trabajo

Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación.

Para configurar un proceso de aprobación, en el editor de flujo de trabajo, haga clic con el botón secundario en el elemento de aprobación, y haga clic en ** las propiedades ** para abrir ** las propiedades ** el formulario.
Asignación de un nombre al proceso de aprobación
-------------------------

Siga estos pasos para asignar un nombre al proceso de aprobación.
1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, especifique un nombre único para el proceso de aprobación.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Especificación de las condiciones en que el sistema realiza una acción automática en el documento
Puede configurar el sistema para que realice alguna acción en el documento de forma automática si se cumplen ciertas condiciones. Por ejemplo, el sistema puede aprobar los informes de gastos con importes totales inferiores a 100 USD. Siga estos pasos para especificar cuándo el sistema realiza una acción en el documento.
1.  En el panel izquierdo, haga clic en **Acciones automáticas**.
2.  Active la casilla **Habilitar acciones automáticas**.
3.  Click **Add condition**.
4.  Escriba una condición.
5.  Escriba condiciones adicionales, si fuera necesario.
6.  Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:
    1.  Haga clic en **Probar** para abrir el formulario **Probar la condición del flujo de trabajo**.
    2.  Seleccione un registro del área **Comprobar condición** del formulario.
    3.  Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.
    4.  Haga clic en **Aceptar** o en **Cancelar** para regresar al formulario **Propiedades**.

7.  En la lista **Acción de autocompletar**, seleccione la acción que el sistema debe realizar en el documento.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones
Puede enviar notificaciones cuando un documento se ha aprobado, rechazado, delegado o remitido a una instancia superior o cuando se ha solicitado un cambio. Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.
1.  En el panel izquierdo, haga clic en **Notificaciones**.
2.  Active las casillas de verificación junto a los eventos que deben notificarse:
    -   **Delegar**: cuando un documento se ha asignado a otro usuario para que se lo apruebe.
    -   **Remitir a una instancia superior**: cuando el usuario asignado no ha realizado ninguna acción en un documento en el tiempo asignado.
    -   **Aprobar**: cuando un documento se ha aprobado.
    -   **Rechazar**: cuando un documento se ha rechazado.
    -   **Solicitar cambio**: cuando el usuario asignado ha solicitado que se realice un cambio en un documento enviado.

3.  Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4.  Haga clic en la ficha **Texto de la notificación**.
5.  En el cuadro de texto, escriba el texto de la notificación.
6.  Para personalizar el texto, puede insertar marcadores de posición, que se reemplazan con los datos adecuados cuando se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  Haga clic en el punto del cuadro de texto en el que debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que se abre, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

7.  Para agregar traducciones de la notificación, haga clic en **Traducciones**. En el formulario que aparece, siga estos pasos:
    1.  Click **Add**.
    2.  En la lista que aparece, seleccione el idioma que usará para escribir el texto.
    3.  En el cuadro de texto **Texto traducido**, escriba el texto.
    4.  Para personalizar el texto, inserte marcadores de posición.
    5.  Haga clic en **Cerrar**.

8.  Haga clic en la ficha **Destinatario**.
9.  Especifique los destinatarios de las notificaciones. Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 10.

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
    <td><strong>Participante</strong></td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td><ol>
    <li>Tras seleccionar <strong>Participante</strong>, haga clic en la ficha <strong>Basado en el rol</strong>.</li>
    <li>En la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><strong>Usuario del flujo de trabajo</strong></td>
    <td>Usuarios que participan en el flujo de trabajo actual</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario de flujo de trabajo</strong>, haga clic en la ficha <strong>Usuario de flujo de trabajo</strong>.</li>
    <li>En la lista <strong>Usuario de flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><strong>User</strong></td>
    <td>Microsoft Dynamics específico 365 para los usuarios de operaciones</td>
    <td><ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li><strong>Usuarios disponible</strong>: la lista incluye todos los Microsoft Dynamics 365 para los usuarios de las operaciones. Seleccione aquellos usuarios a los que enviar notificaciones y, a continuación, muévalos a la lista de <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

10. Repita los pasos 3 a 9 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="specify-a-final-approver"></a>Especificación de un aprobador final
Es posible que desee designar un aprobador final que actúe en las situaciones en las que el aprobador sea la persona que solicitó la aprobación del documento. Para especificar un aprobador final, siga estos pasos.
1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Seleccione la casilla de verificación **Usar aprobador final**.
3.  En la lista, seleccione el usuario que actuará como aprobador final.

## <a name="set-a-time-limit"></a>Definición de un límite de tiempo
Siga estos pasos si el proceso de aprobación se debe completar en un plazo específico.
| **Nota **                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Las opciones que seleccione al realizar estos pasos reemplazarán las opciones que haya seleccionado en las áreas de **Asignación** y **Escalada** de cada paso de aprobación. |

1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Active la casilla **Configurar un límite de tiempo para el elemento de** **flujo de trabajo**.
3.  En el campo **Duración**, especifique cuándo se debe completar el proceso de aprobación. Seleccione una de las siguientes opciones:
    -   **Horas**: escriba la cantidad de horas disponibles para completar el proceso de aprobación. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Días**: escriba la cantidad de días disponibles para completar el proceso de aprobación. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    -   **Semanas**: escriba la cantidad de semanas disponibles para completar el proceso de aprobación.
    -   **Meses**: seleccione el día y la semana en los que vence el plazo para completar el proceso de aprobación. Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana del mes.
    -   **Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar el proceso de aprobación. Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana de diciembre.

4.  Si se supera el límite de tiempo, el sistema realiza una acción en el documento. En la lista **Acción**, seleccione la acción que debe realizar el sistema.

## <a name="specify-which-actions-are-available-to-the-user"></a>Especificación de las acciones de las que dispone el usuario
Cuando se asigna un documento a un usuario para que lo apruebe, este debe realizar alguna acción. Siga estos pasos para especificar las acciones que el usuario puede realizar en el documento enviado.
1.  En el panel izquiero, haga clic en **Configuración avanzada**.
2.  Active la casilla de verificación **Aprobar** si el usuario puede aprobar el documento.
3.  Active la casilla de verificación **Rechazar** si el usuario puede rechazar el documento.
4.  Active la casilla de verificación **Solicitar cambio** si el usuario puede solicitar que se realicen cambios en el documento.
5.  Active la casilla de verificación **Delegar** si el usuario puede asignar el documento a otro usuario para que lo apruebe.

**Nota**: **las acciones de permiso de la casilla de verificación de la lista de trabajo de Enterprise Portal ** se han quedado obsoletas.

## <a name="configure-the-approval-steps"></a> Configuración de los pasos de aprobación
Los procesos de aprobación se componen de pasos de aprobación. Realice el siguiente procedimiento para agregar pasos en el proceso de aprobación y configurarlos.
1.  En el editor de flujo de trabajo, haga doble clic en el proceso de aprobación. Los pasos del proceso se mostrarán en el editor de flujo de trabajo.
2.  Para agregar un paso de aprobación, arrástrelo desde el área de **Elementos del flujo de trabajo** al lienzo.
3.  Para configurar un paso de aprobación, vea [Configuración de un paso de aprobación](http://axhelp.dynamics.com/en/wiki/configure-an-approval-step/).




