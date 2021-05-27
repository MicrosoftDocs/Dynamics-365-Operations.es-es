---
title: Cálculo de TDS en facturas
description: Este tema proporciona una referencia para las transacciones en las que el impuesto deducido en el origen (TDS) se calcula a nivel de factura.
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
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023572"
---
# <a name="tds-calculation-on-invoices"></a>Cálculo de TDS en facturas

[!include [banner](../includes/banner.md)]

Este tema proporciona una referencia para las transacciones en las que el impuesto deducido en el origen (TDS) se calcula a nivel de factura.

| Número de serie | Tipo de transacción                                 | Importe de la transacción | Nombre de la página y ruta de selección                                 | Tipo de cuenta y tipo de cuenta de contrapartida                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Compra realizada a partir de gastos de registro/proveedores   | Debe o Haber  | Página de diarios generales (Contabilidad general > Entradas de diario > Diarios generales), página de diario de aprobación de facturas (Proveedores > Facturas> Aprobación de facturas), página de diario de facturas (Proveedores > Facturas > Diario de facturas) | Contabilidad (Dr.) Proveedor (Cr.).  La retención de impuestos se calcula para la combinación de contabilidad y proveedor solo cuando la cuenta contable tiene el tipo de registro **Compra** de **efectivo**. |
| 2.            | Compra realizada a partir de gastos de registro/cliente | Debe o Haber  | Página de diarios generales (Contabilidad general > Entradas de diario > Diarios generales), página de diario de facturas (Proveedores > Facturas > Diario de facturas) | Contabilidad (Dr.) Cliente (Cr.).                                 |
| 3.            | Compra de activo fijo al proveedor              | Debe o Haber  | Página de diarios generales (Contabilidad general > Entradas de diario > Diarios generales), página de diario de registro de facturas (Proveedores > Facturas> Registro de facturas), página de diario de facturas (Proveedores > Facturas > Diario de facturas) | Activos fijos (Dr.) Proveedor (Cr.)                             |
| 4.            | Compra de activo fijo al cliente            | Debe o Haber  | Página de diarios generales (Contabilidad general > Entradas de diario > Diarios generales), página de diario de facturas (Proveedores > Facturas > Diario de facturas) | Activos fijos (Dr.) Cliente (Cr.)                           |
| 5.            | Factura de compra (proveedor de TDS)                  |                    | Página de pedido de compra (Proveedores > Pedidos de compra > Todos los pedidos de compra) |                                                              |
| 6.            | Factura de ventas (cliente de TDS)                  |                    | Página de pedidos de ventas (Clientes > Pedidos> Todos los pedidos de venta), página de facturas de servicios (Clientes > Facturas > Todas las facturas de servicios) |                                                              |
