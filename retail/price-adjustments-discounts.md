---
title: Ajustes de precios y descuentos
description: "Este artículo proporciona información sobre ajustes de precios y descuentos en ventas al por menor y el comercio de Microsoft Dynamics 365 para las operaciones."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Ajustes de precios y descuentos

Este artículo proporciona información sobre ajustes de precios y descuentos en ventas al por menor y el comercio de Microsoft Dynamics 365 para las operaciones.

En Dynamics 365 para las operaciones (al por menor, puede crear ajustes de precios a los productos, y también puede configurar los descuentos que se aplican a un artículo de línea o de una transacción actualmente la venta (POS), en un pedido de ventas de centro de asistencia, telefónica o en un orden en línea. Tanto los ajustes de precios como los descuentos se pueden vincular a grupos de precios. Para los ajustes de precios y descuentos, puede especificar una sola fecha inicial y la fecha final o un período que se repite, un código de descuento y algunos atributos adicionales. Los ajustes de precios y los descuentos se pueden aplicar a productos, variantes o categorías. Si se aplica más de un descuento a un producto, un cliente puede recibir uno de los descuentos o un descuento combinado, en función de la configuración del descuento. La Dynamics 365 para las operaciones se aplican automáticamente el descuento o una combinación de descuentos que dan el mejor precio al cliente. Cuando configure un ajuste de precio o un descuento, asegúrese de confirmar que los grupos de precios se asignan a los canales, catálogos, afiliaciones o programas de fidelidad correctos a los que desea que el descuento se aplique. Además, si desea generar automáticamente el id. de descuento, puede configurar secuencias numéricas en la página **Parámetros de ventas al por menor** antes de definir un nuevo descuento o ajuste de precios. **Nota**: puede eliminar un ajuste de precios o un descuento. Sin embargo, se perderá la información estadística.

### <a name="types-of-discounts"></a>Tipos de descuentos

Hay cuatro tipos de descuentos comerciales:

-   **Descuento simple**: un único porcentaje o importe.
-   **Descuento por cantidades**: un descuento que se aplica cuando se compran dos o más productos.
-   **Descuento combinado**: un descuento que se aplica cuando se compra una combinación concreta de productos.
-   **Descuento por umbral**: un descuento que se aplica cuando el total de la transacción es superior al importe especificado.

Tanto los ajustes de precios como los descuentos se pueden asociar con los grupos de precios. A continuación, los grupos de precios pueden asociarse con canales, catálogos, afiliaciones y programas de fidelidad.


