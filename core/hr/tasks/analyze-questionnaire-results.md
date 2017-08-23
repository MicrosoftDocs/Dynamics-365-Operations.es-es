--- 
title: Analizar resultados de cuestionario
description: "Las estadísticas de cuestionario se pueden usar para calcular promedios, totales y porcentajes basados en un sistema de datos demográficos."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 353faa30ba37c077479afd985b8808fcdbdcaae6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="analyze-questionnaire-results"></a>Analizar resultados de cuestionario

[!include[task guide banner](../../includes/task-guide-banner.md)]

Las estadísticas de cuestionario se pueden usar para calcular promedios, totales y porcentajes basados en un sistema de datos demográficos. Para iniciar este procedimiento, vaya a Cuestionario > Ver y analizar resultados > Estadísticas de los cuestionarios. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Creación de un registro de estadísticas de cuestionario
1. Vaya a Estadísticas de los cuestionarios.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Estadísticas, escriba un valor.
5. En el campo Descripción, escriba un valor.
6. En el campo Cuestionario, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en la pestaña General.
    * Seleccione si desea incluir resultados anónimos o resultados de trabajadores, contactos y candidatos.  
9. Active o desactive la casilla Trabajador.
    * Si va a ver los resultados por antigüedad o por edad, especifique los intervalos que desea usar para agrupar los resultados.  
    * Al especificar un 5 como intervalo de vencimiento, se agruparán los resultados en intervalos de cinco años de vencimiento.  
10. En el campo Edad, especifique un número.
    * Seleccione si desea ejecutar el cálculo en el cuestionario completo, para cada grupo de resultados, para cada pregunta o para cada fila de pregunta.  
    * Seleccione cómo desea agrupar los resultados.  
    * Por ejemplo, si se calculan los puntos promedio por pregunta, puede que le interese ver las preguntas agrupadas por grupo de resultados.  
    * Seleccione los datos en los que basar el cálculo.  
    * Por ejemplo, si desea ver el porcentaje promedio en el cuestionario entre los trabajadores frente al promedio en puntos.  
11. Haga clic en la ficha Intervalo.
    * Use los intervalos para limitar su conjunto de resultados a solo los que cumplan con los criterios del intervalo.  
12. Haga clic en la ficha Agrupación por.
    * Use Agrupaciones para determinar cómo se deben visualizar los resultados.  
    * Por ejemplo, agrupe los resultados primero por sexo y, a continuación, por edad.  
13. En la lista, busque y seleccione el registro deseado.
    * Mueva las agrupaciones al lado Seleccionadas y póngalas en el orden deseado.  

## <a name="execute-the-statistics-calculation"></a>Ejecución del cálculo de estadísticas
1. Haga clic en Ejecutar.
    * Seleccione qué función de cálculo desea aplicar a los resultados.  
    * Por ejemplo, calcule los porcentajes promedio en el cuestionario para las agrupaciones seleccionadas o calcule el total de puntos en los grupos de resultados para las agrupaciones seleccionadas.  
2. Active o desactive la casilla de verificación Eliminar búsquedas anteriores.
3. Haga clic en Aceptar

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Consulte los resultados de la ejecución de estadísticas del cuestionario.
1. Haga clic en Resultado.
2. Haga clic en Resultado.
3. Cierre la página.


