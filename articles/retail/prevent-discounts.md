---
title: Opciones para evitar descuentos de productos comerciales
description: Existen varios motivos por los que los minoristas pueden querer evitar que algunos de sus productos tengan descuentos, tanto por una promoción o durante la venta PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 64f54c1a63706ccd9225d47df96ffc3f88cf3332
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606927"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Opciones para evitar descuentos de productos comerciales

[!include [banner](includes/banner.md)]

Existen varios motivos por los que los minoristas pueden querer evitar que algunos de sus productos tengan descuentos, tanto por una promoción o durante la venta PDV.

Las opciones siguientes, que se pueden encontrar en la pestaña **Ventas al por menor** de productos emitidos, permitirán que el producto se configure para evitar todos o descuentos manuales. Los valores también se pueden especificar al nivel de categoría de la jerarquía de categoría minorista.

- **Evite todos los descuentos**: Seleccione esta opción para impedir que se apliquen todos los tipos de descuentos a este producto. Esto incluye promociones como Descuentos combinados, los descuentos de cantidad y de umbral, así como los descuentos manuales de línea y transacción que se aplican durante una venta por un PDV.
- **Evitar los descuentos manuales**: Seleccione esta opción para evitar sólo los descuentos manuales de la línea o transacción que se aplican durante una venta por un usuario PDV. Los productos con esta opción seleccionada todavía están aptos para promociones, como descuentos de combinados y de cantidad y de umbral.

> [!NOTE]
> Estos ajustes no limitan la operación de la anulación de precio, ya que esto establece el precio base y no se trata como un descuento.

[![Evite el campo de descuentos](./media/prevent-discounts.png)](./media/prevent-discounts.png)
