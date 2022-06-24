---
title: Artículos fantasma
description: Este artículo describe cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula en Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 05/05/2022
ms.topic: article
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-05-05
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 64139873216decd8ecb2fcaf1f284e726c53c332
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893334"
---
# <a name="phantom-items"></a>Artículos fantasma

[!include [banner](../includes/banner.md)]

Este artículo describe, en detalle, cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula.

En la figura 1, (a) es el L.MAT para el producto H y las parte F y G y (b) es la hoja de ruta de los productos H y la parte F.

![Figura 1: Lista de materiales de ingeniería.](media/product-H-part-F.png)
*Figura 1: Lista de materiales de ingeniería*

La Figura 1 muestra un ejemplo de una estructura de L. MAT en dos niveles. El producto terminado H representa un producto para un ensamblado de equipo. El ensamblado de equipo consta de dos partes, una unidad de iluminación (F) con dos materiales (A y B) y un grupo de materiales de embalaje (G) que también tiene dos materiales (C y D). Otro material (E) se usa durante el montaje general del equipo.

La Figura 1 representa el L. MAT de ingeniería del producto H. Esta estructura proporciona una buena visión general de las piezas y los componentes de montaje total del equipo. Sin embargo, aunque los diseñadores del producto puedan preferir ver la L. MAT representada de esta manera, esta estructura puede que no represente correctamente la forma en que el equipo se construye en planta.

Por ejemplo, la L. MAT de ingeniería de la figura 1 indica que la unidad eléctrica F se monta como una parte independiente en un pedido de trabajo individual. Sin embargo, en planta, es posible que se juzgue que es mejor montar la unidad eléctrica como parte del ensamblado total del equipo, no como un pedido de trabajo individual.

Esta L. MAT de ingeniería también indica que la pieza G es una parte independiente. Sin embargo, en esta estructura, la parte G no representa una parte física sino una colección de materiales de embalaje.

Por lo tanto, aunque la L. MAT de ingeniería proporciona un gran valor al diseño de un producto y al mantenimiento de dicho diseño, es posible que no sea la forma más lógica de dar soporte al proceso de ejecución de fabricación del producto. Por el contrario, una L. MAT de fabricación representa el mejor modo de crear un producto.

La Figura 2 muestra cómo la L. MAT de ingeniería anterior pasa a ser una L. MAT de fabricación. En la figura 2, (a) es la L. MAT del producto H, y b es la hoja de ruta del producto H.

![Figura 2: Lista de materiales de fabricación.](media/product-H-part-B.png)
*Figura 2: Lista de materiales de fabricación*

En esta estructura, puede ver que no hay noción de las piezas F y G y que los materiales de estas piezas se han elevado al siguiente nivel de L. MAT.

A diferencia de la lista de materiales de ingeniería, que tenía dos hojas de operaciones, la L. MAT de fabricación solo tiene una hoja de operaciones. La operación de embalaja que estaba vinculada a la parte G también se ha elevado y ahora es parte de la hoja de operaciones del producto H. El ensamblado de la unidad de iluminación es la primera operación. Este pedido tiene sentido, porque esta unidad se usa en la siguiente operación, que es el ensamblado de equipo. La última operación es la operación de embalaje, que consume dos materiales de embalaje (C y D).

La transición entre el MAT de ingeniería y el MAT de fabricación se habilita a través del tipo de línea de L. MAT fantasma. Como el mismo término “fantasma” indica, las partes F G y han desaparecido durante la transición entre los dos tipos de L. MAT. En este ejemplo, se aplica el tipo de línea fantasma a las L. MAT de las piezas F y G de la L. MAT de ingeniería. Cuando se crea una producción o un pedido de lote, la L. MAT de ingeniería se copia en el pedido de producción o de lote. Posteriormente, cuando se estima el pedido, la transición de la lista de materiales de ingeniería a la L MAT de fabricación se produce, tal como se muestra en la figura 2. En la hoja de operaciones de la figura 2, los materiales de embalaje C y D se introducen para la operación.

## <a name="multilevel-phantom-bom-structures"></a>Estructuras L. MAT fantasma de varios niveles

El tipo de línea fantasma puede usarse en estructuras de varios niveles de L MAT, como se muestra en la figura 3. En la figura 3, (a) es la L. MAT del producto G y (b) es la hoja de ruta de las piezas E y F y el producto G.

![Figura 3: Lista de materiales de ingeniería parte G.](media/product-G.png)
*Figura 3: Lista de materiales de ingeniería parte G*

La Figura 4 muestra la L. MAT de fabricación resultante y la hoja de ruta si las líneas de L. MAT de las partes E y F se configuran de modo que el tipo de línea sea fantasma. En la figura 4, (a) es la L. MAT para el producto G, y (b) es la hoja de ruta para el producto G.

![Figura 4: Lista de materiales de fabricación parte G.](media/product-G-route-sheet-G.png)
*Figura 4: Lista de materiales de fabricación parte G*

## <a name="phantom-and-route-network"></a>Fantasma y red de rutas

Los L. MAT fantasma también se pueden usar para una L. MAT con una red de rutas. En una red de rutas, una o más operaciones se ejecutan en paralelo. La figura 5 muestra un ejemplo de una red de rutas que se usa en una L. MAT multinivel. En la figura 5, (a) es la L. MAT del producto G y la parte F y (b) es la hoja de ruta del producto G y la parte F, que tiene una red de rutas.

![Figura 5: Lista de materiales de ingeniería parte G, red de rutas.](media/product-G-part-F.png)
*Figura 5: Lista de materiales de ingeniería parte G, red de rutas*

En la figura 6, (a) es la L. MAT para le producto G y la parte F, y (b) es la hoja de ruta para el producto G y la parte F.

![Figura 6: Lista de materiales de ingeniería parte G, red de rutas.](media/product-G-part-F-with-route-sheet.png)
*Figura 6: Lista de materiales de ingeniería parte G, red de rutas*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]