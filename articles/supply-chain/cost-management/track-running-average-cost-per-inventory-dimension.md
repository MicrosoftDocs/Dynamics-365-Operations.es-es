---
title: Seguimiento del coste promedio móvil por dimensión de inventario
description: Un grupo de dimensiones de inventario está vinculado a cada artículo de inventario. Por lo tanto, el precio de coste promedio móvil de un artículo se calcula basándose en las dimensiones de inventario seleccionadas para las que se realiza un seguimiento financiero.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8da13a01b28ca09ce9c29ecd3a9342dfb9eaa4bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834322"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>Seguimiento del coste promedio móvil por dimensión de inventario

[!include [banner](../includes/banner.md)]

Un grupo de dimensiones de inventario está vinculado a cada artículo de inventario. Por lo tanto, el precio de coste promedio móvil de un artículo se calcula basándose en las dimensiones de inventario seleccionadas para las que se realiza un seguimiento financiero.

Hay tres tipos distintos de dimensiones de inventario: producto, almacenamiento y seguimiento. Las dimensiones de producto incluyen configuración, tamaño y color. Siempre se hace un seguimiento financiero de las dimensiones de producto. Las dimensiones de almacenamiento y seguimiento incluyen el sitio, el almacén, la ubicación, el estado de inventario, la matrícula de entidad de almacén, el número de lote y el número de serie. Puede elegir las dimensiones de almacenamiento y seguimiento para las que se realizará un seguimiento financiero. 

**Ejemplo 1** 

Si se realiza un seguimiento financiero del grupo de dimensiones de almacenamiento vinculado al artículo por almacén, se calculará el precio de coste promedio móvil para cada almacén. Se han facturado los siguientes pedidos de compra:

-   Para el almacén GW, se ha facturado un pedido de compra que incluye una cantidad de 2 a un precio de coste de 10,00 dólares.
-   Para el almacén GW, se ha facturado un pedido de compra que incluye una cantidad de 3 a un precio de coste de 12,00 dólares.
-   Para el almacén MW, se ha facturado un pedido de compra que incluye una cantidad de 5 a un precio de coste de 15,00 dólares.

El precio de coste promedio móvil para el almacén GW es de 11,20 dólares y el precio de coste promedio móvil del almacén MW es de 15,00 dólares. Se ha registrado una factura de pedido de ventas para el almacén GW. El valor del inventario y el coste de los bienes vendidos (antes de que se ejecute el cierre de inventario y sin marcar) será de 11,20 dólares. Se ha registrado otra factura de pedido de ventas para el almacén MW. El valor del inventario y el coste de los bienes vendidos (antes de que se ejecute el cierre de inventario y sin marcar) será de 15,00 dólares. 

**Ejemplo 2** Si se realiza un seguimiento financiero del grupo de dimensiones de almacenamiento vinculado al artículo por almacén y se realiza un seguimiento financiero del grupo de dimensiones de seguimiento por número de lote, se calcula el precio de coste promedio móvil para cada lote. 

**Nota:** es recomendable que siempre vea el precio de coste para todas las dimensiones financieras para las que se realiza el seguimiento. Se han facturado los siguientes pedidos de compra:

-   Se ha facturado para el almacén GW y el lote AAA un pedido de compra que incluye una cantidad de 2 a un precio de coste de 10,00 dólares.
-   Se ha facturado para el almacén GW y el lote AAA un pedido de compra que incluye una cantidad de 3 a un precio de coste de 12,00 dólares.
-   Se ha facturado para el almacén GW y el lote BBB un pedido de compra que incluye una cantidad de 2 a un precio de coste de 15,00 dólares.

El precio de coste promedio móvil para el almacén GW y el lote AAA es de 11,20 dólares y el precio de coste promedio móvil del almacén GW y el lote BBB es de 15,00 dólares.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]