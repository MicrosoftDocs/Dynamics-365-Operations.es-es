---
title: Configurar propiedades del flujo de trabajo
description: Este artículo explica cómo configurar las diversas propiedades de un flujo de trabajo.
author: ChrisGarty
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec604ed9614b80b3b24c670911b4ea480d6131e2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876452"
---
# <a name="configure-workflow-properties"></a>Configurar propiedades del flujo de trabajo

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este artículo explica cómo configurar las diversas propiedades de un flujo de trabajo.

Para configurar las propiedades de un flujo de trabajo, abra el flujo de trabajo en el editor de flujo de trabajo. Haga clic en el lienzo del editor de flujos de trabajo y luego haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, puede usar los siguientes procedimientos para configurar las diversas propiedades del flujo de trabajo.

## <a name="name-the-workflow"></a>Asignación de un nombre al flujo de trabajo

Siga estos pasos para asignar un nombre al flujo de trabajo.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Nombre**, especifique un nombre exclusivo para el flujo de trabajo. Por ejemplo, si crea un flujo de trabajo de solicitud de compra para cada país o región en los que opera, puede llamar al flujo de trabajo de solicitud de compra **Solicitudes de compra Dinamarca** o **Solicitudes de compra España**.

## <a name="specify-the-workflow-owner"></a>Especificación del propietario del flujo de trabajo

El propietario del flujo de trabajo es la persona que administra y mantiene el flujo de trabajo. Siga estos pasos para especificar el propietario del flujo de trabajo.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En la lista **Propietario**, seleccione el nombre de la persona que administrará el flujo de trabajo.

## <a name="select-an-email-template"></a>Selección de una plantilla de correo electrónico

Siga estos pasos para seleccionar la plantilla de correo electrónico que se usa para generar los mensajes de notificación sobre el flujo de trabajo.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En la lista **Plantilla de correo electrónico para notificaciones de flujo de trabajo**, seleccione la plantilla.

## <a name="enter-instructions-for-users"></a>Especificación de las instrucciones para los usuarios

Puede proporcionar instrucciones a los usuarios que envían los documentos que se deben procesar y aprobar. A estos usuarios también se les conoce como *originadores*. Por ejemplo, está creando un flujo de trabajo de solicitudes de compra y especifica instrucciones. Esas instrucciones se pueden ver entonces por los usuarios que especifican solicitudes de compra en la página **Solicitudes de compra**. Para consultar las instrucciones, el originador hace clic en el icono de la barra de mensajes del flujo de trabajo. Siga estos pasos para escribir las instrucciones para los usuarios.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Instrucciones de envío**, escriba las instrucciones.
3. Para personalizar las instrucciones, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. Haga clic en el campo **Instrucciones de envío** para especificar dónde debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.

4. Para agregar traducciones de las instrucciones, siga estos pasos:

    1. Haga clic en **Traducciones**.
    2. En la página que aparece, haga clic en **Agregar**.
    3. En la lista que aparece, seleccione el idioma en el que escribirá el texto.
    4. En el campo **Texto traducido**, escriba el texto.
    5. Para personalizar el texto, puede insertar marcadores de posición. Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 3.
    6. Haga clic en **Cerrar**.

> [!NOTE]
> Los marcadores de posición no se pueden agregar usando copiar y pegar porque la información de destino no se pega correctamente. Utilice la interfaz para agregar marcadores de posición.

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a>Especifique cuándo se usa este flujo de trabajo mediante condiciones de activación

Puede crear varios flujos de trabajo que estén basados en el mismo tipo de flujo de trabajo. Cuando existen varios flujos de trabajo basados en el mismo tipo, debe especificar cuándo se usa cada uno usando condiciones de activación. Si no se cumplen las condiciones de activación, se utiliza el flujo de trabajo predeterminado. De manera similar, si solo hay una configuración de flujo de trabajo definida para un tipo de flujo de trabajo, entonces esa configuración de flujo de trabajo se usará independientemente de las condiciones de activación.

