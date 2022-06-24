---
title: Registrar pagos automáticamente para las facturas de cliente de empresas vinculadas
description: Este artículo explica cómo registrar pagos automáticamente para las facturas de cliente de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4e8f784cd310026f0a647a0f509999e11ab26ce5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878798"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Registrar pagos automáticamente para las facturas de cliente de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management crea una transacción del cliente al registrar una factura de cliente de empresa vinculada. Esta transacción del cliente permanece abierta hasta que se liquida, lo que significa que se ha pagado. Al actualizar mediante factura el pedido de compra de empresas vinculadas correspondiente, se crea una transacción de proveedor coincidente con la transacción del cliente. Esta transacción de proveedor también permanece abierta hasta que se liquida. Para reducir el riesgo de diferencias, se puede crear y registrar automáticamente un diario de pagos de clientes al registrar el diario de pago de los proveedores.

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Para configurar los pagos de clientes de empresas vinculadas en la página **Empresas vinculadas** para pedidos de ventas, seleccione el enlace **Directivas de pedidos de venta**.
1. En el campo de **Diario de pagos**, seleccione el diario de cuentas de clientes en el que desea registrar los pagos de proveedor de empresas vinculadas. Puede configurar esto en la página **Parámetros de clientes**.
1. Si desea registrar en este diario automáticamente, seleccione la casilla de verificación **Registrar diario automáticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
