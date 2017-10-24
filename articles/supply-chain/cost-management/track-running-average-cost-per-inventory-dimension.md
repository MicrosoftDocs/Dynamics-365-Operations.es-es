---
title: "Seguimiento del coste promedio móvil por dimensión de inventario"
description: "Un grupo de dimensiones de inventario está vinculado a cada artículo de inventario. Por lo tanto, el precio de coste promedio móvil de un artículo se calcula basándose en las dimensiones de inventario seleccionadas para las que se realiza un seguimiento financiero."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a88ec380810a9a2d7048d5a8773ebb5960e4cf86
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Seguimiento del coste promedio móvil por dimensión de inventario

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


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




