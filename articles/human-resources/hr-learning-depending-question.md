---
title: Realizar una pregunta según la respuesta a la pregunta anterior
description: Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39da0418f60273a82cb51e5cf3aad60e4efdb234
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056669"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Realizar una pregunta según la respuesta a la pregunta anterior

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior. Por ejemplo, si pregunta "¿Prefiere café o té?", se podrá determinar una pregunta de seguimiento lógica en función de si el encuestado selecciona café o té como respuesta. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="find-the-existing-questionnaire"></a>Localización del cuestionario existente
1. Vaya a Cuestionario > Diseño > Cuestionarios.
2. En la lista, seleccione el cuestionario de WorkFH.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Adición de todas las preguntas y subpreguntas al cuestionario
1. Haga clic en Preguntas.
2. Haga clic en Nuevo.
3. En el campo Pregunta, seleccione el número de pregunta 00016.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Definición de la secuencia del cuestionario en Condicional y determinación de la pregunta según la respuesta adecuada
1. Haga clic en Editar.
2. Expanda la sección Configuración.
3. En el campo Orden de preguntas, seleccione Condicional.
4. Haga clic en Pregunta condicional.
5. En el árbol, seleccione "Preguntas\Explique por qué respondió así a la pregunta anterior".
6. En el campo Pregunta principal, seleccione el número de pregunta 00009.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Respuesta, especifique el identificador de secuencia de respuesta de la opción de respuesta de la que quiera que dependa la pregunta. Por ejemplo, escriba 1 para la primera opción de respuesta.
9. Haga clic en Guardar.
10. En el árbol, seleccione "Preguntas\Me pagan justamente por el trabajo que hago".
    * Observe cómo el árbol de preguntas se ha actualizado para mostrar la dependencia.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]