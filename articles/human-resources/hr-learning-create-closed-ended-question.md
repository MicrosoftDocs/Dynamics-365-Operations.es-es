---
title: Crear una pregunta cerrada
description: Las preguntas cerradas le permiten proporcionar opciones entre las que el encuestado puede elegir.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18b755675b97e608afccea2e48ea3cfca74c984f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686174"
---
# <a name="create-a-closed-ended-question"></a>Crear una pregunta cerrada


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Las preguntas cerradas le permiten proporcionar opciones entre las que el encuestado puede elegir. Primero, necesita crear el grupo de respuestas con las respuestas y luego crear la pregunta que usará el grupo de respuestas. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-an-answer-group"></a>Creación de un grupo de respuestas
1. Vaya a **Cuestionario** > **Diseño** > **Grupos de respuestas**.
2. Haga clic en **Nuevo**.
3. En el campo **Grupo de respuestas**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
    * Use la función **Aleatorizar** para colocar aleatoriamente las respuestas en un orden diferente cada vez que se use el grupo de respuestas para una pregunta.  
5. Haga clic en **Respuesta**.
6. Haga clic en **Nuevo**.
    * El número de secuencia controla el orden en que se muestran las respuestas, a menos que **Aleatorizar** esté seleccionado en el **grupo de respuestas**.  
    * Se pueden otorgar puntos a las respuestas y usarlas para puntuar el cuestionario.  
7. En el campo **Puntos**, escriba un número.
    * La respuesta correcta se puede marcar para indicar que la respuesta seleccionada es la correcta. Esto se puede usar para puntuar el cuestionario.  
8. En el campo **Respuesta**, escriba un valor.
    * Continúe creando las opciones de selección de respuestas para el grupo de respuestas.  
9. Haga clic en **Nuevo**.
10. En el campo **Puntos**, escriba un número.
11. En el campo **Respuesta**, escriba un valor.
12. Haga clic en **Nuevo**.
13. En el campo **Puntos**, escriba un número.
14. En el campo **Respuesta**, escriba un valor.
15. Haga clic en **Nuevo**.
16. En el campo **Puntos**, escriba un número.
17. En el campo **Respuesta**, escriba un valor.
18. Haga clic en **Nuevo**.
19. En el campo **Puntos**, escriba un número.
20. En el campo **Respuesta**, escriba un valor.
21. Cierre la página.
22. Cierre la página.

## <a name="create-the-question"></a>Creación de la pregunta
1. Vaya a **Cuestionario** > **Diseño** > **Preguntas**.
2. Haga clic en **Nuevo**.
3. Use el campo **Tipo** para agrupar las preguntas relacionadas.
    * Puede usar tipos de entrada de **casilla**, **botón alternativo** o **cuadro combinado** para las preguntas cerradas.  
4. En el campo **Tipo de entrada**, seleccione una opción.
5. En el campo **Grupos de respuestas**, especifique o seleccione un valor.
6. En el campo **Texto**, escriba un valor.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
