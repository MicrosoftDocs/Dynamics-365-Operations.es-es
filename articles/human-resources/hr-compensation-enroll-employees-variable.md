---
title: Inscribir a un empleado en un plan de compensación variable
description: El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11f86bfa4bfcece164755bb5d86944e0bed0fff2
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692293"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Inscribir a un empleado en un plan de compensación variable


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

El director de compensaciones y de prestaciones puede inscribir a empleados en los planes de compensación variable para calcular las primas en efectivo y no efectivo para los empleados. Este procedimiento supone que se ha creado un plan de compensación variable con el campo **Habilitar inscripción** definido en **Sí**, y que se han creado reglas de idoneidad para dicho plan de compensación variable. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Para iniciar este procedimiento, vaya a **Recursos humanos** > **Trabajadores** > **Empleados** > **Compensación** > **Inscripción de plan variable**.

1. Haga clic en **Nuevo**.
2. En el campo **Plan**, haga clic en el botón desplegable para abrir la búsqueda.
    * La búsqueda del plan se filtrará para mostrar únicamente los planes de compensación variable aptos para el empleado según las reglas de idoneidad.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Expanda la sección **General**.
5. En el campo **Fecha de vigencia**, especifique una fecha.
6. Haga clic en **Guardar**.
7. Expanda la sección **Anulaciones**.
    * Existe la opción de definir la fecha de regla de contratación para sobrescribir la fecha de contratación de un empleado cuando la regla de contratación especificada para el plan variable seleccionado es Porcentaje.  
    * Si el plan variable es un porcentaje del plan base, se puede sobrescribir el porcentaje de la prima para el empleado. Si el plan de compensación variable es un plan de número de unidades, se puede sobrescribir el número de unidades para el empleado.  
    * Si el empleado debe recibir un importe fijo como prima, el importe se puede establecer aquí.  
8. Expanda la sección **Anulación de unidades organizativas**.
    * Si se debe tener en cuenta el rendimiento del empleado, el rendimiento de distintos departamentos o un departamento distinto al asignado al puesto del empleado, el departamento se puede sobrescribir. La columna **Porcentaje** debe sumar 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
