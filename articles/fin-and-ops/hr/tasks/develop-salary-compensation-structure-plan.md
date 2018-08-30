--- 
title: Desarrollar planes y estructuras de salarios o compensaciones
description: "Esta guía de la tarea le lleva por el proceso de crear un plan de compensación fija y permitir que los empleados se inscriban en el plan a través de las reglas de idoneidad."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 0514cd485c8fa0026390a22be350ff23933afd7b
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="develop-salarycompensation-structures-and-plans"></a>Desarrollar planes y estructuras de salarios o compensaciones

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea le lleva por el proceso de crear un plan de compensación fija y permitir que los empleados se inscriban en el plan a través de las reglas de idoneidad. La empresa de datos de prueba utilizada para crear esta tarea es USMF y la tarea está pensada para los directores de compensaciones y prestaciones.


## <a name="create-fixed-compensation-plan"></a>Crear un plan de compensación fija
1. Haga clic en Administración de compensaciones.
2. Haga clic en Planes de compensación fija.
3. Haga clic en Nuevo.
4. En el campo Plan, escriba un valor.
5. En el campo Descripción, escriba un valor.
6. En el campo Fecha de vigencia, especifique una fecha.
7. En el campo Tipo, seleccione si el plan de compensación fija es un grupo, una categoría o un paso.
8. La casilla Recomendación permitida actúa como valor predeterminado para las acciones agregadas a este plan de un evento de procesos.  Habilitar las recomendaciones le permite anular el importe calculado del criterio al procesar la compensación.
9. La tolerancia de Fuera de intervalo le permite especificar cómo desea gestionar los importes de contrapartida que se encuentran fuera del intervalo de la estructura de compensación para el nivel dado.  Una tolerancia de Fuera de intervalo establecida en Ninguna permitirá que se use cualquier importe de compensación.  Una tolerancia débil advertirá el usuario si el importe de compensación es inferior al importe mínimo de puntos de referencia para dicho nivel o mayor que el importe máximo para dicho nivel. El usuario puede ignorar la advertencia y continuar.  Una tolerancia estricta generará un error si la compensación del empleado está fuera de los puntos de referencia mínimo y máximo para el nivel y ajustará automáticamente la compensación del empleado para que esté dentro del intervalo.
10. El campo Regla de contratación se usa cuando un evento de proceso de compensación se ejecuta para calcular la compensación del empleado.  Una Regla de contratación de Porcentaje calculará un aumento que esté prorrateado para la duración de tiempo que el trabajador ha estado contratado en el ciclo.
11. En el campo Divisa, escriba un valor.
12. En el campo Conversión de índice salarial, especifique o seleccione un valor.
13. Expanda la sección Matriz del intervalo de aprovechamiento.
    * Opcionalmente, agregue los registros del intervalo de aprovechamiento para hacer más rápidos a los empleados que están en el punto medio y ralentizarlos para que no lleguen al máximo de su intervalo.  
14. En este momento, debe guardar el plan de compensación fija para habilitar el botón Configurar compensación y continuar definiendo su estructura de compensación para el plan.  Haga clic en Guardar.
15. Haga clic en Configurar compensación.
    * Hay tres maneras de crear una estructura de compensación. 1: Para crear una estructura totalmente nueva, seleccione un conjunto de puntos de referencia y agregue niveles para crear su propia estructura. 2: Copiar una estructura de compensación de un plan existente como punto de partida y modificarla para el nuevo plan. 3: Seleccionar una cuadrícula de compensación existente. Si la cuadrícula de compensación se está usando ya en otro plan, cualquier cambio efectuado en la cuadrícula también se reflejará en el otro plan.  
16. Seleccione la opción Crear una nueva matriz a partir de la matriz de compensación existente.
17. En el campo Copiar de cuadrícula, especifique o seleccione un valor.
    * Puede cambiar opcionalmente el nombre de la nueva cuadrícula de compensación que se creará como una copia de la cuadrícula seleccionada.  
18. Haga clic en Aceptar
19. Haga clic en Cambio masivo.
    * El cambio masivo le permite mantener las cantidades de la matriz de compensación aplicando un aumento de porcentaje o fijo a uno o varios niveles y/o puntos de referencia.  
20. En el campo Importe del ajuste, escriba un número.
21. En la lista, active o desactive todas las filas.
22. Haga clic en Aplicar a la cuadrícula.
23. Cierre la página.
    * Una vez que se ha creado o se ha seleccionado una estructura de compensación, puede seleccionar qué puntos de referencia deben utilizarse como punto de control para el plan de compensación fija.  El punto de control se usa para calcular el ratio de comparación de un empleado.  
24. En el campo Punto de control, especifique o seleccione un valor.
25. Cierre la página.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Crear una regla de elegibilidad para el nuevo plan de compensación fija
    * El nuevo plan de compensación fija no se puede asignar a un empleado hasta que se hayan definido las reglas de idoneidad para el plan.  
1. Haga clic en Reglas de idoneidad.
2. Haga clic en Nuevo.
3. En el campo Idoneidad, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Fecha de vigencia, especifique una fecha.
    * Las reglas de idoneidad se utilizan para los planes de compensación fijos y variables.  En el campo Tipo, seleccione para qué tipo de plan es este conjunto de reglas de idoneidad.  
6. En el campo Plan, especifique o seleccione un valor.
    * Seleccione los criterios que un empleado debe cumplir para ser idóneo para el plan de compensación. Los criterios pueden incluir un departamento, un sindicato, una ubicación (región de compensación), un trabajo, una función, un tipo de trabajo o un nivel de compensación. El empleado debe cumplir todos los criterios especificados para ser idóneo para el plan de compensación. Si no se especifica ningún criterio, todos los empleados son idóneos para el plan de compensación. Si un empleado no cumple los criterios especificados en la regla de idoneidad o una regla de idoneidad no se ha especificado para un plan de compensación, el plan de compensación no aparecerá en las búsquedas al crear un registro de compensación fija para un empleado.  
7. Cierre la página.
8. Cierre la página.


