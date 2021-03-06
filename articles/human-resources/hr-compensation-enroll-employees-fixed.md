---
title: Inscribir a un empleado en un plan de compensación fija
description: El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5f0862c86234495c89b2a6ad947cc78e687de37
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054245"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscribir a un empleado en un plan de compensación fija

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base. Este procedimiento supone que se ha creado un plan fijo y que está activo, así como que se han configurado reglas de idoneidad para el plan. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Para iniciar el procedimiento, vaya a Recursos humanos > Trabajadores > Empleados > Compensación > Plan fijo

1. Haga clic en Nuevo.
2. En el campo Acción, seleccione un tipo de acción de compensación fija Contratar/Volver a contratar para describir el cambio en la compensación del empleado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo Puesto, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El nivel que se muestra proviene del nivel de compensación del trabajo en el puesto. El nivel se debe establecer en el trabajo para poder asignar una compensación al empleado.  
6. En el campo Plan, seleccione el plan de compensación fija para el empleado. La búsqueda del plan se filtra para mostrar únicamente los planes aptos para el empleado según las reglas de idoneidad.
7. En la lista, busque y seleccione el registro deseado.
    * Las fechas de vigencia y vencimiento para la compensación es establecen de forma predeterminada a partir de las fechas de inicio y fin de la asignación del puesto del trabajador. Puede ajustar estas fechas de acuerdo con sus necesidades.  
    * Si el plan de compensación fija es un plan por pasos, seleccione el paso que contiene el índice salarial correcto para el empleado. Si el plan de compensación fija es un plan por categorías o grupos, indique el índice salarial correcto para el empleado. El índice salarial se valida en relación con los ajustes de tolerancia para el plan, y los puntos de referencia mínimos y máximos para el nivel de compensación del trabajo.  
8. Haga clic en Aceptar



[!INCLUDE[footer-include](../includes/footer-banner.md)]