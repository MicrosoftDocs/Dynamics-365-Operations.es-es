---
title: Retención de impuestos en transacciones de ventas
description: Este tema enumera los pasos para evitar el cálculo de la retención de impuestos para clientes seleccionados. Para los clientes que especifican la retención de impuestos en sus pagos, puede asignar el grupo de retención de impuestos predeterminado.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d659004a1f61b63d6a782ba6b45bb99030bae9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727437"
---
# <a name="withholding-tax-in-sales-transactions"></a>Retención de impuestos en transacciones de ventas

Este tema enumera los pasos para evitar el cálculo de la retención de impuestos para clientes seleccionados. Para los clientes que especifican la retención de impuestos en los pagos que le hacen, puede asignar el **Grupo de retención de impuestos** predeterminado en la página **Clientes**. 

1. Vaya a **Panel de exploración > Módulos > Clientes > Clientes > Todos los clientes**.

2. Haga clic en la cuenta de cliente correspondiente y haga clic en **Editar**.

3. En la pestaña **Factura y entrega**, configure el campo **Calcular retención de impuestos** en **Sí**.

   > [!NOTE] 
   > La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está activada para este cliente en los datos maestros.

4. Seleccione un grupo de retención de impuestos en **Grupo de retención de impuestos**.

5. Haga clic en **Guardar**.

Para artículos o servicios, que están sujetos a retención de impuestos, puede asignar el valor predeterminado **Grupo de retención de impuestos de artículos** en **Productos emitidos**.

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.

2. Haga clic en el número de artículo correspondiente y, a continuación, haga clic en **Editar**.

3. En la pestaña **Vender**, haga clic en **Calcular retención de impuestos**.

   > [!NOTE] 
   > La retención de impuestos no se calculará si la opción **Calcular retención de impuestos** no está establecida en **Sí** para este artículo en la pestaña **Vender** de la página **Producto emitido**.

4. Seleccione un grupo de retención de impuestos de artículos en la lista **Grupo de retención de impuestos de artículos**.

5. Haga clic en **Guardar**.

Los grupos de retención de impuestos y los grupos de retención de impuestos de artículos se pueden asignar en la página **Pedido de ventas**. 

El grupo de retención de impuestos y el grupo de retención de impuestos de artículos predeterminados se utilizarán como entradas predeterminadas en las líneas de pedido de ventas cuando se cree un nuevo pedido de ventas.

La retención de impuestos se calcula y registra con el **Diario de pagos de clientes**. Puede ajustar manualmente el código de retención de impuestos aplicable, así como el importe real de retención de impuestos en la pestaña **Liquidar transacciones** de la página **Liquidar transacciones**.

El importe de la retención de impuestos calculada se deducirá del pago del cliente y se publicará en la cuenta de **Compensación de retención de impuestos** en un asiento relacionado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
