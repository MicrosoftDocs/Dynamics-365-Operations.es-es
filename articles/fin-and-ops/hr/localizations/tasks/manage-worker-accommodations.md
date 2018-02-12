--- 
title: Administrar ajustes del trabajador
description: "Este procedimiento le muestra los pasos necesarios para configurar tipos de adecuación del entorno de trabajo, como sillas ergonómicas o descansos periódicos."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 10d34d0b2eca95034d1f67931ff72a035be9a6b8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="manage-worker-accommodations"></a>Administrar ajustes del trabajador

[!include[task guide banner](../../../includes/task-guide-banner.md)]

Este procedimiento le muestra los pasos necesarios para configurar tipos de adecuación del entorno de trabajo, como sillas ergonómicas o descansos periódicos. También muestra cómo asignar estos tipos de adecuación a un trabajador y cómo aprobar o denegar el tipo de adecuación. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="setup-accommodations"></a>Configuración de adecuaciones
1. Vaya a Recursos humanos > Configuración > Tipos de adecuaciones.
2. Haga clic en Nuevo.
3. En el campo Tipo de adecuación, especifique un nombre para la adecuación. Ejemplo: Teclado.
4. En el campo Descripción, especifique una descripción para la adecuación. Ejemplo: Teclado ergonómico.
5. En el campo Nota, especifique información que ayude a aclarar la adecuación.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="assign-accommodations"></a>Asignación de adecuaciones
1. Vaya a Recursos humanos > Trabajadores > Empleados.
2. Seleccione un empleado en la lista.
3. Haga clic en el nombre del empleado para ver los detalles del empleado que solicita la adecuación.
4. Expanda la ficha desplegable Información personal.
5. Haga clic en Adecuaciones.
6. Haga clic en Nuevo.
7. En el campo Tipo de adecuación, seleccione la adecuación oportuna. Ejemplo: Teclado
8. En el campo Tarea de trabajo, indique la tarea de trabajo que requiere adecuación.
9. Defina el estado apropiado en el campo Estado. Ejemplo: Razonable
    * Están disponibles los siguientes estados. Solicitado indica que se ha creado la adecuación, pero aún no se ha revisado. Razonable indica que la adecuación es razonable y se concederá. Carga excesiva indica que la adecuación supondrá una carga no razonable para el empleador, y por ello se ha denegado. En este ejemplo, la solicitud se ha aprobado inmediatamente porque la solicitud de adecuación era mínima.  
10. En el campo Aceptado, seleccione la persona que aceptó la solicitud de adecuación.
11. Haga clic en Seleccionar.
12. En el campo de fecha de aceptación, indique la fecha y la hora en que se aceptó la solicitud de adecuación.
13. Expanda la sección Nota.
14. En el campo Financiero, especifique cualquier información o costes de recursos que ayude a aclarar la repercusión de la adecuación.
    * Si se ha denegado la adecuación, el campo Contestación se puede usar para indicar por qué se ha rechazado una solicitud.  
15. Haga clic en Guardar.


