---
title: Ver y evaluar los resultados de un cuestionario
description: "En este tema se explica cómo se pueden ver y evaluar los resultados de los cuestionarios que los encuestados completan."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b7c4a612d54f3ae8967be930c0b98e4783fd8200
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# Ver y evaluar los resultados de un cuestionario
<a id="view-and-evaluate-the-results-of-a-questionnaire" class="xliff"></a>

[!include[banner](includes/banner.md)]


En este tema se explica cómo se pueden ver y evaluar los resultados de los cuestionarios que los encuestados completan. 

Después de que los encuestados completen un cuestionario, puede ver y evaluar los resultados del mismo de las maneras siguientes:

-   **Sesiones de respuestas completadas**: ver los detalles sobre los cuestionarios que los encuestados han completado y generar informes para resumir respuestas y los puntos que se hayan obtenido.
-   **Grupos de resultados**: ver los detalles y las estadísticas del grupo de resultados de los cuestionarios. Es posible generar estadísticas del grupo de resultados para una única sesión de respuestas de un cuestionario o todas las sesiones de respuestas.
-   **Estadísticas de cuestionarios**: especificar los criterios para calcular las estadísticas de un grupo determinado de encuestados.

También puede generar diversos informes para ver los resultados ordenados por persona, sesión de respuestas o grupo de resultados. Están disponibles los siguientes informes relacionados con cuestionarios completados:

-   Respuestas
-   Respuestas por cuestionario
-   Respuestas por persona
-   Análisis de realimentación

## Resultados de la sesión de respuestas
<a id="answer-session-results" class="xliff"></a>
Cuando los encuestados completen un cuestionario, puede ver los resultados de las sesiones de respuestas completadas. Una sesión de respuestas es la respuesta de un usuario a un cuestionario. Puede ver los detalles acerca de las sesiones de respuestas completadas en la página **Respuestas**. Las sesiones de respuestas que se incluyen en la página **Respuestas** se filtran de diversas maneras, en función de cómo abra la página:

-   Todos los cuestionarios
-   Un cuestionario concreto
-   Una persona concreta

En la página **Respuestas**, puede ver los detalles sobre las respuestas, los puntos obtenidos, las respuestas de un encuestado en cada grupo de resultados y la jerarquía de preguntas que se usó en el cuestionario seleccionado, si se usó una jerarquía de preguntas. También puede generar e imprimir los informes siguientes:

-   **Informe de resultados**: este informe muestra una representación gráfica de los puntos que se obtuvieron por grupo de resultados para la sesión de respuestas seleccionada.
-   **Informe de respuestas**: este informe muestra las respuestas que el encuestado seleccionó para cada pregunta del cuestionario.
-   **Respuestas incorrectas**: este informe muestra la información relacionada con las respuestas incorrectas que seleccionó el encuestado.

> **Nota**
>   El informe **Resultados** solo está disponible si usa grupos de resultados en el cuestionario y si seleccionó **Página de resultados** en la página **Cuestionarios**. Los informes **Respuesta** y **Respuestas incorrectas** solo están disponibles si seleccionó **Informe de respuestas** en la página **Cuestionarios**.

## Estadísticas de los cuestionarios
<a id="questionnaire-statistics" class="xliff"></a>
Puede usar las estadísticas del cuestionario para analizar los resultados de un cuestionario completado sobre la base de cálculos que se definan. Para definir cálculos, debe completar las tareas siguientes:

-   Seleccionar un criterio para calcular y mostrar las estadísticas.
    -   Puede mostrar las estadísticas por cuestionario, preguntas, filas de preguntas o grupos de resultados.
    -   Seleccione el tipo de gráfico que se usará al ver resultados.
    -   Seleccionar el tipo de personas de la red, como empleados, personas de contacto o candidatos, para los que incluir respuestas. También puede incluir las respuestas de los cuestionarios que se completaron de manera anónima.
    -   Configurar intervalos sobre la base de edad o antigüedad para analizar los resultados.
-   Seleccionar o comprobar la configuración que limita el sujeto de las estadísticas. Por ejemplo, al seleccionar un código postal, puede analizar los resultados para todos los encuestados dentro de un área geográfica específica.
-   Seleccionar o comprobar los criterios para analizar los resultados según encuestado o según las características del cuestionario. Por ejemplo, al seleccionar un **código postal**, se puede analizar la correlación entre la ubicación del encuestado y las respuestas correctas.

Los parámetros que defina se guardarán y se podrán usar para volver a calcular los resultados de forma periódica.

Consulte también
<a id="see-also" class="xliff"></a>
--------

[Diseñar cuestionarios](design-questionnaires.md)

[Uso de cuestionarios](questionnaires.md)

[Distribuir y completar cuestionarios](distribute-questionnaires.md)




