---
title: Crear y asignar una directiva de asignación de costes a una unidad de control de costes
description: Use este procedimiento para crear y asignar una directiva de asignación de costes y las reglas correspondientes a una unidad de control de costes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a4ba39b5dbba20a58066054da2e24613381cfaa
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144453"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Crear y asignar una directiva de asignación de costes a una unidad de control de costes

[!include [banner](../../includes/banner.md)]

Use este procedimiento para crear y asignar una directiva de asignación de costes y las reglas correspondientes a una unidad de control de costes. Este registro usa la empresa USP2 con los datos para demostración.


## <a name="create-a-policy"></a>Crear una directiva
1. Vaya a Contabilidad de costes > Directivas > Directivas de asignación de costes.
2. Haga clic en Nuevo.
3. En el campo Nombre de directiva, escriba un valor.
4. En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione Organización.  
5. En el campo Dimensión estadística, especifique o seleccione un valor.
6. Haga clic en Guardar.

## <a name="create-allocation-rules"></a>Crear reglas de asignación
1. Haga clic en Nuevo.
2. En la lista, marque la fila seleccionada.
3. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
4. En el campo Comportamiento e costes, seleccione "Total".
5. En el campo Base de asignación, especifique o seleccione un valor.
6. Haga clic en Nuevo.
7. En la lista, marque la fila seleccionada.
8. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
9. En el campo Comportamiento e costes, seleccione "Total".
10. En el campo Base de asignación, especifique o seleccione un valor.
11. Haga clic en Nuevo.
12. En la lista, marque la fila seleccionada.
13. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
14. En el campo Comportamiento e costes, seleccione "Total".
15. En el campo Base de asignación, especifique o seleccione un valor.
    * Continúe hasta haber creado todas las reglas.  
16. Haga clic en Guardar.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Asignar la directiva de una unidad de control de costes
1. Haga clic en Asignaciones de directiva de unidad de control de costes.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Válido desde fecha contable, especifique una fecha.
    * Las reglas entran en vigor en una fecha. Un usuario o el sistema pueden hacer vencer las reglas si se crear una versión más nueva.  
5. En el campo Unidad de control de coste, especifique o seleccione un valor.
6. Haga clic en Guardar.

