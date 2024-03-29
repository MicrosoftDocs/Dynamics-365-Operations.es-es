---
title: Configurar gastos en los pedidos de empresas vinculadas
description: En este artículo se explica cómo configurar gastos en pedidos de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7b84c0bac6c31139170a99afc65cd08d70bd018e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885852"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Configurar gastos en los pedidos de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Los gastos se pueden configurar para que se agreguen a los pedidos de empresas vinculadas. Al agregar gastos a un pedido de venta de empresas vinculadas, se sincroniza automáticamente con el pedido de compra de empresas vinculadas. Esto funciona de ambas formas: del pedido de venta de empresas vinculadas al pedido de compra y viceversa.

También puede utilizar los gastos para agregar ganancias a un pedido de ventas de empresas vinculadas definiendo los gastos como un porcentaje de empresas vinculadas.

Al configurar los gastos que se aplicarán a los pedidos de empresas vinculadas, se habilita el cálculo de las ganancias internas para un pedido de venta de empresas vinculadas a partir del importe neto del pedido de venta original. Es posible que desee hacer esto si el proveedor de empresas vinculadas realiza las ventas al usuario a precio de coste. El siguiente procedimiento describe cómo hacer esto para los clientes de empresas vinculadas. Puede usar el mismo procedimiento para los proveedores.

1. Vaya a **Clientes \> Configuración \> Gastos \> Grupos de gastos de cliente**.
1. Cree un grupo de gastos.
1. Vaya a **Clientes \> Clientes \> Todos los clientes**. Seleccionar un vínculo de cliente. En el panel de acciones, seleccione la pestaña **Cliente** y después la ficha desplegable **Pedidos de ventas**.
1. Seleccione **Editar** en el panel de acciones para habilitar las modificaciones en el campo. En el campo **Gastos de grupo**, seleccione el grupo de gastos de empresas vinculadas que configuró en el paso 2.
1. Vaya a **Clientes \> Configuración \> Cobros \> Cobros automáticos**.
1. Configure los gastos rellenando los campos relevantes.
1. En el campo **Relación de cliente**, seleccione el grupo de gastos de empresas vinculadas que configuró en el paso 2.
1. En la ficha desplegable **Líneas**, en el campo **Categoría**, seleccione **Porcentaje de empresas vinculadas**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
