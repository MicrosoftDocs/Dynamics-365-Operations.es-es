---
title: Registrar pagos automáticamente para las facturas de cliente de empresas vinculadas
description: Este tema explica cómo registrar pagos automáticamente para las facturas de cliente de empresas vinculadas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548522"
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
