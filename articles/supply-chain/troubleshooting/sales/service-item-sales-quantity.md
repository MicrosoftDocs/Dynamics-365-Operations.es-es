---
title: No se puede establecer la cantidad de ventas de un artículo de servicio en una línea de presupuesto de ventas
description: Al trabajar con presupuestos de ventas, no puede establecer una cantidad de ventas para productos que son artículos de servicio, porque no hay artículos físicos para contar.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477565"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>No se puede cambiar la cantidad de ventas de un artículo de servicio en una línea de presupuesto de ventas

## <a name="symptoms"></a>Síntomas

Si intenta establecer una cantidad de ventas (campo **SalesQty**) para un elemento de tipo *Servicio* en una línea de presupuesto de ventas, verá el siguiente mensaje:

> Actualización no permitida para el campo Cantidad.

## <a name="cause"></a>Causa

Esto se debe al diseño. No puede establecer una cantidad de ventas para productos que son artículos de servicio. Por ejemplo, si ofrece un servicio para instalar un artículo, no tiene sentido registrar una cantidad, porque no hay un artículo físico para contar. Solo hay un servicio.
