--- 
title: "Crear y asignar una directiva de distribución de costes a una unidad de control de costes"
description: "Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo."
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 492e4a94ec0caef8c51a691043a1ffb9e6a04758
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Crear y asignar una directiva de distribución de costes a una unidad de control de costes

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


