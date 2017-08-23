--- 
title: "Inscribir a un empleado en un plan de compensación variable"
description: "El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados."
author: kherr75
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
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c6108b11366f615be12e9a9f79ecf84728ee265f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Inscribir a un empleado en un plan de compensación variable

[!include[task guide banner](../../includes/task-guide-banner.md)]

El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados. Este procedimiento supone que se ha creado un plan de compensación variable con el campo Habilitar inscripción definido en Sí, y que se han creado reglas de idoneidad para dicho plan de compensación variable. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Para iniciar este procedimiento, vaya a Recursos humanos > Trabajadores > Empleados > Compensación > Inscripción de plan variable

1. Haga clic en Nuevo.
2. En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.
    * La búsqueda del plan se filtrará para mostrar únicamente los planes de compensación variable aptos para el empleado según las reglas de idoneidad.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Expanda la sección General.
5. En el campo Fecha de vigencia, especifique una fecha.
6. Haga clic en Guardar.
7. Expanda la sección Anulaciones.
    * Existe la opción de definir la fecha de regla de contratación para sobrescribir la fecha de contratación de un empleado cuando la regla de contratación especificada para el plan variable seleccionado es Porcentaje.  
    * Si el plan variable es un porcentaje del plan base, se puede sobrescribir el porcentaje de la prima para el empleado. Si el plan de compensación variable es un plan de número de unidades, se puede sobrescribir el número de unidades para el empleado.  
    * Si el empleado debe recibir un importe fijo como prima, el importe se puede establecer aquí.  
8. Expanda la sección Anulación de unidades organizativas.
    * Si se debe tener en cuenta el rendimiento del empleado, el rendimiento de distintos departamentos o un departamento distinto al asignado al puesto del empleado, el departamento se puede sobrescribir. La columna Porcentaje debe sumar 100.  

