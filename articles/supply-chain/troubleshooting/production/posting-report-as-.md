---
title: Error cuando se registra el diario Notificar como terminado
description: Cuando registra el diario Notificar como terminado, recibe un mensaje de error que indica que la cantidad solicitada no se puede reducir.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 50a11aba46519a3a81c313aa1f685d45dcf35f64b50bc921d93968efab13b7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750939"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Error cuando se registra el diario Notificar como terminado

Número de KB: 4612891

## <a name="symptoms"></a>Síntomas

Cuando registra el diario **Notificar como terminado**, se produce un error y recibe el siguiente mensaje de error:

> No se puede reducir la cantidad pedida, pues no hay suficientes transacciones de inventario abiertas con el estado Pedido. Los artículos se compran, se reciben o se registran.

Este error ocurre solo cuando el campo **Cantidad con errores** se establece en la primera línea del diario **Notificar como terminado** y el campo **Cantidad sin errores** se establece en la última línea. Si el campo **Cantidad con errores** se establece en la última línea, no se produce ningún error.

## <a name="resolution"></a>Resolución

Para evitar este error, abra la página **Parámetros de control de producción** y luego, en la pestaña **General**, establezca la opción **Aumentar cantidad restante con cantidad con errores** a *Sí*.
