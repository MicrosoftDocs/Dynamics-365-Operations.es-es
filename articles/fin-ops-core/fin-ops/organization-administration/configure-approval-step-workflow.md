---
title: Configurar los pasos de aprobación en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades de un paso de aprobación.
author: ChrisGarty
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5442b7db0a1ccd2a2e07faf8635ac12ff06c560
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565743"
---
# <a name="configure-approval-steps-in-a-workflow"></a>Configurar los pasos de aprobación en un flujo de trabajo

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar las propiedades de un paso de aprobación.

Para configurar un paso de aprobación en el editor de flujo de trabajo, haga clic con el botón secundario en el paso de aprobación y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**. A continuación, use los siguientes procedimientos para configurar las propiedades del paso de aprobación.

## <a name="name-the-step"></a>Asignación de un nombre al paso
Siga estos pasos para asignar un nombre al paso de aprobación.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Nombre**, especifique un nombre único para la etapa de aprobación.

## <a name="enter-a-subject-line-and-instructions"></a>Especificación de una línea de asunto e instrucciones

Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados al paso de aprobación. Por ejemplo, si configura un paso de aprobación para solicitudes de compra, el usuario asignado a él ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**. La línea de asunto se muestra en una barra de mensajes de la página. A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones. Siga estos pasos para escribir una línea de asunto e instrucciones.

1. En el panel izquierdo, haga clic en **Configuración básica**.
2. En el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.
3. Para personalizar la línea de asunto, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.

4. Para agregar traducciones de la línea de asunto, siga estos pasos:

    1. Haga clic en **Traducciones**.
    2. En la página que aparece, haga clic en **Agregar**.
    3. En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4. En el campo **Texto traducido**, escriba el texto.
    5. Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.
    6. Haga clic en **Cerrar**.

5. En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.
6. Para personalizar las instrucciones, puede insertar marcadores de posición. Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios. Para insertar un marcador de posición, siga estos pasos:

    1. En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.
    2. Haga clic en **Insertar marcador de posición**.
    3. En la lista que aparece, seleccione el marcador de posición que desea insertar.
    4. Haga clic en **Insertar**.

7. Para agregar traducciones de las instrucciones, siga estos pasos:

    1. Haga clic en **Traducciones**.
    2. En la página que aparece, haga clic en **Agregar**.
    3. En la lista que aparece, seleccione el idioma en el que escribe el texto.
    4. En el campo **Texto traducido**, escriba el texto.
    5. Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.
    6. Haga clic en **Cerrar**.

## <a name="assign-the-approval-step"></a>Asignación del paso de aprobación

Siga estos pasos para especificar a quién se debe asignar el paso de aprobación.

1. En el panel izquierdo, haga clic en **Asignación**.
2. En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.

    <table>
    <thead>
    <tr>
    <th>Opción</th>
    <th>Los usuarios a los que está asignado el paso de aprobación</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Participante</td>
    <td>Usuarios asignados a un grupo o rol específicos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar el paso.</li>
    <li>En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar el paso.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar el paso.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede asignar el paso. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera: <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol>
    </li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar el paso: <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: el paso se asigna a todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: el paso se asigna únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: el paso no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios del flujo de trabajo actual</td>
    <td>
    <ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Usuario</td>
    <td>Usuarios concretos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios del sistema. Seleccione aquellos a los que desea asignar el paso y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para realizar alguna acción en los documentos que llegan al paso de aprobación o, dicho de otro modo, para responder a ellos. Seleccione una de las siguientes opciones:

    - **Horas**: escriba la cantidad de horas de las que dispone el usuario para responder. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Días**: escriba la cantidad de días de los que dispone el usuario para responder. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para responder.
    - **Meses**: seleccione el día y la semana en los que vence el plazo para responder. Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana del mes.
    - **Años**: seleccione el día, la semana y el mes en los que vence el plazo para responder. Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana de diciembre.

    Si el usuario no realiza ninguna acción en el documento en el tiempo asignado, el documento se considera vencido. Los documentos vencidos se remiten a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.

4. Si asignó el paso de aprobación a varios usuarios o a un grupo de usuarios, en la pestaña **Directiva de finalización**, seleccione una de las siguientes opciones:

    - **Un único aprobador**: la acción que se aplica al documento la determina la primera persona que responde. Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD. En este momento, el informe de gastos está asignado a Sue, Jo y Bill. Si Sue es la primera persona que responde al documento, la acción que ella lleva a cabo se aplica al documento. Si Sue rechaza el documento, se lo rechaza y se lo vuelve a enviar a Sam. Si Sue aprueba el documento, se lo envía a Ann para que lo apruebe.

        ![Flujo de trabajo que tiene un proceso de aprobación](./media/workflow_multipleusersinstep.gif)

    - **Mayoría de aprobadores**: la acción que se aplica al documento se determina cuando responde la mayoría de los aprobadores. Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD. En este momento, el informe de gastos está asignado a Sue, Jo y Bill. Si Sue y Jo son las dos primeras aprobadoras en responder, la acción que ellas llevan a cabo se aplica al documento.

        - Si Sue aprueba el documento pero Jo lo rechaza, el documento se rechaza y se vuelve a enviar a Sam.
        - Si tanto Sue como Jo aprueban el documento, se lo envía a Ann para que lo apruebe.

    - **Porcentaje de aprobadores**: la acción que se aplica al documento se determina cuando responde un porcentaje específico de aprobadores. Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD. En este momento, el informe de gastos está asignado a Sue, Jo y Bill, y usted ha establecido el porcentaje en **50**. Si Sue y Jo son las dos primeras aprobadoras en responder, la acción que ellas llevan a cabo se aplica al documento porque, entre ambas, alcanzan el 50% de aprobadores que se requiere.

        - Si Sue aprueba el documento pero Jo lo rechaza, el documento se rechaza y se vuelve a enviar a Sam.
        - Si tanto Sue como Jo aprueban el documento, se lo envía a Ann para que lo apruebe.

    - **Todos los aprobadores**: todos los aprobadores deben aprobar el documento; de lo contrario, el flujo de trabajo no podrá continuar. Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD. En este momento, el informe de gastos está asignado a Sue, Jo y Bill. Si Sue y Jo aprueban el documento pero Bill lo rechaza, el documento se rechaza y se vuelve a enviar a Sam. Si Sue, Jo y Bill aprueban el documento, se lo envía a Ann para que lo apruebe.

