--- 
title: "Crear una directiva de acumulación de costes"
description: "Este procedimiento muestra cómo crear una directiva de acumulación de costes y crea reglas para la directiva."
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
ms.openlocfilehash: 42656cbf445fd3f79844884d7d35243c5b051a4a
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-cost-rollup-policy"></a>Crear una directiva de acumulación de costes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear una directiva de acumulación de costes y crea reglas para la directiva. Los datos de demostración utilizados para crear este procedimiento son los de la empresa USP2.


## <a name="create-a-policy"></a>Crear una directiva
1. Vaya a Contabilidad de costes > Directivas > Directivas de acumulación de costes.
2. Haga clic en Nuevo.
3. En el campo Nombre de directiva, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccionar Tarjeta de crédito para acumulación de costes  
6. En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccionar Tarjeta de crédito para acumulación de costes  
7. Haga clic en Guardar.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Crear reglas para la directiva de acumulación de costes
1. Haga clic en Nuevo.
2. En la lista, marque la fila seleccionada.
3. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione 007.  
4. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccionar BE para acumulación de costes.  
5. En el campo Elemento de coste secundario, especifique o seleccione un valor.
    * Para este ejemplo, asigne el elemento de coste secundario CC-007 el centro de coste.  
6. Haga clic en Nuevo.
7. En la lista, marque la fila seleccionada.
8. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione 008.  
9. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccionar BE para acumulación de costes.  
10. En el campo Elemento de coste secundario, especifique o seleccione un valor.
    * Para este ejemplo, asigne el elemento de coste secundario CC-008 el centro de coste.  
11. Haga clic en Nuevo.
12. En la lista, marque la fila seleccionada.
13. En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.
    * Seleccione 009.  
14. En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.
    * Seleccionar BE para acumulación de costes.  
15. En el campo Elemento de coste secundario, especifique o seleccione un valor.
    * Para este ejemplo, asigne el elemento de coste secundario CC-009 el centro de coste.  
    * Continúe hasta que todos los centros de coste se hayan asignado a los elementos de coste secundarios correspondientes.  
16. Haga clic en Guardar.


