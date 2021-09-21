---
title: Se consume un número de asiento de recibo de producto incluso cuando no se genera un asiento
description: Se consume un número de asiento de recepción de producto incluso si no se genera ningún comprobante financiero durante la recepción del producto
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
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477518"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Se consume un número de asiento de recibo de producto incluso cuando no se genera un asiento

## <a name="symptoms"></a>Síntomas

Se consume un número de asiento de recepción de producto incluso si no se genera ningún comprobante financiero durante la recepción del producto.

## <a name="resolution"></a>Resolución

Si la opción **Acumular pasivo en la recepción del producto** está establecida en *No* para el grupo de modelos de artículo, no se producirán contabilizaciones en el libro mayor. Sin embargo, se registrará un evento físico con el propósito de contabilizarlo en un libro mayor auxiliar y ese evento requiere un número de asiento. Este número de asiento es el número al que se hace referencia en las transacciones de inventario.

Le recomendamos que establezca la opción **Acumular pasivo en la recepción del producto** en *Sí*, como se describe en la siguiente publicación del blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