Por ejemplo, puede crear un flujo de trabajo de solicitudes de compra para cada país o región en los que opera como, por ejemplo, Solicitudes de compra Dinamarca y Solicitudes de compra España, con las siguientes condiciones:

- Se usa Solicitudes de compra Dinamarca cuando: país/región = DK
- Se usa Solicitudes de compra España cuando: país/región = ES

Siga estos pasos para especificar cuándo se usa el flujo de trabajo que está configurando.

1. En el panel izquierdo, haga clic en **Activación**.
2. Active la casilla **Establecer condiciones para ejecutar este flujo de trabajo**.
3. Haga clic en **Agregar condición**.
4. Escriba una condición.
5. Escriba condiciones adicionales que sean necesarias.
6. Revise el flujo de trabajo con algunos registros de destino para comprobar que la condición incluya y excluya correctamente los registros.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones

Cuando se envía un documento para que se lo procese, se crea una instancia de flujo de trabajo. Puede enviar notificaciones a los usuarios para indicar el inicio, la finalización, la terminación o la detención debido a un error de las instancias de flujo de trabajo basadas en el flujo de trabajo. Siga estos pasos para especificar cuándo se envían notificaciones.

1. En el panel izquierdo, haga clic en **Notificaciones**.
2. Active las casillas de verificación correspondientes a los eventos que deben desencadenar las notificaciones:

    - **Iniciado**: enviar notificaciones cuando se inicia una instancia de flujo de trabajo.
    - **Detenido**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error.
    - **Completado**: enviar notificaciones cuando se completa una instancia de flujo de trabajo.
    - **Irrecuperable**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error irrecuperable.
    - **Terminado**: enviar notificaciones cuando finaliza una instancia de flujo de trabajo.

3. Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4. En la pestaña **Texto de notificación**, escriba el texto de la notificación.
5. Para personalizar el texto, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra el texto a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. Haga clic en el campo para especificar dónde debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.
    5. Un marcador de posición **Texto de notificación** común para incluir es "Últimas notas: %Workflow.Last note%", que muestra cualquier comentario del paso anterior.

6. Para agregar traducciones del texto, siga estos pasos:

    1. Haga clic en **Traducciones**.
    2. En la página que aparece, haga clic en **Agregar**.
    3. En la lista que aparece, seleccione el idioma en el que escribirá el texto.
    4. En el campo **Texto traducido**, escriba el texto.
    5. Para personalizar el texto, puede insertar marcadores de posición. Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 5.
    6. Haga clic en **Cerrar**.

7. En la pestaña **Destinatario**, utilice las siguientes opciones para especificar quién debe recibir las notificaciones.

    <table>
    <thead>
    <tr>
    <th>Opción</th>
    <th>Las notificaciones se envían a estos usuarios</th>
    <th>Para enviar notificaciones, siga estos pasos</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td>
    <ol>
    <li>En la pestaña <strong>Destinatario</strong>, haga clic en <strong>Participante</strong>.</li>
    <li>En la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios que participan en el flujo de trabajo</td>
    <td>
    <ol>
    <li>En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario del flujo de trabajo</strong>.</li>
    <li>En la pestaña <strong>Usuario del flujo de trabajo</strong>, en la lista <strong>Usuario del flujo de trabajo</strong>, seleccione un participante de este flujo de trabajo.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuario</td>
    <td>Usuarios concretos</td>
    <td>
    <ol>
    <li>En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario</strong>.</li>
    <li>En la pestaña <strong>Usuario</strong>, la lista <strong>Usuarios disponibles</strong> incluye todos los usuarios. Seleccione aquellos a los que desea enviar notificaciones y muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo.

Para escribir comentarios acerca de los cambios que realizó en el flujo de trabajo, siga estos pasos.

1. En el panel izquierdo, haga clic en **Notas**.
2. En el campo **Especificar comentarios sobre el flujo de trabajo**, escriba sus comentarios.
3. Revise los comentarios: una vez agregados, no podrá modificarlos.
4. Haga **Agregar** clic en para agregar sus comentarios al área **Historial de comentarios**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]