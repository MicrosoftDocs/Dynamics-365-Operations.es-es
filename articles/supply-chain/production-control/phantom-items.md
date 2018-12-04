---
title: "Artículos fantasma"
description: "Este tema describe, en detalle, cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula en Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: shylaw
ms.search.validfrom: 
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: a92dd82f309867586f047e0dfc36e452a44a0f9c
ms.contentlocale: es-es
ms.lasthandoff: 10/01/2018

---

# <a name="phantom-items"></a>Artículos fantasma

[!include [banner](../includes/banner.md)]

Este tema describe, en detalle, cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula. En la siguiente ilustración, (a) es el L.MAT para el producto H y las parte F y G y (b) es la hoja de ruta de los productos H y la parte F.

![Producto H y parte F](media/product-H-part-F.png)


Esta ilustración muestra un ejemplo de una estructura de L. MAT en dos niveles. El producto terminado H representa un producto para un ensamblado de equipo. El ensamblado de equipo consta de dos partes, una unidad de iluminación (F) con dos materiales (A y B) y un grupo de materiales de embalaje (G) que también tiene dos materiales (C y D). Otro material (E) se usa durante el montaje general del equipo.

![Producto H y parte F](media/product-H-part-B.png)

La ilustración anterior representa el L. MAT de ingeniería del producto H. Esta estructura proporciona una buena visión general de las piezas y los componentes de montaje total del equipo. Sin embargo, aunque los diseñadores del producto puedan preferir ver la L. MAT representada de esta manera, esta estructura puede que no represente correctamente la forma en que el equipo se construye en planta. 

Por ejemplo, la L. MAT de la ilustración anterior indica que la unidad eléctrica F se monta como una parte independiente en un pedido de trabajo individual. Sin embargo, en planta, es posible que se juzgue que es mejor montar la unidad eléctrica como parte del ensamblado total del equipo, no como un pedido de trabajo individual.

Esta L. MAT de ingeniería también indica que la pieza G es una parte independiente. Sin embargo, en esta estructura, la parte G no representa una parte física sino una colección de materiales de embalaje. 

Por lo tanto, aunque la L. MAT de ingeniería proporciona un gran valor al diseño de un producto y al mantenimiento de dicho diseño, es posible que no sea la forma más lógica de dar soporte al proceso de ejecución de fabricación del producto. Por el contrario, una L. MAT de fabricación representa el mejor modo de crear un producto.

La ilustración siguiente muestra cómo la L. MAT de ingeniería anterior pasa a ser una L. MAT de fabricación. En este ejemplo, (a) es la L. MAT del producto H, y b es la hoja de ruta del producto H.

En esta estructura, puede ver que no hay noción de las piezas F y G y que los materiales de estas piezas se han elevado al siguiente nivel de L. MAT. 

A diferencia de la lista de materiales de ingeniería, que tenía dos hojas de operaciones, la L. MAT de fabricación solo tiene una hoja de operaciones. La operación de embalaja que estaba vinculada a la parte G también se ha elevado y ahora es parte de la hoja de operaciones del producto H. El ensamblado de la unidad de iluminación es la primera operación. Este pedido tiene sentido, porque esta unidad se usa en la siguiente operación, que es el ensamblado de equipo. La última operación es la operación de embalaje, que consume dos materiales de embalaje (C y D).

En Microsoft Dynamics 365 for Finance and Operations, la transición entre la L.MAT de ingenier'ia y la L. MAT de fabricación se habilita a través del tipo de línea de L. MAT fantasma. Como el mismo término “fantasma” indica, las partes F G y han desaparecido durante la transición entre los dos tipos de L. MAT. En este ejemplo, se aplica el tipo de línea fantasma a las L. MAT de las piezas F y G de la L. MAT de ingeniería. Cuando se crea una producción o un pedido de lote, la L. MAT de ingeniería se copia en el pedido de producción o de lote. Posteriormente, cuando se estima el pedido, la transición de la lista de materiales de ingeniería a la L MAT de fabricación se produce, tal como se muestra en las ilustraciones precedentes. En la hoja de operaciones de la segunda ilustración, los materiales de embalaje C y D se introducen para la operación. 

## <a name="multilevel-phantom-bom-structures"></a>Estructuras L. MAT fantasma de varios niveles
El tipo de línea fantasma puede usarse en estructuras de varios niveles de L MAT, como se muestra en la siguiente ilustración. En este ejemplo, (a) es la L. MAT del producto G y (b) es la hoja de ruta de las piezas E y F y el producto G. 

![Producto G y parte F con hojas de ruta](media/product-G-route-sheet-G.png)


La ilustración siguiente muestra la L. MAT de fabricación resultante y la hoja de ruta si las líneas de L. MAT de las partes E y F se configuran de modo que el tipo de línea sea fantasma. En este ejemplo, (a) es la L. MAT del producto G y (b) es la hoja de ruta del producto G.

![Producto G](media/product-G.png)


## <a name="phantom-and-route-network"></a>Fantasma y red de rutas
Los L. MAT fantasma también se pueden usar para una L. MAT con una red de rutas. En una red de rutas, una o más operaciones se ejecutan en paralelo. La ilustración siguiente muestra un ejemplo de una red de rutas que se usa en una L. MAT multinivel. En este ejemplo, (a) es la L. MAT del producto G y la parte F y (b) es la hoja de ruta del producto G y la parte F, que tiene una red de rutas.

![Producto G y parte F](media/product-G-part-F.png)


En la siguiente ilustración, (a) es el la L.MAT del producto G y la parte F y (b) es la hoja de ruta del producto G y la parte F.

![Producto G y parte F con hojas de ruta](media/product-G-part-F-with-route-sheet.png)

