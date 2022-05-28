---
title: Pedidos de empresas vinculadas y pedidos de devolución
description: Este tema explica cómo cambiar la funcionalidad de pedidos de empresas vinculadas y la devolución de pedidos
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 1c22c021adce5f892ccb6c2ff8735f9e647e8b81
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671853"
---
# <a name="intercompany-orders-and-return-orders"></a>Pedidos de empresas vinculadas y pedidos de devolución

[!include [banner](../../includes/banner.md)]

Este tema describe cómo se crean y actualizan pedidos de compra de empresas vinculadas, pedidos de ventas, pedidos de devolución, acuerdos de compra y acuerdos de venta.

## <a name="about-intercompany-orders"></a>Acerca de los pedidos de empresas vinculadas

Cuando se crea un pedido de ventas de empresas vinculadas, Microsoft Dynamics 365 Supply Chain Management crea automáticamente un pedido de compra correspondiente. Del mismo modo, cuando se crea un pedido de compra de empresas vinculadas, se crea un pedido de ventas de empresas vinculadas automáticamente.

Esto se aplica tanto en el caso de pedidos de dos segmentos (transacciones entre dos empresas relacionadas), como de empresas de tres segmentos (cuando una transacción de empresas vinculadas se origina con un pedido de ventas para un cliente externo).

## <a name="intercompany-order-example"></a>Ejemplo de pedido de empresas vinculadas

Se tienen dos empresas relacionadas. La Empresa A es una filial de ventas y la Empresa B es una unidad de distribución. Los pedidos de compra y de ventas de empresas vinculadas se crean automáticamente en los escenarios siguientes:

- Cuando la Empresa A crea un pedido de compra y el proveedor es la Empresa B, se crea automáticamente un pedido de ventas de empresas vinculadas en la Empresa B. La cadena de pedido de dos segmentos está formada por un pedido de compra en la Empresa A y un pedido de ventas de empresas vinculadas en la Empresa B.
- Cuando la Empresa B crea un pedido de ventas y el cliente es la Empresa A, se crea automáticamente un pedido de ventas de empresas vinculadas en la Empresa A. La cadena de pedidos de dos segmentos está formada por un pedido de ventas de la Empresa B y un pedido de compra de empresas vinculadas en la Empresa A.
- Cuando la Empresa A primero crea un pedido de ventas para un cliente externo, se puede crear automáticamente un pedido de compra en la Empresa A. Esto, a su vez, causará la creación automática de un pedido de ventas de empresas vinculadas en la Empresa B. La cadena de pedido de tres segmentos está formada por un pedido de ventas y un pedido de compra en la empresa A, así como de un pedido de ventas de empresas vinculadas en la Empresa B.

## <a name="about-intercompany-return-orders"></a>Acerca de los pedidos de devolución de empresas vinculadas

Se pueden devolver artículos de empresas vinculadas del mismo modo que las devoluciones habituales. Sin embargo, en el caso de los artículos de empresas vinculadas, el pedido de devolución del cliente externo crea un pedido de compra de empresas vinculadas. Esto lleva a la creación automática de un pedido de devolución de ventas de empresas vinculadas. También se puede devolver un artículo de empresas vinculadas sin un pedido de devolución de cliente externo.

Los pedidos de devolución de empresas vinculadas, similares a los pedidos de devolución regulares, se inician en la página **Crear pedido de devolución**.

En Microsoft Dynamics 365 Supply Chain Management, los acuerdos de compra y venta de empresas vinculadas se actualizan automáticamente para reflejar un artículo devuelto. El compromiso del acuerdo de compra o venta de ese artículo se ajusta automáticamente para reflejar el cambio en la cantidad o el importe cuando se devuelve un artículo.

## <a name="intercompany-return-order-example"></a>Ejemplo de pedido de devolución de empresas vinculadas

La Empresa A crea un pedido de compra vinculado a un acuerdo de compra de un artículo de empresas vinculadas. Un pedido de venta de empresas vinculadas se crea automáticamente en la Empresa B y se vincula al acuerdo de venta correspondiente. El acuerdo de compra y el acuerdo de venta se relacionan como acuerdos de empresas vinculadas.

La Empresa A devuelve el artículo de empresas vinculadas a la Empresa B. La Empresa B crea un pedido de devolución para el artículo, y un pedido de devolución de compra se crea automáticamente en la Empresa A. Los compromisos de ambos acuerdos de compra y venta vinculados a los pedidos originales se ajustan automáticamente para reflejar el cambio de cantidad o importe.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
