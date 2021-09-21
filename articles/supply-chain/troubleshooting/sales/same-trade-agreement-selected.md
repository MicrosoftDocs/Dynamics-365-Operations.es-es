---
title: Mismo acuerdo comercial seleccionado al crear líneas de orden de venta
description: Si hay más de un acuerdo comercial definido para una fecha determinada, siempre se selecciona el que tiene el precio más bajo al crear líneas de pedido de venta.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a586a399fb349965b972191bec1271651bec5fcb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477529"
---
# <a name="if-two-trade-agreements-exist-for-overlapping-dates-the-same-one-is-always-selected"></a>Si existen dos acuerdos comerciales para fechas superpuestas, siempre se selecciona el mismo

## <a name="symptoms"></a>Síntomas

Si se definen dos acuerdos comerciales para el mismo período o para períodos superpuestos, parece que se selecciona el mismo acuerdo comercial cuando se crean líneas de pedido de ventas que contengan esos artículos.

## <a name="resolution"></a>Resolución

Si hay más de un acuerdo comercial para una fecha determinada, siempre se selecciona el acuerdo comercial que tiene el precio más bajo. Para obtener más información, descargue las notas del producto siguientes: [Acuerdos comerciales en Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).
