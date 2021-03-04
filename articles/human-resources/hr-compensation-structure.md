---
title: Desarrollar una estructura de compensaciones
description: Este artículo le guía por el proceso de crear un plan de compensación fijo e inscribir empleados en el plan siguiendo reglas de idoneidad.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420444"
---
# <a name="develop-a-compensation-structure"></a>Desarrollar una estructura de compensaciones

Este artículo le guía por el proceso de crear un plan de compensación fijo e inscribir empleados en el plan siguiendo reglas de idoneidad. Este artículo utiliza los datos de demostración de USMF y se aplica a los Gerentes de Compensación y Beneficios.

## <a name="create-a-fixed-compensation-plan"></a>Crear un plan de compensación fija

1. Seleccione **Administración de compensaciones**.

2. Seleccione **Crear planes de compensación fija**.

3. Seleccione **Nuevo**.

4. En el campo **Plan**, escriba un valor.

5. En el campo **Descripción**, especifique un valor.

6. En el campo **Fecha de vigencia**, especifique una fecha.

7. En el campo **Tipo,** seleccione si el plan de compensación fija es un plan de **Banda**, **Categoría** o **Paso**.

8. La casilla **Recomendación permitida** actúa como valor predeterminado para las acciones agregadas a este plan de un evento de procesos. Habilitar las recomendaciones le permite anular el importe calculado del criterio al procesar la compensación.

9. El campo **Fuera de intervalo de tolerancia** le permite especificar cómo desea gestionar los importes de contrapartida que se encuentran fuera del intervalo de la estructura de compensación para el nivel dado. Establecer el campo **Fuera del rango de tolerancia** a **Ninguno** le permite usar cualquier importe de compensación. Una **Tolerancia débil** advertirá a los usuarios si el importe de compensación es inferior o superior al importe de punto de referencia máximo para ese nivel. El usuario puede ignorar la advertencia y continuar. Una **Tolerancia estricta** generará un error si la compensación del empleado está fuera de los puntos de referencia mínimo y máximo para el nivel y ajustará automáticamente la compensación del empleado para que esté dentro del intervalo.

10. El campo **Regla de contratación** calcula la compensación de un empleado durante un evento de proceso. Una **Regla de contratación** de **Porcentaje** calculará un aumento que esté prorrateado para la duración de tiempo que el trabajador ha estado contratado en el ciclo.

11. En el campo **Divisa**, escriba un valor.

12. En el campo **Conversión de índice salarial**, especifique o seleccione un valor.

13. Expanda la sección **Matriz del intervalo de aprovechamiento**. Opcionalmente, agregue los registros del intervalo de aprovechamiento para hacer más rápidos a los empleados que están en el punto medio y ralentizarlos para que no lleguen al máximo de su intervalo.

14. Seleccione **Guardar**. Esto activa el botón **Configurar compensación** y continúa definiendo su estructura de compensación para el plan.

15. Seleccione **Configurar compensación**. Puede crear una estructura de compensación usando uno de estos tres métodos:

    - Para crear una estructura totalmente nueva, seleccione un conjunto de puntos de referencia y agregue niveles para crear su propia estructura.
    - Copiar una estructura de compensación de un plan existente como punto de partida y modificarla para el nuevo plan.
    - Seleccionar una cuadrícula de compensación existente. Si otro plan ya usa la cuadrícula de compensación, el otro plan también releja cualquier cambio que haga a la cuadrícula.

16. Seleccione **Crear nueva a partir de la matriz de compensación existente**.

17. En el campo **Copiar cuadrícula**, especifique o seleccione un valor. Puede cambiar opcionalmente el nombre de la nueva cuadrícula de compensación que creará como una copia de la cuadrícula seleccionada.

18. Seleccione **Aceptar**.

19. Seleccione **Cambio masivo**. **Cambio masivo** le permite mantener las cantidades de la matriz de compensación aplicando un aumento de porcentaje o fijo a uno o varios niveles o puntos de referencia.

20. En el campo **Importe del ajuste**, escriba un número.

21. En la lista, active o desactive todas las filas.

22. Haga clic en **Aplicar a la cuadrícula**.

23. Cierre la página. Una vez que ha creado una estructura de compensación, puede seleccionar qué puntos de referencia deben utilizarse como punto de control para el plan de compensación fija. El punto de control se usa para calcular el ratio de comparación de un empleado.

24. En el campo **Punto de control**, especifique o seleccione un valor.

25. Cierre la página.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Crear una regla de elegibilidad para el plan de compensación fija

El nuevo plan de compensación fija no se puede asignar a un empleado hasta que se hayan definido las reglas de idoneidad para el plan.  

1. Seleccione **Reglas de idoneidad**.

2. Seleccione **Nuevo**.

3. En el campo **Elegibilidad**, especifique o seleccione un valor.

4. En el campo **Descripción**, especifique un valor.

5. En el campo **Fecha de vigencia**, especifique una fecha. Las reglas de idoneidad se utilizan para los planes de compensación fijos y variables. En el campo **Tipo**, seleccione el tipo de plan.

6. En el campo **Plan**, especifique o seleccione un valor. Seleccione los criterios que un empleado debe cumplir para ser idóneo para el plan de compensación. Los criterios pueden incluir:

    - **Departamento**
    - **Sindicato**
    - **Ubicación** (**Región de compensación**)
    - **Trabajo**
    - **Función**
    - **Tipo de trabajo**
    - **Nivel de compensación**
    
    El empleado debe cumplir todos los criterios especificados para ser idóneo para el plan de compensación. Si no especifica ningún criterio, todos los empleados son idóneos para el plan de compensación. Si un empleado no cumple los criterios especificados en la regla de idoneidad o una regla de idoneidad no se ha especificado para un plan de compensación, el plan de compensación no aparecerá en las búsquedas cuando cree un registro de compensación fija para un empleado.

7. Cierre la página.

8. Cierre la página.



[!INCLUDE[footer-include](../includes/footer-banner.md)]