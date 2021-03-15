---
title: Retención de impuestos en transacciones de compra
description: Para los proveedores sujetos a retención de impuestos, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Todos los proveedores**.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06997e2d6b47d867e014a7d493d91015c78a5e04
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060789"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Retención de impuestos en transacciones de compra

Para los proveedores sujetos a retención de impuestos, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Todos los proveedores**.

1. Vaya a **Panel de exploración > Módulos > Proveedores > Proveedores > Todos los proveedores**.

2. Haga clic en la cuenta de proveedor correspondiente y, a continuación, haga clic en **Editar**.

3. En la pestaña **Factura y entrega**, establezca el campo **Calcular retención de impuestos** en **Sí**.

   > [!NOTE] 
   > La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está activada para este proveedor en los datos maestros.

4. Seleccione un grupo de retención de impuestos en **Grupo de retención de impuestos**.

5. Haga clic en **Guardar**.

Para artículos o servicios, que están sujetos a retención de impuestos, puede asignar el valor predeterminado **Grupo de retención de impuestos de artículos** en **Productos emitidos**.

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.

2. Haga clic en el número de artículo correspondiente y, a continuación, haga clic en **Editar**.

3. En la pestaña **Comprar**, haga clic en **Calcular retención de impuestos**.

   > [!NOTE] 
   > La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está establecida en **Sí** para este artículo en la pestaña **Comprar** de la página **Producto emitido**.

4. Seleccione un grupo de retención de impuestos de artículos en la lista **Grupo de retención de impuestos de artículos**.

5. Haga clic en **Guardar**.

Los grupos de retención de impuestos y los grupos de retención de impuestos de artículos se pueden asignar en las páginas: 

- **Pedido de compra**
- **Factura del proveedor**
- **Diario de facturas**

El grupo de retención de impuestos predeterminado y el grupo de retención de impuestos de artículo se llevarán a las líneas al crear **Pedidos de compra** o **Facturas de proveedores pendientes**. Para **Diario de facturas de proveedor**, puede activar **Calcular retención de impuestos** y seleccionar **Grupo de retención de impuestos de artículo** en la pestaña **General** del diario.

El importe temporal de retención de impuestos está disponible en el campo **Retención de impuestos ajustada** de la pestaña **Totales** de la página **Pedido de compra**.

![La retención de impuestos se incluye en el pedido de compra.](media/withholding-tax-adjusted.png)

La retención de impuestos se calcula en el **Diario de pagos a proveedores**. Puede ajustar manualmente los códigos de retención de impuestos aplicables, así como los importes de retención de impuestos en la pestaña **Retención de impuestos** de la página **Liquidar transacciones**.

![La retención se puede ajustar manualmente en la página Liquidar transacciones](media/withholding-tax-vendor-payment-tab.png)

El importe de retención de impuestos derivado se deducirá del pago del proveedor y se publicará en la **Cuenta de retención de impuestos** en un asiento relacionado.

![Cuenta de retención de impuestos que muestra un asiento relacionado](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]