---
title: Realizar una pregunta según la respuesta a la pregunta anterior
description: Las preguntas condicionales le permiten especificar qué pregunta de seguimiento aparecerá, en función de la respuesta a la pregunta anterior.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e49ee4dd1f2d4a5af3112d27eaf8d697904d2487
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538500"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Realizar una pregunta según la respuesta a la pregunta anterior

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

