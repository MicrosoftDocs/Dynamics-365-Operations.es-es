--- 
title: Calcular una L. MAT. mediante una estructura multinivel (solo febrero de 2016)
description: "Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión multinivel basada en la hoja de Gestión de costes."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 1ad38f67bba299bbd581aba6010b4028c91fbf3a
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a>Calcular una L. MAT. mediante una estructura multinivel (solo febrero de 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión multinivel basada en la hoja de Gestión de costes. Es la séptima tarea en las series de cálculo BOM. La empresa de datos de prueba utilizada para crear esta tarea es USMF.

1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione el producto BOM_1  
3. En el panel de acciones, haga clic en Gestionar costes.
4. Haga clic en Precio de artículo.
5. Haga clic en Calcular coste del artículo.
    * Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.  
6. En el campo Versión de la gestión de costes, especifique o seleccione un valor.
    * Seleccione la versión de Gestión de costes 20, dado que el tipo de Coste planificado y el Modo de expansión es Multinivel.   El modo de expansión Multinivel es para los costes planificados y las simulaciones. No se usa para los costes estándar.  
7. Haga clic en Aceptar
8. Haga clic en Ver detalles de cálculo.
    * Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.  En este caso, observe cómo se ha calculado BOM_2 teniendo en cuenta en cuenta la materia prima, el proceso y los costes generales con un total de 29,40 en lugar del coste estándar de 10, que se ha activado en la Guía de tareas inicial en esta serie.  
9. Haga clic en la pestaña de la hoja Gestión de costes.
    * Pasando a la pestaña de la hoja Gestión de costes, los totales por grupo de costes son diferentes en relación con el cálculo hecho en la guía de tareas anterior.  
10. En el campo Nivel, seleccione "Multi".
    * Al seleccionar Múltiple, los costes se clasifican según la composición de BOM_2, donde 10 se deriva del grupo de costes M1 (ITEM_C), y 15,60 se deriva de la fabricación donde L2 es el grupo de costes. Los costes indirectos también varían.  
11. Cierre la página.
12. Cierre la página.


