---
title: Crear artículos de préstamo
description: Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a812887f20a8ae5ae3b677ac452a498230c244a
ms.sourcegitcommit: 1cc56643160bd3ad4e344d8926cd298012f3e024
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731745"
---
# <a name="create-loan-items"></a>Crear artículos de préstamo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Los artículos en préstamo son registros que ayudan a realizar un seguimiento de los artículos físicos que su empresa presta a los trabajadores, como teléfonos u ordenadores. Cada artículo físico debe tener un artículo correspondiente de préstamo. Cada registro de los artículos de préstamo debe describir lo que se está prestando, la persona responsable del préstamo y el número de días que se puede prestar el artículo. Puede crear varios artículos en préstamo al mismo tiempo, como llaves, tarjetas de acceso o uniformes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-loan-types"></a>Creación de tipos de préstamo
1. Vaya a **Recursos humanos** > **Trabajadores** > **Artículos de préstamo** > **Tipos de préstamo**.
2. Haga clic en **Nuevo**.
3. En el campo **Tipo de préstamos**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Especifique el número de días en los que se pueden devolver los artículos asignados a este tipo de préstamo una vez vencida la fecha de devolución. 
6. Haga clic en **Guardar**.
7. Cierre la página.
8. Actualice la página.

## <a name="create-loan-items"></a>Creación de artículos de préstamo
1. Vaya a **Recursos humanos** > **Trabajadores** > **Artículos de préstamo** > **Artículos de préstamo**.
2. Haga clic en **Crear artículos de préstamo**.
3. En el campo **Cant.**, especifique un número.
4. En el campo **Descripción**, escriba un valor.
5. En el campo **Tipo de préstamo**, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Escribir el número de días en el que el artículo puede estar en préstamo.
    * El valor predeterminado del campo Devolución planificada en la página Equipo prestado se calcula como la fecha en curso más este número.  
9. En el campo **Persona a cargo**, haga clic en el botón desplegable para abrir la búsqueda.
10. Haga clic en **Seleccionar**.
11. En el campo **Valor inicial**, escriba un número.
12. Escriba un número en el campo **Intervalo**.
13. En el campo **Formato**, escriba un valor.
    * Por ejemplo, si el número de inicio para un artículo en préstamo es 10, especifique dos símbolos de almohadilla en el campo **Formato**.  
14. Haga clic en **Aceptar**.
15. Actualice la página.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
