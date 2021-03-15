---
title: Entradas de costes
description: Este artículo proporciona información acerca de las entradas de coste y de cuándo se crean. Una entrada de coste es un registro que registra la cantidad y el coste de un evento dado.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12ff771cf44595420ca721605daabaa6b071a4ff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967834"
---
# <a name="cost-entries"></a>Entradas de costes

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las entradas de coste y de cuándo se crean. Una entrada de coste es un registro que registra la cantidad y el coste de un evento dado.

Las entradas de costes son agregaciones de las transacciones de inventario que se registran en las dimensiones de inventario financieras activas.

## <a name="examples"></a>Ejemplo
### <a name="example-1-no-cost-entries-are-created"></a>Ejemplo 1: No se crean entradas de costes

Se registra un evento de diario de transferencia. El evento transfiere una pieza del artículo A desde la ubicación A a la ubicación B. La dimensiones de inventario de ubicación no se considera parte del objeto de coste. Por lo tanto, el evento crea dos transacciones de inventario y ninguna entrada de coste.

### <a name="example-2-cost-entries-are-created"></a>Ejemplo 2: Se crean entradas de costes

Se registra un evento de diario de transferencia. El evento transfiere una pieza del artículo A desde el sitio 1 al sitio 2. La dimensión de inventario de sitio se considera parte del objeto de coste. Por lo tanto, el evento crea dos transacciones de inventario y dos entradas de coste.

### <a name="example-3-one-cost-entry-is-created"></a>Ejemplo 3: Se crea una entrada de coste

Se registra un evento de recepción de producto para un pedido de compra. El evento registra 100 piezas del artículo A en un coste unitario de 10,00 dólares estadounidenses (USD). Dado que el artículo A usa un número de serie para realizar un seguimiento de la finalidad de la administración de inventario, se crea un número de serie único para cada artículo que se recibe. Por lo tanto, el evento crea 100 transacciones de inventario y una entrada de coste.

## <a name="cost-entries-page"></a>Página Entradas de costes
La nueva página **Entradas de costes** le permite ver y controlar registros de cantidades y costes. Esta página complementa las páginas **Transacción de inventario** y **Liquidación del inventario**. Los registros se registran en orden cronológico para un evento. Por lo tanto, puede encontrar y controlar rápidamente los costes acumulados de un evento específico o todos los eventos relacionados con un documento. Este es un ejemplo:

-   Se registra un evento de recepción de producto para el artículo A. Se reciben cien piezas en un coste unitario de 10,00 USD.
-   Algunos días después del registro del evento de la factura, el coste aumenta a 11,00 USD. Por tanto, el importe total es 1.100 USD. Se crea un segundo asiento para tener en cuenta la diferencia de 100 USD.
-   Unos días más tarde, se registra un cargo vario de 15,00 USD para cubrir el coste de transporte en el pedido de compra.

| Asiento | Fecha       | Referencia      | Número | Id. de lote interno  | Cantidad | Importe  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | Pedido de compra | 100001 | 0000101 | 100,00   | 1000.00 |
| 00002   | 20-01-2015 | Pedido de compra | 100001 | 0000101 |          | 100,00  |
| 00003   | 31-01-2015 | Ajuste     | 100001 | 0000101 |          | 15:00   |

La página **Entradas de costes** permite el filtrado por id. de documento y fecha de documento. 

> [!NOTE]
> Las entradas de costes solo están disponibles para [objetos de costes](cost-object.md) o productos liberados.

<a name="additional-resources"></a>Recursos adicionales
--------

[Objetos de coste](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]