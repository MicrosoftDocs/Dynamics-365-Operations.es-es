---
title: Configurar tareas automatizadas en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades de una tarea automatizada.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a9f37228beedafa085987668d5c89b06c6c9d61
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "365118"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>Configurar tareas automatizadas en un flujo de trabajo

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar las propiedades de una tarea automatizada.

Para configurar una tarea automatizada en el editor de flujo de trabajo, haga clic con el botón secundario en la tarea y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, use los siguientes procedimientos para configurar las propiedades de la tarea automatizada.

## <a name="name-the-task"></a>Asignación de un nombre a la tarea

Siga estos pasos para asignar un nombre a la tarea automatizada.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Nombre**, especifique un nombre único para la tarea.

## <a name="specify-when-notifications-are-sent"></a>Especificación del momento en que se envían notificaciones

Puede enviar notificaciones cuando se ha ejecutado o cancelado una tarea automatizada. Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.

1. En el panel izquierdo, haga clic en **Notificaciones**.
2. Active las casillas de verificación junto a los eventos que deben notificarse:

    - **Ejecución**: se envían notificaciones cuando la tarea se ha ejecutado.
    - **Cancelado**: se envían notificaciones cuando la tarea se ha cancelado.

3. Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.
4. En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.
5. Para personalizar la notificación, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra la notificación a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.

6. Para agregar traducciones de la notificación, siga estos pasos:

    1. Haga clic en **Traducciones**.
    2. En la página que aparece, haga clic en **Agregar**.
    3. En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4. En el campo **Texto traducido**, escriba el texto.
    5. Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.
    6. Haga clic en **Cerrar**.

7. En la pestaña **Destinatario**, especifique a quién se envían las notificaciones. Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.

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
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios que participan en el flujo de trabajo actual</td>
    <td>
    <ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Usuario</td>
    <td>Usuarios de Microsoft Dynamics 365 for Finance and Operations específicos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Finance and Operations. Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.
