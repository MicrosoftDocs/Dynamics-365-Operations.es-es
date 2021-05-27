---
title: Característica de factura dividida
description: Este tema describe la configuración y la característica para dividir facturas por dirección de entrega y número de cuenta de impuestos (TAN).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023573"
---
# <a name="split-invoice-functionality"></a>Característica de factura dividida

[!include [banner](../includes/banner.md)]

Este tema describe la configuración y la característica para dividir facturas por dirección de entrega y número de cuenta de impuestos (TAN).

En la página **Parámetros de proveedores**, en la pestaña **General**, seleccione las casillas **Recepción de producto** o **Factura** para registrar y dividir una recepción o factura de producto que tiene diferentes direcciones de entrega y TAN en la página **Pedido de compra**. La factura registrada se dividirá por dirección de entrega y TAN.

En la pestaña **Actualización conjunta**, en ficha desplegable **Dividir por**, en la fila **Información de entrega**, establezca las opciones **Confirmación**, **Lista de selección**, **Albarán** o **Factura** a **Sí** para registrar y dividir una confirmación, lista de selección, albarán o factura donde se definen diferentes direcciones de entrega y TAN para diferentes líneas de factura en la página **Pedidos de ventas**. La factura se dividirá primero por dirección de entrega y después por TAN.

> [!IMPORTANT]
> - Si ninguna opción para **Información de entrega** se ha establecido como **Sí**, la factura se registrará como una sola factura. No se producirá ninguna división de facturas.
> - Para dividir y registrar un albarán donde las líneas de la factura tienen diferentes direcciones de entrega y TAN, debe establecer la opción **Albarán** para **Información de entrega** a **Sí**.
> - Para dividir y registrar una factura donde las líneas de la factura tienen diferentes direcciones de entrega y TAN, debe establecer la opción **Factura** para **Información de entrega** a **Sí**.
> - Para dividir y registrar una factura donde las líneas de la factura tienen diferentes direcciones de entrega, pero el mismo TAN, debe establecer la opción **Factura** para **Información de entrega** a **No**. La factura se dividirá por dirección de entrega.

## <a name="example"></a>Ejemplo

En este ejemplo, la opción **Factura** para **Información de entrega** se establece en **Sí** en la pestaña **Actualización conjunta** de la página **Parámetros de proveedores**. Se registra una factura de compra que tiene la siguiente configuración para direcciones de entrega y TAN en las líneas:

- **Línea de artículo 1:** dirección de entrega 1, TAN-ABCD12345A
- **Línea de artículo 2:** dirección de entrega 1, TAN-ABCD12345A
- **Línea de artículo 3:** dirección de entrega 2, TAN-ABCE12345B
- **Línea de artículo 4:** dirección de entrega 3, TAN-ABCD12345A

En este caso, la factura original se divide en dos facturas y se registra de la siguiente manera:

- La factura 1 se registra para la línea de artículo 1 y la línea de artículo 2, ya que ambas líneas tienen la misma dirección de entrega y TAN.
- La factura 2 se registra para la línea de artículo 3.
- La factura 3 se registra para la línea de artículo 4.
