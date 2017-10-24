---
title: "Configuración de las propiedades de un flujo de trabajo"
description: "Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6cad67d4108a81de545a1e633dc4e12a31af683b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="configure-the-properties-of-a-workflow"></a>Configuración de las propiedades de un flujo de trabajo

[!include[banner](../includes/banner.md)]


Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.

Para configurar las propiedades de un flujo de trabajo, abra el flujo de trabajo en el editor de flujo de trabajo. Haga clic en el lienzo del editor de flujos de trabajo y luego haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, puede usar los siguientes procedimientos para configurar las diversas propiedades del flujo de trabajo.

## <a name="name-the-workflow"></a>Asignación de un nombre al flujo de trabajo
Siga estos pasos para asignar un nombre al flujo de trabajo.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, especifique un nombre exclusivo para el flujo de trabajo. Por ejemplo, si crea un flujo de trabajo de solicitud de compra para cada país o región en los que opera, puede llamar al flujo de trabajo de solicitud de compra **Solicitudes de compra Dinamarca** o **Solicitudes de compra España**.

## <a name="specify-the-workflow-owner"></a>Especificación del propietario del flujo de trabajo
El propietario del flujo de trabajo es la persona que administra y mantiene el flujo de trabajo. Siga estos pasos para especificar el propietario del flujo de trabajo.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En la lista **Propietario**, seleccione el nombre de la persona que administrará el flujo de trabajo.

## <a name="select-an-email-template"></a>Selección de una plantilla de correo electrónico
Siga estos pasos para seleccionar la plantilla de correo electrónico que se usa para generar los mensajes de notificación sobre el flujo de trabajo.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En la lista **Plantilla de correo electrónico para notificaciones de flujo de trabajo**, seleccione la plantilla.

## <a name="enter-instructions-for-users"></a>Especificación de las instrucciones para los usuarios
Puede proporcionar instrucciones a los usuarios que envían los documentos que se deben procesar y aprobar. A estos usuarios también se les conoce como *originadores*. Por ejemplo, está creando un flujo de trabajo de solicitudes de compra y especifica instrucciones. Esas instrucciones se pueden ver entonces por los usuarios que especifican solicitudes de compra en la página **Solicitudes de compra**. Para consultar las instrucciones, el originador hace clic en el icono de la barra de mensajes del flujo de trabajo. Siga estos pasos para escribir las instrucciones para los usuarios.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Instrucciones de envío**, escriba las instrucciones.
3.  Para personalizar las instrucciones, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  Haga clic en el campo **Instrucciones de envío** para especificar dónde debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

4.  Para agregar traducciones de las instrucciones, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribirá el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Para personalizar el texto, puede insertar marcadores de posición. Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 3.
    6.  Haga clic en **Cerrar**.

## <a name="specify-when-this-workflow-is-used"></a>Especificación de las condiciones en que se usa el flujo de trabajo
Puede crear varios flujos de trabajo que estén basados en el mismo tipo. Por ejemplo, puede crear un flujo de trabajo de solicitudes de compra para cada país o región en los que opera como, por ejemplo, Solicitudes de compra Dinamarca y Solicitudes de compra España. Cuando existen varios flujos de trabajo basados en el mismo tipo, debe especificar cuándo se usa cada uno. Para el ejemplo anterior, especifique las siguientes condiciones:

-   Se usa Solicitudes de compra Dinamarca cuando: país/región = DK
-   Se usa Solicitudes de compra España cuando: país/región = ES

Siga estos pasos para especificar cuándo se usa el flujo de trabajo que está configurando.

1.  En el panel izquierdo, haga clic en **Activación**.
2.  Active la casilla **Establecer condiciones para ejecutar este flujo de trabajo**.
3.  Haga clic en **Agregar condición**.
4.  Escriba una condición.
5.  Escriba condiciones adicionales que sean necesarias.
6.  Para comprobar que las condiciones definidas se hayan establecido correctamente, siga estos pasos:
    1.  Haga clic en **Probar**.
    2.  En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.
    3.  Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones que se especificaron. Por ejemplo, si crea un flujo de trabajo de solicitudes de compra para España, el área **Comprobar condición** de la página muestra una lista de solicitudes de compra. Al hacer clic en **Probar**, el sistema evalúa la solicitud de compra seleccionada para determinar si el país o región es ES.
    4.  Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones
Cuando se envía un documento para que se lo procese, se crea una instancia de flujo de trabajo. Puede enviar notificaciones a los usuarios para indicar el inicio, la finalización, la terminación o la detención debido a un error de las instancias de flujo de trabajo basadas en el flujo de trabajo. Siga estos pasos para especificar cuándo se envían notificaciones.

1.  En el panel izquierdo, haga clic en **Notificaciones**.
2.  Active las casillas de verificación correspondientes a los eventos que deben desencadenar las notificaciones:
    -   **Iniciado**: enviar notificaciones cuando se inicia una instancia de flujo de trabajo.
    -   **Detenido**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error.
    -   **Completado**: enviar notificaciones cuando se completa una instancia de flujo de trabajo.
    -   **Irrecuperable**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error irrecuperable.
    -   **Terminado**: enviar notificaciones cuando finaliza una instancia de flujo de trabajo.

3.  Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4.  En la pestaña **Texto de notificación**, escriba el texto de la notificación.
5.  Para personalizar el texto, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra el texto a los usuarios. Para insertar un marcador de posición, siga estos pasos:
    1.  Haga clic en el campo para especificar dónde debe aparecer el marcador de posición.
    2.  Haga clic en **Insertar marcador de posición**.
    3.  En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4.  Haga clic en **Insertar**.

6.  Para agregar traducciones del texto, siga estos pasos:
    1.  Haga clic en **Traducciones**.
    2.  En la página que aparece, haga clic en **Agregar**.
    3.  En la lista que aparece, seleccione el idioma en el que escribirá el texto.
    4.  En el campo **Texto traducido**, escriba el texto.
    5.  Para personalizar el texto, puede insertar marcadores de posición. Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 5.
    6.  Haga clic en **Cerrar**.

7.  En la pestaña **Destinatario**, utilice las siguientes opciones para especificar quién debe recibir las notificaciones.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Opción</th>
    <th>Las notificaciones se envían a estos usuarios</th>
    <th>Para enviar notificaciones, siga estos pasos</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td><ol>
    <li>En la pestaña <strong>Destinatario</strong>, haga clic en <strong>Participante</strong>.</li>
    <li>En la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios que participan en el flujo de trabajo</td>
    <td><ol>
    <li>En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario del flujo de trabajo</strong>.</li>
    <li>En la pestaña <strong>Usuario del flujo de trabajo</strong>, en la lista <strong>Usuario del flujo de trabajo</strong>, seleccione un participante de este flujo de trabajo.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Usuario</td>
    <td>Usuarios específicos de Finance and Operations</td>
    <td><ol>
    <li>En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario</strong>.</li>
    <li>En la pestaña <strong>Usuario</strong>, la lista <strong>Usuarios disponibles</strong> incluye todos los usuarios de Finance and Operations. Seleccione aquellos a los que desea enviar notificaciones y muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo.
Para escribir comentarios acerca de los cambios que realizó en el flujo de trabajo, siga estos pasos.

1.  En el panel izquierdo, haga clic en **Notas**.
2.  En el campo **Especificar comentarios sobre el flujo de trabajo**, escriba sus comentarios.
3.  Revise los comentarios: una vez agregados, no podrá modificarlos.
4.  Haga **Agregar** clic en para agregar sus comentarios al área **Historial de comentarios**.





