---
title: El grupo de impuestos predeterminado y el descuento por pronto pago predeterminado no se rellenan desde la cuenta de factura
description: Un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenan desde la cuenta de factura
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477517"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>El grupo de impuestos predeterminado y el descuento por pronto pago predeterminado no se rellenan desde la cuenta de factura

## <a name="symptoms"></a>Síntomas

Si utiliza una cuenta de factura que difiere de la cuenta de cliente, un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenarán desde la cuenta de factura cuando se cree un pedido de compra.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. Los valores predeterminados para el grupo de impuestos, descuentos por pronto pago y otra información de precios se basan en la cuenta del cliente, no en la cuenta de la factura.
