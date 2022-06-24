---
title: El subtotal del resumen del pedido no incluye los impuestos sobre los gastos cuando se utilizan módulos personalizados de resumen del pedido.
description: Este artículo proporciona una guía para la solución de problemas que puede ayudar cuando usa módulos de resumen de pedidos personalizados y el subtotal del resumen de pedidos no incluye impuestos sobre los cargos en el escenario "el precio incluye impuestos sobre las ventas".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 260dcb6bc1585615195e32adfcd1da6bfbca294e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848846"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>El subtotal del resumen del pedido no incluye los impuestos sobre los gastos cuando se utilizan módulos personalizados de resumen del pedido.

Este artículo proporciona una guía para la solución de problemas que puede ayudar cuando usa módulos de resumen de pedidos personalizados y el subtotal del resumen de pedidos no incluye impuestos sobre los cargos en el escenario "el precio incluye impuestos sobre las ventas".

## <a name="description"></a>Description

A partir de la versión 10.0.27 de Microsoft Dynamics 365 Commerce, se han realizado los siguientes cambios en el escenario "el precio incluye el impuesto sobre las ventas" para proporcionar una experiencia coherente en los módulos de resumen de pedidos en las páginas del sitio de comercio electrónico.

- Se han añadido dos nuevos campos: **TaxOnShippingCharge** y **TaxOnNonShippingCharges**.
- Las interfaces de programación de aplicaciones **GetSalesOrderBySalesId** y **GetSalesOrderByTransactionId** (API) tienen valores precisos para los siguientes campos en el escenario "el precio incluye el impuesto sobre las ventas":

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Sin embargo, si utiliza módulos de resumen de pedidos personalizados, estos cambios pueden afectar los valores del subtotal del resumen de pedidos al no incluir los impuestos sobre los cargos.

## <a name="resolution"></a>Resolución

Si usa módulos de resumen de pedidos personalizados y no desea heredar los cambios realizados en el escenario "el precio incluye el impuesto sobre las ventas" en la versión 10.0.27 y posteriores de Commerce, siga las instrucciones de esta sección.

Al volver al comportamiento de resumen de orden anterior (antes de la versión 10.0.27) de los campos **salesTransaction.SubtotalAmount** y **salesTransaction.SubtotalAmountWithoutTax**, restablece la inclusión del monto total del impuesto de cargo (**TaxOnShippingCharge** y **TaxOnNonShippingCharges**) en los importes subtotales (**SubtotalAmount** y **SubtotalAmountWithoutTax**).

Para volver al comportamiento anterior del resumen del pedido, siga estos pasos.

1. En Commerce headquarters, abra la página de parámetros de Commerce (**Retail y Commerce \> Configuración de la sede \> Parámetros \> Parámetros de Commerce**).
1. En el panel de navegación izquierdo, seleccione **Parámetros de configuración**.
1. Agregue los siguientes parámetros de configuración y establezca el valor de cada uno en **verdadero**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Si ha utilizado anteriormente el parámetro de configuración **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** y desea conservar el mismo comportamiento para la propiedad **order.NetAmountWithoutTax**, también debe agregar el parámetro de configuración **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** y establezca su valor en **verdadero**.

## <a name="additional-resources"></a>Recursos adicionales

[Ocultar información de desglose de impuestos en resúmenes de pedidos](../hide-taxes-breakup.md)
