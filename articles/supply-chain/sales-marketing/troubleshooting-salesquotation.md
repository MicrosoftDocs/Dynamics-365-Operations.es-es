---
title: Solución de problemas de presupuestos de ventas
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con presupuestos de ventas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436808"
---
# <a name="troubleshoot-sales-quotations"></a>Solución de problemas de presupuestos de ventas

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con presupuestos de ventas.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>No puedo cambiar la cantidad de ventas de un presupuesto de venta para un artículo de servicio.

### <a name="issue-description"></a>Descripción del problema

Si intenta establecer una cantidad de ventas (campo **SalesQty**) para un elemento de tipo *Servicio* en una línea de presupuesto de ventas, verá el siguiente mensaje: "Actualización no permitida para el campo Cantidad".

### <a name="issue-resolution"></a>Solución de problemas

No puede establecer una cantidad de ventas para productos que son artículos de servicio. Por ejemplo, si ofrece un servicio para instalar un artículo, no tiene sentido registrar una cantidad, porque no hay un artículo físico. Solo hay un servicio.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]