---
title: Diseñar cuestionarios
description: Este artículo describe el proceso para crear un cuestionario. El primer paso es diseñar el cuestionario. Cuando diseñe un cuestionario, no solo escribe las preguntas y respuestas, sino que también crea la estructura que permite que se registren y se tabulen respuestas.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: da4250b281438c29c82150af8db9cb8cca41c6c9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420479"
---
# <a name="design-questionnaires"></a>Diseñar cuestionarios

Este artículo describe el proceso para crear un cuestionario. El primer paso es diseñar el cuestionario. Cuando diseñe un cuestionario, no solo escribe las preguntas y respuestas, sino que también crea la estructura que permite que se registren y se tabulen respuestas. 

Un cuestionario de cuidado diseño puede ayudarle a aumentar la calidad de los datos recopilados. Con un cuidado diseño, puede seleccionar mejor las opciones adecuadas para un cuestionario en el momento adecuado. Los siguientes puntos pueden ayudarle a planificar un cuestionario efectivo:

-   Defina claramente el propósito del cuestionario para ayudarle a garantizar que las preguntas apoyan el propósito.
-   Determine la persona individual o el grupo de personas que deben completar el cuestionario.
-   Escriba las preguntas que aparecerán en el cuestionario e incluya opciones de respuesta, si procede.
-   Asegúrese de que el cuestionario fluye de manera lógica, de modo que los encuestados sigan interesados.
-   Organice las preguntas y respuestas en el orden en que deben presentarse a los encuestados.
-   Decida cómo deben evaluarse los resultados, si procede.
-   Decida si necesitará características adicionales. Por ejemplo, determine si se deben clasificar resultados y cómo se hará, si se requiere un límite de tiempo o si todas las preguntas serán obligatorias.

La fase de diseño incluye cuatro categorías de tareas que debe completar en este orden:

1.  Configurar los requisitos previos, según sea necesario.
2.  Configurar grupos de respuestas y respuestas, si procede.
3.  Configurar preguntas y su asociación con los grupos de respuestas.
4.  Configurar el propio cuestionario y vincularle preguntas.

## <a name="prerequisites"></a>Requisitos previos
Algunos requisitos previos deben estar implementados para poder crear cuestionarios, respuestas y preguntas. Sin embargo, no todos los requisitos previos son necesarios para la funcionalidad completa.

### <a name="required"></a>Requerido

| Requisito previo        | Descripción                |
|---------------------|----------------------------|
| Tipos de cuestionario | Categorizar cuestionarios. |
| Tipos de pregunta      | Categorizar preguntas.      |

### <a name="optional"></a>Opcional

| Requisito previo             | Descripción                                                    |
|--------------------------|----------------------------------------------------------------|
| Parámetros del cuestionario | Modificar los controles básicos y los parámetros predeterminados para los cuestionarios. |

### <a name="questionnaire-types"></a>Tipos de cuestionario

Los tipos de cuestionario son obligatorios y deben asignarse al crear un cuestionario. Los tipos de cuestionario ayudan a la gestión y clasificación de los cuestionarios. Use los tipos de cuestionario para clasificar los cuestionarios y diferenciarlos entre sí. Por ejemplo, si hay varios cuestionarios entre los que seleccionar, puede filtrarlos según el tipo para que sea más fácil encontrar un cuestionario concreto. Estos son algunos ejemplos de tipos de cuestionario:

-   Desarrollo de recursos humanos
-   Encuestas de clientes
-   Proceso de revisión

### <a name="question-types"></a>Tipos de pregunta

Los tipos de pregunta son obligatorios y deben asignarse al crear una pregunta. 

Use los tipos de pregunta para clasificar las consultas para los informes. Los tipos de pregunta también facilitan la búsqueda de preguntas, porque puede usar tipos como filtros en la página **Consultas**. Estos son algunos ejemplos de tipos de pregunta:

-   Recursos humanos
-   Actividades comerciales de gestión
-   Evaluación del curso

### <a name="questionnaire-parameters"></a>Parámetros del cuestionario

