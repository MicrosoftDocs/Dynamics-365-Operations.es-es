---
title: Realizar una pregunta según la respuesta a la pregunta anterior
description: Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f28f75a902121f23c92a919b539517dbdb191447
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066734"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Realizar una pregunta según la respuesta a la pregunta anterior


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior. Por ejemplo, si pregunta "¿Prefiere café o té?", se podrá determinar una pregunta de seguimiento lógica en función de si el encuestado selecciona café o té como respuesta. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="find-the-existing-questionnaire"></a>Localización del cuestionario existente
1. Vaya a **Cuestionario** > **Diseño** > **Cuestionarios**.
2. En la lista, seleccione el cuestionario de WorkFH.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Adición de todas las preguntas y subpreguntas al cuestionario
1. Haga clic en **Preguntas**.
2. Haga clic en **Nuevo**.
3. En el campo **Pregunta**, seleccione el número de pregunta 00016.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en **Guardar**.
7. Cierre la página.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Definición de la secuencia del cuestionario en Condicional y determinación de la pregunta según la respuesta adecuada
1. Haga clic en **Editar**.
2. Expanda la sección **Configuración**.
3. En el campo **Orden de preguntas**, seleccione 'Condicional'.
4. Haga clic en **Pregunta condicional**.
5. En el árbol, seleccione "Preguntas\Explique por qué respondió así a la pregunta anterior".
6. En el campo **Pregunta principal**, seleccione el número de pregunta 00009.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo **Respuesta**, especifique el identificador de secuencia de respuesta de la opción de respuesta de la que quiera que dependa la pregunta. Por ejemplo, escriba 1 para la primera opción de respuesta.
9. Haga clic en **Guardar**.
10. En el árbol, seleccione "Preguntas\Me pagan justamente por el trabajo que hago".
    * Observe cómo el árbol de preguntas se ha actualizado para mostrar la dependencia.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
