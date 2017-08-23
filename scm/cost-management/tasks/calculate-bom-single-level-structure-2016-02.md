--- 
title: Calcular una L. MAT. mediante una estructura de un solo nivel (solo febrero de 2016)
description: "Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes."
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 36096c9a0c8dde1028728ec257dfa63e7fb669af
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a>Calcular una L. MAT. mediante una estructura de un solo nivel (solo febrero de 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes. Es la sexta tarea en las series de cálculo BOM. La empresa de datos de prueba utilizada para crear esta tarea es USMF.

1. Vaya a Productos emitidos.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione el producto BOM_1  
3. En el panel de acciones, haga clic en Gestionar costes.
4. Haga clic en Precio de artículo.
5. Haga clic en Calcular coste del artículo.
    * Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.  
6. En el campo Versión de la gestión de costes, haga clic en el botón desplegable para abrir la búsqueda.
    * Para esta demostración, seleccione 10. Esta es la misma versión de gestión de costes utilizada para agregar el precio de coste a los componentes.  
7. Haga clic en Aceptar
8. Haga clic en Ver detalles de cálculo.
    * Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.    A continuación se indica la composición del coste:  •    10 se deriva de ITEM_A, 10 de ITEM_B, 10 de BOM_2. En este caso no hay detalles para BOM_2, ya que se ha especificado como coste estándar de 10 pero no mediante el cálculo.  •  7 se deriva del tiempo de configuración, que es un coste constante, y el 7 adicional se deriva de la operación de tiempo de ejecución (Proceso).  •   También hay otros importes que corresponden a costes indirectos.  
9. @SysTaskRecorder:_RequestClose


