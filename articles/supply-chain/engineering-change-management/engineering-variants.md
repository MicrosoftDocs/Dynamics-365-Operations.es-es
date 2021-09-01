---
title: Generar variantes de productos de ingeniería
description: Este tema describe cómo generar variantes para productos de ingeniería.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 57eda6a833df6ff8e91c006bbc5096554eff6c503a8b7ba2bd0b13e2f8e98f56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766169"
---
# <a name="generate-variants-for-engineering-products"></a>Generar variantes de productos de ingeniería

[!include [banner](../includes/banner.md)]

Este tema describe cómo generar variantes para productos de ingeniería.

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Generar una o más variantes nuevas de un producto de ingeniería

Puede crear una o más variantes nuevas de un producto sin copiar información de un producto existente. Esto es útil cuando necesita crear varias variantes de producto al mismo tiempo.

El siguiente procedimiento proporciona un ejemplo de cómo crear varias variantes que incluyen la dimensión de color.

1. Abre la página **Productos lanzados** (por ejemplo, vaya a **Gestión de cambios de ingeniería\> Común\> Productos lanzados**).
1. En el panel de acciones, abra la pestaña **Producto** y, en el grupo **Nuevo**, seleccione **Producto de ingeniería**.
1. Se abre el cuadro de diálogo **Nuevo producto**. Seleccione la **Categoría de ingeniería** apropiada.
1. Si su categoría de ingeniería seleccionada incluye dimensiones variantes, puede establecer valores para ellas ahora. Para este ejemplo, si la categoría tiene una dimensión de **Color**, puede configurarla en *Azul*.
1. Realice otros ajustes según sea necesario. Seleccione **Aceptar** para crear el producto.
1. Se crean el producto y la variante azul V-1, y ahora se abre el nuevo producto.
1. Agregue una lista de materiales (BOM) y enrute a la variante según sea necesario.
1. En el panel de acciones, abra la pestaña **Producto** y, en el grupo **Producto maestro**, seleccione **Dimensiones de producto**.
1. Se abrirá la página **Dimensiones del producto**. Esta página incluye una pestaña para cada dimensión disponible. En cada pestaña, agregue una fila para cada valor que admitirá para cada dimensión relevante. (Para este ejemplo, puede agregar filas en la ficha **Color** para *Blanco*, *Amarillo* y *Verde*).
1. Cierre la página y seleccione **Variantes de producto lanzado**. Tenga en cuenta que aparece la primera variante creada (V-1 blanco).
1. Seleccione **Sugerencias de variantes**.
1. El sistema sugiere variantes con los valores de color creados (por ejemplo, blanco V-1, amarillo V-1 y verde V-1).
1. Seleccione las variantes sugeridas y seleccione **Aceptar** para entregar las variantes a la empresa de ingeniería. Tenga en cuenta que se aplicarán las condiciones siguientes: 
    - Ninguna de las variantes creadas tendrá una lista de materiales o una ruta.
    - Los atributos para estas variantes serán predeterminados de la categoría de ingeniería y no se copiarán de la variante anterior.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Generar una variante como copia de otra variante de producto

Puede crear una variante de un producto basada en otra variante de producto. La lista de materiales (BOM) y la ruta de la variante del producto de origen se copian en la nueva variante. Esto puede resultar útil para productos de fabricación discreta en los que puede resultar útil crear la lista de materiales basada en una lista de materiales inicial y realizar un seguimiento de los cambios de la variante anterior. Para mantener la trazabilidad, el sistema registra qué variante se copió para crear una nueva copia.

El siguiente procedimiento proporciona un ejemplo de cómo crear una nueva variante que incluye la dimensión de color creando una copia de una variante existente.

1. Abre la página **Productos lanzados** (por ejemplo, vaya a **Gestión de cambios de ingeniería\> Común\> Productos lanzados**).
1. En el panel de acciones, abra la pestaña **Producto** y, en el grupo **Nuevo**, seleccione **Producto de ingeniería**.
1. Se abre el cuadro de diálogo **Nuevo producto**. Seleccione la **Categoría de ingeniería** apropiada.
1. Si su categoría de ingeniería seleccionada incluye dimensiones variantes, puede establecer valores para ellas ahora. Para este ejemplo, si la categoría tiene una dimensión de **Color**, puede configurarla en *Azul*.
1. Realice otros ajustes según sea necesario. Seleccione **Aceptar** para crear el producto.
1. Se crean el producto y la variante azul V-1, y ahora se abre el nuevo producto.
1. Agregue una lista de materiales y enrute a la variante según sea necesario.
1. Agregue atributos a la variante del producto según sea necesario.
1. Agregue la variante de producto azul V-1 a una orden de cambio de ingeniería.
1. Defina **Impacto** como *Nueva variante*.
1. Seleccione el nuevo valor de color (por ejemplo,*Blanco*). Tenga en cuenta que se aplicarán las condiciones siguientes: 
    - La nueva variante tiene una lista de materiales y una ruta que se han copiado de la variante anterior.
    - La nueva variante tiene los atributos copiados de la variante anterior.
1. Apruebe la orden de cambio.
1. Procese la orden de cambio. Una vez procesada la orden, se creará la nueva variante V-1 y se entregará a la empresa de ingeniería.
