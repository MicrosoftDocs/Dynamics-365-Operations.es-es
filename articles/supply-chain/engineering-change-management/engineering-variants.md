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
ms.openlocfilehash: 4e2133263f4bee09a3365236601e0d2fdd08a7ae
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471845"
---
# <a name="generate-variants-for-engineering-products"></a>Generar variantes de productos de ingeniería

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Este tema describe cómo generar variantes para productos de ingeniería.

## <a name="turn-on-variant-generation-for-engineering-products"></a>Activar la generación de variantes de productos de ingeniería

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo**: *Administración de cambios de ingeniería*
- **Nombre de característica**: *Generación de variantes de productos de ingeniería*

> [!IMPORTANT]
> La función *Generación de variantes para productos de ingeniería* será visible en su sistema solo después de que habilite la clave de configuración *Gestión de cambios de ingeniería*. Para instrucciones, vea [Resumen de gestión de cambios de ingeniería](product-engineering-overview.md).

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
1. Cierre la página y luego seleccione **Variantes de producto lanzado**. Observe que aparece la primera variante que creó (azul V-1).
1. En el panel de acciones, en la pestaña **Variante de producto**, seleccione **Sugerencias de variantes**.
1. En el cuadro de diálogo **Sugerencias de variantes**, siga uno de estos pasos:

    - En la parte superior del cuadro de diálogo, hay una sección para cada dimensión disponible. Para cada dimensión, seleccione la casilla de verificación para cada valor para el que desea generar una sugerencia de variante y luego seleccione **Sugerir** en la barra de herramientas. Las sugerencias relevantes se agregan a la sección **Variantes sugeridas**.
    - Seleccione **Sugerir todo** en la barra de herramientas para generar sugerencias de variantes para todas las combinaciones disponibles de valores de dimensión. Las sugerencias se agregan a la sección **Variantes sugeridas**.

1. En la sección **Variantes sugeridas**, seleccione la casilla de verificación para cada variante que desee crear. Luego seleccione **Crear** para generar y entregar las variantes seleccionadas a la empresa de ingeniería. Se aplican las siguientes condiciones:

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
