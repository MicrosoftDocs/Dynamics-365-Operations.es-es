--- 
title: Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes
description: "El comportamiento del coste es la clasificación de los costes como fijos o variables."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 392cb83ceb8612a2e73cc54bb2d8d40c62a6b7b6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

El comportamiento del coste es la clasificación de los costes como fijos o variables. Una directiva y las reglas correspondientes tienen que asignarse a una unidad de control de costes para que la directiva entre en vigor. Use este procedimiento para crear una directiva y después asignar la directiva a una unidad de control de costes.


## <a name="create-a-cost-behavior-hierarchy"></a>Crear una jerarquía de comportamiento de costes
1. Vaya a Contabilidad de costes > Dimensiones > Jerarquías de dimensiones.
2. Haga clic en Nuevo.
3. Haga clic en Crear.
4. En el campo Nombre de la jerarquía de dimensiones, escriba “Jerarquía de comportamiento de costes”.
5. En el campo Dimensión, especifique o seleccione un valor.
    * Seleccionar elementos de coste.  
6. Haga clic en Guardar.
7. Haga clic en Ver jerarquía.
8. Haga clic en Nuevo.
9. En el campo Nombre de nodo, escriba un valor.
    * Especifique el coste fijo  
10. En el árbol, seleccione "Jerarquía de comportamiento de costes”.
11. Haga clic en Nuevo.
12. En el campo Nombre de nodo, escriba un valor.
    * Especifique el coste variable.  
13. Haga clic en Guardar.
14. En el árbol, seleccione "Jerarquía de comportamiento de costes\Coste fijo”.
15. Haga clic en Nuevo.
16. En la lista, marque la fila seleccionada.
17. En el campo Desde miembro de dimensión, especifique o seleccione un valor.
    * El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.  
18. En el campo Hasta miembro de dimensión, especifique o seleccione un valor.
    * El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.  
19. En el árbol, seleccione "Jerarquía de comportamiento de costes\Coste variable”.
20. Haga clic en Nuevo.
21. En la lista, marque la fila seleccionada.
22. En el campo Desde miembro de dimensión, especifique o seleccione un valor.
    * El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.  
23. En el campo Hasta miembro de dimensión, especifique o seleccione un valor.
    * El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.  
24. Haga clic en Guardar.

## <a name="create-the-policy-and-rules"></a>Cree la directiva y las reglas
1. Vaya a Contabilidad de costes > Directivas > Directivas de comportamiento de costes.
2. Haga clic en Nuevo.
3. En el campo Nombre de directiva, escriba un valor.
4. En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccione la jerarquía de directivas que acaba de crear.  
5. En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione Organización.  
6. Haga clic en Guardar.
7. Haga clic en Nuevo.
8. En la lista, marque la fila seleccionada.
9. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Expanda la jerarquía para seleccionar Coste variable.  
10. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * De forma predeterminada, el porcentaje variable es del 100 por ciento.  
11. Haga clic en Asignaciones de directiva de unidad de control de costes.
12. Haga clic en Nuevo.
13. En la lista, marque la fila seleccionada.
14. En el campo Válido desde fecha contable, especifique una fecha.
    * Las reglas entran en vigor en una fecha y un usuario o el sistema puede hacer vencer una regla si se crea una versión más nueva.  
15. En el campo Unidad de control de coste, especifique o seleccione un valor.
16. Haga clic en Guardar.


