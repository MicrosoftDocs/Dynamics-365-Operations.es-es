---
title: Crear y asignar una directiva de distribución de costes a una unidad de control de costes
description: Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
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
ms.openlocfilehash: 1d040f9495c7fb36985b5f96c15ac43aa226da24
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841330"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Crear y asignar una directiva de distribución de costes a una unidad de control de costes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo. El contable de costes se asegura de que el coste se distribuye en los centros de coste, en función de la base de asignación seleccionada. Una directiva y las reglas correspondientes se asignan a una unidad de control de costes. Esta guía de tareas utiliza un ejemplo para mostrar cómo crear una directiva de distribución de costes y las reglas correspondientes.


## <a name="create-a-policy"></a>Crear una directiva
1. Vaya a Contabilidad de costes > Directivas > Directivas de distribución de costes.
2. Haga clic en Nuevo.
3. En el campo Nombre de directiva, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione Organización.  
6. En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccione P/G de CDS.  
7. En el campo Dimensión estadística, especifique o seleccione un valor.
    * Seleccione elementos estadísticos.  
8. Haga clic en Guardar.

## <a name="create-rules-for-the-policy"></a>Cree reglas para la directiva
1. Haga clic en Nuevo.
2. En la lista, marque la fila seleccionada.
3. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Expanda la jerarquía para seleccionar 094.  
4. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccione Otros gastos de explotación y Limpieza de 605110.  
5. En el campo Comportamiento de costes, seleccione una opción.
    * Seleccione Coste fijo.  
6. En el campo Base de asignación, especifique o seleccione un valor.
7. Haga clic en Nuevo.
8. En la lista, marque la fila seleccionada.
9. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Expanda la jerarquía para seleccionar 094.  
10. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccione Otros gastos de explotación y Alquiler de 605150.  
11. En el campo Comportamiento de costes, seleccione una opción.
    * Seleccione Coste fijo.  
12. En el campo Base de asignación, especifique o seleccione un valor.
13. Haga clic en Guardar.

## <a name="assign-rules-to-a-cost-control-unit"></a>Asignar reglas a una unidad de control de costes
1. Haga clic en Asignaciones de directiva de unidad de control de costes.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Válido desde fecha contable, especifique una fecha.
    * Seleccione 1 de septiembre en el ejercicio válido.  
5. En el campo Unidad de control de coste, especifique o seleccione un valor.
6. Haga clic en Guardar.

