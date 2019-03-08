---
title: Inscribir a un empleado en un plan de compensación fija
description: El director de compensaciones y prestaciones puede asignar a los empleados planes de compensación fija para gestionar su sueldo base.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c9c11292feec06a53cd4426a25bfb2aaac7de3e8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "353342"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>Inscribir a un empleado en un plan de compensación fija

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

