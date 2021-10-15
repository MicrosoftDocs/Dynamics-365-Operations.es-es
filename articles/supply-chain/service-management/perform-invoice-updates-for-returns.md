---
title: Actualizaciones de facturas para devoluciones
description: Esta funcionalidad también admite los procesos empresariales de muchas organizaciones que deciden que la misma persona facture pedidos de devolución y de ventas a la vez.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 736496a0499e70987f80f3d4687414371606cd8c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578761"
---
# <a name="perform-invoice-updates-for-returns"></a>Actualizaciones de facturas para devoluciones 

[!include [banner](../includes/banner.md)]


Un pedido de devolución es un tipo de pedido de ventas marcado como artículo devuelto. Por lo tanto, la página de lista **Todos los pedidos de venta** se usa para generar facturas para los pedidos de devolución en lugar del formulario **Pedidos de devolución**. Esta funcionalidad también admite los procesos empresariales de muchas organizaciones que deciden que la misma persona facture pedidos de devolución y de ventas a la vez.

Dado que la factura para un artículo devuelto es para un importe negativo, se denomina nota de abono.

Al configurar la actualización de factura para el procesamiento por lotes, el pedido de ventas del tipo **Pedido devuelto** debe tener un estado de línea de devolución de **Recibido**, lo que indica que el albarán del pedido se ha actualizado.

## <a name="post-an-invoice-for-a-return-order"></a>Registrar una factura para un pedido de devolución

1.  Haga clic en **Clientes** \> **Común** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.

2.  Seleccione un pedido de ventas para el que se muestra **Pedido devuelto** en el campo **Tipo de pedido**.

3.  En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, haga clic en **Factura**.

4.  En la pestaña **Parámetros**, seleccione la casilla de verificación **Registrar**.

5.  Revise la información del formulario y realice los cambios pertinentes.

6.  Haga clic en **Aceptar**. La nota de abono se ha registrado.

## <a name="see-also"></a>Consulte también

[Actualizaciones de albaranes para devoluciones](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]