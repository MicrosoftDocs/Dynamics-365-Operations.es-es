---
title: Creación de entradas de un presupuesto original y luego de un presupuesto inverso para el sector público
description: Este tema proporciona información sobre cómo crear y revertir una entrada de presupuesto original utilizando el modelo de presupuesto y los valores de dimensión que tienen importes de presupuesto preliminares.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 134e2ca851d72965198026107817c66a808ac705
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987963"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>Creación de entradas de un presupuesto original y luego de un presupuesto inverso para el sector público

[!include [banner](../../includes/banner.md)]

Cuando crea una entrada de presupuesto original y usa el modelo presupuestario y los valores de dimensión que contienen importes presupuestarios preliminares, se pueden invertir los importes presupuestarios preliminares. Este procedimiento se ha creado con los datos de empresa de demostración PSUS en la partición del sector público.

1. Vaya a Gestión presupuestaria > Entradas de registro presupuestario.
2. Haga clic en Nuevo.
3. En el campo Modelo presupuestario, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En el campo Código presupuestario, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en Presupuesto original.
7. Haga clic en Guardar.
8. Haga clic en Agregar línea.
9. Opcional: Si desea cambiar la fecha de la que se encuentra en el encabezado, especifique una fecha nueva. Esta fecha determina el período fiscal en el que registrará el presupuesto.
10. En el campo Estructura contable, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque y seleccione el registro deseado.
12. En el campo Valores de dimensión, especifique los valores deseados.
13. En el campo Importe, especifique un número.
14. En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. Haga clic en Guardar.
17. Haga clic en Actualizar saldos presupuestarios.
    * Opcional: Puede seleccionar la opción Invertir presupuesto preliminar. Tenga en cuenta que puede invertir todas las entradas de presupuesto preliminares o solo las entradas de presupuesto preliminares que tengan el código de presupuesto que especifique.  
    * Para realizar selecciones opcionales, haga clic en el icono Desbloquear de la parte superior de la página.  
18. Haga clic en Actualizar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]