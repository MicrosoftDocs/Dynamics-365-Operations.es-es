---
title: Ajustes de precios y descuentos
description: Este artículo proporciona información sobre ajustes de precios y descuentos en Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240951"
---
# <a name="price-adjustments-and-discounts"></a>Ajustes de precios y descuentos

[!include [banner](includes/banner.md)]

Este artículo proporciona información sobre ajustes de precios y descuentos en Dynamics 365 Commerce.

En Commerce, puede realizar ajustes de precios en los productos y configurar los descuentos que se aplican a un artículo de línea o a una transacción en el punto de venta (PDV), en un pedido de ventas del centro de llamadas o en un pedido en línea. Tanto los ajustes de precios como los descuentos se pueden vincular a grupos de precios. Para los ajustes de precios y descuentos, puede especificar una sola fecha inicial y la fecha final o un período que se repite, un código de descuento y algunos atributos adicionales. 

Los ajustes de precios y los descuentos se pueden aplicar a productos, variantes o categorías. Si se aplica más de un descuento a un producto, un cliente puede recibir uno de los descuentos o un descuento combinado, en función de la configuración del descuento. Commerce aplica automáticamente el descuento o la combinación de descuentos que proporcionan el mejor precio al cliente. Cuando configure un ajuste de precio o un descuento, asegúrese de confirmar que los grupos de precios se asignan a los canales, catálogos, afiliaciones o programas de fidelidad correctos a los que desea que el descuento se aplique. Además, si desea generar automáticamente el id. de descuento, puede configurar secuencias numéricas en la página **Parámetros de Commerce** antes de definir un nuevo descuento o ajuste de precios.

> [!NOTE]
> Puede eliminar un ajuste de precios o un descuento. Sin embargo, se perderá la información estadística.

## <a name="types-of-discounts"></a>Tipos de descuentos

Hay muchos tipos de descuentos:

- **Descuento simple**: un único porcentaje o importe.
- **Descuento por cantidades**: un descuento que se aplica cuando se compran dos o más productos.
- **Descuento combinado**: un descuento que se aplica cuando se compra una combinación concreta de productos.
- **Descuento por umbral**: un descuento que se aplica cuando el total de la transacción es superior al importe especificado.
- **Descuento basados en la forma de pago**: un descuento que se aplica cuando el total de la transacción es superior a un monto específico y se utiliza un tipo de pago específico (por ejemplo, efectivo, tarjeta de crédito o débito) para el pago.
- **Descuento de envío**: un descuento que se aplica cuando el total de la transacción es superior a una cantidad especificada y se utiliza un modo de entrega específico (por ejemplo, envío en dos días o envío al día siguiente) en el pedido.

Tanto los ajustes de precios como los descuentos se pueden asociar con los grupos de precios. A continuación, los grupos de precios pueden asociarse con canales, catálogos, afiliaciones y programas de fidelidad.

> [!NOTE]
> El descuento de combinación y coincidencia y el descuento de umbral tienen propiedades denominadas "Contar productos no descontables" y "Contar productos no descontables hasta el umbral", respectivamente. Si estas propiedades están habilitadas, un artículo que no es apto para ningún descuento aún puede ser apto para una transacción para el descuento, pero el artículo no apto no obtendrá el descuento. 
> 
> Por ejemplo, si crea un descuento de combinación y coincidencia con dos líneas, A y B, donde un cliente debería obtener un 10 % de descuento en ambos artículos, pero el artículo A tiene marcada la configuración "Evitar todos los descuentos", entonces esto normalmente impediría que el artículo A se incluyera en el descuento. Sin embargo, si la propiedad "Contar productos no descontables" está habilitada, entonces el artículo A se puede usar para recibir el descuento de combinación, pero el descuento del 10 % solo se aplicará al artículo B. Se aplica una lógica similar al descuento de umbral. . 
>
> Sin embargo, la propiedad "Contar productos no descontables hasta el umbral" tiene una capacidad adicional en comparación con la propiedad "Contar productos no descontables" de los descuentos de combinación. Si el descuento de umbral está habilitado, y si hay un artículo que tiene un descuento existente que evitaría que el artículo tenga otros descuentos, entonces el precio pagado por este artículo calificaría para alcanzar el umbral, pero este artículo no obtendrá el descuento adicional.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
