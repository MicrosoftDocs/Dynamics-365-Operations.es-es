---
title: Objetos de coste
description: Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4590a1c1761d72472ec681be0cc3fbd098957d42
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188521"
---
# <a name="cost-objects"></a>Objetos de coste

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.  

## <a name="cost-objects"></a>Objetos de coste

La página **Objetos de coste** muestra todos los objetos de coste que se registran en un producto. Los objetos de coste se definen por datos desde los siguientes orígenes:

-   Producto
-   Grupo de dimensiones de producto
-   Grupo de dimensiones de almacenamiento
-   Grupo de dimensiones de seguimiento

**Nota:** Un objeto de coste representa un elemento de coste solo del tipo **Material directo**. Un objeto de coste y un objeto de inventario difieren de la forma en que un objeto de coste está definido por las dimensiones de inventario seleccionadas para el inventario financiero. Por ejemplo, un artículo tiene la configuración siguiente:

-   **Sitio:** Inventario físico = Sí, Inventario financiero = Sí
-   **Almacén:** Inventario físico = Sí, Inventario financiero = No
-   **N.º de lote:** Inventario físico = Sí, Inventario financiero = No

La tabla siguiente muestra qué es un objeto de coste y qué es un objeto de inventario.

| Tipo de objeto      | Número de artículo | Sitio | Almacén | N.º de lote |
|------------------|-------------|------|-----------|-----------|
| Objeto de coste      | x           | x    |           |           |
| Objeto de inventario | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>Acumulación de costes y cantidades
-   El valor del campo **Valor** es una suma de los valores siguientes:
    -   Importe de coste físico
    -   Importe de coste financiero
    -   Ajustes
-   El valor del campo **Cantidad** es una suma de los valores siguientes:
    -   Recibido
    -   Deducido
    -   Cantidad registrada
-   El campo **Coste unitario promedio** es un campo calculado. El valor se calcula dividiendo el valor **Valor** por el valor **Cantidad**.

**Nota**: El parámetro **Incluir valor físico en coste** no tiene ningún efecto en los cálculos precedentes.

## <a name="additional-resources"></a>Recursos adicionales

[Grupo de dimensiones de producto](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[Grupo de dimensiones de almacenamiento](/dynamicsax-2012//storage-dimension-groups-form)

[Grupo de dimensiones de seguimiento](/dynamicsax-2012//tracking-dimension-groups-form)

[Novedades y cambios](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[Entradas de costes](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]