Los parámetros de cuestionario son opcionales. Es posible que no los use, en función de los requisitos de la empresa. 

Los parámetros del cuestionario definen el anonimato, los códigos de secuencia numérica y los tipos de referencia de un cuestionario. Cuando una organización distribuye un cuestionario, la opción de permitir que los encuestados sigan siendo anónimos podría ser de interés. 

Los códigos de secuencia numérica se usan para organizar preguntas y respuestas. Según estos códigos de secuencia numérica, los valores se asignan automáticamente a los artículos. 

Debe definir todos los parámetros antes de empezar a crear los datos. Puede modificar los parámetros del cuestionario en cualquier momento.

## <a name="questionnaire-components"></a>Componentes de cuestionario
Los cuestionarios constan de tres elementos principales: grupos de respuestas que contienen las respuestas a preguntas de respuesta múltiple, consultas y el propio cuestionario. Opcionalmente puede agrupar las preguntas de un cuestionario en grupos de resultados. Los grupos de resultados le permiten clasificar consultas y proporcionar análisis adicional sobre el cuestionario. 

[![Componentes del cuestionario](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Responder a grupos y respuestas

Los encuestados pueden responder a una pregunta de dos formas, en función del asunto de la pregunta:

-   Las respuestas abiertas no requieren respuestas en un formato específico. Los encuestados pueden escribir una respuesta como texto, un número, una fecha o una hora. Estas preguntas suelen requerir que los encuestados proporcionen información subjetiva en sus respuestas, como una opinión, descripción, evaluación o estimación.
-   Las preguntas cerradas requieren que el encuestado seleccione una respuesta en una lista de posibles respuestas correctas.

Para proporcionar una lista de posibles respuestas para preguntas cerradas, puede crear respuestas en la página **Grupos de respuestas**. 

Los grupos de respuestas y las respuestas son componentes que conforman el cuerpo principal de la información a partir de la que se crean las preguntas. Después de crear un grupo de respuestas, puede asociar el grupo de respuestas con una pregunta en el campo **Grupo de respuestas** de la página **Preguntas**. 

Un grupo de respuestas se puede usar para de una pregunta del mismo cuestionario, así como en varios cuestionarios. 

> [!NOTE]
> Si modifica el texto de la respuesta en grupos de respuestas que ya se han usado en cuestionarios completados, se hace difícil evaluar datos y es posible que los resultados del cuestionario ya no sean válidos. Si debe cambiar un grupo de respuestas, piense en crear un nuevo grupo de respuestas en lugar de cambiar uno existente. No puede eliminar los grupos de respuestas que están vinculados a una pregunta o a una respuesta o que ya se han contestado.

### <a name="questions"></a>Preguntas

Un cuestionario debe contener preguntas. Las preguntas pueden ser abiertas o cerradas.

-   No se puede controlar las respuestas a preguntas abiertas, en las cuales el encuestado puede escribir su propia respuesta.
-   Las preguntas cerradas requieren una lista de opciones de respuesta predefinidas y las preguntas se pueden estructurar para permitir a un encuestado seleccionar múltiples respuestas. Las preguntas se deben diseñar para obtener información específica de un encuestado y se deben vincular a un grupo de respuestas que proporcione las opciones de respuesta para cada pregunta cerrada. 

    > [!NOTE]
    > Antes de configurar las preguntas cerradas, debe crear grupos de respuestas y respuestas.

Se puede organizar las preguntas en una jerarquía de preguntas condicionales, de modo que las preguntas que sean secundarias dependan de la respuesta que el encuestado selecciona para la pregunta anterior. Puede escribir las preguntas primero y, a continuación, organizarlas en una jerarquía posteriormente.

## <a name="setting-up-questionnaires"></a>Configurar cuestionarios

> [!NOTE]
> Para poder configurar un cuestionario, debe configurar respuestas, preguntas y requisitos previos. 

Para cada cuestionario, puede especificar la información siguiente:

-   El tiempo total o el límite de tiempo para responder a las preguntas obligatorias.
-   Si todas las preguntas son obligatorias.
-   Si se deben calcular puntos de un cuestionario.
-   Cómo clasificar resultados.
-   Si el cuestionario estará disponible para un conjunto restringido de encuestados.
-   Si se debe mostrar una plantilla de formulario como fondo detrás de cada página del cuestionario.
-   Si se requieren notas adicionales para aclarar el objetivo del cuestionario a los encuestados.
-   Si desea que las preguntas se muestren en un orden fijo o que se seleccionen de un grupo de forma aleatoria.
-   Si las preguntas se realizarán solo si se proporcionan respuestas específicas para las respuestas anteriores.

### <a name="set-up-a-questionnaire"></a>Configurar un cuestionario

La página principal que se usa para configurar un cuestionario es la página **Cuestionarios**. Para configurar un cuestionario, complete las tareas siguientes para:

1.  Crear de un cuestionario.
2.  Siga uno de estos pasos para vincular preguntas al cuestionario:
    -   Si utiliza grupos de resultados, puede vincular preguntas a un cuestionario mediante grupos de resultados. Configure primero los grupos de resultados del cuestionario y, a continuación, agregue preguntas a los grupos de resultados.
    -   Si no usa grupos de resultados, las preguntas se pueden adjuntar directamente al cuestionario.

3.  Configurar una jerarquía de preguntas condicionales, si fuera necesario.
4.  Realizar una prueba del cuestionario.

En la página **Cuestionarios**, haga clic en **Validar** para comprobar si el cuestionario se ha agrupado correctamente. Sin embargo, es buena idea completar el cuestionario y probarlo usted el mismo antes de distribuirlo.

### <a name="modify-a-questionnaire"></a>Modificar un cuestionario

Puede completar las siguientes tareas en la página **Cuestionarios**:

-   Modificar la mayor parte de la información del cuestionario, como los grupos de resultados y preguntas.
-   Eliminar y agregar preguntas.
-   Realizar cambios en los grupos de resultados y la secuencia numérica 

> [!CAUTION]
> Tenga cuidado al cambiar los cuestionarios que ya se hayan respondido. Los cambios pueden reducir la precisión de las estadísticas y por tanto para convertirlas en una base deficiente para la evaluación. Piense en crear una nueva pregunta en lugar de cambiar una pregunta que ya se haya respondido.

En un cuestionario, no puede eliminar los siguientes tipos de preguntas:

-   Preguntas vinculadas a un cuestionario.
-   Preguntas que ya se han respondido y que, por tanto, aparecen en el cuadro de diálogo **Respuestas**.

### <a name="result-groups"></a>Grupos de resultados

Los grupos de resultados son opcionales al adjuntar preguntas a un cuestionario. 

El cálculo de los puntos y la clasificación de los resultados del cuestionario se realiza mediante un grupo de resultados. Si usa grupos de resultados, puede realizar las tareas siguientes:

-   Evaluar los resultados del cuestionario en base a las estadísticas de la puntuación.
-   Evaluar la puntuación de un encuestado por cada grupo de resultados que haya configurado.
-   Generar estadísticas para cada grupo de resultados, para ayudarle a analizar los resultados.
-   Imprimir un informe con los resultados de cada grupo de resultados y, además, los puntos/textos opcionales basados en los puntos obtenidos en cada uno de estos grupos.

> [!NOTE]
> Para poder configurar los grupos de resultados, debe completar las tareas siguientes:

-   Configurar preguntas cerradas. Para una pregunta cerrada, el tipo de entrada de la página **Preguntas** debe ser **Casilla**, **Botón alternativo** o **Cuadro combinado**.
-   Defina puntos para las respuestas de los grupos de respuestas asignados a cada pregunta.
-   Configurar un cuestionario.

Para adjuntar preguntas a un cuestionario mediante los grupos de resultados, primero debe configurar los grupos de resultados del cuestionario y, a continuación, agregar las preguntas a dichos grupos. En caso de que no use grupos de resultados, las preguntas se pueden adjuntar directamente a un cuestionario. 

Puede configurar varios grupos de resultados para evaluar los puntos que un encuestado obtiene en cada categoría. Una vez completado el cuestionario, puede ver los puntos obtenidos por cada grupo. 

> [!TIP]
> Para evaluar un cuestionario mediante los puntos, aunque sin categorías independientes, puede agregar todas las preguntas a un único grupo de resultados. 

También puede configurar uno o más mensajes basados en puntos que los encuestados reciben tras completar un cuestionario. El texto que se muestra puede variar en función de la puntuación que logre un encuestado en un grupo de resultados. Para utilizar mensajes basados en puntos, se deben definir los intervalos de puntos y la descripción de cada intervalo. Cuando un encuestado logra una puntuación en un intervalo concreto, el texto de ese intervalo se incluye en el informe de resultados. 

Debido a que un grupo de resultados está relacionado con los puntos asociados con determinados sistemas de preguntas de un cuestionario, solo se puede usar un grupo de resultados concreto para un cuestionario.

#### <a name="example-pointstexts-for-result-group-3"></a>Ejemplo: Creación de puntos/textos para un grupo de resultados 3

Usa un cuestionario para una prueba de liderazgo que tiene 15 preguntas en tres categorías. Cree tres grupos de resultados y agrega cinco preguntas a cada grupo de resultados. A continuación, se obtiene el total de los puntos de los tres grupos. Los tres grupos de resultados son los siguientes:

-   Habilidades de creatividad
-   Habilidades de liderazgo
-   Habilidades de técnica

Para usar mensajes basados en puntos, puede configurar los intervalos de texto de cada grupo de resultados. A cada pregunta se le asignan dos puntos. Por lo tanto, el total máximo del punto de cada grupo de resultados es 10. 

En la tabla siguiente se muestran los mensajes basados en puntos que define para el grupo de resultados de las "capacidades de la dirección”.

| Intervalo de puntos | Texto                                       |
|----------------|--------------------------------------------|
| De 1 a 3         | Su capacidad de liderazgo está en la media.     |
| De 4 a 7         | Su capacidad de liderazgo es buena.        |
| De 8 a 10        | Su capacidad de liderazgo es excepcional. |

Se pueden configurar intervalos de puntos y textos para cada grupo de resultados de un cuestionario. Se mostrarán los textos de cada grupo de resultados que correspondan a la puntuación de cada encuestado. 

> [!NOTE]
> Puede realizar cambios en los intervalos y en los textos. No obstante, si se ha completado el cuestionario, los cambios pueden provocar diferencias entre los informes de resultados previos y los nuevos.

### <a name="conditional-question-hierarchies"></a>Jerarquías de preguntas condicionales

Las jerarquías de preguntas condicionales son opcionales al configurar un cuestionario. 

> [!NOTE]
> Antes de configurar una jerarquía de preguntas condicionales, debe adjuntar preguntas que tengan asignados grupos de respuestas al cuestionario. 

Para usar las preguntas condicionales para crear una jerarquía de preguntas en un cuestionario, puede hacer que la secuencia en la que se presentan las preguntas dependa de la respuesta que el encuestado selecciona para cada pregunta. Al basar la secuencia de preguntas en la respuesta del encuestado, puede modificar el cuestionario conforme el encuestado lo completa.

#### <a name="examples"></a>Ejemplo

Una entidad jurídica ofrece tanto artículos como servicios a sus clientes. Como suele ocurrir en esos casos, algunos clientes solo compran artículos, otros compran solo servicios y otros compran tanto artículos como servicios. Por tanto, cuando la entidad jurídica distribuye una encuesta de satisfacción del cliente, aplica una estructura condicional al cuestionario, de manera que los clientes que solo compran servicios no tengan que responder a preguntas sobre artículos. 

De forma alternativa, configure un cuestionario de manera que un encuestado seleccione la respuesta A para la pregunta 1; la pregunta 2 es la siguiente en la secuencia de preguntas. Sin embargo, si el encuestado selecciona la respuesta B para la pregunta 1, la pregunta 5 será la siguiente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]