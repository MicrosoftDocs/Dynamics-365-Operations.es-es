---
title: Media móvil secuencia de costes de reserva
description: Este tema proporciona información sobre secuencias de costos de reserva para cálculos de promedio móvil en Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: AnnBe
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: b2172dfbec0a7f0fa25a081e4d92635a09f00e46
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261373"
---
# <a name="moving-average-fallback-cost-sequence"></a>Media móvil secuencia de costes de reserva

Una forma de calcular el costo de su inventario es mediante el uso de una _media móvil_. Se pueden asociar hasta tres valores de coste con cada artículo de inventario:

- **Ultima emisión** - El último costo de emisión que se asignó antes de que el inventario fuera negativo
- **Coste activo** - El último coste que se activó en una versión de gestión de costes
- **Precio del articulo** - El coste que se especifica para el producto lanzado

Para determinar cuál de estos valores de coste debe usarse en los cálculos de promedio móvil, el sistema utiliza una _secuencia de costos de reserva_ para establecer el orden de preferencia para los valores. Si el valor de coste preferido no está disponible, el sistema usa el siguiente valor preferido, y así sucesivamente.

En versiones anteriores de Microsoft Dynamics 365 Supply Chain Management, el sistema utilizó una secuencia de costo de recuperación fija (_Última emisión - Coste activo - Precio del artículo_). En la versión 10.0.11, esta secuencia sigue siendo la secuencia predeterminada. Sin embargo, también puede activar una función que le permite seleccionar entre tres secuencias de costes de reserva disponibles. Esta característica puede ser especialmente útil para organizaciones que usan regularmente valores de inventario negativos.

Para que el selector de la secuencia de costes de reserva esté disponible, usted (o un administrador) debe usar [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la función que se llama _Secuencia de coste de recuperación promedio móvil_.

Para seleccionar la secuencia de costes de respaldo para los cálculos de promedio móvil, siga estos pasos.

1. Abra la página **Parámetros**.
2. En la pestaña **Contabilidad de inventario**, en la sección **Media móvil**, establezca el campo **Secuencia de costes de reserva** a uno de los siguientes valores:

    - **Última emisión - Coste activo - Precio del artículo** - Esta secuencia es la secuencia predeterminada. Es la misma secuencia que se usa si la función _Secuencia de costo de recuperación promedio móvil_ no está activada.
    - **Coste activo - Última emisión**
    - **Coste activo - Precio del artículo** - Las organizaciones pueden experimentar problemas de rendimiento si utilizan procesos comerciales en los que el inventario se vuelve negativo regularmente y, al mismo tiempo, el volumen de transacciones es alto. Esta configuración puede ayudar a mitigar esos problemas de rendimiento.

![Parámetros de contabilidad de inventario](media/inventory-accounting-parameters.png "Parámetros de contabilidad de inventario")
