---
title: Objetos de coste
description: "Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 823d3edd106925339607d01fbf5f1921b85ff244
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Objetos de coste
<a id="cost-objects" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.  

Objetos de coste
<a id="cost-objects" class="xliff"></a>
------------

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

## Acumulación de costes y cantidades
<a id="accumulation-of-costs-and-quantities" class="xliff"></a>
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

Consulte también
<a id="see-also" class="xliff"></a>
--------

[Grupo de dimensiones de producto](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Grupo de dimensiones de almacenamiento](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Grupo de dimensiones de seguimiento](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Novedades y cambios](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)

[Entradas de costes](cost-entries.md)




