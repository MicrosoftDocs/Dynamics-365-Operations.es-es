---
title: Agregar una directiva de cálculo de cantidad kanban a una regla kanban
description: Este procedimiento se centra en la creación de una directiva de cálculo de cantidad kanban y su adición a una regla kanban para optimizar el tamaño y las cantidades kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 039c4aaa355cf2b850ded06913e8e39ee8cac543
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436586"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Agregar una directiva de cálculo de cantidad kanban a una regla kanban

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la creación de una directiva de cálculo de cantidad kanban y su adición a una regla kanban para optimizar el tamaño y las cantidades kanban. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento va destinado al administrador del flujo de valor. Este procedimiento es requisito previo para crear el procedimiento Calcular sugerencias de cantidades kanban. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Creación de una directiva de cálculo de cantidad kanban
1. Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Directivas de cálculo de cantidad kanban.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
    * Por ejemplo, escriba Speaker2016.  
4. En el campo Plan maestro, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
    * Seleccione StaticPlan para calcular la demanda.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en Guardar.
8. En el campo Cantidad kanban mínima, especifique "1".
    * Este es el número de kanbans adicionales que se incluyen en el cálculo de la cantidad kanban.  
9. Defina Factor de seguridad en "1".
    * Este es el factor que se usa para calcular la cantidad adicional de existencias de seguridad.  
10. En el campo Días por delante, especifique "30".
    * Este es el número de días anteriores a la fecha de cálculo de la cantidad kanban que se incluye en el cálculo de la demanda.  
11. En el campo Días por detrás, especifique "30".
    * Este es el número de días posteriores a la fecha de cálculo de la cantidad kanban que se incluye en el cálculo de la demanda.  La fórmula usada para el cálculo muestra los valores reales. Por ejemplo, Cantidad kanban = ((Demanda diaria promedio x plazo x 2.00) / Cantidad de producto por unidad de gestión de material) + 1  
12. Cierre la página.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Adición de una directiva de cálculo de cantidad kanban a una regla kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione la regla kanban 000020 para este procedimiento.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Expanda la sección Directivas de cálculo de cantidad kanban.
5. Haga clic en Agregar.
    * Agregue la directiva de cálculo de cantidad kanban que acaba de crear en la subtarea anterior.  
6. En la lista, marque la fila seleccionada.
7. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la directiva Speaker2016 que acaba de crear en la subtarea anterior.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]