## <a name="specify-when-the-approval-step-is-required"></a>Especificación de las condiciones en que se requiere el paso de aprobación

Puede especificar cuándo se requiere el paso de aprobación. El paso de aprobación se puede requerir siempre o solo si se cumplen determinadas condiciones.

### <a name="the-approval-step-is-always-required"></a>El paso de aprobación se requiere siempre

Siga estos pasos si el paso de aprobación se requiere siempre.

1. En el panel izquierdo, haga clic en **Condición**.
2. Seleccione la opción **Ejecutar siempre este paso**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>El paso de aprobación se requiere en condiciones específicas

Es posible que el paso de aprobación que está configurando se requiera solo si se cumplen determinadas condiciones. Por ejemplo, si está configurando un paso de aprobación para un flujo de trabajo de solicitudes de compra, es posible que desee que el paso de aprobación se lleve a cabo solamente cuando el importe de una solicitud de compra sea superior a 10.000 USD. Siga estos pasos para especificar cuándo se requiere el paso de aprobación.

1. En el panel izquierdo, haga clic en **Condición**.
2. Seleccione la opción **Ejecutar este paso únicamente si se cumplen las condiciones siguientes**.
3. Escriba una condición.
4. Escriba condiciones adicionales que sean necesarias.
5. Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:

    1. Haga clic en **Probar**.
    2. En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.
    3. Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.
    4. Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Especificación de la acción que se realiza cuando vence el documento

Si un usuario no realiza ninguna acción en un documento en el tiempo asignado, el documento se considera vencido. Los documentos vencidos se pueden remitir a una instancia superior o asignar a otro usuario de forma automática para que los apruebe. Si el documento ha vencido, siga estos pasos para remitirlo a una instancia superior.

1. En el panel izquierdo, haga clic en **Remisión a una instancia superior**.
2. Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior. De manera automática, el sistema asigna el documento a los usuarios que forman parte de la ruta de remisión a una instancia superior. La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.

    | Secuencia | Ruta de remisión a una instancia superior      |
    |----------|----------------------|
    | 1        | Asignar a rol: Donna     |
    | 2        | Asignar a rol: Erin      |
    | 3        | Acción final: Rechazar |

    En este ejemplo, el sistema asigna el documento vencido a Donna. Si Donna no responde en el tiempo asignado, el sistema asigna el documento a Erin. Si Erin no responde en el tiempo asignado, el sistema rechaza el documento.

3. Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**. En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 4.

    <table>
    <thead>
    <tr>
    <th>Opción</th>
    <th>Usuarios a los que se remite el documento</th>
    <th>Pasos adicionales</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Jerarquía</td>
    <td>Usuarios de una jerarquía organizativa específica</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir a una instancia superior el documento.</li>
    <li>El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía. Dichos nombres representan a los usuarios a los que se puede remitir el documento. Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera: <ol>
    <li>Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</li>
    <li>Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>. A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</li>
    </ol>
    </li>
    <li>En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir el documento para una instancia superior: <ul>
    <li><strong>Asignar a todos los usuarios recuperados</strong>: el documento se remite para una instancia superior para todos los usuarios del intervalo.</li>
    <li><strong>Asignar sólo al último usuario recuperado</strong>: el documento se remite para una instancia superior únicamente al último usuario del intervalo.</li>
    <li><strong>Excluir usuarios con la siguiente condición</strong>: el documento no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada. Haga clic en <strong>Agregar condición</strong> para especificar la condición.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Usuario del flujo de trabajo</td>
    <td>Usuarios del flujo de trabajo actual</td>
    <td>
    <ul>
    <li>Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Usuario</td>
    <td>Usuarios concretos</td>
    <td>
    <ol>
    <li>Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</li>
    <li>La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios. Seleccione aquellos a los que desea remitir el documento para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para realizar alguna acción en los documentos, dicho de otro modo, para responder a ellos. Seleccione una de las siguientes opciones:

    - **Horas**: escriba la cantidad de horas de las que dispone el usuario para responder. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Días**: escriba la cantidad de días de los que dispone el usuario para responder. A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.
    - **Semanas**: escriba la cantidad de semanas de las que dispone el usuario para responder.
    - **Meses**: seleccione el día y la semana en los que vence el plazo para responder. Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana del mes.
    - **Años**: seleccione el día, la semana y el mes en los que vence el plazo para responder. Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana de diciembre.

5. Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior. El orden de los usuarios se puede modificar.
6. Si los usuarios de la ruta de remisión a una instancia superior no responden en el tiempo asignado, el sistema realiza una acción en el documento de manera automática. Para especificar la acción que el sistema realiza, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una acción.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]